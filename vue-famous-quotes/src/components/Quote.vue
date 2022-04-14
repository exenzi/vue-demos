<template>
<Transition>
  <p v-if="quote">{{ quote }}</p>
</Transition>
</template>

<script>
export default {
  props: ['quote'],
}
</script>

<style lang="scss" scoped>
p {
  font-size: 2rem;
}
.v-enter {
  &-active {
    transition: opacity 2s ease;
  }

  &-from {
    opacity: 0;
  }
}
</style>