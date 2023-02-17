<template>
    <div class="search-area">
        <form @submit.prevent="setPokemonUrl">
            <label>
                Insira o nome ou "número de ID" de um pokemon abaixo:
            </label>
            <input 
            type="text" 
            v-model="searchValue"
            @submit="setPokemonUrl"
            >
        </form>
        <i class="fas fa-search"></i>
    </div>
</template>

<script>
    export default {
        props: [
            'apiUrl'
        ],

        data: () => {
            return {
                searchValue: '',
            }
        },

        methods: {
            setPokemonUrl() {
                if(this.searchValue !== ''){
                    this.$emit('setPokemonUrl', this.apiUrl + this.searchValue.toLocaleLowerCase());
                }
            }
        }
    }
</script>

<style>
    .search-area{
        background-color: #efefef;
        border-radius: 5px;
        position: relative;
        width: 100%;
        margin-bottom: 1rem;
        max-width: 510px;
        padding: 1rem;
    }

    label{
        color:black;
        margin-bottom: 2rem;
    }

    input {
        border: 3px solid #1E90FF;
        outline: none;
        border-radius: 5px;
        padding: 1rem 4rem 1rem 1rem;
        width: 100%;
        font-size: 1rem;
        box-shadow: 10px 15px 30px rgba(0,0,0,.2),
                    10px 10px 10px rgba(0,0,0,.2);
    }

</style>