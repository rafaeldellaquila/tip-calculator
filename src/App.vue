<template>
    <main>
        <img alt="Vue logo" width="62" src="./assets/logo.svg" />
        <card-component />
    </main>
</template>

<script>
import CardComponent from './components/MainContainer/CardComponent.vue'

export default {
    name: 'App',
    components: {
        'card-component': CardComponent,
    },
}
</script>

<style lang="scss">
@import './styles/theme.scss';
body {
    #app {
        background-color: $light-grey-cyan;
        height: 100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        flex-direction: row;
        align-content: center;

        main {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            img {
                margin-bottom: 60px;
            }
        }
    }
}
</style>
