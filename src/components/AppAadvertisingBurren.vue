<script>
export default {
    props: { imgSrc: String }
}
</script>

<template>
    <div class="bunner">
        <div class="row">
            <div class="col" :class="`col-${index}`" v-for="(col, index) in 9"><img :src="imgSrc" alt=""></div>
        </div>
        <div>
            <h2>GO AHEAD AND BUID TOUR OWN PIZZA WE WON'T JUDGE!</h2>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as*;
@use "../style/partials/variables" as*;


.bunner {
    position: relative;
    .row {
        @include flex;
        flex-wrap: wrap;

        .col-0,
        .col-2,
        .col-3,
        .col-5,
        .col-6,
        .col-8 {
            width: 100px;
            height: 100px;

            img {
                object-fit: none;
                height: 100px;
            }
        }

        .col-3,
        .col-5 {
            height: 200px;
            img {
                object-fit: none;
                height: 200px;
            }
        }

        .col-1,
        .col-4,
        .col-7 {
            width: calc(100% - 200px);
            height: 100px;

            img {
                object-fit: none;
                height: 100px;
                width:100% ;
            }
        }

        .col-4 {
            height: 200px;
            img {
                height: 200px;
                object-position: 10%;
            }
        }

    }

h2 {
    color: white;
    width: 10%;
    position: absolute;
    top: 26%;
    right: 82%;
}

}
</style>