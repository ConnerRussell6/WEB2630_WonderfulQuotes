<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label>Quote</label>
        <!--ToDo: Within the textarea use v-model that is set to quote-->
        <textarea
          class="form-control"
          rows="3"
          v-model="quote"
        ></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <!--ToDo: Add a click event with .prevent modifier and set it equal to the createNew method created below-->
        <button @click.prevent="createNew()" class="btn btn-primary">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      // ToDo: Create a data object called quote that is se to an empty string
      quote: '',
      maxQuotes: 10
    };
  },
  methods: {
    // ToDo: Create a method createNew that emits a custom event named quoteAdded that passes the quote data object above
    // Set quote to an empty string
    createNew() {
      if (this.quote != '') {
        this.$emit('quoteAdded', this.quote)
      }
    }
  }
}
</script>
