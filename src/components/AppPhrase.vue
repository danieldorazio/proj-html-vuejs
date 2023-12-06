<script>
export default {
    props: { phrase: Array, },

    methods: {
        dynamicStyleSelector: function (array) {
            if (array.includes("CHOOSE YOUR FLAVOR")) {
                return 'choose'

            }
        }
    }
}
</script>

<template>
    <div class="phrase" :class="dynamicStyleSelector(phrase)">
        <div v-for="(element, index) in phrase" :class="`phrase-${index}`"> {{ element }} </div>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as*;
@use "../style/partials/variables" as*;
.choose {
    text-align: center;
    margin-top: 30px;

    .phrase-0 {
        font-size: .8rem;
        font-weight: 600;
        color: $color-text-phrase-0-choose;
    }

    .phrase-1 {
        font-size: 1.5rem;
        font-weight: bold;
        margin: 10px 0;
    }

    .phrase-2 {
       color: $color-text-phrase-2-choose; 
    }
    
}
</style>