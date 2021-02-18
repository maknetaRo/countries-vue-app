<template>
  <div>
    <h1>Countries List</h1>
    <table style="width: 100%">
      <tr>
        <th>name</th>
        <th>capital city</th>
        <th>flag</th>
        <th>population</th>
        <th>timezone</th>
        <th>languages</th>
        <th>currencies</th>
      </tr>

      <CountryRow
        v-for="country in countries"
        :key="country.name"
        :name="country.name"
        :capital="country.capital"
        :flag="country.flag"
        :population="country.population"
        :timezone="country.timezones[0]"
        :language="country.languages[0].name"
        :currency="country.currencies[0].code"
      />
    </table>
  </div>
</template>

<script>
import axios from "axios";
import CountryRow from "./CountryRow.vue";

export default {
  name: "all-countries-list",
  data() {
    return {
      countries: [],
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = await axios.get(
        "https://restcountries.eu/rest/v2/all",
        config
      );
      this.countries = res.data;
      console.log(res.data);
    } catch (error) {
      console.log(error);
    }
  },
  components: {
    CountryRow,
  },
};
</script>

<style scoped>
tr {
  padding: 1.5rem;
}
th,
td {
  padding: 0.25rem;
}
th {
  background: lime;
}
tr:nth-of-type(2n) {
  background: lightgoldenrodyellow;
}
</style>