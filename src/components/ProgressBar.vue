<template>
    <div id="progress_bar">
        <div id="progress_bar--container">
            <div id="progress_bar--length" :style="{width:length * 10 + '%'}">
                <div v-if="length != 0">{{ length }} / {{ maxQuotes }}</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ["length", "maxQuotes"]
};
</script>

<style>
</style>