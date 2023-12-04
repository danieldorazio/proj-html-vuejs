<script>
export default {
    props: {
        navList: Array,
    },
    data() {
        return {

        }
    },
}

</script>

<template>
        <ul class="d-flex m-0 p-0 gap-3">
            <li v-for="elemet in navList"><a href="">{{ elemet }}</a></li>
        </ul>
</template>

<style scoped lang="scss"></style>