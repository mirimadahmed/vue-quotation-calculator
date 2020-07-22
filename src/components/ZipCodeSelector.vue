<template>
  <TextInput v-model="local_value"  :settings="zipCodeSettings" @clicked="validateZipCode" />
</template>

<script>
import TextInput from "@/components/inputs/text-input.vue";
export default {
    components: {
        TextInput
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
            local_value: ''
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