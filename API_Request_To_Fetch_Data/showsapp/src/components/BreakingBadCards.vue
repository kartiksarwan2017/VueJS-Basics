<!-- <script setup>
import axios from "axios";
// import { ref, onMounted  } from "vue";

// export default {

//     setup(){
//         const movies = ref([]);

//     const fetchMovies = async () => {

//         const options = {
//                 method: 'GET',
//                 headers: {
//                     accept: 'application/json',
//                     Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiI4ZjcwOGZkMDlhNGFkZGM3MTczZDA3YzQ2ZGYyMDVlNCIsInN1YiI6IjY0NTkwMDI1NmFhOGUwMDExY2ExNDAzNiIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.UXbpoC0_kBOKR8Npku7XpKdWH-ELp4k4qTWQUoyRVbk'
//                 }
//             };

//         try {
//             const { data: { results } } = await axios.get(`https://api.themoviedb.org/3/movie/popular`, options);
//             movies.value = results;
//             console.log(await axios.get(`https://api.themoviedb.org/3/movie/popular`, options));
//         }catch(error) {
//             console.log(error);
//         }
//     }

//     onMounted(() => {
//         fetchMovies();
//     })

//     return {
//         movies,
//     };
// }}

</script>

<template>
    <div>
        <h1>Breaking Bad Cards</h1>
        <div v-for="movie in movies" :key="movie.id">
            <img :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`" />
        </div>
    </div>
</template> -->

<script>
import axios from "axios";
import { ref, watch, onMounted } from "vue";
import Card from "./Card.vue";
import md5 from 'md5';

export default {
    setup() {
    const characters = ref(null);
    const page = ref(0);
    const publicKey= ref("079e684d61a8f93d1cf7dcce70d45ef5");
    const  privateKey= ref("3290aa55419da747278751418487809eb0124144");
    const  timestamp= Math.floor(Date.now() / 1000).toString();
    const hash= ref("");
    const apiUrl = ref("https://gateway.marvel.com/v1/public/characters");

    const generateHash = () => {
        const hashInput = timestamp + privateKey.value + publicKey.value;
        hash.value = md5(hashInput);
    }

    const makeApiRequest = async () => {
        const fullApiUrl = `${apiUrl.value}?limit=8&apikey=${publicKey.value}&ts=${timestamp}&hash=${hash.value}`;

        const response  = await axios.get(`${fullApiUrl}`);
        characters.value = response.data.data.results;
    }

    onMounted(() => {
        generateHash();
        makeApiRequest();
    });

    watch(page, async () => {
    const res = await axios.get(`${apiUrl.value}?limit=8&offset=${page.value*8}&apikey=${publicKey.value}&ts=${timestamp}&hash=${hash.value}`);
    characters.value = res.data.data.results;
});

return {
    characters,
    page
}
}
}

</script>

<template>
    <!-- <div class="container">
        <div class="cards">
            <Card />
        </div>
    </div> -->
    <div>
        {{ characters }}

        <button @click="page = page + 1">next</button>
        <button @click="page = page - 1">prev</button>
    </div>
</template>

<style scoped>
.container {
    background-color: rgb(27, 26, 26);
    padding: 30px
}
.cards {
    max-width: 1000px;
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    height: 700px
}
.cards h3 {
    font-weight: bold;
}
.cards p {
    font-size: 10px;
}
.jobs {
    display: flex;
    flex-wrap: wrap;
}
.button-container {
    display: flex;
    justify-content: center;
    padding-top: 30px
}
.button-container button {
    border: none;
    width: 50px;
    height: 50px;
    border-radius: 100%;
    margin: 0 5px;
    cursor: pointer;
}
.spinner {
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>