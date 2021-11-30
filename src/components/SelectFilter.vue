<template>
  <section>
    <select 
    v-model="genre"
    @change="$emit('changeGenre',genre)"
    class="form-select">
        <option value="All" selected>Tutti i generi</option>
        <option value="Jazz">Jazz</option>
        <option value="Rock">Rock</option>
        <option value="Metal">Metal</option>
        <option value="Pop">Pop</option>
    </select>
  </section>
</template>

<script>
export default {
    name: 'SelectFilter',
    data(){
        return{
            genre: '',
        }
    }
}
console.log(genre);
</script>

<style>
    section{
        width: 20%;
    }
</style>