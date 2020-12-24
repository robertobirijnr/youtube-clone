<template>
  <div class="container">
    <search-bar @termChange="onTermChange"/>  
    <video-list
     :vidoeList="videos"
     @videoSelect="videoSelected"
     />
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from '../components/searchBar.vue'
import VideoList from '../components/videoList.vue';
// @ is an alias to /src

const API_KEY = 'AIzaSyB-AUC3gvo-cDatZVS1dMKeyDDgKA9EstE';

export default {
  name: 'Home',
  components: {
    SearchBar,
    VideoList
    
  },
  data() {
    return {
      videos: []
    }
  },
  methods:{
    videoSelected(video){
      console.log(video)
    },
    onTermChange(searchTerm){
      axios.get('https://www.googleapis.com/youtube/v3/search',{
        params:{
        key:API_KEY,
        type:'video',
        part:'snippet',
        q:searchTerm
        }
      }).then(response=>{
        this.videos = response.data.items
        console.log(response)
      })
    }
  }
}
</script>
