<template>
  <div>
    <header class="container-fluid">
      <img src="..\assets\img\logo.png" alt="">
    </header>

    <main>
      <div class="container">
        <div v-if="loaded" class="row">
          <Album
            v-for="album in albums"
            :key="album.id"
            :album="album"
          />
          />
        </div>
        <Loader v-else titleLoader="Is loading....."/>
      </div>
    </main>
  </div>
</template>

<script>

import axios from 'axios';

import Album from './Album.vue'

export default {
  name: 'AlbumList',
  components: { 
    Album, 
  },
  data(){
    return{
      Album: [],
      loaded:false,
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music'
    }
  },
  methods:{
    getApi(){
      axios.get(this.apiUrl)
        .then( r => {
          this.album = r.data;
          this.loaded = true;
        })
        .catch( e => {
          console.log(e);
        })
      }
  },
  mounted(){
    this.getApi();
  }
}
</script>


<style scoped lang="scss">
  header{
    background-color: #2e3a46;
    height: 50px;

    img{
      height: 90%;  
    }
  }

  main{
    background-color: #1e2d3b;
    height: calc(100vh - 50px);
    
    .container{
      display: flex;
      justify-content: space-between;
      align-content: center;    
    }
  }

  .row{
    padding-top: 50px;
    .box{
      color: white;
    }

  }

</style>
