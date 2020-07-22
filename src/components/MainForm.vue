<template>
  <div>
    <ZipCodeSelector :zipCodeSettings="zipCodeSettings" :zipCodeMapping="zipCodeMapping" @zip-selected="zipCodeSelected" @zip-not-supported="zipNotSupported" />
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
import ZipCodeSelector from "@/components/ZipCodeSelector.vue";

export default {
  components: {
    CheckboxInput,
    DateInput,
    MultiselectInput,
    RadioInput,
    RangeInput,
    TextInput,
    ZipCodeSelector
  },
  computed: {
    mainSettings() {
      return inputs;
    },
    zipCodeMapping() {
      return inputs.postCodeMapping;
    },
    mainServices() {
      return inputs.services.map(item => item.heading);
    },
    zipCodeSettings() {
      return inputs.zipCodeSettings
    }
  },
  data() {
    return {};
  },
  methods: {
    zipCodeSelected(zip) {
      alert(zip);
    },
    zipNotSupported() {
      alert('Zip not supported show error here')
    }
  }
};
</script>

<style scoped>
</style>
