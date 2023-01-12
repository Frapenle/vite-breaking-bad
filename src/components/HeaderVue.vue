<template lang="">
    <header>
        <h1>Yu-Gi-Oh Api</h1>
        <select v-model="archetype" id="archetypes" @change="$emit('selection', archetype)">
            <option :value="item.toLowerCase()" v-for="item in archetypes">{{item}}</option>
        </select>
    </header>
</template>

<script>
export default {
    name: 'HeaderVue',
    data() {
        return {
            archetypes: ['Alien', 'Laval', 'Vylon', 'Inzektor', 'Umi', 'Gusto'],
            archetype: 'alien'
        }
    },
}
</script>

<style lang="scss" scoped>
header {
    height: 60px;
    padding: 0 1rem;
    background-color: antiquewhite;
}

h1 {
    line-height: 60px;
}
</style>