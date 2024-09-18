<script>

export default {
    data() {
        return {
        };
    },
    props: {
        cardName: {
            type: String,
            required: true,
        },
        cardImage: {
            type: String,
            required: true,
        },
        cardArchetype: {
            type: String,
            required: true,
        },
    },

    methods: {

    }
};
</script>

<template>
    <main>
        <div class="card" style="width: 18rem;">
            <img :src="cardImage" class="card-img-top" :alt="cardName">
            <div class="card-body">
                <h5 class="card-title">{{ cardName }}</h5>
                <p class="card-text">{{ cardArchetype }}</p>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    h5 {
        color: white;
    }
}
</style>