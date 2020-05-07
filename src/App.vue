<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header> 
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div>
            <div class="info">
                Info: Click on a Quote to delete it.
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';

    export default {
       data: function () {
           return{
               quotes:[
                   'Just a quote!'
               ],
               maxQuotes :10
           };
       },
       methods:{
           newQuote(quote){
               if(this.quotes.length >= this.maxQuotes){
                   return alert('Limit Reached! Please delete a quote first.');
               }

                if(!quote.replace(/\s/g, '').length){
                   return alert('Quote cannont be blank.');
                }

               this.quotes.push(quote);
           },
           deleteQuote(i){
               this.quotes.splice(i, 1);
           }
       },
       components:{
           appQuoteGrid: QuoteGrid,
           appNewQuote: NewQuote,
           appHeader: Header,
       }
    }
</script>

<style>
    .container{
        width: 90vw;
        margin: 20px auto;
        padding: 20px;
    }

    .info{
        background-color: rgb(16, 172, 211);
        color: #fff;
        padding:5px;
        margin: 50px auto;
        text-align: center;
    }
</style>
