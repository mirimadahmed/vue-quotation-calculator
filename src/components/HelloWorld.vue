<template>
<div class="container">
  <div class="row">
    <div class="col-md-8">
          <div class="hello">
    <h1>Checkbox input {{ radioInput }}</h1>
    <CheckboxInput
      v-model="checkboxInput"
      :settings="inputDef.services[0].subServices[0].questions[1]"
    />
    <h1>Text input {{ textInput }}</h1>
    <TextInput
      v-model="textInput"
      :settings="inputDef.services[0].subServices[0].questions[0]"
      @clicked="btnClicked"
    />
    <h1>Date input {{ dateInput }}</h1>
    <DateInput v-model="dateInput" :settings="inputDef.services[0].subServices[0].questions[2]" />
    <h1>Radio input {{ radioInput }}</h1>
    <RadioInput v-model="radioInput" :settings="inputDef.services[0].subServices[0].questions[3]" />
    <h1>Range input {{ rangeInput }} </h1>
    <RangeInput v-model="rangeInput" :settings="inputDef.services[0].subServices[0].questions[4]" />
    <h1>Multiselect input {{ multiSelectInput }} </h1>
    <MultiselectInput v-model="multiSelectInput" :settings="inputDef.services[0].subServices[0].questions[5]" />
  </div>
    </div>
    <div class="col-md-4">
      <div class="p-3" style="border: 1px solid gray; border-radius:10px;">
          <h1>Text input {{ textInput }}</h1>
           <h1>Date input {{ dateInput }}</h1>
            <h1>Radio input {{ radioInput }}</h1>
            <h1>Radio input {{ radioInput }}</h1>
             <h1>Range input {{ rangeInput }} </h1>
            <h1>Multiselect input {{ multiSelectInput }} </h1>
      </div>
    </div>

  </div>
</div>
</template>

<script>
import inputs from "@/data/setup.json";
import CheckboxInput from "@/components/inputs/checkbox-input.vue";
import DateInput from "@/components/inputs/date-input.vue";
import MultiselectInput from "@/components/inputs/multiselect-input.vue";
import RadioInput from "@/components/inputs/radio-input.vue";
import RangeInput from "@/components/inputs/range-input.vue";
import TextInput from "@/components/inputs/text-input.vue";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    CheckboxInput,
    DateInput,
    MultiselectInput,
    RadioInput,
    RangeInput,
    TextInput
  },
  computed: {
    inputDef() {
      return inputs;
    }
  },
  data() {
    return {
      textInput: "",
      radioInput: "",
      rangeInput: 0,
      checkboxInput: [],
      multiSelectInput: [],
      dateInput: ""
    };
  },
  methods: {
    btnClicked() {
      alert("btn clicked from text input");
    }
  }
};
</script>

<style scoped>
</style>
