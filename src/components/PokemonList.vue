<template>
    <div class="list">
        <article v-for="(pokemon, index) in pokemons"
        :key="'poke'+index"
        @click="setPokemonUrl(pokemon.url)">
            <img :src="imageUrl + pokemon.id + '.png'" width="96" alt="">
            <h3>{{ pokemon.name }}</h3>
        </article>
    </div>
</template>

<script>
    export default{
        props: [
            'imageUrl',
            'apiUrl'
        ],
        data: () => {
            return {
                pokemons: [],
                nextUrl: '',
                currentUrl: ''
            }
        },
        methods: {
            async getPokeAPI() {
                let req = new Request(this.currentUrl);
                fetch(req)
                .then((resp) => {
                    if(resp.status === 200)
                    return resp.json();
                })
                .then((data) => {
                    this.nextUrl = data.next;
                    data.results.forEach(pokemon => {
                    pokemon.id = pokemon.url.split('/')
                        .filter(function(part) { return !!part }).pop();
                    this.pokemons.push(pokemon);
                    });
                })
                .catch((error) => {
                    console.log(error);
                })
            },
            
            next() {
                this.currentUrl = this.nextUrl;
                this.getPokeAPI();
            },
            setPokemonUrl(url) {
                this.$emit('setPokemonUrl', url);
            }
        },
        
        created() {
            this.currentUrl = this.apiUrl;
            this.getPokeAPI();
        },

        mounted() {
            this.scrollTrigger();
        }
    }
</script>

<style>
    .list{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
        grid-gap: .5rem;
        width: 100%;
        max-width: 510px;
    }

    article{
        background-color: #fefefe;
        border-radius: 5px;
        box-shadow: 0 15px 30px rgba(0,0,0,.2),
                    0 10px 10px rgba(0,0,0,.2);
        cursor: pointer;
        height: 150px;
        text-align: center;
        text-transform: capitalize;
    }

    h3{
        margin: 0;
    }
</style>