<template>
    <div class="card">
        <img class="img-poster" :src="elem.poster_path == null ? 'https://i0.wp.com/learn.onemonth.com/wp-content/uploads/2017/08/1-10.png?fit=845%2C503&ssl=1':`https://image.tmdb.org/t/p/w342/${elem.poster_path}`" alt="img"> 
        <div class="card-text">
            <h2>Titolo Originale: {{elem.original_name}}</h2>
            <h2>Titolo: {{elem.name}}</h2>
            <div class="cont-bandiera">
                <h3>Lingua Orginale:</h3>
                <img class="bandiera-lingua" :src="`https://www.countryflagicons.com/FLAT/32/${elem.original_language.toUpperCase()}.png`" alt="img">
            </div>
            <div class="cont-voto">
                <span>Voto:</span>
                <font-awesome-icon v-for="(elem,index) in this.splitVoto()" :key="index" icon="fa-solid fa-star"/>
                <p>{{elem.overview}}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'CardSeries',

        props:{

            elem: Object
        },
        data(){
            return{

                votoStelle:''
            }
        },
   
        beforeUpdate(){

            this.cambioBandiera(this.elem)
        },
        mounted(){

             this.cambioBandiera(this.elem)
        },
        methods:{

            cambioBandiera(elem){

                if(elem.original_language === "en"){

                    elem.original_language = "us";

                }else if (elem.original_language === "ja"){

                    elem.original_language = "jp";

                }else if (elem.original_language === "hi"){

                    elem.original_language = "in";

                }else if (elem.original_language === "cs") {

                    elem.original_language = "cz";

                } else if (elem.original_language === "ko") {
                    
                    elem.original_language = "kr";

                } else if (elem.original_language === "sv") {

                    elem.original_language = "ch";

                } else if (elem.original_language === "fa") {

                    elem.original_language = "ir";

                } else if (elem.original_language === "zh") {

                    elem.original_language = "cn";

                } else if (elem.original_language === "he") {

                    elem.original_language = "il";

                } else if (elem.original_language === "te") {

                    elem.original_language = "in";

                } else if (elem.original_language === "ur") {

                    elem.original_language = "pk";

                } else if (elem.original_language === "sq") {

                    elem.original_language = "al";

                } else if (elem.original_language === "da") {

                    elem.original_language = "dk";

                }else{

                    elem.original_language
                } 

            },

            splitVoto(){

                this.votoStelle = parseInt(this.elem.vote_average/2)

                return this.votoStelle
                
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
    overflow-x: auto;

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
            padding-bottom: 10px;
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

    .cont-voto{

        span{

            font-weight: bold;
            font-size: 1.2rem;
            padding-right: 10px;
        }

        .fa-star{

            color: rgb(255, 230, 0);
        }

        
        p{

            line-height: 20px;
            padding-top: 10px;
        }
    }
}

</style>