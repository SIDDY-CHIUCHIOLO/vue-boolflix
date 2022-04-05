<template>
        <div class="card text-center m-1" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">{{title}} {{name}}</h5>
                <p class="card-text">{{originalTitle}} {{originalName}}</p>
                <div class="d-flex justify-content-center align-items-center mb-1">
                    <span>language : <lang-flag :iso='language'/></span>
                </div>
                <p>{{vote}}</p>
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
    props:['title', 'originalTitle', 'language', 'vote', 'name', 'originalName'],
    data: function(){
        return{
        }
    },
    methods:{
    }
}
</script>

<style lang="scss" scoped>
    img{
        width: 50px;
        height: 30px;
    }
</style>