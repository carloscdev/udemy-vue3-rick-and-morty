<template>
  <div class="search">
    <input
      type="text"
      placeholder="Search by name"
      v-model="name"
      @keyup="filter()"
    >
  </div>
</template>

<script>
import { ref } from 'vue'
import { useStore } from 'vuex'
export default {
  setup() {
    const name = ref('')
    const store = useStore()
    const filter = () => {
      store.dispatch('filterByName', name.value)
    }

    return {
      name,
      filter
    }
  }
}
</script>

<style lang="scss">
.search {
  width: 400px;
  margin: 3rem auto 0;
  input {
    height: 53px;
    width: 400px;
    border: none;
    border-radius: 10px;
    padding: 0 0.5rem;
  }
}
</style>