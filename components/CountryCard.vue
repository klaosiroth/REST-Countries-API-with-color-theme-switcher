<template>
  <div class="country-card">
    <!-- Generally not a good idea to pass this much thru router.
    But instead of importing a state manager, this was smoother.-->
    <router-link
      :to="{
        name: 'CountryInfo',
        params: {
          name: country.name,
          nativeName: country.nativeName,
          population: country.population,
          region: country.region,
          subregion: country.subregion,
          capital: country.capital,
          topLevelDomain: country.topLevelDomain,
          currencies: country.currencies,
          languages: country.languages,
          borders: country.borders,
          flag: country.flag,
        },
      }"
    >
      <div class="country-flag-container">
        <img class="country-flag" :src="country.flag" />
      </div>
      <div class="country-info">
        <h4 class="country-name">{{ country.name }}</h4>
        <ul>
          <li>
            <b>Population:</b>
            {{ country.population }}
          </li>
          <li>
            <b>Region:</b>
            {{ country.region }}
          </li>
          <li>
            <b>Capital:</b>
            {{ country.capital }}
          </li>
        </ul>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  props: {
    country: {
      type: String,
      required: true,

      validator: (value) => {
        return ['syncing', 'synced', 'version-conflict', 'error'].includes(
          value
        )
      },
    },
  },
}
</script>
