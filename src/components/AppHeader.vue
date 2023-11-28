<script>
export default {
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="navbar">
        <div class="container">
            <span class="logo">
                <img src="../assets/img/logo.jpg" alt="logo">
            </span>
            <div class="navbar-text">
                <h2>
                    Yu-Gi-Oh Api!
                </h2>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixins" as *;
@use "../style/partials/variables" as *;

.navbar {
    background-color: white;
    height: 80px;
    .container {
        @include flex(row, start, center);
        gap: 20px;
    
        .logo {
            img {
                height: 50px;
                width: 50px;
            } 
        }
    
        .navbar-text {
            color: black;
        }
    }

}

</style>