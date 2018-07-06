<template>
  <div id="container">
      <app-new-quote v-on:quoteAdded="addNewQuote"></app-new-quote>
      <app-quote-grid :quotess="quotes" :maxQuotes="maxQuotes" @quoteDeleted="deleteTheQuote"></app-quote-grid>
      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert alert-info">Info: Click on a Quote to delete it</div>
        </div>
      </div>
  </div>
</template>


<script>
  import NewQuote from './components/NewQuote';
  import QuoteGrid from './components/QuoteGrid.vue';
  export default {
    data: function() {
      return {
        quotes: ['Just a quote to see something'],
        maxQuotes: 10
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote
    },
    methods: {
      addNewQuote(quote) {
          this.quotes.push(quote)
      },
      deleteTheQuote(index) {
         this.quotes.splice(index,1);
      }
    }

  }


</script>

<style>

</style>
