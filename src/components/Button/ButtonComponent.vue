<template>
    <template v-if="this.title == 'reset' || this.title != 'custom'">
        <button
            :class="this.title != 'reset' ? 'tips' : 'reset'"
            type="button"
            :value="this.value"
        >
            {{ this.title }}
        </button>
    </template>
    <template v-else>
        <button class="custom" type="button" :value="this.value">
            {{ this.title }}
        </button>
    </template>
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
    font-size: 20px;
    width: 115px;
    transition: 0.3s;
    &:hover {
        background-color: $color-cyan;
    }
}

.tips {
    background-color: $dark-cyan;
    color: $white;
    padding: 8px 30px;
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

.custom {
    background-color: $neutral-cyan;
    color: $dark-lighter-cyan;
    text-transform: capitalize;
    font: $font-700;
    font-size: 20px;
}
</style>
