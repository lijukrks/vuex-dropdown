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
## Usage
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

## Usage

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



## Example - Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## License

MIT © Liju Kuriakose
