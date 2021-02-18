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
      <tr v-for="country in countries" :key="country.name">
        <td>{{ country.name }}</td>
        <td>{{ country.capital }}</td>
        <td>{{ country.flag }}</td>
        <td>{{ country.population }}</td>
        <td>{{ country.timezones[0] }}</td>
        <td>{{ country.languages[0].name }}</td>
        <td>{{ country.currencies[0].code }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "all-countries-list",
  data() {
    return {
      countries: [],
    };
  },
  created() {
    axios
      .get("https://restcountries.eu/rest/v2/all")
      .then((response) => {
        this.countries = response.data;
        console.log(response.data);
      })
      .catch((error) => console.log(error));
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