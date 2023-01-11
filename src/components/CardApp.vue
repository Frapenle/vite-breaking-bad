<script>
export default {
    // name: 'CardApp',
    props: {
        imgurl: String,
        title: String
    }
}
</script>
<template lang="">
    <div class="card">
        <img :src="imgurl" :alt="title">
        <p class="text-name">{{title}}</p>
        <p class="text-type"></p>
    </div>
</template>
<style lang="scss">

</style>