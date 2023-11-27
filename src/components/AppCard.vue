<script>
    export default {
        props: {
            card: Object,
        },
        data() {
            return {

            }
        }
    }
</script>

<template>
<div class="text-center">
    <img :src="card.card_images[0].image_url" class="card-img-top" alt="">
    <div class="card-body">
        <p class="card-title">
            {{ card.name }}
        </p>
        <p class="archetype">
            {{ card.archetype }}
        </p>
    </div>
</div>

</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.card-title {
    color: white;
    text-transform: uppercase;
}

.archetype {
    color: black;
    text-transform: capitalize;
}
</style>