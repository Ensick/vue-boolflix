<template>
    <section>

        <h2 v-show="dataSeries.length > 0">Serie Tv</h2>

        <div class="cont-cards">

            <CardSeries v-for="(elem,index) in dataSeries" :key="index" :elem ="elem"/>
        </div>
        
    </section>
</template>

<script>

    import CardSeries from './CardSeries.vue'

    export default {
        name: 'SeriesComp',

        components:{

            CardSeries,
        },

        props:{

            dataSeries: Array
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