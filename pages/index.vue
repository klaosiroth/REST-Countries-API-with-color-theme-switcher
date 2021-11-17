<template>
  <main
    class="max-w-2xl px-4 py-6 mx-auto sm:py-12 sm:px-6 lg:max-w-7xl lg:px-8"
  >
    <div class="mb-10">
      <input type="text" class="" placeholder="Search for a country..." />
    </div>
    <div class="mb-8">
      <select id="country" name="country" class="">
        <option value="name">name</option>
        <option value="name">name</option>
        <option value="name">name</option>
        <option value="name">name</option>
        <option value="name">name</option>
      </select>
    </div>

    <h2 class="sr-only">List of countries</h2>

    <div
      class="grid grid-cols-1 gap-10  sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 xl:gap-16"
    >
      <a
        v-for="product in products"
        :key="product.id"
        :href="product.href"
        class="group"
      >
        <div
          class="w-full overflow-hidden bg-gray-200 rounded-lg  aspect-w-1 aspect-h-1 xl:aspect-w-7 xl:aspect-h-8"
        >
          <img
            :src="product.imageSrc"
            :alt="product.imageAlt"
            class="object-cover object-center w-full h-full  group-hover:opacity-75"
          />
        </div>
        <h3 class="mt-4 text-sm text-gray-700">
          {{ product.name }}
        </h3>
        <p class="mt-1 text-lg font-medium text-gray-900">
          {{ product.price }}
        </p>
      </a>
    </div>

    <ColorModePicker />

    <!-- <div v-for="(country, index) in countries" :key="index" class="mb-10 card">
      {{ country.name }}
    </div> -->

    <!-- <h1>Home page</h1>
    <NuxtLink to="/about">
      About (internal link that belongs to the Nuxt App)
    </NuxtLink>
    <a href="https://nuxtjs.org">External Link to another page</a> -->
  </main>
</template>

<script>
import ColorModePicker from '../components/ColorModePicker'

const products = [
  {
    id: 1,
    name: 'Earthen Bottle',
    href: '#',
    price: '$48',
    imageSrc:
      'https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-01.jpg',
    imageAlt:
      'Tall slender porcelain bottle with natural clay textured body and cork stopper.',
  },
  {
    id: 2,
    name: 'Nomad Tumbler',
    href: '#',
    price: '$35',
    imageSrc:
      'https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-02.jpg',
    imageAlt:
      'Olive drab green insulated bottle with flared screw lid and flat top.',
  },
  {
    id: 3,
    name: 'Focus Paper Refill',
    href: '#',
    price: '$89',
    imageSrc:
      'https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-03.jpg',
    imageAlt:
      'Person using a pen to cross a task off a productivity paper card.',
  },
  {
    id: 4,
    name: 'Machined Mechanical Pencil',
    href: '#',
    price: '$35',
    imageSrc:
      'https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-04.jpg',
    imageAlt:
      'Hand holding black machined steel mechanical pencil with brass tip and top.',
  },
  {
    id: 5,
    name: 'Machined Mechanical Pencil',
    href: '#',
    price: '$35',
    imageSrc:
      'https://tailwindui.com/img/ecommerce-images/category-page-04-image-card-05.jpg',
    imageAlt:
      'Hand holding black machined steel mechanical pencil with brass tip and top.',
  },
  // More products...
]

export default {
  components: {
    ColorModePicker,
  },

  data() {
    return {
      products,
      isOpen: false,
    }
  },

  methods: {
    toggle() {
      this.isOpen = !this.isOpen
    },
  },
}
// export default {
//   // async asyncData({ $axios }) {
//   //   const countries = await $axios.$get('https://restcountries.com/v2/all')
//   //   return { countries }
//   // },
//   // data() {
//   //   return {
//   //     title: 'List of countries',
//   //     countries: [],
//   //     country: {},
//   //     show_country: false,
//   //   }
//   // },
//   // methods: {
//   //   fetchCountries() {
//   //     const baseUrl = 'https://restcountries.com/v2/all'
//   //     // eslint-disable-next-line no-undef
//   //     axios.get(baseUrl).then((res) => {
//   //       this.countries = res.data
//   //     })
//   //   },
//   // },
// }
</script>

<style>
:root {
  --color: #243746;
  --color-primary: #158876;
  --color-secondary: #0e2233;
  --bg: #f3f5f4;
  --bg-secondary: #fff;
  --border-color: #ddd;
}

.dark-mode {
  --color: #ebf4f1;
  --color-primary: #41b38a;
  --color-secondary: #fdf9f3;
  --bg: #091a28;
  --bg-secondary: #071521;
  --border-color: #0d2538;
}
.sepia-mode {
  --color: #433422;
  --color-secondary: #504231;
  --bg: #f1e7d0;
  --bg-secondary: #eae0c9;
  --border-color: #ded0bf;
}

body {
  background-color: var(--bg);
  color: var(--color);
  transition: background-color 0.3s;
}

a {
  color: var(--color-primary);
}
</style>
