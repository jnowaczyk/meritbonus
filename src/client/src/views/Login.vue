<script setup lang="ts">
import { ref } from 'vue'
import TextBox from '@/components/Shared/Controls/TextBox.vue'
import Button from '@/components/Shared/Controls/Button.vue'
import { ButtonType } from '@/components/Shared/Controls/enums'
import Panel from '@/components/Shared/Controls/Panel.vue'

const myTextValue = ref('')
const capt = ref('thetest')
// onMounted lifecycle hook
</script>

<template>
  <div class="centered">
    <Panel title="Login">
      <TextBox
        inputPlaceholder="user name"
        caption="test"
        v-model="myTextValue"
        id="unique1"
        :tabindex="1"
      />
      <TextBox
        inputPlaceholder="password..."
        :caption="capt"
        v-model="myTextValue"
        id="userName"
        :tabindex="3"
        hint=""
      />
      <Button @click="" text="asdff" :buttonType="ButtonType.Primary">This is slot property</Button>
      <!-- <p>{{ myTextValue }}</p> -->
    </Panel>
  </div>
</template>
<style>
.centered {
  /* display: inline-block; */
  position: absolute;
  top: 50%;
  left: 50%;

  transform: TRANSLATE(-50%, -50%);
}
</style>
