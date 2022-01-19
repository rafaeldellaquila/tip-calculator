<template>
    <h1>CardComponent</h1>
    <input-card-component />
    <result-card-component />
</template>

<script>
import InputCardComponent from '../CardComponents/InputCardComponent.vue'
import ResultCardComponent from '../CardComponents/ResultCardComponent.vue'
export default {
    components: {
        'input-card-component': InputCardComponent,
        'result-card-component': ResultCardComponent,
    },
    name: 'CardComponent',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss"></style>
