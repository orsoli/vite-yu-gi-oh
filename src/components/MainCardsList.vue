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
    props: {
        selectedValue: {
            type: String,
            required: false
        }
    },
    components: {
        MainCard
    },
    methods: {
    },

    created() {
        this.$emit('getArchetypes') // In created moment emit getArchetypes customized event on AppMain in MainCardsList component
    }
};
</script>

<template>
    <div class="row row-cols-3 row-cols-md-5 g-2">
        <MainCard v-for="card in store.cardsList" :key="card.id" :cardName="card.name"
            :cardImage="card.card_images[0].image_url" :cardArchetype="card.archetype" />
    </div>
</template>

<style lang="scss" scoped></style>