<template>
    <section class="input-card">
        <section class="bills">
            <h2>Bill</h2>
            <input-component name="bill" />
        </section>
        <section class="tips">
            <h2>Select Tip %</h2>
            <section class="buttons">
                <button-component
                    v-for="(tip, index) in tipValues"
                    :value="tip.value"
                    :title="tip.name"
                    :key="index"
                    @click="this.handleTips(tip.value)"
                />
            </section>
        </section>
        <section class="persons">
            <h2>Number of People</h2>
            <input-component name="people" />
        </section>
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

    {
        name: 'custom',
        value: null,
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

.input-card {
    max-width: 385px;
    margin: auto 35px;
    display: flex;
    flex-direction: column;
    align-items: flex-start;

    h2 {
        font: $font-700;
        text-transform: capitalize;
        color: $dark-cyan;
        margin-bottom: 10px;
        font-size: 14px;
    }

    .bills {
        margin-bottom: 35px;
    }

    .buttons {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        justify-content: space-around;
        gap: 10px;
        max-height: 290px;
        margin-bottom: 35px;
    }
}
</style>
