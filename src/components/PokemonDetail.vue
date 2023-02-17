<template>
    <div class="detail">
        <div class="detail-view" v-if="show">
            <div v-if="pokemon" class="image">
                <img :src="imageUrl+pokemon.id+'.png'" alt="">
            </div>
            <div v-if="pokemon" class="data">
                <h2>{{ pokemon.name }}</h2>
                <div class="property">
                    <div class="left">
                        HP
                    </div>
                    <div class="right">
                        {{ pokemon.stats[0].base_stat }}
                    </div>
                </div>
                <div class="property">
                    <div class="left">
                        Attack
                    </div>
                    <div class="right">
                        {{ pokemon.stats[1].base_stat }}
                    </div>
                </div>
                <div class="property">
                    <div class="left">
                        Defese
                    </div>
                    <div class="right">
                        {{ pokemon.stats[2].base_stat }}
                    </div>
                </div>
                <div class="property">
                    <div class="left">
                        Special Attack
                    </div>
                    <div class="right">
                        {{ pokemon.stats[3].base_stat }}
                    </div>
                </div>
                <div class="property">
                    <div class="left">
                        Special Defense
                    </div>
                    <div class="right">
                        {{ pokemon.stats[4].base_stat }}
                    </div>
                </div>
                <div class="property">
                    <div class="left">
                        Speed
                    </div>
                    <div class="right">
                        {{ pokemon.stats[5].base_stat }}
                    </div>
                </div>
                <h3>Pokemon Types</h3>
                <div class="types">
                    <div class="type" 
                        v-for="(value, index) in pokemon.types"
                        :key="'value'+index">
                        {{ value.type.name }}
                    </div>
                </div>
                <h3>Abilities</h3>
                <div class="abilities">
                    <div class="ability" 
                        v-for="(value, index) in pokemon.abilities"
                        :key="'value'+index">
                        {{ value.ability.name }}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props: [
            'pokemonUrl',
            'imageUrl'
        ],

        data: () => {
            return {
                show: false,
                pokemon: {}
            }
        },

        methods: {
            getPokeAPI() {
                let req = new Request(this.pokemonUrl);
                fetch(req)
                    .then(resp =>{
                        if(resp.status === 200)
                            return resp.json();
                    })
                    .then(data => {
                        console.log(data);
                        this.pokemon = data;
                        this.show = true;
                    })
                    .catch(error => {
                        console.log(error);
                    })
            }, 
        },

        created() {
            this.getPokeAPI();
        }
    }
</script>

<style>
    .detail {
        align-items: flex-start;
        background:rgba(0, 0, 0, 0.700);
        display: flex;
        height: 100%;
        justify-content: center;
        left: 0;
        padding: 9rem 1rem 1rem;
        position: fixed;
        top: 0;
        width: 100%;
    }

    .detail-view{
        align-items: center;
        background-color: #fff;
        border-radius: 5px;
        box-shadow: 0 15px 30px rgba(0,0,0,.2),
                    0 10px 10px rgba(0,0,0,.2);
        display: flex;
        flex-direction: column;
        justify-content: center;
        max-width: 510px;
        padding: 5rem 0 0;
        position: relative;
        width: 100%;
    }

    .image{
        align-items: center;
        background-color: #efefef;
        border-radius: 50%;
        box-shadow: 0 15px 30px rgba(0,0,0,.2),
                    0 10px 10px rgba(0,0,0,.2);
        display: flex;
        height: 120px;
        justify-content: center;
        overflow: hidden;
        position: absolute;
        top: -60px;
        width: 120px;
    }

    h2{
        text-transform: capitalize;
    }

    .data{
        align-items: center;
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin-bottom: 4rem;
        width: 100%;
    }

    .property{
        width: 90%;
        max-width: 400px;
        border-bottom: 1px solid #ccc;
        margin-bottom: 1rem;
    }

    .left{ 
            float: left;
    }

    .right{ 
            float: right;
    }

    h3{
        border-bottom: 1px solid #ccc;
        max-width: 400px;
        width: 90%;
    }

    .types, .abilities{
        display: flex;
        flex-wrap: wrap;
        justify-content: flex-start;
        max-width: 400px;
        width: 90%;
    }

    .type, .ability{
        border-radius: 20px;
        color: #fff;
        letter-spacing: 2px;
        margin: 1rem 1rem 1rem 0;
        padding: .5rem 1rem;
        text-transform: capitalize;
        word-wrap: none;
        word-break: keep-all;
    }

    .type{
        background-color: #0a2e50;
    }

    .ability{
        background-color: #c73015;
    }

</style>