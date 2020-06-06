<template>
  <div class="m-4">
      <h2 class="text-4xl">{{ title }}</h2>
      <p class="text-l m-12">{{ extract }}</p>
  </div>
</template>

<script>
export default {
    name: 'Article',
    props: ['title', 'extract']
}
</script>

<style>

</style>