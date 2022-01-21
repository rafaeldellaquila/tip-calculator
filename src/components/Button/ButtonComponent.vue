<template>
    <button
        :class="this.title != 'reset' ? 'tips' : 'reset'"
        type="button"
        :value="this.value"
    >
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

button {
    cursor: pointer;
    font: $font-400;
    border: none;
    border-radius: 6px;
    text-transform: uppercase;
}

.tips {
    background-color: $dark-cyan;
    color: $white;
    padding: 10px 35px;
}

.reset {
    color: $dark-cyan;
    background-color: $color-cyan;
    width: 100%;
    font-weight: 700;
    padding: 10px 0;

    &:disabled {
        opacity: 0.2;
        cursor: no-drop;
    }
}
</style>
