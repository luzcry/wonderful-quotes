<template>
  <div class="container">
    <NewQuote @quoteAdded="NewQuote"></NewQuote>
    <QuotesGrid :quotes="quotes" @quoteDeleted="deleteQuote"></QuotesGrid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid";
import NewQuote from "./components/NewQuote";
export default {
  components: { QuotesGrid, NewQuote },
  data: function () {
    return {
      quotes: ["Just a quote to see something"],
      maxQuotes: 10,
    };
  },
  methods: {
    NewQuote(quote) {
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    },
  },
};
</script>

<style>
</style>
