<template>
  <div></div>
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
  components: {
    CheckboxInput,
    DateInput,
    MultiselectInput,
    RadioInput,
    RangeInput,
    TextInput
  },
  computed: {
    mainSettings() {
      return inputs;
    },
    postCodeMapping() {
      return inputs.postCodeMapping;
    },
    mainServices() {
      return inputs.services.map(item => item.heading);
    }
  },
  data() {
    return {};
  },
  methods: {}
};
</script>

<style scoped>
</style>
