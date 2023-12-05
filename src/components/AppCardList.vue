<script>
export default {
    props: { imgFirstSrc: String, imgSecondSrc: String, specialList: Object, }
}

</script>

<template>
    <div class="row">
        <!-- IMG -->
        <div class="col">
            <img class="img" :src="imgFirstSrc" alt="">
            <img class="img-logo" :src="imgSecondSrc" alt="">
        </div>

        <!-- SPECIALS -->
        <div class="col">
            <ul>
                <li>
                    <div class="title">{{ specialList.title }}</div>
                    <p> {{ specialList.titleParagraph }}</p>
                </li>

                <li class="combo" v-for="(combo, index) in specialList.combo">
                    <div class="price">{{ combo.price }}</div>
                    <div>
                        <div class="name">{{ combo.name }}</div>
                        <p class="description">{{ combo.description }}</p>
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

        .img-logo {
            position: absolute;
            width: 50%;
            z-index: 2;
            top: 15%;
            left: 25%;
            // transform: translate(-50% -50%);
        }

        ul {
            margin: 0 auto;

            .title {
                font-weight: bold;
                font-size: 2rem;
                margin-bottom: .8rem;
            }

            .combo {
                margin: 2rem 0;
                @include flex (row, start, start);
                gap: 20px;

                .price {
                    color :$color-text-combo-price;
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
    }
}
</style>