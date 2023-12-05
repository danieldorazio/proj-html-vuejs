<script>
import AppListOfImages from './AppListOfImages.vue';

export default {
    components: { AppListOfImages },

    data() {
        return {
            imgNewPlace: ['h3-img-1.jpg', 'h3-img-2.jpg', 'h3-img-3.jpg', 'h3-img-4.jpg']
        }
    },

    methods: {
    }

}
</script>

<template>
    <AppListOfImages :imgSrc="imgNewPlace"></AppListOfImages>
</template>

<style  scoped lang="scss"></style>