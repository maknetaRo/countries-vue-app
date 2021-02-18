<template>
  <div>
    <tr>
      <td>{{ name }}</td>
      <td>{{ capital }}</td>
      <td><img :src="flag" style="max-width: 5rem" /></td>
      <td>{{ population }}</td>
      <td>{{ timezone }}</td>
      <td>{{ language }}</td>
      <td>{{ currency }}</td>
    </tr>
  </div>
</template>

<script>
export default {
  name: "CountryRow",
  props: [
    "name",
    "capital",
    "flag",
    "population",
    "timezone",
    "language",
    "currency",
  ],
};
</script>

<style>
</style>