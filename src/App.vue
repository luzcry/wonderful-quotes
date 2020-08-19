<template>
  <div class="container">
    <QuotesGrid :quotes="quotes"></QuotesGrid>
  </div>
</template>

<script>
import QuotesGrid from "./components/QuotesGrid";
export default {
  components: { QuotesGrid },
  data: function () {
    return {
      quotes: ["Just a quote to see something"],
      maxQuotes: 10,
    };
  },
};
</script>

<style>
</style>
