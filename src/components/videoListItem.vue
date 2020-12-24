<template>
    <li class="list-group-item">
        {{videoItem.snippet.title}}
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
        }
        
    }
</script>

<style lang="scss" scoped>

</style>