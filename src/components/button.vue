<script setup>
defineOptions({name: 'button-component'});
</script>

<template>
  <button class="button-component">
    <slot>Button</slot>
  </button>
</template>

<style>
.button-component {
  background-color: rgb(var(--color-primary));
  border: var(--px) solid rgb(var(--color-primary));
  border-radius: 0.75rem;
  color: rgb(var(--color-primary-complement));
  outline: 0px solid rgba(var(--color-primary), 0);
  outline-offset: 0.5rem;
  padding: 0.5rem 1.25rem;
  transition-property: outline-color, outline-offset, outline-width;
}

.button-component:focus-visible {
  outline-color: rgb(var(--color-primary));
  outline-offset: 0px;
  outline-width: calc(var(--px) * 2);
}
</style>
