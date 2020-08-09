<template>
  <div class="m-auto p-3 row text-center">
    <div class="col-12 text-center">
      <label class="">{{ settings.title }}</label>
      <multiselect
        v-model="local_value"
        :options="settings.options"
        :multiple="settings.multiple"
        :close-on-select="settings.closeOnSelect ? settings.closeOnSelect : false"
        :clear-on-select="false"
        :preserve-search="true"
        :placeholder="settings.label"
        label="label"
        track-by="value"
        :preselect-first="false"
      />
    </div>
    <div v-if="showButton" class="p-3 col-12" :class="settings.buttonPosition ? settings.buttonPosition : 'text-right'">
      <button
        type="button"
        class="btn btn-success btn-lg"
        v-if="settings.hasButton"
        @click="$emit('clicked')"
      >{{ settings.buttonText }}</button>
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
  },
  computed: {
    showButton() {
      return this.settings.hasButton && Array.isArray(this.local_value) ? this.local_value.length > 0 : this.local_value !== null;
    }
  }
};
</script>

<style src="vue-multiselect/dist/vue-multiselect.min.css"></style>
