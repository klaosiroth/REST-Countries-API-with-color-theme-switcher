<template>
  <div>
    <ul>
      <li
        v-for="color of colors"
        :key="color"
        @click="$colorMode.preference = color"
      >
        {{ color }}
      </li>
    </ul>
  </div>
</template>

<script>
// Doc: https://nuxtjs.org/tutorials/going-dark-with-nuxtjs-color-mode/
export default {
  data() {
    return {
      colors: ['system', 'light', 'dark', 'sepia'],
    }
  },
}
</script>
