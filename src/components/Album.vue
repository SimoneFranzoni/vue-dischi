<template>
    <div class="col-3">
        <div class="box">
            <img :src="album.image" :alt="album.name" class="img-fluid">
            <h2>{{album.title}}</h2>
            <p>{{album.author}}</p>
            <p>{{album.genre}}</p>
            <p>{{album.yeae}}</p>
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