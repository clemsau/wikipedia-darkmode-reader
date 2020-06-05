<template>
  <div>
    <header class="flex justify-between p-1">
      <nuxt-link to="/" class="items-center text-gray-800 dark:text-white underline">Wikipedia dark mode reader</nuxt-link>
      <div class="inline-block relative w-64">
        <select v-model="$colorMode.preference" class="block items-center appearance-none w-full border border-gray-400 hover:border-gray-500 px-2 py-1 pr-4 rounded shadow leading-tight focus:outline-none focus:shadow-outline dark:bg-gray-800 dark:border-gray-600">
          <option value="light">Light</option>
          <option value="dark" selected="selected" style="dark:text-blue-200">Dark</option>
        </select>
        <div class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700">
          <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z"/></svg>
        </div>
      </div>
      <script async defer data-domain="wikipediadarkmodereader.clementsauvage.com" src="https://plausible.io/js/plausible.js"></script>
    </header>
    <nuxt />
  </div>
</template>
