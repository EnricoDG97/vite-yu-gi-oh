<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="container-fluid">
        <div class="number-of-cards">
            <h3>
                Found ... Cards
            </h3>
        </div>
        <div class="cards">
            <div class="card col">
                <img src="..." class="card-img-top" alt="...">
                <div class="card-body">
                    <p class="card-text">
                        titolo
                    </p>
                </div>
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
        gap: 12px;
        .card.col {
            max-width: calc(100% / 5);
            img {
                width: 100%;
            }
        }
    }
}
</style>