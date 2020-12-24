<template>
  <div class="home">
    <search-bar @termChange="onTermChange"/>  
  </div>
</template>

<script>
import SearchBar from '../components/searchBar.vue'
// @ is an alias to /src


export default {
  name: 'Home',
  components: {
    SearchBar
    
  },
  methods:{
    onTermChange(searchTerm){
      console.log(searchTerm)
    }
  }
}
</script>
