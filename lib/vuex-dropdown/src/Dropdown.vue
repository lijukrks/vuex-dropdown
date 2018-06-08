<template>
   <div v-bind:class="getClassNames" v-click-outside="outsideClick">
        <div class="dropdown__header" v-bind:class= "{'is-active' : isOpened}" @click="toggleDropdown()">
            <span>{{selected.label}}</span>
            <i class="fa fa-angle-down" aria-hidden="true"></i>
            <i class="fa fa-angle-up" aria-hidden="true"></i>
        </div>
        
        <div class="dropdown__content">
            <ul>
                <li v-for="(option,index) in options" v-bind:key="index" v-on:click="hadleClick(option)">{{option.label}}</li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
  props: ["options", "selected", "classNames"],
  data: function() {
    return {
      isOpened: false
    };
  },
  methods: {
    hadleClick(option) {
      this.isOpened = !this.isOpened;
      this.$emit("onSelect", option);
    },
    toggleDropdown() {
      this.isOpened = !this.isOpened;
    },
    outsideClick() {
      this.isOpened = false;
    }
  },
  computed: {
    getClassNames: function() {
      let classObj = {
        dropdown: true
      };
      if (this.classNames) {
        this.classNames.map(name => {
          classObj[name] = true;
        });
      }
      return classObj;
    }
  },
  directives: {
    "click-outside": {
      bind: function(el, binding, vNode) {
        // Define Handler and cache it on the element
        const bubble = binding.modifiers.bubble;
        const handler = e => {
          if (bubble || (!el.contains(e.target) && el !== e.target)) {
            binding.value(e);
          }
        };
        el.__vueClickOutside__ = handler;

        // add Event Listeners
        document.addEventListener("click", handler);
      },

      unbind: function(el, binding) {
        // Remove Event Listeners
        document.removeEventListener("click", el.__vueClickOutside__);
        el.__vueClickOutside__ = null;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dropdown {
  width: 25%;
}
.dropdown__header {
  background-color: #fff;
  border: solid 1px #cdcdcd;
  height: 30px;
  line-height: 30px;
  padding: 0px 8px;
  position: relative;
  -webkit-border-radius: 4px;
  border-radius: 4px;
}

.dropdown__header {
  padding-right: 40px;
  cursor: pointer;
}

.dropdown__header i.fa {
  position: absolute;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
  transition: opacity 0.3s ease-in-out;
  font-size: 22px;
}

.dropdown__header i.fa.fa-angle-up {
  opacity: 0;
}

.dropdown__header.is-active i.fa.fa-angle-up {
  opacity: 1;
}

.dropdown__header.is-active i.fa.fa-angle-down {
  opacity: 0;
}

.dropdown {
  display: block;
  margin: 0;
  position: relative;
  min-width: 160px;
}

.dropdown__header.is-active + .dropdown__content {
  height: auto;
  opacity: 1;
  visibility: visible;
}

.dropdown .dropdown__content {
  position: absolute;
  width: 100%;
  display: block;
  height: 0;
  opacity: 0;
  overflow: hidden;
  padding: 0;
  transition: all 0.3s ease-in-out;
  visibility: hidden;
  z-index: 999;
  background-color: #fff;
  border: solid 1px #f2f2f2;
  -webkit-border-radius: 4px;
  border-radius: 4px;
  -webkit-box-shadow: 0 3px 8px rgba(0, 0, 0, 0.3);
  -moz-box-shadow: 0 3px 8px rgba(0, 0, 0, 0.3);
  box-shadow: 0 3px 8px rgba(0, 0, 0, 0.3);
}

.dropdown .dropdown__content ul {
  display: block;
}

.dropdown .dropdown__content ul li {
  display: block;
  padding: 8px 10px;
  display: block;
  padding: 8px 10px;
  margin: 0;
  background-color: transparent;
  text-align: left;
  margin-top: 15px;
  cursor: pointer;
}
.dropdown .dropdown__content ul li:hover {
  background: whitesmoke;
}
</style>

