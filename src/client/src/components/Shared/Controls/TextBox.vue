<script setup lang="ts">
const props = defineProps({
  inputPlaceholder: {
    type: String,
    default: ''
  },
  caption: {
    type: String,
    default: ''
  },
  id: {
    type: String,
    default: ''
  },
  tabindex: {
    type: Number,
    required: false,
    default: -1
  },
  hint: {
    type: String,
    required: false,
    default: undefined
  }
})

const model = defineModel()
</script>

<template>
  <div class="form-group" :title="props.hint">
    <label v-if="props.caption" class="label-margin">{{ props.caption }}</label>
    <input
      :id="props.id"
      type="text"
      :placeholder="inputPlaceholder"
      v-model="model"
      :tabindex="tabindex"
    />
  </div>
</template>

<style scoped>
.form-group {
  padding: 0.5rem 0;
  width: 100%;
}

input {
  background-color: white;
  border: 1px solid rgb(85, 85, 85);
  border-radius: 4px;
  padding: 0.3rem 0.2rem;
  outline: none;
  transition:
    border-color 0.3s ease,
    background-color 0.3s ease,
    box-shadow 0.3s ease; /* Smooth transitions */
}

input[type='text']:focus {
  box-shadow: 0 0 8px rgba(85, 85, 85, 0.6);
  outline: none;
  background-color: rgb(240, 240, 240);
}

label {
  display: block;
  text-transform: uppercase;
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial,
    sans-serif;
  font-weight: 400;
  color: #5e5b5b;
  padding-left: 0.1rem;
  padding-bottom: 0rem;
  line-height: 1.2;
  font-size: 0.9rem;
}

/* label::after {
  content: ':';
} */
</style>
