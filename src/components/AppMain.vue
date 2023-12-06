<script>
import AppListOfImages from './AppListOfImages.vue';
import AppJumbotron from './AppJumbotron.vue';
import AppCardList from './AppCardList.vue';
import AppAdvertisingBurren from './AppAdvertisingBurren.vue';
import AppPhrase from './AppPhrase.vue';
import AppCarosel from './AppCarosel.vue';
import AppForm from './AppForm.vue';

export default {
    components: { AppListOfImages, AppJumbotron, AppCardList, AppAdvertisingBurren, AppPhrase, AppCarosel, AppForm },

    data() {
        return {
            imgNewPlace: ['h3-img-1.jpg', 'h3-img-2.jpg', 'h3-img-3.jpg', 'h3-img-4.jpg'],
            phraseTestimonials: ["“", "FORGHET THE TRANDY PIZZA SHOPS, THIS HIDDEN SPOT MAKES THE BEST NEW YORK-STYLE PIZZA SLICE IN NAPLES", "WASHINGTON POST 2018"],
            specials: {
                id: "specials",
                title: "SPECIALS*",
                titleParagraph: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                elem: [
                    {
                        number: "$10",
                        name: "COMBO PICCOLO",
                        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    },

                    {
                        number: "$20",
                        name: "COMBO MEZZO",
                        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    },

                    {
                        number: "$30",
                        name: "COMBO GRANDE",
                        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    },
                ]
            },
            imgTeam: ['h1-team-1a-700x700.jpg', 'h1-team-2a.jpg', 'h1-team-4a.jpg', 'h1-team-3a.jpg'],
            imgClients: ['h1-clients-img-4.png', 'h1-clients-img-3.png', 'h1-clients-img-1.png', 'h1-clients-img-2.png', 'h1-clients-img-5.png'],
            phrasePizzaMenu: ['CHOOSE YOUR FLAVOR', 'THE BEST PIZZA MENU IN TOWN', 'lorem ipsum dolor si amet'],
            imgChoosePizza: [
                {
                    pizzaSrc: 'h3-product-img-1a-100x100.png',
                    pizzaName: 'BISMARCK',
                    pizzaPrice: '$5.00 - $30.00',
                },
                {
                    pizzaSrc: 'h3-product-img-2a-150x150.png',
                    pizzaName: 'FIORI DI ZUCCA',
                    pizzaPrice: '$7.00 - $50.00',
                },
                {
                    pizzaSrc: 'h3-product-img-3a-150x150.png',
                    pizzaName: 'CAMPAGNOLA',
                    pizzaPrice: '$50.00 - $95.00',
                },
                {
                    pizzaSrc: 'h3-product-img-4a-150x150.png',
                    pizzaName: 'PIZZA TARTUFATA',
                    pizzaPrice: '$45.00',
                },
                {
                    pizzaSrc: 'h3-product-img-5a-150x150.png',
                    pizzaName: 'FRANCESCANA',
                    pizzaPrice: '$25.00',
                },
                {
                    pizzaSrc: 'h3-product-img-6a-100x100.png',
                    pizzaName: 'VALDOSTANA',
                    pizzaPrice: '$55.00',
                },
            ],
            eventList: {
                id: "eventList",
                title: "MADE WITH LOVE ",
                titleParagraph: "DELISH PIZZA DEALS",
                elem: [
                    {
                        number: "02 NOV",
                        name: "TRADITIONAL NEAPOLITAN PIES IN KYOTO PIZZA MERCATO",
                        description: "204 E. Pizzetta Tommaso"
                    },
                    {
                        number: "03 NOV",
                        name: "TERAZZA PATIO DINING SPACE OPENING THIS WEEKEND",
                        description: "204 E. Pizzetta Tommaso"
                    },
                    {
                        number: "05 NOV",
                        name: "SIENNA PRIVATE DINING ROOM WITH STE'PHANE BRUNN",
                        description: "204 E. Pizzetta Tommaso"
                    },
                ]


            }
        }
    },

    methods: {
        getImagePath: function (img) {
            return new URL(`../assets/img/${img}`, import.meta.url).href;
        },
    }
}
</script>

<template>
    <AppListOfImages :imgSrc="imgNewPlace"></AppListOfImages>
    <AppJumbotron :imgUpperSrc="getImagePath('h3-testimonials-bckgrnd.jpg')" :phraseTestimonials="phraseTestimonials">
    </AppJumbotron>
    <AppCardList :imgFirstSrc="getImagePath('h1-img-4.jpg')" :imgSecondSrc="getImagePath('h1-img-7n.png')"
        :specialList="specials"></AppCardList>
    <AppAdvertisingBurren :imgSrc="getImagePath('h3-background-img.jpg')"></AppAdvertisingBurren>
    <AppListOfImages :imgSrc="imgTeam"></AppListOfImages>
    <AppListOfImages :imgSrc="imgClients"></AppListOfImages>
    <AppPhrase :phrase="phrasePizzaMenu"></AppPhrase>
    <AppCarosel :arrayImg="imgChoosePizza"></AppCarosel>
    <AppCardList :imgFirstSrc="getImagePath('h3-img-5a.jpg')" :imgSecondSrc="getImagePath('h1-img-7n.png')"
        :specialList="eventList"></AppCardList>
    <AppForm></AppForm>
</template>

<style  scoped lang="scss"></style>