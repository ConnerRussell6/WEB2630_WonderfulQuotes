<template>
  <div class="row">
    <!--ToDo: Use the Quote component selector-->
    <!--Loop through quotes using v-for and get quote and index-->
    <!--Add a click event with .native modifier and set it equal to the deleteQuote method created below and pass index-->
    <!--Display the quote inside the appQuote component, in other words pass the data object to the slot in Quote.vue-->
    <app-quote v-for="(quote, index) in quotes" :key="index" @click.native="deleteQuote(index)">
      <p>{{quote}}</p>
    </app-quote>
  </div>
</template>

<script>
// ToDo: import the Quote Component
import Quote from './Quote.vue';

export default {
  // ToDo: Create props of quote
  props: ['quotes'],
  components: {
    // ToDo: Initiate the Quote Component with a Custom Selector
    'app-quote': Quote,
  },
  methods: {
    // ToDo: Create a method deleteQuote that takes a paremeter of index
    // $emit a custom event listener named quotesDeleted and pass index in the second parameter
    deleteQuote(index) {
      this.$emit('quotesDeleted', index)
    }
  }
}
</script>
