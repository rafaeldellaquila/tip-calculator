<template>
    <button class="tips" type="button" :value="this.value">
        {{ this.title }}
    </button>
</template>

<script>
export default {
    name: 'InputComponent',

    props: {
        value: Number,
        title: String,
    },
}
</script>

<style scoped lang="scss">
@import '../../styles/theme.scss';

.tips {
    background-color: $dark-cyan;
    border: none;
    color: $white;
    font: $font-400;
    padding: 10px 35px;
    border-radius: 6px;
}
</style>
