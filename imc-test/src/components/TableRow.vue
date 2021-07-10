<template>
      <tr class="table__row">
        <td class="table__row-cell">{{user.id}}</td>
        <td class="table__row-cell">{{user._foreigner}}</td>
        <td class="table__row-cell">{{user._name}}</td>
        <td class="table__row-cell">{{user._sex}}</td>
      </tr>
</template>
<script>
export default {
  name: "TableRow",
  props: ["user"]
};
</script>
<style>
  .table {
    font-size: 14px;
    border-collapse: collapse;
  }
  .table__row-cell {
      background-color: #d8e6f3;
      border: 1px solid white
  }
</style>