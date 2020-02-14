<template>
    <div id="output_quote">
        <div v-if="quotes.length != 0">
            <h1>Your Quotes</h1>
            <p>
                <i>Click quote to delete</i>
            </p>
        </div>

        <div id="output_quote--list">
            <single-quote
                v-for="(quote,i ) in quotes"
                :key="quote + i"
                @click.native="removeQuote(quote, i)"
                title="Click to delete"
            >{{ quote }}</single-quote>
        </div>
    </div>
</template>

<script>
import SingleQuote from "./Quote.vue";

export default {
    props: ["quotes"],
    components: {
        "single-quote": SingleQuote
    },
    methods: {
        removeQuote(quote, i) {
            let dataQuote = {
                quote: quote,
                index: i
            };
            this.$emit("removeQuote", dataQuote);
        }
    }
};
</script>

<style>
</style>