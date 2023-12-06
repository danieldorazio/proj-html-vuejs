<script>
export default {
    props: { imgFirstSrc: String, imgSecondSrc: String, specialList: Object, },

    methods: {
        dynamicStyleSelector: function (Object) {
            if (Object.id === "specials") {
                return 'specials'
            } if (Object.id === "eventList") {
                return 'event-list'
            }
        },
    }
}

</script>  

<template>
    <div class="row card-list" :class="dynamicStyleSelector(specialList)">
        <!-- IMG -->
        <div class="col">
            <img class="img" :src="imgFirstSrc" alt="">
            <img class="img-logo d-none" :src="imgSecondSrc" alt="">
        </div>

        <!-- SPECIALS -->
        <div class="col">
            <ul>
                <li>
                    <div class="title">{{ specialList.title }}</div>
                    <p class="title-paragraph"> {{ specialList.titleParagraph }}</p>
                </li>

                <li class="combo" :class="`combo-${index}`" v-for="(element, index) in specialList.elem">
                    <div class="number"  :class="`number-${index}`">{{ element.number }}</div>
                    <div>
                        <div class="name"  :class="`name-${index}`">{{ element.name }}</div>
                        <p class="description" :class="`description-${index}`"><span></span>{{ element.description }}</p>
                    </div>
                </li>
            </ul>

        </div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/mixin' as*;
@use '../style/partials/variables' as*;

.row {
    @include flex;

    .col {
        position: relative;
        @include flex;
        width: 50%;

        ul {
            margin: 0 auto;
            width: 80%;

        }
    }
}


//sezione specials
.specials {

    .img-logo {
        display: block;
        position: absolute;
        width: 50%;
        z-index: 2;
        top: 15%;
        left: 25%;
        // transform: translate(-50% -50%);
    }

    .title {
        font-weight: bold;
        font-size: 2rem;
        margin-bottom: .8rem;
    }

    .combo {
        margin: 2rem 0;
        @include flex (row, start, start);
        gap: 20px;

        .number {
            color: $color-text-combo-price;
            font-weight: 600;
        }

        div {
            .name {
                margin-bottom: .5rem;
                font-weight: 600;
            }
        }

    }
}

//sezione eventlist

.event-list {
    flex-direction: row-reverse;
    background-color: $bg-event-list;

    .title, .description {
        font-size: .5rem;
        color: $color-text-eventlist;
    }

    .number {
        color: $color-text-eventlist;
        font-size: 1.3rem;
        text-align: center;
    }

    .title-paragraph, .name {
        color: $bg-img-testimonials;
    }

    .title {
        margin-bottom: 8px;
    }
    .title-paragraph {
        margin-bottom: 20px;
    }

    .combo {
        @include flex (row, start, start);
        gap: 20px;
        padding: 10px 0;
    }
    .combo-1 {
        border-top: 1px dotted $color-border-eventlist;
        border-bottom: 1px dotted $color-border-eventlist;
    }
}
</style>