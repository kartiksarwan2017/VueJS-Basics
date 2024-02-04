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

<script setup>
import axios from "axios";
import { ref, watch } from "vue";

    const characters = ref(null);
    const page = ref(0);

    const response  = await axios.get(`https://pokeapi.co/api/v2/ability/?limit=8`);
    characters.value = response.data.results;

    watch(page, async () => {
        const res = await axios.get(`https://pokeapi.co/api/v2/ability/?limit=8&offset=${page.value*8}`);
        characters.value = res.data.results;
        console.log(res);
    });

</script>

<template>
    <div>
        <h1>Breaking Bad Cards</h1>
        <h1>{{ characters }}</h1>
        <div>
            <button @click="page = page + 1">Next</button>
            <button @click="page = page - 1">Back</button>
        </div>
    </div>
</template>