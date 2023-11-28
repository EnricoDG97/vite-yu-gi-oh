<script>
    import axios from "axios";
    import { store } from "./store.js";
    import AppHeader from './components/AppHeader.vue';
    import AppMain from './components/AppMain.vue';

    export default {
        components: { AppHeader, AppMain },
        data() {
            return {
                store,
            }
        },
        created() {
            // set loading to true
            this.store.loading = true;
            axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
            .then((resp) => {
                this.store.cards = resp.data.data;
                // set to false so it disappear
                this.store.loading = false;
            })
        }
    }
</script>

<template>
    <div class="background">

        <AppHeader/>
        
        <select class="form-select container" aria-label="Default select example">
            <option selected>Open this select menu</option>
            <option value="1">One</option>
            <option value="2">Two</option>
        </select>

        <div class="container main-c">
            <AppMain/>
        </div>
    </div>

</template>

<style lang="scss">
@use "./style/general.scss";
@use "../src/style/partials/mixins" as *;

.background {
    background-color: #e5bc55;
    height: 100%;
    .form-select {
        width: fit-content;
        margin-top: 40px;
    }
    .container.main-c {
        background-color: white;
        min-height: 60vh;
        margin-top: 40px;
        padding: 0;
    }
}

</style>
