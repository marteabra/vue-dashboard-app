<template>
  <div class="table-container">
    <div class="table">
      <button class="current-sort" @click="toggleSortOrder">
        Sort: {{ sort.key }}
      </button>
      <table class="table__content">
        <thead>
          <tr class="table__buttons">
            <td><button @click="sortBy('firstname')">First Name</button></td>
            <td><button @click="sortBy('lastname')">Last Name</button></td>
            <td><button @click="sortBy('age')">Age</button></td>
            <td><button @click="sortBy('city')">City</button></td>
          </tr>
        </thead>

        <tbody>
          <tr v-for="row in alphabeticalSort">
            <td v-for="value in row">{{ value }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
const tableData = `[{ "firstname": "Marte", "lastname": "Abrahamsen", "age": 24, "city": "Trondheim" }, { "firstname": "Ellie", "lastname": "Abrha", "age": 23, "city": "Oslo" }, { "firstname": "Kristine", "lastname": "Strømme", "age": 24, "city": "Oslo" }, { "firstname": "Ole", "lastname": "Hansen", "age": 45, "city": "Bergen" }, { "firstname": "Karen", "lastname": "Lund", "age": 16, "city": "Stavanger" }, { "firstname": "Marie", "lastname": "Nilsen", "age": 11, "city": "Moss" }, { "firstname": "Ola", "lastname": "Nordmann", "age": 52, "city": "Oslo" }, { "firstname": "Kari", "lastname": "Nordmann", "age": 51, "city": "Oslo" }, { "firstname": "Ane", "lastname": "Åker", "age": 34, "city": "Telemark" }]`;

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
    alphabeticalSort() {
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

      return this.content.sort((a, b) => compareFunction(a, b) * orderValue);
    },

    naturalSort() {
      const key = this.sort.key;
      const orderValue = this.sort.order === "asc" ? 1 : -1;

      function compareFunction(a, b) {
        a = a[key].toString();
        b = b[key].toString();

        return a.localCompare(b, undefined, { numeric: true });
      }

      return this.content.sort((a, b) => compareFunction(a, b) * orderValue);
    },
  },

  methods: {
    sortBy(key) {
      this.sort.key = key;
      this.$router.push({
        query: { ...this.$route.query, sort: this.sort.key },
      });
    },

    toggleSortOrder() {
      this.sort.key = this.sort.order === "asc" ? "desc" : "asc";
      this.$router.push({
        query: { ...this.$route.query, order: this.sort.order },
      });
    },
  },
};
</script>

<style>
.table-container {
  width: 30vw;
  height: 60vh;
  padding: 1em;
}

.current-sort {
  margin: 10px 0 0 10px;
  text-align: center;
  width: 100%;
  font-weight: bold;
  font-size: 1em;
}

.table {
  position: relative;
  background: white;
  border-collapse: collapse;
  height: 100%;
  width: 100%;
}

.table__content {
  margin-top: 10px;
  position: relative;
  display: flex;
  justify-content: space-evenly;
  width: 100%;
  text-align: center;
}

.table thead {
  font-weight: bold;
  background: grey;
  width: 100%;
}

.table__buttons {
  text-align: center;
  border: none;
  background: none;
}

.table button {
  border: none;
  background: none;
  font-size: 0.8em;
}

.table tr {
  border: 1px solid black;
}

.table tbody {
  margin-top: 15px;
  font-size: 0.8em;
}

.table td {
  padding: 0.5em;
}
</style>