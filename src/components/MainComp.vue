<template>
    <main>
 
        <FilmsComp :dataFilms = 'dataFilms'/>
        <SeriesComp :dataSeries = 'dataSeries'/>

    </main>
</template>

<script>

    import FilmsComp from './FilmsComp.vue'
    import SeriesComp from './SeriesComp.vue'

    export default {

        name: 'MainComp',

        components:{

            FilmsComp,
            SeriesComp,

        },

        props:{

            dataFilms: Array,
            dataSeries: Array
        }
    }
</script>

<style lang="scss" scoped>

    main{

        height: calc(100% - 100px);
        background-color: rgb(48, 48, 48);
        overflow-y: auto;
        padding-bottom: 60px;
    }

</style>