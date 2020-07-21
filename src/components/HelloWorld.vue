<template>
  <div class="hello">
    <h1>Checkbox input</h1>
    <CheckboxInput />
    <h1>Text input {{ textInput }} </h1>
    <TextInput v-model="textInput" :settings="inputDef.services[0].subServices[0].questions[0]" />
    <h1>Date input</h1>
    <DateInput  :settings="inputDef.services[0].subServices[0].questions[0]" />
    <h1>Radio input</h1>
    <RadioInput :settings="inputDef.services[0].subServices[0].questions[0]" />
    <h1>Range input</h1>
    <RangeInput />
    <h1>Multiselect input</h1>
    <MultiselectInput />
  </div>
</template>

<script>
import inputs from '@/data/setup.json';
import CheckboxInput from '@/components/inputs/checkbox-input.vue';
import DateInput from '@/components/inputs/date-input.vue';
import MultiselectInput from '@/components/inputs/multiselect-input.vue';
import RadioInput from '@/components/inputs/radio-input.vue';
import RangeInput from '@/components/inputs/range-input.vue';
import TextInput from '@/components/inputs/text-input.vue';

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  components: {
    CheckboxInput,
    DateInput,
    MultiselectInput,
    RadioInput,
    RangeInput,
    TextInput,
  },
  computed: {
    inputDef() {
      return inputs;
    },
  },
  data() {
    return {
      textInput: '',
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
