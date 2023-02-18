<template>
  <div>
    <button @click="decrement" :disabled="count <= min">-</button>
    <span>{{ count }}</span>
    <button @click="increment" :disabled="count >= max">+</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'Counter',
  props: {
    initialCount: {
      type: Number,
      default: 0,
    },
    min: {
      type: Number,
      default: 0,
    },
    max: {
      type: Number,
      default: Infinity,
    },
  },
  setup(props) {
    const count = ref(props.initialCount);

    function increment() {
      if (count.value < props.max) {
        count.value++;
      }
    }

    function decrement() {
      if (count.value > props.min) {
        count.value--;
      }
    }

    return {
      count,
      increment,
      decrement,
    };
  },
};
</script>
