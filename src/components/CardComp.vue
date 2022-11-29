<template>
    <div class="card">
        <img :src="elem.poster_path == null ? 'https://i0.wp.com/learn.onemonth.com/wp-content/uploads/2017/08/1-10.png?fit=845%2C503&ssl=1':`https://image.tmdb.org/t/p/w342/${elem.poster_path}`" alt="img"> 
        <div class="card-text">
            <h2>Titolo Originale: {{elem.original_title}}</h2>
            <h2>Titolo: {{elem.title}}</h2>
            <h3>Lingua Orginale: {{elem.original_language}}</h3>
            <h3>Voto: {{elem.vote_average}}</h3>
        </div>
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
    
    margin-inline-end: 4px;
    width: 350px;
    aspect-ratio: 2/3;
    flex-shrink: 0;
    position: relative;

    .card-text{

        padding: 20px;
        background-color: rgba(0, 0, 0, 0.8);
        width: 100%;
        height: 100%;
        color: white;
        display: none;
        font-size: 1rem;
        position: absolute;
        top: 0;
        left: 0;


        h2,h3{

            line-height: 35px;
            padding-bottom: 15px;
        }
    }

     &:hover .card-text{

        display: block;
    }


    img{
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
    }  
}

</style>