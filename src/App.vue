<script>
import axios from "axios";
import { store } from "./store.js";
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppSelector from "./components/AppSelector.vue";

export default {
    components: { AppHeader, AppMain, AppSelector },
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
    },
    methods: {
        handleChangeSelect() {
            // console.log("cambia-opzione");
            axios
                .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&", {
                    params: {
                        archetype: this.store.selectedOption,
                    },
                })
                .then((resp) => {
                    this.store.cards = resp.data.data;
                });
        }

    }
}
</script>

<template>
    <div class="background">

        <AppHeader />

        <AppSelector @changeSelect="handleChangeSelect" />

        <div class="container main-c">
            <AppMain />
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
