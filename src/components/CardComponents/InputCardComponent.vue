<template>
    <section class="input-card">
        <h2>Bill</h2>
        <input-component name="bill" />
        <h2>Select Tip %</h2>
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
        <h2>Number of People</h2>
        <input-component name="people" />
    </section>
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

h2 {
    font: $font-700;
    text-transform: capitalize;
    color: $dark-cyan;
    margin-bottom: 10px;
    font-size: 14px;
}
</style>
