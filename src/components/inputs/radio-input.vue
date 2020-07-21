<template>
  <div class="p-3 text-left">
    <h2 class="text-left" v-if="settings.title.length > 0">{{ settings.title }}</h2>
    <p class="text-left" v-if="settings.subTitle.length > 0">{{ settings.subTitle }}</p>
    <div class="custom-control custom-radio" v-for="option in settings.options" :key="option.value">
      <label>{{ option.label }}</label>
      <input class="rado ml-3" type="radio" id="one" :value="option.value" v-model="local_value" />
    </div>
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
label {
  font-size: 2em;
}

input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
  height: 16px;
  width: 16px;
}

.rado:before {
  content: "";
  position: absolute;
  left: 2px;
  top: 2px;
  background-color: #00a8e3;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  opacity: 0;
  transition: opacity 0.3s ease-in-out 50ms;
}
</style>
