<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
import AppLoader from "./AppLoader.vue";

export default {
    data() {
        return {
            store,
        }
    },
    components: { AppCard, AppLoader },
}
</script>

<template>
    <div class="container-fluid">
        <div class="number-of-cards">
            <h3>
                Found {{ store.cards.length }} Cards
            </h3>
        </div>
        <AppLoader v-if="store.loading"/>
        <div class="cards" v-else>
            <div class="card" v-for="card in store.cards" :key="card.id">
                <AppCard :card="card"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.container-fluid {
    padding: 30px;

    .number-of-cards {
        height: 60px;
        background-color: #477c7f;
        @include flex(row, start, center);
        padding: 0 1rem;
        h3 {
            color: white;
        }
    }

    .cards {
        width: 100%;
        @include flex(row, space-between, start);
        align-items: normal;
        flex-wrap: wrap;
        gap: 12px;
        .card {
            width: calc((100% / 5) - 12px);
            background-color: #e5bc55;
        }
    }
}
</style>