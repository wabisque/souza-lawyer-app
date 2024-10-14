<script setup>
defineOptions({name: 'text-field-component'});
</script>

<template>
  <div class="text-field-component">
    <div class="text-field-component__label">
      <slot name="label"></slot>
    </div>

    <input type="text" class="text-field-component__field">

    <div class="text-field-component__error">
      <slot name="error"></slot>
    </div>
  </div>
</template>

<style>
.text-field-component {
  display: inline-grid;
  grid-template-columns: [error-start field-start label-start] 1fr [error-end field-end label-end];
  grid-template-rows: [label-start] auto [label-end field-start] auto [field-end error-start] 1fr [error-end];
}

.text-field-component__label {
  color: rgb(var(--color-heading));
  font-size: 0.875rem;
  font-weight: 500;
  grid-area: label;
}

.text-field-component__label:empty {
  display: none;
}

.text-field-component__field {
  background-color: transparent;
  border: var(--px) solid rgb(var(--color-border));
  border-radius: 0.75rem;
  grid-area: field;
  outline: 0px solid rgba(var(--color-primary), 0);
  outline-offset: 0.5rem;
  padding: 0.5rem;
  transition-property: border-color, outline-color, outline-offset, outline-width;
}

.text-field-component__field:focus-visible {
  border-color: rgb(var(--color-primary));
  outline-color: rgb(var(--color-primary));
  outline-offset: 0px;
  outline-width: calc(var(--px) * 2);
}

.text-field-component__error {
  color: rgb(var(--color-danger));
  font-size: 0.75rem;
  font-weight: bold;
  grid-area: error;
}

.text-field-component__error:empty {
  display: none;
}
</style>
