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
            axios.get(this.store.apiUrl).then((response) => {
                // console.log(response.data.data) // Test printing in console
                this.store.cardsList = response.data.data
                console.dir(this.store.cardsList) // Test print in console
            })
        }
    },
    created() {
        // Call function after 2 seconds
        setTimeout(() => {
            this.getCardsList()
        }, 2000)
    }
};
</script>

<template>
    <div class="row row-cols-3 row-cols-md-5 g-2">
        <MainCard v-for="card in store.cardsList" :key="card.id" :cardName="card.name"
            :cardImage="card.card_images[0].image_url" :cardArchetype="card.archetype" />
    </div>
</template>

<style lang="scss" scoped>
@use "/node_modules/bootstrap/scss/bootstrap.scss";
@use "/styles/generics.scss" as *;
</style>