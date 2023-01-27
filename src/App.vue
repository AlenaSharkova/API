<template>
  <div>
    <EpisodeList />
  </div>
</template>

<script>
import EpisodeList from '@/components/EpisodeList';
export default {
  name: 'App',
  components: {
    EpisodeList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
