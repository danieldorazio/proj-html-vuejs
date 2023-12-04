<script>
export default {
    props: {
        navList: Array,
    },
}
</script>

<template>
    <ul>
        <li v-for="elemet in navList"><a href="">{{ elemet }}</a></li>
    </ul>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as*;

ul {
    @include flex;
    padding: 0px;

    li {
        @include flex;
        margin: 0 10px;

        font-size: .8rem;
    }
}
</style>