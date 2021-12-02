<template>
  <button @click="toggleSortOrder">Sort: {{ sort.key }}</button>
  <table>
    <thead>
      <tr>
        <td><button @click="sortBy('firstname')">First Name</button></td>
        <td><button @click="sortBy('lastname')">Last Name</button></td>
        <td><button @click="sortBy('age')">Age</button></td>
        <td><button @click="sortBy('city')">Name</button></td>
      </tr>
    </thead>

    <tbody>
      <tr v-for="row in alphabeticalSort">
        <td v-for="value in row">{{ value }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
const tableData = `[{"firstname": "Marte", "lastname": "Abrahamsen", "age": 24, "city": "Trondheim"}, {"firstname": "Mayoo", "lastname": "??", "age": 30, "city": "Oslo"}, ]`;

export default {
  data() {
    return {
      sort: {
        key: "name",
        order: "asc",
      },
      content: JSON.parse(tableData),
    };
  },

  created() {
    const query = this.$route.query;

    if (query.sort) {
      this.sort.key = query.sort;
    }

    if (query.order) {
      this.sort.order = query.order;
    }
  },

  computed: {
    aplhabeticalSort() {
      const key = this.sort.key;
      const orderValue = this.sort.order === "asc" ? 1 : -1;

      function compareFunction(a, b) {
        if (a[key] > b[key]) {
          return 1;
        } else if (a[key] < b[key]) {
          return -1;
        } else {
          return 0;
        }
      }
    },
  },
};
</script>

<style>
table {
  width: 30vw;
  position: absolute;
}
</style>