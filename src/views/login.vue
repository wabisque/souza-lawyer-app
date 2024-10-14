<script setup>
import ButtonComponent from '@/components/button.vue';
import LinkComponent from '@/components/link.vue';
import TextFieldComponent from '@/components/text-field.vue';

defineOptions({name: 'login-view'});
</script>

<template>
  <div class="login-view">
    <form
      class="login-view__card"
      @submit.prevent
    >
      <div class="login-view__card__logo"></div>

      <div class="login-view__card__greeting">
        <div class="login-view__card__greeting__hello">Hello,</div>
        <div class="login-view__card__greeting__welcome">Welcome!</div>
      </div>

      <div class="login-view__card__form">
        <text-field-component class="login-view__card__form__field">
          <template #label>
            Email*
          </template>
        </text-field-component>

        <text-field-component class="login-view__card__form__field">
          <template #label>
            Password*
          </template>
        </text-field-component>
      </div>

      <div class="login-view__card__actions">
        <button-component class="login-view__card__actions__submit">Login</button-component>

        <link-component class="login-view__card__actions__forget">Forgot password?</link-component>
      </div>
    </form>
  </div>
</template>

<style>
.login-view {
  align-items: center;
  display: flex;
  justify-content: center;
  padding: clamp(1.5rem, 6dvw, 2.5rem);
}

.login-view__card {
  background-color: rgb(var(--color-foreground));
  border-radius: 1.125rem;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  max-width: 27.5rem;
  padding: 4rem 2.5rem;
  width: 100%;
}

.login-view__card__logo {
  background-color: rgb(var(--color-background));
  border-radius: 100vmax;
  height: 5rem;
  width: 5rem;
}

.login-view__card__greeting {
  color: rgb(var(--color-primary));
  line-height: 1;
}

.login-view__card__greeting__hello {
  font-size: 3.5rem;
  font-weight: 300;
}

.login-view__card__greeting__welcome {
  font-size: 3rem;
  font-weight: bold;
}

.login-view__card__form {
  display: flex;
  flex-direction: column;
}

.login-view__card__actions {
  align-items: center;
  display: flex;
  justify-content: space-between;
}
</style>
