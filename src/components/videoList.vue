<template>
    <div>
        <ul class="list-group">
            <video-list-item v-for="video in vidoeList" 
            :key="video.etag"
            :videoItem="video"
            />
        </ul>
        
    </div>
</template>

<script>
import videoListItem from './videoListItem.vue'
    export default {
  components: { videoListItem },
        name:"VideoList",
        props:{
            vidoeList:{
                type:Array,
                required:true
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>