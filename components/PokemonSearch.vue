<template>
    <div class="search-area">
        <form @submit.prevent="setPokemonUrl">
            <input 
            type="text" 
            v-model="searchValue"
            @submit="setPokemonUrl"
            placeholder="Insira o nome ou número de ID de um pokemon"
            >
        </form>
        <i 
            class="fas fa-search"
            @submit="setPokemonUrl"
        ></i>
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
        border-radius: 5px;
        margin-bottom: 1rem;
        max-width: 510px;
        padding: 1rem 0;
        position: relative;
        width: 100%;
    }

    label{
        color:#efefef;
        margin-bottom: 2rem;
    }

    input {
        background-color: #0A2E50;
        border: none;
        border-radius: 5px;
        box-shadow: 10px 15px 30px rgba(0,0,0,.2),
                    10px 10px 10px rgba(0,0,0,.2);
        color: #efefef;
        font-size: 1rem;
        max-width: 510px;
        outline: none;
        padding: 1rem 4rem 1rem 1rem;
        width: 100%;
    }

    input::placeholder {
        color: #efefef;
    }


    i{
        color: #0A2E50;
        cursor: pointer;
        font-size: 1rem;
        position: absolute;
        right: 20px;
        top: 27px;
    }

</style>