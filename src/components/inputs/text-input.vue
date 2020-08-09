<template>
  <div class="m-auto p-3">
    <h2 class="text-left" v-if="settings.title.length > 0">{{ settings.title }}</h2>
    <p class="text-left" v-if="settings.subTitle.length > 0">{{ settings.subTitle }}</p>
    <div class="form-group input-group-lg" id="holder">
      <small id="label" for="input" v-if="settings.label.length > 0">{{ settings.label }}</small>
      <input type="text" id="input" class="form-control" v-model="local_value" />
    </div>
    <div :class="settings.buttonPosition ? settings.buttonPosition : 'text-right'">
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
#holder {
  height: 50px;
}
#label {
  margin-bottom: -50px;
  padding-left: 35px;
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
.btn-green {
  color: #002e11;
  background-color: #75f1a6;
  border-color: #4ded91;
}
</style>
