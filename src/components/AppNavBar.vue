<script>
import AppList from "./AppList.vue"

export default {
    data() {
        return {
            navListHome: ["HOME", "PAGES", "MENU"],
            navListEvent: ["EVENT", "BLOG", "LANDING"]
        }
    },
    components: { AppList, }
}
</script>

<template>
    <div class="hero d-flex justify-content-center">
        <div class="my_nav-bar container d-flex justify-content-between align-items-center">
            <button type="button" class="my_button btn btn-warning d-inline-block">ORDER ONLINE</button>
            <div class="my_list d-flex justify-content-center align-items-center ">
                <img class="my_icon_svg" src="../assets/svg/svg-0.svg" alt="">
                <AppList :navList="navListHome"></AppList>
                <img class="my_logo w-25 m-4" src="../assets/img/h5-logo-divided-header.png" alt="Logo Don Peppe">
                <AppList :navList="navListEvent"></AppList>
            </div>
            <div class="d-flex flex-nowrap gap-2">
                <div class="d-flex align-items-center">
                    <img class="my_icon_svg"  src="../assets/svg/svg-1.svg" alt="">
                    <span>CART</span>   
                </div>
                <div class="d-flex align-items-center">
                    <img class="my_icon_svg"  src="../assets/svg/loupe-svgrepo-com.svg" alt="">
                    <span>SEARCH</span>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as*;

.hero {
    background-color: $bg-Nav-Bar;
    color: $color-text-white;

    .my_button {
        height: fit-content;
        padding: 5px 20px;
        border-radius: 0px;
        color: inherit;
        border: none;
        background-color: $bg-button;
        font-size: .6rem;
    };

    .my_icon_svg {
        max-width: 1rem;
        filter: invert(100%);
    }
}
</style>