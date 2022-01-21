<template>
    <legend>Bill</legend>
    <input-component name="bill" />
    <legend>Select Tip %</legend>
    <section>
        <button-component
            v-for="(tip, index) in tipValues"
            :value="tip.value"
            :title="tip.name"
            :key="index"
            @click="this.handleTips(tip.value)"
        />
        <input-component name="custom" />
    </section>
    <legend>Number of People</legend>
    <input-component name="people" />
</template>

<script>
import ButtonComponent from '../Button/ButtonComponent.vue'
import InputComponent from '../Input/InputComponent.vue'

const StandardTipValues = [
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
]

export default {
    components: { InputComponent, ButtonComponent },
    name: 'InputCardComponent',

    computed: {
        tipValues: () => {
            return StandardTipValues
        },
    },

    methods: {
        handleTips(value) {
            return console.log(value)
        },
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
