<template>
    <legend>Bill</legend>
    <input-component name="bill" />
    <legend>Select Tip %</legend>
    <button-component
        v-for="(value, index) in tipValues"
        :value="value.value"
        :title="value.name"
        :key="index"
    />
    <legend>Number of People</legend>
    <input-component name="people" />
</template>

<script>
import ButtonComponent from '../Button/ButtonComponent.vue'
import InputComponent from '../Input/InputComponent.vue'

const tipValues = [
    {
        name: '5%',
        value: 5,
    },
    {
        name: '10%',
        value: 10,
    },
    {
        name: '15%',
        value: 15,
    },
    {
        name: '25%',
        value: 25,
    },
    {
        name: '50%',
        value: 50,
    },
    {
        name: 'Custom',
        value: null,
    },
]

export default {
    components: { InputComponent, ButtonComponent },
    name: 'InputCardComponent',

    setup() {
        return {
            ButtonComponent: tipValues,
        }
    },
}
</script>

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
