<template>
  <div class="home">
    <search-bar @termChange="onTermChange"/>  
  </div>
</template>

<script>
import axios from 'axios'
import SearchBar from '../components/searchBar.vue'
// @ is an alias to /src

const API_KEY = 'AIzaSyB-AUC3gvo-cDatZVS1dMKeyDDgKA9EstE';

export default {
  name: 'Home',
  components: {
    SearchBar
    
  },
  methods:{
    onTermChange(searchTerm){
      axios.get('https://www.googleapis.com/youtube/v3/search',{
        params:{
        key:API_KEY,
        type:'video',
        part:'snippet',
        q:searchTerm
        }
      }).then(response=>{
        console.log(response)
      })
    }
  }
}
</script>
