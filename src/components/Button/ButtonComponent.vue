<template>
    <button type="button" :value="this.value">{{ this.title }}</button>
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
</style>
