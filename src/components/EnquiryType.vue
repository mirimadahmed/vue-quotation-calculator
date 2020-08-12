<template>
  <!-- <TextInput v-model="local_value"  :settings="zipCodeSettings" @clicked="validateZipCode" /> -->
  <!-- <RadioInput v-model="radioInput" @clicked="validateType"/> -->
  <div class="row">
      <div v-if="currentStep === 1">
            
      </div>
      <div v-if="currentStep === 2"></div>
      <div v-if="currentStep === 3"></div>
      <div class="col-md-12 row">
          <button v-if="currentStep > 1" @click="currentStep--">Back</button>
          <button v-if="currentStep < steps" @click="currentStep++">Next</button>
      </div>
  </div>
</template>

<script>
import RadioInput from "@/components/inputs/radio-input.vue";
export default {
    components: {
        RadioInput
    },
    props: {
        zipCodeSettings: {
            type: Object,
            required: true
        },
        zipCodeMapping: {
            type: Object,
            required: true
        }
    },
    data() {
        return {
            local_value: '',
            steps: 5,
            currentStep: 1
        };
    },
    methods: {
        validateZipCode() {
            const zipCode = this.local_value;
            if(this.zipCodeMapping.hasOwnProperty(zipCode)) {
                this.$emit('zip-selected', {
                    zipCode,
                    price: this.zipCodeMapping[zipCode]
                })
            } else {
                this.$emit('zip-not-supported')
            }
        }
    }
}
</script>

<style>

</style>