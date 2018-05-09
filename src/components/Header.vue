<template>
    <div class="row text-center">
        <h2><strong>Quotes Added</strong></h2>
        <div class="progress mb-3">
            <div class="progress-bar" :style="{ width: (quotesNumber * 10) + '%' }">
                {{quotesNumber}} / {{maxQuotes}}
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: ["quotes", "maxQuotes"],
  computed: {
      quotesNumber() {
          return this.quotes.length;
      }
  }
};
</script>

<style>

</style>
