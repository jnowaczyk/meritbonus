<script setup lang="ts">
import { computed, onMounted, type PropType } from 'vue'
import { ButtonType } from './enums'

const props = defineProps({
  text: {
    type: String,
    default: 'Default',
    required: false
    // validator(val) {
    //   return val !== ''
    // } // Provides a default value if not supplied
  },
  buttonType: {
    type: String as PropType<ButtonType>,
    required: false,
    default: ButtonType.Secondary
  }
})

const buttonClass = computed(() => {
  switch (props.buttonType) {
    case ButtonType.Primary:
      return 'btn-primary'
    case ButtonType.Secondary:
      return 'btn-secondary'
    case ButtonType.Yes:
      return 'btn-yes'
    case ButtonType.No:
      return 'btn-no'
    default:
      return 'btn-secondary'
  }
})
</script>
<template>
  {{ props.buttonType }}
  <button :class="buttonClass"><slot /></button>
</template>

<style scoped>
.btn-primary {
  background-color: rgb(10, 103, 241);
}

.btn-secondary {
  background-color: rgb(87, 92, 100);
}

.btn-yes {
  background-color: rgb(91, 239, 250);
}

.btn-no {
  background-color: rgb(247, 29, 47);
}
</style>
