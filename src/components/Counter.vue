<template>
  <button @click="increment">
    Count: {{ state.count }} Double {{ state.double }}
  </button>
</template>

<script>
import { reactive, computed } from 'vue';

export default {
  setup() {
    const state = reactive({
      count: 0,
      double: computed(() => state.count * 2),
    });
    function increment() {
      state.count++;
    }
    return { state, increment };
  },
};
</script>
