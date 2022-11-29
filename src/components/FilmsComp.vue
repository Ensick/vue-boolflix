<template>
    <section>

        <CardComp v-for="(elem,index) in dataFilms" :key="index" :elem ="elem" :dataFilms = 'dataFilms'/>

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

</style>