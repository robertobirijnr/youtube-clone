<template>
  <div class="container">
    <search-bar @termChange="onTermChange"/>
    <div class="row">
       <video-detail :video="selectedVideo"/> 
    <video-list
     :vidoeList="videos"
     @videoSelect="videoSelected"
     />
    </div>
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from '../components/searchBar.vue'
import VideoList from '../components/videoList.vue';
import VideoDetail from '../components/videoDetail.vue';
// @ is an alias to /src

const API_KEY = 'AIzaSyBudXzFUR-EtTGPEIvWsio2lq1VvIulR6A';

export default {
  name: 'Home',
  components: {
    SearchBar,
    VideoList,
    VideoDetail
    
  },
  data() {
    return {
      videos: [],
      selectedVideo:null
    }
  },
  methods:{
    videoSelected(video){
      this.selectedVideo = video;
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
