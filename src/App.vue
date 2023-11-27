<script>
    import axios from "axios";
    import { store } from "./store.js";
    import AppHeader from './components/AppHeader.vue';

    export default {
        components: { AppHeader },
        data() {
            return {
                store,
            }
        },
        created() {
            axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
            .then((resp) => {
                this.store.cards = resp.data;
            })
        }
    }
</script>

<template>

    <AppHeader/>

</template>

<style lang="scss">
@use "./style/general.scss";

</style>
