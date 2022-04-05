<template>
        <div class="card text-center m-1" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">{{title}} {{name}}</h5>
                <p class="card-text">{{originalTitle}} {{originalName}}</p>
                <div class="d-flex justify-content-center align-items-center mb-1">
                    <span>language : <lang-flag :iso='language'/></span>
                </div>
                <p>{{vote}}</p>
                <img :src="srcImage()" alt="">
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
            listSizeImage: ["w45","w92","w154","w185","w300","w500","w780","w1280","h632","original"]
        }
    },
    methods:{
        srcImage(){
            this.Image = this.urlBase + this.listSizeImage[3] + this.urlImage;
            return this.Image
        }
    }
}
</script>

<style lang="scss" scoped>
</style>