# Vue Loaders CSS

> Vue wrapper for [Loaders.css](https://connoratherton.com/loaders), the delightful and performance-focused pure css loading animations

## Demo

The live demo is available here: [Vue Loaders CSS Demo](http://vue-loaders-css.surge.sh/).

## Installation

### With Yarn

```bash
yarn add vue-loaders-css loaders.css
```

### With CDN

```html
<!-- In <body>, after Vue import -->
<script src="https://unpkg.com/vue-loaders-css/dist/vue-loaders-css.min.js"></script>
```

## Usage

### With an ES6 bundler (via npm)

In your index file

```js
import VueLoadersCss from 'vue-loaders-css'
Vue.use(VueLoadersCss)
```

### With CDN

```html
<script>
    Vue.use(VueLoadersCss)

    new Vue({
        // ...
    })
</script>
```

---

### Available props

| Option     | Type    | Description   |
| ------------- |-------------| -----|
| type | String | The loaders.css animation class name|

## License

The MIT License (MIT)
