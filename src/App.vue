<template>
    <div class="container">
        <app-header :maxQuotes="maxQuotes" :quoteCount="quotes.length"></app-header>
        <app-new-quote @newQuoteAdded="addNewQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @appDeleteQuote="deleteQuote"></app-quote-grid>
        <div class="row">
          <div class="col-sm-12 text-center">
            <div class="alert alert-info">Info: Click on the quote to delete.</div>
          </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuotesGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import Header from './components/Header.vue';
    
    export default {
        data: function(){
            return{
                maxQuotes:10,
                quotes:['This is just a simple qoute to at least see something']
            }
        },
        components:{
            appQuoteGrid:QuoteGrid,
            appNewQuote:NewQuote,
            appHeader:Header
        },
        methods:{
          addNewQuote(quote){
            if(this.quotes.length >= this.maxQuotes){
              return alert('Kindly delete old quotes to add new one!')
            }
              this.quotes.push(quote);
          },
          deleteQuote(index){
            this.quotes.splice(index, 1);
          }
        }
        
    }
</script>

<style>

</style>
