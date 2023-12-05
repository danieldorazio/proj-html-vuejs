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
    margin: 10px 0;
    .row {
        @include flex;
        flex-wrap: wrap;

        .col-0,
        .col-2,
        .col-3,
        .col-5,
        .col-6,
        .col-8 {
            width: 50px;
            height: 50px;

            img {
                object-fit: none;
                height: 50px;
            }
        }

        .col-3,
        .col-5 {
            height: 100px;
            img {
                object-fit: none;
                height: 100px;
            }
        }

        .col-1,
        .col-4,
        .col-7 {
            width: calc(100% - 100px);
            height: 50px;

            img {
                object-fit: none;
                height: 50px;
                width:100% ;
            }
        }

        .col-4 {
            height: 100px;
            img {
                height: 100px;
                object-position: 10%;
            }
        }

    }

h2 {
    color: white;
    font-size: 1rem;
    width: 20%;
    position: absolute;
    top: 30%;
    right: 68%;
}

}
</style>