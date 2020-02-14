<template>
    <div id="app">
        <app-progress :length="length" :maxQuotes="maxQuotes"></app-progress>
        <app-input @addQuote="getQuote"></app-input>
        <app-credit></app-credit>
        <app-output :quotes="quotes" @removeQuote="removeQuote"></app-output>
    </div>
</template>

<script>
import ProgressBar from "./components/ProgressBar.vue";
import InputQuote from "./components/InputQuote.vue";
import OutputQuote from "./components/OutputQuote.vue";
import Credit from "./components/Credit.vue";

export default {
    data() {
        return {
            quotes: ["Hello World", "Lorem Impsum Dolor sir amet"],
            maxQuotes: 10
        };
    },
    computed: {
        length() {
            return this.quotes.length;
        }
    },
    components: {
        "app-progress": ProgressBar,
        "app-input": InputQuote,
        "app-output": OutputQuote,
        "app-credit": Credit
    },
    methods: {
        getQuote(quote) {
            // if (this.length < this.maxQuotes) this.quotes.push(quote);
            this.length < this.maxQuotes
                ? this.quotes.push(quote)
                : alert("Maximum of quotes :(");
        },
        removeQuote(quote) {
            this.quotes.splice(quote.index, 1);
        }
    }
};
</script>

<style>
</style>
