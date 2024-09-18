<script>
// Import components
import MainCard from './MainCard.vue';

//Import axios
import axios from 'axios';

// Import store
import { store } from "../store.js";

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
                console.log(response.data.data) // Test printing in console
                this.store.cardsList = response.data.data
            })
        }
    },
    mounted() {
        this.getCardsList()
        console.log(store.cardsList) // Test print in console
    }
};
</script>

<template>
    <div class="">

    </div>
</template>

<style scoped></style>