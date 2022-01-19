<template>
    <img alt="Vue logo" src="./assets/logo.svg" />
    <card-component />
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

<style lang="scss"></style>
