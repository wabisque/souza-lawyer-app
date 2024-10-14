<script setup>
defineOptions({name: 'link-component'});
</script>

<template>
  <a href="javascript:void(0);" class="link-component">
    <slot></slot>
  </a>
</template>

<style>
.link-component {
  color: rgb(var(--color-primary));
  font-weight: 500;
  outline: 0px solid rgba(var(--color-primary), 0);
  outline-offset: 0.5rem;
  transition-property: outline-color, outline-offset, outline-width;
}

.link-component:focus-visible {
  outline-color: rgb(var(--color-primary));
  outline-offset: 0px;
  outline-width: calc(var(--px) * 2);
}
</style>
