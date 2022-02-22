<template>
    <section class="main-card">
        <section class="input-card">
            <section class="bills">
                <h2>Bill</h2>
                <input
                    type="number"
                    class="bill"
                    placeholder="0"
                    v-model="billValue"
                />
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
                    <input
                        type="number"
                        class="custom"
                        name="custom"
                        placeholder="custom"
                    />
                </section>
            </section>

            <section class="persons">
                <h2>Number of People</h2>
                <input
                    type="number"
                    class="people"
                    placeholder="0"
                    v-model="numberOfPeople"
                    @change="handleTotalPerson"
                />
            </section>
        </section>
        <section class="result-card">
            <section class="results">
                <tip-amount-component
                    name="tip amount"
                    :valueTip="this.tipAmount > 1 ? this.tipAmount : 0"
                />
                <tip-amount-component
                    name="total"
                    :totalValue="this.totalResult > 1 ? this.totalResult : 0"
                />
            </section>
            <button-component
                title="reset"
                :disabled="this.totalResult > 1 ? false : true"
                aria-disabled="Fill the values correctly"
                @click="this.resetTips"
            />
        </section>
    </section>
</template>

<script>
import ButtonComponent from '../Button/ButtonComponent.vue'
import TipAmountComponent from '../ResultComponents/TipAmountComponent.vue'

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
    components: {
        ButtonComponent,
        TipAmountComponent,
    },

    name: 'CardComponent',

    data() {
        return {
            billValue: null,
            numberOfPeople: null,
            tipValue: null,
            tipAmount: null,
            totalPerson: null,
            totalResult: null,
        }
    },

    computed: {
        tipValues: () => {
            return StandardTipValues
        },
    },

    methods: {
        handleTips(value) {
            return (this.tipValue = value)
        },

        handleTotalPerson() {
            let value = this.tipValue / 100
            let totalTipValue = value * this.billValue // / this.numberOfPeople //primeiro input
            let totalAmount = totalTipValue + this.billValue

            this.tipAmount = parseFloat(
                ((value * this.billValue) / this.numberOfPeople).toFixed(2)
            )
            this.totalResult = parseFloat(
                (totalAmount / this.numberOfPeople).toFixed(2)
            )
        },

        resetTips() {
            console.log('asd')
            ;(this.billValue = null),
                (this.numberOfPeople = null),
                (this.tipValue = null),
                (this.tipAmount = null),
                (this.totalPerson = null),
                (this.totalResult = null)
        },
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../styles/theme.scss';

.main-card {
    background-color: $white;
    border-radius: 24px;
    display: flex;
    padding: 30px;
    justify-content: center;
    align-items: center;
}

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

    input {
        background-repeat: no-repeat;
        background-size: 4%;
        background-position-y: 50%;
        background-position-x: 5%;
        text-align: right;
        padding: 5px 20px;
        font: $font-700;
        color: $dark-cyan;
        border-radius: 6px;
        border-color: transparent;
        background-color: $neutral-cyan;
        margin: 0;
        font-size: 24px;

        &::placeholder {
            color: $light-darker-cyan;
            font: $font-400;
        }

        &:focus {
            outline: none;
            border: 2px solid $color-cyan;
        }

        &::-webkit-outer-spin-button,
        &::-webkit-inner-spin-button {
            -webkit-appearance: none;
        }

        &[type='number'] {
            -moz-appearance: textfield;
        }
    }

    .bill {
        background-image: url('../../assets/icon-dollar.svg');
    }

    .people {
        background-image: url('../../assets/icon-person.svg');
    }

    .custom {
        text-align: right;
        padding: 5px 15px;
        font: $font-700;
        font-size: 20px;
        color: $dark-cyan;
        border-radius: 6px;
        border-color: transparent;
        background-color: $neutral-cyan;
        margin: 0;
        width: 83px;
        max-width: 115px;

        &::placeholder {
            color: $light-darker-cyan;
            font: $font-700;
            text-transform: capitalize;
            letter-spacing: -1px;
        }
    }
}

.result-card {
    background-color: $dark-cyan;
    padding: 50px 40px 40px 40px;
    border-radius: 15px;
    max-width: 410px;

    .results {
        margin-bottom: 90px;
    }
}

@media (max-width: $mq-medium) {
    .main-card {
        flex-direction: column;
        max-width: 360px;
    }

    .result-card {
        margin-top: 40px;
    }
}

@media (max-width: $mq-small) {
    .main-card {
        margin: 20px;
    }
}
</style>
