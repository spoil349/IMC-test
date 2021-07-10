<template>
      <Table/>
      <FormData/>
</template>

<script>
import Table from "@/components/Table";
import FormData from "@/components/FormData";

export default {
  name: 'App',
  components: {
    Table,
    FormData
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  justify-content: center;
  flex-flow: row wrap;
}
</style>
