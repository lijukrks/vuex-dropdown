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
          label: "Heck",
          value: "heck"
        },
        {
          label: "Jane",
          value: "jane"
        }
      ],
      selected: {
        label: "Heck",
        value: "heck"
      }
    };
  },
  components: {
    VuexDropdown
  },
  methods: {
    handleChangedropdown: function(e) {
      this.selected = e;
    }
  }
};
</script>

<style>
</style>
