<template>
  <div class="container">
    <NewQuote @quoteAdded="NewQuote"></NewQuote>
    <QuotesGrid :quotes="quotes"></QuotesGrid>
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
  },
};
</script>

<style>
</style>
