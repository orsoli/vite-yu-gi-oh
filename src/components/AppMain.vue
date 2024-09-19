<script>
//Import Components
import MainCardsList from './MainCardsList.vue';
import AppLoader from './AppLoader.vue';

//Import Store
import { store } from "../store"
import axios from 'axios';


export default {
    data() {
        return {
            store,
            // Variables
            archetypesUrl: "https://db.ygoprodeck.com/api/v7/archetypes.php",
            archetypesList: [], // Save archetypes get from api
            selectedArchetype: "" // Save selcted value
        };
    },

    components: {
        MainCardsList,
        AppLoader
    },

    methods: {
        getArchetypes() {
            axios.get(this.archetypesUrl, {
                params: {
                }
            }).then(response => {
                this.archetypesList = response.data // Save the archetype ocjects in this archetypesList
                console.dir(this.archetypesList) // Test log print
            })
        }
    },
};
</script>

<template>
    <AppLoader v-if="store.cardsList.length === 0" />
    <main class="p-5">
        <div class="container">
            <header>
                <h5>Found {{ store.cardsList.length }} cards</h5>
                <select class="form-select w-25 my-2" v-model="selectedArchetype">
                    <option disabled value="" selected>Archetype</option>
                    <option v-for="(archetype, i) in this.archetypesList" :key="i"
                        :archetupeName="archetype.archetype_name" :value="archetype.archetype_name">{{
                            archetype.archetype_name }}
                    </option>
                </select>
            </header>
            <MainCardsList @get-archetypes="getArchetypes" :selectedValue="selectedArchetype" />
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