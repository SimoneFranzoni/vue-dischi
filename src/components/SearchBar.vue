<template>
    <section>     
            <div class="col-10">
                <input 
                v-model="textToSearch"
                @keyup.enter="$emit('sendSearch',textToSearch)"
                class="form-control" type="text" placeholder="Ricerca un nome">
            </div>

            <div class="col 1">
                <button 
                @click="$emit('sendSearch',textToSearch)"
                class="btn btn-info">Cerca</button>
            </div>

            <div class="col 1">
                <button class="btn btn-warning">Reset</button>
            </div>
    </section>
  </template>

<script>
export default {
    name: 'SearchBar',
    data(){
        return{
            textToSearch: '',
        }
    }
};
</script>

<style scoped lang="scss">
    section{
        padding: 0 5%;
        display: flex;
    }
</style>