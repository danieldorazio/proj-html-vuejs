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
    <div class="hero ">
        <div class="my_nav-bar container">

            <button type="button" class="my_button">ORDER ONLINE</button>

            <div class="my_list">
                <div class="my_home">
                    <img class="my_icon_svg" src="../assets/svg/svg-0.svg" alt="">
                    <AppList :navList="navListHome"></AppList>
                </div>
                <img class="my_logo" src="../assets/img/h5-logo-divided-header.png" alt="Logo Don Peppe">
                <AppList :navList="navListEvent"></AppList>
            </div>

            <div class="my_search">
                <div>
                    <img class="my_icon_svg" src="../assets/svg/svg-1.svg" alt="">
                    <span>CART</span>
                </div>
                <div>
                    <img class="my_icon_svg" src="../assets/svg/loupe-svgrepo-com.svg" alt="">
                    <span>SEARCH</span>
                </div>
            </div>

        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as*;
@use "../style/partials/mixin" as*;

.hero {
    background-color: $bg-Nav-Bar;
    color: $color-text-white;

    .container {
        @include flex;

        .my_button {
            height: fit-content;
            padding: 5px 20px;
            border-radius: 0px;
            color: inherit;
            border: none;
            background-color: $bg-button;
            font-size: .6rem;
        }

        .my_list {
            @include flex;

            .my_home {
                @include flex;
            }


            .my_logo {
                width: 25%;
            }
        }

        .my_search {
            @include flex;
            gap: 10px;

            div {
                @include flex;
                gap: 5px
            }
        }
    }



    ;

    .my_icon_svg {
        max-width: 1rem;
        filter: invert(100%);
    }
}
</style>