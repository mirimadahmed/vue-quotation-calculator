/* eslint-disable max-len */
<template>
  <div class="p-3">
    <div>
      <label class="typo__label">{{ settings.title }}</label>
      <multiselect
        v-model="local_value"
        :options="settings.options"
        :multiple="true"
        :close-on-select="false"
        :clear-on-select="false"
        :preserve-search="true"
        :placeholder="settings.label"
        label="label"
        track-by="value"
        :preselect-first="false"
      />
    </div>
  </div>
</template>

<script>
import Multiselect from "vue-multiselect";

export default {
  components: {
    Multiselect
  },
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

<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
