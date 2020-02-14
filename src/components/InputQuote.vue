<template>
    <div id="input_quote">
        <div id="input_quote--container">
            <div id="input_quote--form">
                <textarea type="text" v-model="quoteItem" rows="5" placeholder="Hello World :)"></textarea>
            </div>
            <div id="input_quote--button">
                <button @click="addItem" class="input_quote--button__add">Add Quote</button>
                <button @click="quoteItem = ''" class="input_quote--button__reset">Reset</button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            quoteItem: ""
        };
    },
    methods: {
        addItem() {
            if (this.quoteItem != "") {
                this.$emit("addQuote", this.quoteItem);
                this.quoteItem = "";
            } else {
                alert("Please input your quote");
            }
        },
        resetForm() {
            this.quoteItem = "";
        }
    }
};
</script>

<style>
</style>