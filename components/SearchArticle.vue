<template>
    <form @submit.prevent="onSubmit" class="m-2">
        <input type="text" v-model="text" placeholder="dog" class="py-2 px-4 border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <input type="submit" value="Search Article" class="rounded-full py-2 px-4 border border-gray-500 dark:bg-gray-800 dark:border-gray-600">
    </form>
</template>

<script>
export default {
    name: 'SearchArticle',
    data() {
        return {
            text: ''
        }
  },
  methods: { 
      onSubmit() {
          this.$emit("search-text", this.text);
          this.text = "";
      }
  }
}
</script>

<style>

</style>