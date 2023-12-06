<script>
export default {
    props: {
        arrayImg: Array,
    },

    data() {
        return {
            imgIndex: 0,
            timer: "",
        }
    },

    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        },

        dynamicStyleSelector: function (array) {
            if (array[0].pizzaSrc === "h3-product-img-1a-100x100.png") {
                return 'choose'
            }
        },

        showNext: function () {
            if (this.imgIndex === this.arrayImg.length - 1) {
                this.imgIndex = 0;
            } else {
                this.imgIndex++;
            }
        },

        startAutoPlay: function () {
            this.timer = setInterval(this.showNext, 1000)
        },

        stopAutoPlay: function () {
            clearInterval(this.timer);
            this.timer = null;
        },
    },

    created() {
        this.startAutoPlay();
    },


}

</script>

<template>
    <div class="carosel" :class="dynamicStyleSelector(arrayImg)" @mouseover="stopAutoPlay" @mouseleave="startAutoPlay">
        <div :class="[`img-${index}`, `img-${index}` === `img-${imgIndex}` ? 'd-none' : '']"
            v-for="(img, index) in arrayImg">
            <img class="img" :src="getImagePath(img.pizzaSrc)" alt="">
            <div class="name">{{ img.pizzaName }}</div>
            <div class="price"> {{ img.pizzaPrice }}</div>

        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/mixin' as*;
@use '../style/partials/variables' as*;

.carosel {
    @include flex;
    gap: 20px;
    margin: 50px 0;

    img {
        width: 200px;
    }
}

.choose {
    .name, .price {
        font-size: .8rem;
        font-weight: 600;
        text-align: center;
        margin: 10px 0;
    }

    .name {
        color: $color-text-name-choose;
    }

    .price {
        color: $color-text-price-choose;
    }
}
</style>