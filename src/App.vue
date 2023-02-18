<template>
  <div class="app">
    <h1>My App</h1>
    <Counter :initialCount="10" :max="20" :min="0" />
  </div>
</template>

<script>
import Counter from './components/Counter.vue';

export default {
  components: {
    Counter,
  },
};
</script>

<style>
.app {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}
</style>
