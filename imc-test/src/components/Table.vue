<template>
    <table class="table">
      <tr class="table__row">
        <th class="table__row-header">Идентификатор</th>
        <th class="table__row-header">Иностранец</th>
        <th class="table__row-header">Имя</th>
        <th class="table__row-header">Пол</th>
      </tr>
      <tr class="table__row" v-for="user in users" :key="user.id">
        <td class="table__row-cell">{{user.id}}</td>
        <td class="table__row-cell">{{user._foreigner}}</td>
        <td class="table__row-cell">{{user._name}}</td>
        <td class="table__row-cell">{{user._sex}}</td>
      </tr>
    </table>
</template>
<script>
export default {
  name: "Table",
  data() {
    return {
      users: []
    }
  },
  async mounted() {
    const res = await fetch(
      'http://localhost:3000/table'
    );
    const users = await res.json();
    this.users = users;
  }

};
</script>
<style>
  .table {
    font-size: 14px;
    border-collapse: collapse;
  }
  .table__row-header {
    background-color: #afcde7;
    color: #fff;
    padding: 10px 20px;
    border: 1px solid white
  }
  .table__row-cell {
      background-color: #d8e6f3;
      border: 1px solid white
  }
</style>