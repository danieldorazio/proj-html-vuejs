<script>
import AppListOfImages from './AppListOfImages.vue';
import AppJumbotron from './AppJumbotron.vue';
import AppCardList from './AppCardList.vue';
import AppAadvertisingBurren from './AppAadvertisingBurren.vue';

export default {
    components: { AppListOfImages, AppJumbotron, AppCardList, AppAadvertisingBurren },

    data() {
        return {
            imgNewPlace: ['h3-img-1.jpg', 'h3-img-2.jpg', 'h3-img-3.jpg', 'h3-img-4.jpg'],
            phraseTestimonials: ["“", "FORGHET THE TRANDY PIZZA SHOPS, THIS HIDDEN SPOT MAKES THE BEST NEW YORK-STYLE PIZZA SLICE IN NAPLES", "WASHINGTON POST 2018"],
            specials: {
                title: "SPECIALS*",
                titleParagraph: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                combo: [
                    {
                        price: "$10",
                        name: "COMBO PICCOLO",
                        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    },

                    {
                        price: "$20",
                        name: "COMBO MEZZO",
                        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    },

                    {
                        price: "$30",
                        name: "COMBO GRANDE",
                        description: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
                    },
                ]
            },
            imgTeam: ['h1-team-1a-700x700.jpg', 'h1-team-2a.jpg', 'h1-team-4a.jpg', 'h1-team-3a.jpg'],
            imgClients: ['h1-clients-img-4.png', 'h1-clients-img-3.png', 'h1-clients-img-1.png', 'h1-clients-img-2.png', 'h1-clients-img-5.png']
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
    <AppCardList :imgFirstSrc="getImagePath('h1-img-4.jpg')" :imgSecondSrc="getImagePath('h1-img-7n.png')" :specialList="specials"></AppCardList>
    <AppAadvertisingBurren :imgSrc="getImagePath('h3-background-img.jpg')"></AppAadvertisingBurren>
    <AppListOfImages :imgSrc="imgTeam"></AppListOfImages>
    <AppListOfImages :imgSrc="imgClients"></AppListOfImages>
</template>

<style  scoped lang="scss"></style>