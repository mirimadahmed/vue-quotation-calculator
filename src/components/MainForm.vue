<template>
  <div class="row justify-content-md-center">
    <div class="col-md-6" v-if="selectedZip === null">
      <MultiselectInput
        v-if="!selectedService"
        :settings="servicesQuestion"
        v-model="selectedServiceItem"
        @clicked="serviceSelected"
      />
      <ZipCodeSelector
        v-else
        :zipCodeSettings="zipCodeSettings"
        :zipCodeMapping="zipCodeMapping"
        @zip-selected="zipCodeSelected"
        @zip-not-supported="zipNotSupported"
      />

    </div>
    <div v-else class="col-md-12">
        <div v-if="selectedServiceItem===''" class="col-md-12">
            
        </div>
        <div v-else-if="selectedServiceItem==='a'" class="col-md-12">
            
        </div>
        <div v-else-if="selectedServiceItem==='b'" class="col-md-12">
            
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
import ZipCodeSelector from "@/components/ZipCodeSelector.vue";
import EnquirySelector from "@/components/EnquirySelector.vue";

export default {
  components: {
    CheckboxInput,
    DateInput,
    MultiselectInput,
    RadioInput,
    RangeInput,
    TextInput,
    ZipCodeSelector,
    EnquirySelector
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
      return inputs.zipCodeSettings;
    },
    servicesQuestion() {
      return inputs.servicesQuestion;
    },
    selectedServiceSettings() {
      this.selectedService ? this.mainSettings.services.find(item => item.type === this.selectedServiceItem.value) : null
    }
  },
  data() {
    return {
      selectedServiceItem: null,
      selectedService: false,
      selectedZip: null,
      currentQuestion: 0
    };
  },
  methods: {
    zipCodeSelected(zip) {
      this.selectedZip = zip;
    },
    zipNotSupported() {
      alert("Zip not supported show error here");
    },
    serviceSelected() {
      this.selectedService = true;
    }
  }
};
</script>

<style scoped>
</style>
