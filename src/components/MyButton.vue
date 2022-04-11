<template>
  <button @click="handleClick" class="btn btn-sm btn-success">
    {{ label }}
  </button>
</template>

<script>
export default {
  name: "MyButton",
  props: {
    label: String,
    isVisible: Boolean,
  },

  emits: ["toggleVisibility"],

  methods: {
    handleClick() {
      this.$emit("toggleVisibility");
    },
  },
};
</script>
