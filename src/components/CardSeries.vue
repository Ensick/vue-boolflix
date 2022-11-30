<template>
    <div class="card">
        <img class="img-poster" :src="elem.poster_path == null ? 'https://i0.wp.com/learn.onemonth.com/wp-content/uploads/2017/08/1-10.png?fit=845%2C503&ssl=1':`https://image.tmdb.org/t/p/w342/${elem.poster_path}`" alt="img"> 
        <div class="card-text">
            <h2>Titolo Originale: {{elem.original_name}}</h2>
            <h2>Titolo: {{elem.name}}</h2>
            <div class="cont-bandiera">
                <h3>Lingua Orginale:</h3>
                <img class="bandiera-lingua" :src="`https://www.countryflagicons.com/FLAT/32/${this.linguaTrasformata.toUpperCase()}.png`" alt="img">
            </div>
            <div>
                <font-awesome-icon v-for="(elem,index) in 5" :key="index" icon="fa-solid fa-star"/>
            <!-- {{elem.vote_average}} -->
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

                linguaTrasformata: ''
            }
        },
        beforeUpdate(){

            if(this.elem.original_language === "en") {

               return this.linguaTrasformata = "us";

            } else if (this.elem.original_language === "ja") {

                return this.linguaTrasformata = "jp";

            } else if (this.elem.original_language === "hi") {

               return this.linguaTrasformata = "in";

            }else if (this.elem.original_language === "cs") {

                return this.linguaTrasformata = "cz";

            } else if (this.elem.original_language === "ko") {
                
                return this.linguaTrasformata = "kr";

            } else if (this.elem.original_language === "sv") {

                return this.linguaTrasformata = "ch";

            } else if (this.elem.original_language === "fa") {

                return this.linguaTrasformata = "ir";

            } else if (this.elem.original_language === "zh") {

                return this.linguaTrasformata = "cn";

            } else if (this.elem.original_language === "he") {

                return this.linguaTrasformata = "il";

            } else if (this.elem.original_language === "te") {

                this.linguaTrasformata = "in";

            } else if (this.elem.original_language === "ur") {

                return this.linguaTrasformata = "pk";

            } else if (this.elem.original_language === "sq") {

                return this.linguaTrasformata = "al";

            } else if (this.elem.original_language === "da") {

                return this.linguaTrasformata = "dk";

            }else{

                return this.linguaTrasformata = this.elem.original_language
            }
        },
        methods:{

            splitVoto(){
                
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