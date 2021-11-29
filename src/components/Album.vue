<template>
    <div class="col-3">
        <div class="box">
            <img :src="item.poster" :alt="item.name" class="img-fluid">
            <h2>{{item.title}}</h2>
            <p>{{item.author}}</p>
            <p>{{item.genre}}</p>
            <p>{{item.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Album',
    props:{
        album: Object
  }
}
</script>

<style>

</style>