<template>
  <div>
    <AlbumList />
  </div>
</template>

<script>

import AlbumList from './components/AlbumList.vue'


export default {
  name: 'App',
  components: {
    AlbumList
  }
}
</script>

<style lang="scss">

@import './assets/style/generals.scss';
@import './assets/style/var.scss';

</style>
