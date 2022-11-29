<template>
    <main>
        
        <FilmsComp :dataFilms = 'dataFilms'/>
        
    </main>
</template>

<script>

    import FilmsComp from './FilmsComp.vue'

    export default {

        name: 'MainComp',

        components:{

            FilmsComp,

        },

        props:{

            dataFilms: Array,
        }
    }
</script>

<style lang="scss" scoped>

    main{

        height: calc(100% - 100px);
        background-color: rgb(48, 48, 48);
    }

</style>