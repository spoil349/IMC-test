<template>
  <div class="component">
    <p class="component__name">
      {{element.ns}}
    </p>
    <input
      v-if="this.type == 1"
      v-bind:style="'width: ' + elementWidth + 'px;'"
      v-bind:type="elementType()"
      v-bind:value="user[element.rv]"
    >
    <input
      v-if="this.type == 3"
      v-bind:type="elementType()"
      v-model="checkedFunc"
    >
    <select
      v-if="this.type == 2"
      v-bind:style="'width: ' + elementWidth + 'px;'"
      v-model="selectedFunc"
    >
      <option
        v-for="v in element.sl"
        :key="v.id"
      >{{v.name}}</option>
    </select>
  </div>
</template>
<script>
export default {
  name: "OptionalFormElement",
  props: ["element", "type", "width", "user", "rv", "foreigner", "sex"],
  computed: {
    elementWidth: function () {
      return this.width;
    },
    checkedFunc: {
      get(){
        if (this.foreigner == true) {
          return true
        } else {
          return false
        }
      }
    },
    selectedFunc: {
      get() {
        if (this.sex == "1") {
          return 'муж'
        } else {
          return 'жен'
        }
      }
    }
  },
  methods: {
    elementType: function() {
      if (this.type == 1) {
        return 'text'
      } else if (this.type == 3) {
        return 'checkbox'
      }
    },
  }
};
</script>
<style>
  .component {
    display: flex;
    margin-bottom: 10px;
  }
  .component:not(:last-child) {
    margin-bottom: 10px;
  }
  .component__name {
    margin: 0 20px 0 0;
  }
</style>