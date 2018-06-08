<template>
    <VuexDropdown 
      v-on:onSelectOption="handleChangedropdown($event)" 
      v-bind:options="options"
      v-bind:selected="selected"/>
</template>

<script>
import VuexDropdown from "vuex-dropdown";

export default {
  name: "App",
  data: function() {
    return {
      options: [
          {
            label: "H1",
            value: "h1"
          },
          {
            label: "H2",
            value: "h2"
          }
        ],
        selected: {
          label: "H1",
          value: "h1"
        }
    };
  },
  components: {
    VuexDropdown
  },
  methods:{
    handleChangedropdown:function(e){
      this.selected = e;
    }
  }
};
</script>

<style>
</style>
