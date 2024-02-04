<script>
import axios from "axios";
import { ref, watch, onMounted, computed } from "vue";
import md5 from 'md5';
import Card from "./Card.vue";

export default {  
    components: {
        Card
    },
    setup() {
    const characters = ref(null);
    const page = ref(0);
    const publicKey= ref("079e684d61a8f93d1cf7dcce70d45ef5");
    const  privateKey= ref("3290aa55419da747278751418487809eb0124144");
    const  timestamp = computed(() => {Math.floor(Date.now() / 1000).toString()});
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

        console.log(characters.value);

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
}}}

</script>

<template>
    <div class="container">
        <div class="cards">
            <Card 
              v-for="character in characters"
              :key="character.id"
              :name="character.name"
              :image="`${character.thumbnail.path}.jpg`"
              :seriesItems="character.series.items"
            />
        </div>
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