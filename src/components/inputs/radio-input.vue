<template>
    <div class="p-3 text-left">
      <h2 class="text-left" v-if="settings.title.length > 0">{{ settings.title }}</h2>
      <p class="text-left" v-if="settings.subTitle.length > 0">{{ settings.subTitle }}</p>
      <div class="custom-control custom-radio">
        <label>Domestic</label>
        <input class="rado ml-3" type="radio" id="one" value="Domestic" v-model="picked">
      </div>
      <hr>
      <div class="custom-control custom-radio">
        <label>Comercial</label>
        <input class="ml-3" type="radio" id="two" value="Comercial" v-model="picked">
      </div>
      <span>Picked: {{ picked }}</span>
    </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      required: true,
    },
    settings: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      picked: this.value,
    };
  },
  watch: {
    picked(val) {
      if (val !== this.value) {
        this.$emit('input', val);
      }
    },
  },
};
</script>

<style>
label{
  font-size: 2em;
}

input[type=checkbox], input[type=radio] {
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
    transition: opacity .3s ease-in-out 50ms;
}
</style>
