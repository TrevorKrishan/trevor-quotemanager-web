<template>
    <div>
        <app-quote v-for="(quote, i) in quotes" :key="i" @click.native="deleteQuote(i)">{{ quote }}</app-quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';

    export default {
        props: ['quotes'],
        methods:{
            deleteQuote(i){
                this.$emit('quoteDeleted',i);
            }
        },
        components: {
            appQuote: Quote,
        }
    }
</script>

<style scoped>
    
</style>  