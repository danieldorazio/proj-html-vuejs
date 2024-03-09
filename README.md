# Don Peppe Layout - WEBSITE a componenti 

Questa è una soluzione per eseguire questo esercizio puramente dal lato visivo con il solo uso di HTML, SCSS e Vite.JS.

## Sommario

- [Panoramica](#Panoramica)
  - [La sfida](#La-sfida)
  - [Screenshot](#screenshot)
- [Il mio processo](#il-mio-processo)
  - [Osservazioni](#osservazioni)
  - [Costruito con](#costruito-con)
  

## Panoramica

### La sfida

Ricostruire un layout di una WebSite cercando di utilizzare piu componenti riutilizzabili possibili

### Screenshot

**Layout Desktop**
![screencapture-localhost-5173-2024-03-09-00_43_13](https://github.com/danieldorazio/proj-html-vuejs/assets/133901578/312623d9-f366-49e3-8add-c0fda3b6b5cd)


## Il mio processo
Per prima cosa ho esaminato bene il lalayout fornito cercando di individuare piu componenti simili tra loro 
Effettuato un scaffolding della pagina senza dettagli 
Reso il componente con stile dinamico a seconda della props in ingresso cosi da poterlo riutilizzare in piu sezioni differenti 

## Osservazioni
Molto interessante il comportamento dei componenti a seconda del props in ingresso, il codice è un pochino vincolante a determinate regole commentate all'interno del codice, però è stato una estremizzazione a scopo didatticolizzando.

```html
<section class="list-of-images">
        <div class="row" :class="dynamicStyleSelector(imgSrc)" >
            <div class="col" v-for="img in imgSrc">
                <img class="img-primary" :src="getImagePath(img)" alt="">
                <img class="img-see" src="../assets/svg/view-svgrepo-com.svg" alt="">
            </div>
        </div>
    </section>
```

``` javascript
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
```

**Sezione css Con dynamicStyleSelector**
```css
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
```

### Costruito con

- Semantica HTML5 markup
- SCSS
- Javascript  VUE.js + Vite.js
