<template>
  <div class="container">
    <!--ToDo: Use the Header component selector-->
    <!--Bind data props quoteCount and set it equal to the quote length-->
    <!--Bind data props maxQuotes and set it equal to the maxQuotes created below-->
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>

    <!--ToDo: Use the NewQuote component selector-->
    <!--Call @quoteAdded that is emitted from the NewQuote Component and pass the newQuote method created below-->
    <new-quote @quoteAdded="newQuote"></new-quote>

    <!--ToDo: Use the QuoteGrid component selector-->
    <!--Bind data props quotes and set it equal to the quotes array created below-->
    <!--Call @quoteDeleted that is emitted from the QuoteGrid Component and pass the deleteQuote method created below-->
    <quote-grid :quotes="quotes" @quotesDeleted="deleteQuote"></quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
//  Todo: Import QuoteGrid, NewQuote, and Header Components
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

export default {
  data () {
    return {
      // ToDo: Create an array called quotes
      // Have at least one string by default
      quotes: [
        'default'
      ],
      // ToDo: Create maxQuotes that is set to 10
      maxQuotes: 10,
    }
  },
  methods: {
    // ToDo: Create a method called newQuote that takes the parameter quote.
    // This method will check if the quotes length is greater than or equal to the maxQuotes
    // If it is return an alert telling the user to delete a quote
    // Outside of conditional, push quote (method parameter) to the quotes array
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes){
        alert('Please delete a quote before generating another.')
      } else {
        this.quotes.push(quote)
      }
      
    },
    // ToDo: Create a method called deleteQuote that takes in a parameter of index
    // This method will splice the quotes array by (index, 1)
    deleteQuote(index) {
      this.quotes.splice(index, 1)
    }
  },
  components: {
    // ToDo: Initiate the QuoteGrid, NewQuote, and Header Components with Custom Selectors
    'quote-grid': QuoteGrid,
    'new-quote': NewQuote,
    'app-header': Header
  }

}
</script>

<style></style>
