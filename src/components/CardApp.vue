<script>
export default {
    name: 'CardApp',

    //aggiungo props via object specificando il tipo di dato
    props: {
        imgUrl: String,
        title: String,
        archetype: String
    }
}
</script>
<template lang="">
    <div class="card">
        <img :src="imgUrl" :alt="title">
        <div class="texts">
            <h4 class="text-name">{{title}}</h4>
            <p class="text-archetype">{{archetype}}</p>
        </div>
    </div>
</template>
<style lang="scss">
@use '../styles/partials/variables' as *;
@use '../styles/general.scss' as *;

.card {
    width: calc(100% / 5 - 1rem);
    -webkit-box-shadow: 3px 7px 15px -4px rgba(0, 0, 0, 0.74);
    box-shadow: 3px 7px 15px -4px rgba(0, 0, 0, 0.74);
    border-radius: 5px;
    overflow: hidden;

    img {
        width: 100%;
        object-fit: cover;
        vertical-align: top;
    }

    .texts {
        background-color: $card-bg;
        height: 6rem;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;

        h4 {
            padding: .5rem;
            color: rgb(255, 255, 255);
        }

        p {
            padding: .5rem;
            font-weight: 300;
        }
    }
}
</style>