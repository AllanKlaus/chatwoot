<template>
  <button type="submit" :disabled="disabled" :class="computedClass">
    <i v-if="!!iconClass" :class="iconClass" class="icon"></i>
    <span>{{ buttonText }}</span>
    <spinner v-if="loading" />
  </button>
</template>

<script>
import Spinner from '../Spinner';

export default {
  components: {
    Spinner,
  },
  props: {
    disabled: {
      type: Boolean,
      default: false,
    },
    loading: {
      type: Boolean,
      default: false,
    },
    buttonText: {
      type: String,
      default: '',
    },
    buttonClass: {
      type: String,
      default: '',
    },
    iconClass: {
      type: String,
      default: '',
    },
  },
  computed: {
    computedClass() {
      return `button nice ${this.buttonClass || ' '}`;
    },
  },
};
</script>
