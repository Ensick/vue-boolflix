<template>
    <div class="card">
        <img class="img-poster" :src="elem.poster_path == null ? 'https://i0.wp.com/learn.onemonth.com/wp-content/uploads/2017/08/1-10.png?fit=845%2C503&ssl=1':`https://image.tmdb.org/t/p/w342/${elem.poster_path}`" alt="img"> 
        <div class="card-text">
            <h2>Titolo Originale: {{elem.original_title}}</h2>
            <h2>Titolo: {{elem.title}}</h2>
            <div class="cont-bandiera">
                <h3>Lingua Orginale:</h3>
                <img class="bandiera-lingua" :src="`https://www.countryflagicons.com/FLAT/32/${this.bandieraLingua.toUpperCase()}.png`" alt="img">
            </div>
            
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
        },

        data(){
            return{

                bandieraLingua: this.elem.original_language
            }
        },
        mounted(){

            this.sovrascritturaLingua()
        },
        methods:{

            sovrascritturaLingua(){
                
                if(this.bandieraLingua === "en") {

                    this.bandieraLingua = "us";

                } else if (this.bandieraLingua === "ja") {

                    this.bandieraLingua = "jp";

                } else if (this.bandieraLingua === "hi") {

                    this.bandieraLingua = "in";
                }
            }
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
    
    .img-poster{
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: center;
    }  

    .cont-bandiera h3{

        display: inline;
        padding-right: 10px;
    }

    .cont-bandiera img{

        vertical-align: middle;
        padding-bottom: 2px;
    }

}

</style>