<template>
    <div class="totalizers">
        <span class="title">
            <h3>{{ name == 'total' ? 'total' : 'tip amount' }}</h3>
            <p>/person</p>
        </span>

        <span class="totals"
            >$<span>{{
                name == 'tip amount' ? this.valueTip : this.totalValue
            }}</span>
        </span>
    </div>
</template>

<script>
export default {
    name: 'TipAmountComponent',
    props: {
        valueTip: Number,
        totalValue: Number,
        name: String,
    },
}
</script>

<style scoped lang="scss">
@import '../../styles/theme.scss';

.totalizers {
    font: $font-400;

    .title {
        h3 {
            text-transform: capitalize;
            color: white;
            font-size: 16px;
        }
        p {
            color: $light-darker-cyan;
            font-size: 14px;
        }
    }

    .totals {
        color: $color-cyan;
        font: $font-700;
        font-size: 48px;
    }
}
</style>
