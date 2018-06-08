<template>
    <VuexDropdown 
      v-on:onSelect="handleChangedropdown($event)" 
      v-bind:options="options"
      v-bind:selected="selected"
      v-bind:classNames="['test']"/>
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
      debugger;
      this.selected = e;
    }
  }
};
</script>

<style>
</style>
