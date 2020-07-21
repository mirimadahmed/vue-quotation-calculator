<template>
  <div class="p-3 text-left">
    <div class="form-check form-check-inline">
      <input
        class="form-check-input"
        type="checkbox"
        id="option1"
        value="option1"
        v-model="checkedNames"
      />
      <label class="form-check-label ml-3">Antiviral Sanitazion</label>
    </div>
    <br />
    <div class="form-check form-check-inline">
      <input
        class="form-check-input"
        type="checkbox"
        id="option2"
        value="option2"
        v-model="checkedNames"
      />
      <label class="form-check-label ml-3">Detergents</label>
    </div>
    <br />
    <div class="form-check form-check-inline">
      <input
        class="form-check-input"
        type="checkbox"
        id="option3"
        value="option3"
        v-model="checkedNames"
      />
      <label class="form-check-label ml-3">Detergents</label>
    </div>
  </div>
</template>
<script>
export default {};
</script>

<style>
</style>
