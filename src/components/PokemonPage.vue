<template>
    <div class="container">
        <h1>Pokemon's</h1>

    </div>
</template>

<script>
    export default {
        name: 'PokemonPage',
    };
</script>

<style>
    .container{
        background: url(../../public/assets/img/poke-bg.jpg) no-repeat center / cover;
        display:flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        padding: 1rem;
        width: calc(100%-20px);
        min-height: calc(100%-20px);
        font-family: 'Paytone One', sans-serif;
        font-size: 1rem;
    }
    
    h1{
        background: #fefefe;
        border: #1E90FF solid 3px;
        box-shadow: 0 15px 30px #fefefe,
                    0 10px 10px #fefefe;
        border-radius: 10px;
        padding: 0 .5rem;
    }
</style>