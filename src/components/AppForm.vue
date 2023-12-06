<script>
export default {
    data() {
        return {
            formElem: [
                {
                    id: "person",
                    placeholder: '1 person',
                    img: 'person-244.svg',
                    space: "FOR",
                },
                {
                    id: "data",
                    placeholder: '11/29/2020',
                    img: 'Calendar_icon_2.svg',
                    space: "AT",

                },
                {
                    id: "hours",
                    placeholder: '7:30 pm',
                    img: 'clock.svg'
                },
            ]
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/svg/${img}`, import.meta.url).href;
        },
    }
}
</script>

<template>
    <div class="form-section">
        <div class="form container">
            <div class="element" v-for="(element, index) in formElem">
                <div class="input">
                    <label for="person d-none"></label>
                    <input type="text" :name="element.id" :placeholder="element.placeholder">
                    <img :src="getImagePath(element.img)" alt="">
                </div>
                <div class="space">{{ element.space }}</div>
            </div>
            <button>BOOK A TABLE</button>
        </div>
        <p class="container">*Powered by OpenTable</p>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/mixin' as*;
@use '../style/partials/variables' as*;


.form-section {
    background-image: url(../assets/img/h3-background-img-3.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    padding: 100px 0;

}

.form {
    @include flex;
    flex-wrap: wrap;


    .element {
        @include flex;
        width: calc(100% / 4);

        .input {
            background-color: white;
            border: 1px solid black;
            padding: 10px;
            @include flex;

            input {
                width: 80%;
                border: none;

            }

            img {
                width: 15px;
            }
        }

        .space {
            color: white;
            margin: 0 5px;
        }
    }

    button {
        font-size: .8rem;
        background-color: $bg-button-form;
        color: white;
        border: none;
        padding: 10px 20px;
    }
}

p {
    font-size: .8rem;
    color: white;
}</style>
