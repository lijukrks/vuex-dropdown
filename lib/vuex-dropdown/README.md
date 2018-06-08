# vuex-dropdown

> A vue.js dropdown component

## Installation of vuex-dropdown

```js
npm i --save vuex-dropdown
```

### Browser

Include the script file 

```html
<script type="text/javascript" src="node_modules/vuejs/dist/vue.min.js"></script>
<script type="text/javascript" src="node_modules/vue-dropdown/dist/vuex-dropdown.min.js"></script>
```

## Browser Usage

then install the component with `Vue.use(VuexDropdown);`

```html
<script type="text/javascript">
  Vue.use(VuexDropdown);
</script>
```

### Module

```js
import VuexDropdown from 'vuex-dropdown';
```

## Module Usage

Once installed, it can be used in a template as simply as:

```html
<VuexDropdown 
      v-on:onSelectOption="handleChange($event)" 
      v-bind:options="options"
      v-bind:selected="selected"/>
```

## Options

```js
[
  {
    label: "Heck",
    value: "heck"
  },
  {
    label: "Jane",
    value: "jane"
  }
]
```

## Selected

```js
{
  label: "Heck",
  value: "heck"
}
```