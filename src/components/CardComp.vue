<template>
    <div class="card">
        <!-- <h1>{{elem.original_title}}</h1> -->
        <img :src="elem.poster_path == null ? 'https://i0.wp.com/learn.onemonth.com/wp-content/uploads/2017/08/1-10.png?fit=845%2C503&ssl=1':`https://image.tmdb.org/t/p/w342/${elem.poster_path}`" alt="img"> 
    </div>
</template>

<script>
    export default {

        name: 'CardComp',

        props: {

            dataFilms: Array,
            elem: Object
        }
    }
</script>

<style lang="scss" scoped>

.card{
    
    background-color: red;
    border: 2px solid black;
    width: 350px;
    aspect-ratio: 2/3;
    flex-shrink: 0;

    img{
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
    }  
}

</style>