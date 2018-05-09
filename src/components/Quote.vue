<template>
    <span class="quote mr-3">{{quote}}</span>
</template>

<script>
export default {
    name: 'quote',
    props: ['quote'],
}
</script>

<style scoped>
    span {
        cursor: pointer;
    }
</style>
