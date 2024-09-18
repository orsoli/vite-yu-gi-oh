<script>
//Import Components
import MainCardsList from './MainCardsList.vue';


export default {
    data() {
        return {

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
                Founded 39 cards
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