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
            // type: String,
            required: true,
        },
    },

    methods: {

    }
};
</script>

<template>
    <div class="col">
        <div class="card text-center" id="card">
            <img :src="cardImage" class="card-img-top" :alt="cardName">
            <div class="card-body">
                <h5 class="card-title fs-6 mt-0">{{ cardName }}</h5>
                <p class="card-text mb-1">{{ cardArchetype }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
#card {
    background-color: #D48F3C;
    height: 400px;

    h5 {
        color: white;
    }
}
</style>