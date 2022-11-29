<template>
    <div class="card">
        <h1>{{elem.original_title}}</h1>
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

    background-color: red;
    height: 100px;
    width: 100px;
    padding: 10px;
}

</style>