<script>
export default {
    props: {
        imgUpperSrc: String,
        imgBackGroundSrc: String,
    },

    data() {
        return {

        }
    },

    methods: {
    },

}

</script>

<template>
    <div class="jumbotron jumbotron-fluid ">
        <button @click="$emit('prevButtonClicked')">prev</button>

        <div class="container"> 
            <img class="back-ground" :src="imgBackGroundSrc" alt="">
            <img class="img-upper" :src="imgUpperSrc" alt="">
        </div>

        <button @click="$emit('nextButtonClicked')">next</button>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as*;
@use "../style/partials/mixin" as*;

.jumbotron {
    background-color: $bg-Nav-Bar;
    @include flex;

    .container {
        background-repeat: no-repeat;
        background-position: center;
        background-size: 60%;
        @include flex;
        position: relative;

        .back-ground {
            width: 50%;
            position: absolute;
            left: 25%;
            bottom: 25%;
            // transform: translate(50% 50%);
        }

        .img-upper {
            position: relative;
            z-index: 2;
            width: 20%;
            margin: 50px auto;
        }

    }
}
</style>