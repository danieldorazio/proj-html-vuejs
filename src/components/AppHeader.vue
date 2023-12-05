<script>
import AppNavBar from "./AppNavBar.vue";
import AppJumbotron from "./AppJumbotron.vue";

export default {
    components: { AppNavBar, AppJumbotron, },

    data() {
        return {
            imgBackGroundNum: 1,
            imgUpperNum: 2,
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/h3-rev-img-${img}.png`, import.meta.url).href;
        },

        incrementImgNum: function () {
            if (this.imgUpperNum != 6 && this.imgBackGroundNum != 5) {
                this.imgUpperNum = this.imgUpperNum + 2;
                this.imgBackGroundNum = this.imgBackGroundNum +2;

            } else {
                this.imgUpperNum = 2
                this.imgBackGroundNum = 1

            }
        },

        decreaseImgNum: function () {
            if (this.imgUpperNum != 2 && this.imgBackGroundNum != 1) {
                this.imgUpperNum = this.imgUpperNum - 2;
                this.imgBackGroundNum = this.imgBackGroundNum -2;

            } else {
                this.imgUpperNum = 6
                this.imgBackGroundNum = 5

            }
        },        
    },
}
</script>

<template>
    <section class="header">
        <AppNavBar></AppNavBar>
        <AppJumbotron 
        :imgUpperSrc="getImagePath(imgUpperNum)" 
        :imgBackGroundSrc="getImagePath(imgBackGroundNum)"  
        @prevButtonClicked="decreaseImgNum()" 
        @nextButtonClicked="incrementImgNum()" ></AppJumbotron>
    </section>
</template>

<style scoped lang="scss"></style>