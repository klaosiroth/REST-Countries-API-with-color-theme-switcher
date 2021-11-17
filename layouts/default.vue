<template>
  <div>
    <TheHeader />
    <Nuxt keep-alive :keep-alive-props="{ max: 10 }" />
    <TheFooter />
  </div>
</template>

<script>
export default {
  head: {
    title: 'Nuxt.js with TailwindCSS',
    meta: [
      { charset: 'utf-8' },
      { name: 'viewport', content: 'width=device-width, initial-scale=1' },
      {
        hid: 'description',
        name: 'description',
        content: 'Nuxt.js with TailwindCSS',
      },
    ],
  },
}
</script>
