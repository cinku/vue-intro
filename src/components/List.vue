<template>
    <div class="row list-container">
        <app-quote v-for="(quote, index) in quotes" v-bind:key="quote" v-bind:quote="quote" @click.native="deleteQuote(index)"></app-quote>
        <p v-if="quotes.length === 0">Add some new quotes ;)</p>
    </div>
</template>

<script>
import Quote from './Quote.vue';

export default {
    name: 'quoteList',
    props: {
        'quotes': {
            required: true
        }
    },
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(index) {
            this.$emit('deleteQuote', index);
        }
    }
}
</script>

<style>

</style>
