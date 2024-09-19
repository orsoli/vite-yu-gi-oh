<script>
//Import Components
import MainCardsList from './MainCardsList.vue';
import AppLoader from './AppLoader.vue';

//Import Store
import { store } from "../store"


export default {
    data() {
        return {
            store
        };
    },

    components: {
        MainCardsList,
        AppLoader
    },

    methods: {

    }
};
</script>

<template>
    <AppLoader v-if="store.cardsList.length === 0" />
    <main class="p-5">
        <div class="container">
            <header>
                <h5>Found {{ store.cardsList.length }} cards</h5>
                <select class="form-select w-25 my-2">
                    <option value="1">One</option>
                    <option value="2">Two</option>
                    <option value="3">Three</option>
                </select>
            </header>
            <MainCardsList />
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: #D48F3C;

    header {
        color: white;
        background-color: #222429;
        padding: 15px 10px;
    }

    .container {
        background-color: white;
        padding: 20px;
    }
}
</style>