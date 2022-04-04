<template>
        <div class="card text-center" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">{{title}}</h5>
                <p class="card-text">{{originalTitle}}</p>
                <div class="d-flex justify-content-center align-items-center mb-1">
                    <span>language : {{language}}</span>
                </div>
                <p>{{vote}}</p>
                <button @click="listLanguage">click</button>
            </div>
            <div v-for="(element, index) in flegList" :key="index">
                <img v-if="(element.active == true)" :src="require(`@/assets/img/${element.url}`)" alt="">
            </div>
        </div>
</template>

<script>

export default {
    name:'FilmIndex',
    props:['title', 'originalTitle', 'language', 'vote'],
    data: function(){
        return{
            lingua: "prova",
            flegList:[
                {
                    url:"fr-logo.png",
                    language:"fr",
                    active: false,
                },
                {
                    url:"de-logo.png",
                    language:"de",
                    active: false,
                },
                {
                    url:"it-logo.png",
                    language:"it",
                    active: false,
                },
                {
                    url:"pt-logo.png",
                    language:"pt",
                    active: false,
                },
                {
                    url:"en-logo.png",
                    language:"en",
                    active: false,
                },
                {
                    url:"ru-logo.png",
                    language:"ru",
                    active: false,
                },
                {
                    url:"es-logo.png",
                    language:"es",
                    active: false,
                },
            ],
        }
    },
    methods:{
        listLanguage(){
            this.flegList.forEach(element => {
                if(element.language == this.language){
                    element.active = true;
                } else {
                    false
                }
            });
        }
    }
}
</script>

<style lang="scss" scoped>
    img{
        width: 50px;
        height: 30px;
    }
</style>