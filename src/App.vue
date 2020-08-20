<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
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
import header from "./components/header";

export default {
  components: { QuotesGrid, NewQuote, appHeader: header },
  data: function () {
    return {
      quotes: ["Just a quote to see something"],
      maxQuotes: 10,
    };
  },
  methods: {
    NewQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete quotes first");
      }
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
