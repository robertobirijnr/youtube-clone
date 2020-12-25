<template>
        <ul class="list-group col-md-4">
            <video-list-item v-for="video in vidoeList" 
            :key="video.etag"
            :videoItem="video"
            @videoSelect="viewVideoDetail"
            />
        </ul>
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