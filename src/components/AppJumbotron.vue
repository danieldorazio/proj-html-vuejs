<script>
export default {
    props: {
        imgUpperSrc: String,
        imgBackGroundSrc: String,
        phraseTestimonials: Array,
    },

    data() {
        return {

        }
    },

    methods: {
        dynamicStyleSelector: function (String) {
            if (String.includes("h3-rev-img-2.png")) {
                return 'img-pizza'
            } if (String.includes("h3-rev-img-4.png")) {
                return 'img-pizza'
            } if (String.includes("h3-rev-img-6.png")) {
                return 'img-pizza'
            } if (String.includes("h3-testimonials-bckgrnd.jpg"))
                return 'img-testimonials'
        }

    },

}

</script>

<template>
    <div class="jumbotron" :class="dynamicStyleSelector(imgUpperSrc)">
        <!--:class="[dynamicStyleSelector(imgUpperSrc), dynamicStyleSelector(imgBackGroundSrc)]" -->
        <button @click="$emit('prevButtonClicked')">prev</button>

        <div class="container">
            <img class="back-ground" :src="imgBackGroundSrc" alt="">
            <img class="img-upper" :src="imgUpperSrc" alt="">

            <div class="phrase-testimonials">
                <div v-for="(element, index) in phraseTestimonials" :class="`phrase-${index}`"> {{ element }} </div>
            </div>
        </div>


        <button @click="$emit('nextButtonClicked')">next</button>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/variables" as*;
@use "../style/partials/mixin" as*;

.jumbotron {
    @include flex;

    .back-ground {
        display: none;
    }

    .phrase-testimonials {
        display: none;
    }
}

.img-pizza {
    background-color: $bg-Nav-Bar;

    .container {
        background-repeat: no-repeat;
        background-position: center;
        background-size: 60%;
        @include flex;
        position: relative;

        .back-ground {
            display: block;
            width: 50%;
            position: absolute;
            left: 25%;
            bottom: 25%;
            // transform: translate(50% 50%);
        }

        .img-upper {
            position: relative;
            z-index: 2;
            width: 20%;
            margin: 50px auto;
        }
    }
}

.img-testimonials {
    .container {
        position: relative;


        
        .phrase-testimonials {
            display: block;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 2;
            text-align: center;

            .phrase-0 {
                display: inline-block;
                font-size: 5rem;
                font-weight: bold;
                color: $color-text-phrase-0;
            }

            .phrase-1 {
                font-weight: bold;
                margin-bottom: 20px;
            }

            .phrase-2 {
                color: $color-text-phrase-2;
                font-size: .8rem;
                font-weight: 600;
            }


        }
    }


}</style>