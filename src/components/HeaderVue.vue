<template lang="">
    <header>
        <h1>Yu-Gi-Oh Api</h1>
        <select name="archetype" id="archetypes">
            <option value="Alien">Alien</option>
            <option value="Laval">Laval</option>
            <option value="Vylon">Vylon</option>
            <option value="Inzektor">Inzektor</option>
            <option value="Umi">Umi</option>
            <option value="Gusto">Gusto</option>
        </select>
    </header>
</template>

<script>
export default {
    name: 'HeaderVue',
    data() {
        return {

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