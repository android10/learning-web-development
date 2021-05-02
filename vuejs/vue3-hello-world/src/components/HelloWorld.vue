<template>
  <div>
    <h2>Filter 'LearnVue' Articles</h2>
    <input
      v-model="query" 
      type="text" 
      placeholder="Filter Search" 
    >
    <br>
    <button @click="reset">
      Reset
    </button>
    <search-results :query="query" />
  </div>  
</template>

<script>
import { ref } from 'vue'
import SearchResults from './SearchResults.vue'

export default {
  components: {
    SearchResults
  },

  setup() {
    const query = ref('')

    const reset = () => {
      query.value = ''
    }

    return {
      reset,
      query
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  input[type='text'] {
    margin-bottom: 20px;
    padding: 10px;
  }
</style>
