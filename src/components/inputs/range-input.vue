<template>
  <div class="quantity">
    <div class="input-group">
      <input type="button" value="-" class="button-minus" variant="success" @click="decrement()" />
      <input type="number" min="0.00" :value="local_value" max="5.00" class="quantity-field" />
      <input type="button" value="+" class="button-plus" variant="success" @click="increment()" />
    </div>
  </div>
</template>
<script>
export default {
  props: {
    value: {
      type: Number,
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
  methods: {
    increment() {
      if (this.local_value <= 4) {
        this.local_value += 1;
      }
    },
    decrement() {
      if (this.local_value !== 0) {
        this.local_value -= 1;
      }
    },
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
input,
textarea {
  border: 1px solid #eeeeee;
  box-sizing: border-box;
  margin: 0;
  outline: none;
  padding: 10px;
}

input[type="button"] {
  -webkit-appearance: button;
  cursor: pointer;
}

input[type="button"]:before {
  content: "\e00b";
}

input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
}

.input-group {
  clear: both;
  margin: 15px 0;
  position: relative;
}

.input-group input[type="button"] {
  transition: all 300ms ease;
  border-radius: 100px;
  font-size: 32px;
  padding: 3px;
  line-height: 0;
  width: 31px;
  height: 31px;
  background: none;
  color: #4ded90;
  border: 1px solid #4ded90;
}

.input-group .button-minus,
.input-group .button-plus {
  font-weight: bold;
  height: 38px;
  padding: 0;
  width: 38px;
  position: relative;
}

.input-group .quantity-field {
  position: relative;
  height: 38px;
  left: -6px;
  text-align: center;
  width: 62px;
  display: inline-block;
  font-size: 13px;
  margin: 0 0 5px;
  resize: vertical;
  border: 0px;
  background: none;
}

.button-plus {
  left: -13px;
}

input[type="number"] {
  -moz-appearance: textfield;
  -webkit-appearance: none;
  font-size: 26px !important;
  font-weight: bold;
}
</style>
