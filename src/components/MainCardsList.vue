<script>
// Import components
import MainCard from './MainCard.vue';

//Import axios
import axios from 'axios';

// Import store
import { store } from "../store";

export default {
    data() {
        return {
            store
        };
    },

    components: {
        MainCard
    },
    methods: {
        getCardsList() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=39&offset=0').then((response) => {
                // console.log(response.data.data) // Test printing in console
                this.store.cardsList = response.data.data
                console.log(this.store.cardsList[0].card_images[0].image_url) // Test print in console
            })
        }
    },
    mounted() {
        this.getCardsList()
    }
};
</script>

<template>
    <MainCard v-for="card in store.cardsList" :key="card.id" :cardName="card.name"
        :cardImage="card.card_images[0].image_url" :cardArchetype="card.archetype" />
</template>

<style scoped></style>