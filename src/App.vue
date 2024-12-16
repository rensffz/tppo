<template>
  <div class="app">
    <div class="championship-container">
      <h1>Championship</h1>
      <div class="tabs">
        <button class="tab active">Положение</button>
        <button class="tab">Статистика</button>
      </div>
      <div class="table-container">
        <table class="championship-table">
          <thead>
            <tr>
              <th>Имя пользователя</th>
              <th>Штраф</th>
              <th>A</th>
              <th>B</th>
              <th>C</th>
              <th>D</th>
              <th>E</th>
              <th>Итого</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(user, index) in users" :key="index">
              <td>{{ user.name }}</td>
              <td>{{ user.penalty }}</td>
              <td :class="getCellClass(user.scores.A)">{{ user.scores.A }}</td>
              <td :class="getCellClass(user.scores.B)">{{ user.scores.B }}</td>
              <td :class="getCellClass(user.scores.C)">{{ user.scores.C }}</td>
              <td :class="getCellClass(user.scores.D)">{{ user.scores.D }}</td>
              <td :class="getCellClass(user.scores.E)">{{ user.scores.E }}</td>
              <td>{{ user.total }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [
        {
          name: "user",
          penalty: 1234,
          scores: { A: "+11", B: "-5", C: "+7", D: "+2", E: "+1" },
          total: 4,
        },
        {
          name: "student",
          penalty: 5666,
          scores: { A: "-11", B: "-1", C: "+8", D: "-4", E: "+3" },
          total: 2,
        },
        {
          name: "user1111",
          penalty: 4,
          scores: { A: "+5", B: "-10", C: "+7", D: "-5", E: "+5" },
          total: 3,
        },
        {
          name: "meoooe",
          penalty: 567,
          scores: { A: "+1", B: "+4", C: "+15", D: "+6", E: "+10" },
          total: 5,
        },
        {
          name: "userrresu",
          penalty: 445,
          scores: { A: "-1", B: "+12", C: "+4", D: "+6", E: "+12" },
          total: 4,
        },
        {
          name: "user123",
          penalty: 67777,
          scores: { A: "-6", B: "-3", C: "+5", D: "-13", E: "+15" },
          total: 2,
        },
        {
          name: "user111111111111111",
          penalty: 64,
          scores: { A: "+2", B: "+4", C: "-4", D: "+12", E: "+9" },
          total: 4,
        },
        {
          name: "user1234",
          penalty: 1,
          scores: { A: "+5", B: "+11", C: "-12", D: "-1", E: "-16" },
          total: 2,
        },
      ],
    };
  },
  methods: {
    getCellClass(score) {
      return score.startsWith("+") ? "positive" : score.startsWith("-") ? "negative" : "";
    },
  },
};
</script>

<style scoped>
.app {
  height: 100vh;
  font-family: Arial, sans-serif;
  background-color: #2c2c2c;
  color: #fff;
  text-align: center;
}

.championship-container {
  max-width: 800px;
  margin: 0 auto;
}

.tabs {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

.tab {
  background-color: #444;
  border: none;
  color: #fff;
  padding: 10px 20px;
  cursor: pointer;
  margin: 0 5px;
}

.tab.active {
  background-color: #666;
}

.table-container {
  overflow-x: auto;
}

.championship-table {
  width: 100%;
  border-collapse: collapse;
}

.championship-table th,
.championship-table td {
  border: 1px solid #444;
  padding: 10px;
  text-align: center;
}

.championship-table th {
  background-color: #333;
}

.positive {
  color: red;
}

.negative {
  color: lightblue;
}
</style>
