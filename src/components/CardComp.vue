<template>
    <div class="card">
        <h1>{{elem.original_title}}</h1>
        <!--  https://image.tmdb.org/t/p/w342/wwemzKWzjKYJFfCeiB57q3r4Bcm.png  -->
        <img :src="'https://image.tmdb.org/t/p/w342/'+elem.poster_path" alt="img">
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

}

</style>