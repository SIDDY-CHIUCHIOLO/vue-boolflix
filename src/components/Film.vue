<template>
        <div class="card text-center" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">{{title}}</h5>
                <p class="card-text">{{originalTitle}}</p>
                <p>{{language}}</p>
                <p>{{vote}}</p>
            </div>
        </div> 
</template>

<script>

export default {
    name:'FilmIndex',
    props:['title', 'originalTitle', 'language', 'vote']
}
</script>

<style>

</style>