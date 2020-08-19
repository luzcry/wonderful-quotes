<template>
  <div class="row">
    <app-quote v-for="quote in quotes" :key="quote">{{ quote }}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote";
export default {
  name: "QuotesGrid",
  props: ["quotes"],
  components: {
    appQuote: Quote,
  },
};
</script>

<style>
</style>