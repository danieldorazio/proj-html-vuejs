<script>
export default {
    props: { imgSrc: Array },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        },

        dynamicStyleSelector: function (array) {
            if (array.includes("h3-img-1.jpg")) {
                return 'img-new-place'
            } if(array.includes("h1-team-1a-700x700.jpg")) {
                return 'img-team'
            } if(array.includes("h1-clients-img-1.png")) {
                return 'img-clients'
            }
        }
    }
}
</script>

<template>
    <section class="list-of-images">
        <div class="row" :class="dynamicStyleSelector(imgSrc)" >
            <div class="col" v-for="img in imgSrc">
                <img class="img-primary" :src="getImagePath(img)" alt="">
                <img class="img-see" src="../assets/svg/view-svgrepo-com.svg" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;


.row {
    @include flex (row, space-between, stretch);
    .img-see {
        display: none;
    }
}


//style h3-img-1.jpg
.img-new-place {
    gap: 8px;
    margin-top: 10px;
    .col {
        @include flex;

        .img-see {
            display: none;
        }

        &:hover {
            .img-primary {
                display: none;
            }
            .img-see {
                display: block;
                width: 15%;
                margin: 0 auto;
            }
        }
    }
}

//style "h1-team-1a-700x700.jpg"
.img-team {
   img {
    width: 100%;
    max-width: 700px;
    aspect-ratio: 1;
   }
}

//style "h1-clients-img-1.png"
.img-clients {
    padding: 20px 0;
    background-color: $bg-clients;
    @include flex (row, center, center);
    .col {
        width: calc(100% / 6);
    }
}
</style>