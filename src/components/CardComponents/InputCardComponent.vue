<template>
    <legend>Bill</legend>
    <input-component name="bill" />
    <legend>Select Tip %</legend>
    <legend>Number of People</legend>
    <input-component name="people" />
</template>

<script>
import InputComponent from '../Input/InputComponent.vue'
export default {
    components: { InputComponent },
    name: 'InputCardComponent',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../styles/theme.scss';
legend {
    font: $font-700;
    text-transform: capitalize;
    color: $dark-cyan;
    margin-bottom: 10px;
    font-size: 14px;
}
</style>
