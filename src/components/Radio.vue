<template>
  <div class="radio-container">
    <label class="label">
      <input ref="radio" type="radio" :value="label" v-model="v" />
      <slot></slot>
    </label>
  </div>
</template>

<script>
export default {
  name: 'my-radio',
  props: {
    value: [String, Number],
    label: [String, Number, Boolean],
  },
  data() {
    return {};
  },
  computed: {
    v: {
      get() {
        return this.value;
      },
      set(val) {
        this.$emit("input", val);
      },
    },
  }
};
</script>

<style>
.label {
  cursor: pointer;
}
</style>