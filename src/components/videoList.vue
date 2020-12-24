<template>
    <div>
        <ul class="list-group">
            <video-list-item v-for="video in vidoeList" 
            :key="video.etag"
            :videoItem="video"
            @videoSelect="viewVideoDetail"
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
        },
        methods:{
            viewVideoDetail(vidoeList){
                this.$emit('videoSelect',vidoeList)
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>