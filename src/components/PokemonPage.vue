<template>
    <div class="container">
        <h1>Pokemon's</h1>
        <PokemonSearch 
            :apiUrl="apiUrl"
            @setPokemonUrl="setPokemonUrl"
        />
        <PokemonList 
            :imageUrl="imageUrl" 
            :apiUrl="apiUrl"
            @setPokemonUrl="setPokemonUrl"
        />
        <PokemonDetail 
            v-if="showDetail"
            :pokemonUrl="pokemonUrl"
            :imageUrl="imageUrl"
            @closeDetail="closeDetail"
        />
    </div>
</template>

<script>
    import PokemonSearch from './PokemonSearch.vue';
    import PokemonList from './PokemonList.vue';
    import PokemonDetail from './PokemonDetail.vue';
    
    export default {
        name: 'PokemonPage',

        data: () => {
           return {
            imageUrl: 'https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/',
            apiUrl: 'https://pokeapi.co/api/v2/pokemon/',
            pokemonUrl:'',
            showDetail: false
           } 
        },
        components: {
            PokemonSearch,
            PokemonList,
            PokemonDetail
        },
        methods: {
            setPokemonUrl(url) {
                this.pokemonUrl = url;
                this.showDetail = true;
            },
            closeDetail() {
                this.pokemonUrl = '';
                this.showDetail = false;
            }
        }
    };
</script>

<style>
    .container{
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
        box-shadow: 0 15px 30px rgba(0,0,0,.2),
                    0 10px 10px rgba(0,0,0,.2);
        border-radius: 10px;
        color: #0a2e50;
        margin-bottom: 1rem;
        padding: 0 1rem;
    }
</style>