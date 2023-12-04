<script>
import AppNavBar from "./AppNavBar.vue";
import AppJumbotron from "./AppJumbotron.vue";

export default {
    data() {
        return {

        }
    },
    components: {AppNavBar,AppJumbotron}
}
</script>

<template>
    <section class="header">

        <AppNavBar></AppNavBar>
        <AppJumbotron></AppJumbotron>
       
        
    </section>
</template>

<style scoped lang="scss">

</style>