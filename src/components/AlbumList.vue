<template>
  <div>
    <header class="container-fluid">
      <img src="..\assets\img\logo.png" alt="">
    </header>

    <main>
      <SearchBar @sendSearch="performSearch" />
      <div class="container">
        <div v-if="loaded" class="row">
          <Album
            v-for="item in filteredAlbum"
            :key="item.id"
            :item="item"
          />
        </div>
        <Loader v-else titleLoader="Is loading....."/>
      </div>
    </main>
  </div>
</template>

<script>

import axios from 'axios';

import Album from './Album';
import Loader from './Loader';
import SearchBar from './SearchBar';

export default {
  name: 'AlbumList',
  components: { 
    Album, 
    Loader,
    SearchBar,
  },
  data(){
    return{
      //da chiarire la questione singolare e plurale nel ciclo v-for
      album: [],
      loaded: false,
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      textToSearch: '',
    }
  },
  //si attiva quando viene modificato qualcosa al suo interno
  computed:{
    //non funziona
    filteredAlbum(){
      if(this.textToSearch === ''){
        return this.album;
        
      } else {
        return this.albums.filter( item =>{
        return item.name.toUpperCase().includes(this.textToSearch.toUpperCase());
        }
      ) 
    }
  }
}, 
  methods:{
    //text è un nome random per chiamare il dato che mi arriva
    performSearch(text){
      this.textToSearch = text;
      //console.log(text)
    },
    getApi(){
      axios.get(this.apiUrl)
      .then( r => {
        this.album = r.data.response;
        this.loaded = true;
        console.log('r.data', r.data.response)
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
    height: calc(100% - 50px);
    
    .container{
      display: flex;
      justify-content: space-between;
      align-content: center; 
    }
  }

  .row{
    padding-top: 50px;
  }

</style>
