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
            axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
            .then((resp) => {
                this.store.cards = resp.data.data;
            })
        }
    }
</script>

<template>
    <div class="background">
        <div class="container">
            <AppHeader/>
            <AppMain/>
        </div>
    </div>

</template>

<style lang="scss">
@use "./style/general.scss";

.background {
    background-color: #e5bc55;
    height: 100vh;
}

</style>
