<script>
export default {

    data() {
        return {
            imgNum: 2,
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/h3-rev-img-${img}.png`, import.meta.url).href;
        },

        incrementImgNum: function () {
            if (this.imgNum != 6) {
                this.imgNum = this.imgNum + 2;

            } else {
                this.imgNum = 2

            }
        },

        decreaseImgNum: function () {
            if (this.imgNum != 2) {
                this.imgNum = this.imgNum - 2;

            } else {
                this.imgNum = 6

            }
        },

        controlImgNum: function () {
            if (this.imgNum === 2) {
                return `crust`
            } else if (this.imgNum === 4) {
                return `taste`
            } else if (this.imgNum === 6) {
                return `urban`
            }
        },
    },

}

</script>

<template>
    <div class="jumbotron jumbotron-fluid ">
        <button @click="decreaseImgNum">prev</button>

        <div class="container" :class="controlImgNum()">
            <img :src="getImagePath(imgNum)" alt="">
        </div>

        <button @click="incrementImgNum">next</button>
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

            img {
                width: 20%;
                margin: 50px auto;
            }
     
    }
}




.crust {
    background-image: url(../assets/img/h3-rev-img-1.png);
}

.taste {
    background-image: url(../assets/img/h3-rev-img-3.png);
}

.urban {
    background-image: url(../assets/img/h3-rev-img-5.png);
}
</style>