<template>
  <div class="p-3 text-left row">
    <h2 class="text-left col-12" v-if="settings.title.length > 0">{{ settings.title }}</h2>
    <p class="text-left col-12" v-if="settings.subTitle.length > 0">{{ settings.subTitle }}</p>
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
#holder {
  height: 50px;
}
#label {
  margin-bottom: -50px;
  padding-left: 15px;
  padding-top: 5px;
  position: absolute;
  color: #ccc;
  left: 10px;
  color: #4ded90;
}
#input {
  font-size: 15px;
  width: 100%;
  padding: 23px 25px 15px;
  border: 1px solid rgba(126, 115, 115, 0.55);
  margin-top: 0;
  height: 120%;
  border-color: #4ded90;
}
</style>
