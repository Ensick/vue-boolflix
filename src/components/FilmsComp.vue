<template>
    <section>

        <h2 v-show="dataFilms.length > 0">Film</h2>

        <div class="cont-cards">

            <CardComp v-for="(elem,index) in dataFilms" :key="index" :elem ="elem" :dataFilms = 'dataFilms'/>

        </div>
        
    </section>
</template>

<script>
    import CardComp from './CardComp.vue'

    export default {

        name: 'FilmsComp',

        components: {

            CardComp,

        },

        props: {

            dataFilms: Array
        }
    }
</script>

<style lang="scss" scoped>

    section{

        padding-top: 60px;
        width: 90%;
        margin: 0 auto;

        h2{

            font-size: 2.5rem;
            color: white;
            padding-bottom: 10px;
        }
        
        .cont-cards{

         
            display: flex;
            overflow-y: auto;
            padding-bottom: 5px;

        }
    }

</style>