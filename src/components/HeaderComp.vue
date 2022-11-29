<template>
    <header>
        <div>
            <h1>BOOLFLIX</h1>
        </div>

        <div>
            <input type="text" placeholder="Cerca">
        </div>
    </header>
</template>

<script>
    export default {
        
        name: 'HeaderComp'
    }
</script>

<style lang="scss" scoped>

    header{

        height: 100px;
        background-color: black;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding-inline: 25px;

        div{

            h1{
                color: red;
            }
        }
        
        input{

            padding-inline-start: 10px;
            height: 30px;
            width: 250px;
        }
    }

</style>