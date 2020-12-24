<template>
    <li class="list-group-item media" @click="viewDetails">
        <img class="mr-3" :src="thumbnails" alt="">
        <div class="media-body pt-4">
            {{videoItem.snippet.title}}
        </div>
    </li>
</template>

<script>
    export default {
        name:'VideoListItem',
        props:{
            videoItem:{
                type:Object,
                required:true
            }
        },
        computed:{
            thumbnails(){
                return this.videoItem.snippet.thumbnails.default.url
            }
        },
        methods:{
            viewDetails(){
                this.$emit('videoSelect',this.videoItem)
            }
        }
        
    }
</script>

<style scoped>
li{
    display: flex;
    cursor: pointer;
}

li:hover{
    background-color: #eeeeee;
}
</style>