<template>
    <div>
        <ul>{{vidoeList.length}}</ul>
    </div>
</template>

<script>
    export default {
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