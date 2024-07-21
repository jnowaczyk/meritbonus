<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div>
    <header>
      {{ props.title }}
      <hr />
    </header>
    <main>
      <slot />
    </main>
  </div>
</template>

<style scoped>
div {
  background-color: var(--panel-background-color);
  border: 1px solid var(--border-color);
  border-radius: 15px;
  padding: 1rem 1rem;
}

header {
  font-size: 1.6rem;
  color: var(--header-title-color);
  /* border-bottom: 1px solid black; */
  line-height: 1;
}

.title {
  /* margin-bottom: 0.2rem; */
}

hr {
  display: block;
  height: 1px;
  border: 0;
  border-top: 1px solid var(--border-color);
  margin-top: 0.2rem;
  padding: 0;
}
</style>
