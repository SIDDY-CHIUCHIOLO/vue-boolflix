<template>
        <div class="card text-center m-1" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">{{title}} {{name}}</h5>
                <p class="card-text">{{originalTitle}} {{originalName}}</p>
                <div class="d-flex justify-content-center align-items-center mb-1">
                    <span>language : <lang-flag :iso='language'/></span>
                </div>
                <div class="d-flex justify-content-center">
                    <div v-for="(element, index) in listIcon" :key="index" :class="(element.id <= formattingValue() ? 'text-danger' : '')">
                    <i :class="element.icon"></i>
                </div>
                </div>
                <img :src="srcImage()" alt="poster film">
            </div>
        </div>
</template>

<script>
import LangFlag from 'vue-lang-code-flags';

export default {
    name:'FilmIndex',
    components:{
        LangFlag
    },
    props:['title', 'originalTitle', 'language', 'vote', 'name', 'originalName', 'urlImage'],
    data: function(){
        return{
            urlBase: 'https://image.tmdb.org/t/p/',
            Image: '',
            roundedValue: '',
            listSizeImage: ["w45","w92","w154","w185","w300","w500","w780","w1280","h632","original"],
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
                this.Image = this.urlBase + this.listSizeImage[3] + this.urlImage;
                return this.Image
            } else {
                console.warn('immagine non disponibile')
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

</style>