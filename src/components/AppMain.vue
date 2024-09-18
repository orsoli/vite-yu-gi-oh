<script>
//Import Components
import MainCardsList from './MainCardsList.vue';

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
    },

    methods: {

    }
};
</script>

<template>
    <main class="p-5">
        <div class="container">
            <header>
                <h5>Found {{ store.cardsList.length }} cards</h5>
            </header>
            <MainCardsList />
        </div>
    </main>
</template>

<style lang="scss" scoped>
@use "/node_modules/bootstrap/scss/bootstrap.scss";

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