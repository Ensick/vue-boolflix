<template>
    <section>

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

        .cont-cards{

            width: 90%;
            margin: 0 auto;
            display: flex;
            overflow-y: auto;
        }
    }

</style>