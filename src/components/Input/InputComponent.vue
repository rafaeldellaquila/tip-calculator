<template>
    <input
        type="number"
        :class="this.name"
        :name="name"
        :placeholder="this.name == 'custom' ? 'Custom' : 0"
    />
</template>

<script>
export default {
    name: 'InputComponent',

    props: {
        name: String,
    },
}
</script>

<style scoped lang="scss">
@import '../../styles/theme.scss';

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
    padding: 10px 35px;
    &::placeholder {
        color: $dark-lighter-cyan;
        font-family: $font-700;
        font-weight: bold;
    }
}
</style>
