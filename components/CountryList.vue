<template>
  <div class="country-layout">
    <country-card
      v-for="country in countryList"
      :key="country.name"
      :country="country"
    ></country-card>
  </div>
</template>

<script>
import CountryCard from './CountryCard'

export default {
  name: 'CountryList',
  components: {
    CountryCard,
  },

  // eslint-disable-next-line vue/require-prop-types
  props: ['searchValue', 'region'],

  data() {
    return {
      countryList: [],
    }
  },
  mounted() {
    this.getAll()
  },

  // watch: {
  //   searchValue: function () {
  //     this.getCountries(this.searchValue)
  //   },
  // },

  methods: {
    getAll() {
      // eslint-disable-next-line no-undef
      axios
        .get('https://restcountries.eu/rest/v2/all')
        .then((response) => {
          this.countryList = response.data
        })
        .catch((error) => {
          // handle error
          console.log(error)
        })
    },

    getCountries() {
      // eslint-disable-next-line no-undef
      axios
        .get('https://restcountries.eu/rest/v2/name/' + this.searchValue)
        .then((response) => {
          this.countryList = []
          response.data.forEach((e) => {
            if (e.region === this.region || this.region === 'All') {
              this.countryList.push(e)
            }
          })
          // this.countryList = response.data;
        })
        .catch((_error) => {
          this.countryList = []
        })
    },
  },
}
</script>
