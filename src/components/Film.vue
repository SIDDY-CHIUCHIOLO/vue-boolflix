<template>
        <ul>
            <li class="h-100">
                <div class="card h-100 border border-2 border-light position-relative">
                    <!-- card immagine del film -->
                    <div class="front-card h-100 d-flex judtify-content-center position-relative">
                        <img :src="srcImage()" alt="post film">
                    </div>

                    <!-- card dettagli del film -->
                    <div class="back-card bg-dark text-white h-100 w-100 p-4  position-absolute">
                        <h2 class="text-center pb-4">{{title}} {{name}}</h2>
                        <div class="d-flex justify-content-center  pb-5">
                            <div v-for="(element, index) in listIcon" :key="index" :class="(element.id <= formattingValue() ? 'text-danger' : '')">
                                <i :class="element.icon"></i>
                            </div>
                        </div>
                        <p class="card-text"> <span class="fw-bold text-danger">Titolo originale:</span> {{originalTitle}} {{originalName}}</p>
                        <p><span class="fw-bold text-danger">language :</span> {{language}} <lang-flag  :iso='language'/></p>
                        <p v-if="overview !== ''"><span class="fw-bold text-danger">Overview: </span>{{overview}}</p>
                        <p v-else><span class="fw-bold text-danger">Overview: </span>non disponible</p>
                    </div>
                </div>
            </li>
        </ul>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
    name:'FilmIndex',
    components:{
        LangFlag
    },
    props:['title', 'originalTitle', 'language', 'vote', 'name', 'originalName', 'urlImage', 'overview'],
    data: function(){
        return{
            urlBase: 'https://image.tmdb.org/t/p/',
            Image: '',
            roundedValue: '',
            listSizeImage: ["w45","w92","w154","w185","w300", "w342","w500","w780","w1280","h632","original"],
            listIcon:[
                {
                    id: 1,
                    icon: "fas fa-star"
                },
                {
                    id: 2,
                    icon: "fas fa-star"
                },
                {
                    id: 3,
                    icon: "fas fa-star"
                },
                {
                    id: 4,
                    icon: "fas fa-star"
                },
                {
                    id: 5,
                    icon: "fas fa-star"
                }
            ]

        }
    },
    methods:{
        srcImage(){
            if(this.urlImage !== null){
                this.Image = this.urlBase + this.listSizeImage[5] + this.urlImage;
                return this.Image
            } else {
                console.warn('immagine non disponibile')
                this.Image = 'https://images.sample.net/wp-content/uploads/2019/10/Classic-Movie-Poster.jpg'
                return this.Image
            }
        },
        formattingValue(){
            this.roundedValue = this.vote.toFixed(0) / 10 * 5;
            return this.roundedValue.toFixed(0);
        }
    }
}
</script>

<style lang="scss" scoped>
ul{
    height: 520px;
    li{
        list-style: none;
        .card{
            width: 350px;
            .back-card{
                overflow-y: auto;
                display: none;
                p{
                    margin: 0;
                }
            }
        }
        .card:hover .back-card{
            display: inline;
        }
    }
}

</style>