<template>
  <h2 class="text-center title-underline">
    <slot />
  </h2>
</template>

<script>
export default {
  props: {}
}
</script>

<style scoped lang="postcss">
.title-underline {
  @apply relative mb-8 text-blue-800;
}
.title-underline:before {
  content: '';
  bottom: -15px;
  width: 60px;
  height: 5px;
  left: 50%;
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
  background-color: theme('colors.blue.800');
  border-radius: 2px;
  @apply absolute inline-block;
}
</style>
