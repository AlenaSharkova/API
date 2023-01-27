<template>
    <h1>Episode List</h1>
    <div class="episode-list">
        <div class="episode" v-for="item in episodes" :key="item.id">
          <h2 class="episode__name">{{ item.name }}</h2>
          <p class="episode__air-date">{{item.air_date }}</p>
        </div>
        
    </div>
</template>

<script>

import axios from 'axios';
console.log(axios.isCancel('something'));
export default {
  data() {
    return {
      episodes: null
    };
  },
  methods: {
    getEpisodes: async function() {
      try {
        const episodesData = await axios.get('https://rickandmortyapi.com/api/episode')
        if (episodesData.data.results) {
          this.episodes = episodesData.data.results;
        } else {
          alert('error')
        }
      } catch(err) {
          alert(err)
      }
    }
  },
  mounted() {
    this.getEpisodes();
  }

}
</script>

<style>
* {
  box-sizing: border-box;
}

.episode__name {
  font-size: 16px;
}

.episode__air-date {
  font-size: 14px;
}

.episode-list {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.episode {
  width: 150px;
  height: 150px;
  margin-bottom: 20px;
  margin-right: 20px;
  padding: 20px;
  background-color: antiquewhite;
  border-radius: 10%;
  box-shadow: 20px 5px 14px #676767;
}

</style>