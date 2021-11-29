<template>
    <div class="col-2">
        <div class="box">
            <img :src="item.poster" :alt="item.name" class="img-fluid">
            <h4>{{item.title}}</h4>
            <div>{{item.author}}</div>
            <div>{{item.genre}}</div>
            <div>{{item.year}}</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Album',
    props:{
        item: Object
  }
}
</script>

<style lang="scss" scoped>
    .box{
        color: white;
        text-align: center;
        img{
           width: 100%; 
        }
    }
</style>