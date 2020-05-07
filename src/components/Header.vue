<template>
    <div>
        <div class="progress-bar">
            <div class="progress"
                :style="{width:( quoteCount / maxQuotes ) * 100 + '%'}"
            >
            </div>
            <div class="count">
                {{ quoteCount }} / {{ maxQuotes }}
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['quoteCount','maxQuotes']
}
</script>

<style scoped>
    .progress-bar{
        border: 1px solid #ccc;
        text-align: center;
        margin: 1rem;
        border-radius: 10px;
        height: 1rem;
    }
    .progress{
        background-color: rgb(18, 173, 39);
        border-radius: 10px;
        height: 100%;
    }
    .count{
        position: relative;
        top: -100%;
    }
</style>