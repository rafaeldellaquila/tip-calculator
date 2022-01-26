<template>
    <section class="result-card">
        <section class="results">
            <tip-amount-component name="tip amount" :valueTip="0.15" />
            <tip-amount-component name="total" :totalValue="0.2" />
        </section>
        <button-component title="reset" disabled />
    </section>
</template>

<script>
import ButtonComponent from '../Button/ButtonComponent.vue'
import TipAmountComponent from '../ResultComponents/TipAmountComponent.vue'
export default {
    name: 'ResultCardComponent',

    components: {
        TipAmountComponent,
        ButtonComponent,
    },
}
</script>

<style scoped lang="scss">
@import '../../styles/theme.scss';

.result-card {
    background-color: $dark-cyan;
    padding: 50px 40px 40px 40px;
    border-radius: 15px;
    max-width: 410px;

    .results {
        margin-bottom: 90px;
    }
}
</style>
