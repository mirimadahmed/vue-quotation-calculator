<template>
  <div class="p-3 text-left row">
    <h2 class="text-left col-12" v-if="settings.title.length > 0">{{ settings.title }}</h2>
    <p class="text-left col-12" v-if="settings.subTitle.length > 0">{{ settings.subTitle }}</p>
    <input class="col-12 form-control" type="date" id="input" v-model="local_value" />
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
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
