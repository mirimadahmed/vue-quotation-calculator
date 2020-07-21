<template>
  <div class="p-3 text-left row">
    <div v-for="option in settings.options" :key="option.value" class="form-check form-check-inline col-12 p-3">
      <input
        class="form-check-input"
        type="checkbox"
        :id="option.value"
        :value="option.value"
        v-model="local_value"
      />
      <label class="form-check-label ml-3">{{ option.label }}</label>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    value: {
      type: Array,
      required: true
    },
    settings: {
      type: Object,
      required: true
    }
  },
  data() {
    return {
      local_value: this.value
    };
  },
  watch: {
    local_value(val) {
      if (val !== this.value) {
        this.$emit("input", val);
      }
    }
  }
};
</script>

<style>
</style>
