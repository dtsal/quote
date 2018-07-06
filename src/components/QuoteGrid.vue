<template>
   <div class="row">
         <app-quote v-for="(quote,index) in quotess" @click.native="deleteQuote(index)">{{quote}}{{maxQuotes}}</app-quote>
   </div>
</template>

<script>
    import Quote from './Quote.vue';
    export default {
      props: ['quotess','maxQuotes'],
      components: {
         appQuote: Quote
      },
      methods: {
        deleteQuote(index) {
          this.$emit('quoteDeleted',index)
        }
      }
    }
</script>

<style scoped>

</style>
