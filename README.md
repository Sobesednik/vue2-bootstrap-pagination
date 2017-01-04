# vue-bootstrap-paginator
A Vue.js 2 component for simple pagination with Bootstrap layout.

```bash
npm i --save vue-bootstrap-paginator
```

### Narrow template

![narrow template](http://i.giphy.com/l4Jz78JMWi1As3fuo.gif)

### Full template

![full template](http://i.giphy.com/26gJz1XhjIBAjQeHe.gif)

## Usage

The component has the following properties:

- _page_: current page
- _pages_: total number of pages
- _width_: maximum number of pages after which compact mode will be used
- _pageFn_: a function to generate href attribute for a page, e.g.,

```js
function pageFunction(page) {
    return `./${page}`
}
```

The component will emit `change` event with new page number when a user changes the page.

You can require the component in `Vue` components:

```vue
<template>
    <div class="parent-component">
        <pagination :page="1" :pages="15" :width="20" @change="onPageChange"></pagination>
    </div>
</template>
<script>
    const Pagination = require('vue-bootstrap-pagination')
    module.exports = {
        data: () => ({ ... }),
        props: [ ... ],
        components: { Pagination },
        methods: {
            onPageChange: function (page) {
                console.log('New page: %s', page)
            },
        },
    }
</script>
```

Or you can register `pagination` as a global component:

```js
const Vue = require('vue')
const Pagination = require('vue-bootstrap-pagination')
Vue.component('pagination', Pagination)
```

## Generated HTML for full template

```html
<ul class="pagination">
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./4" aria-label="Previous">«</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./1">1</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./2">2</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./3">3</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./4">4</a>
    </li>
    <li data-v-7e3a6e65="" class="active">
        <a data-v-7e3a6e65="" href="./5">5</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./6">6</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./7">7</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./6" aria-label="Next">»</a>
    </li>
</ul>
```

## Generated HTML for narrow template

```html
<ul class="pagination">
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./4" aria-label="Previous">«</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./1">1</a>
    </li>
    <li data-v-7e3a6e65="" class="hellip disabled">
        <span data-v-7e3a6e65="">…</span>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./4">4</a>
    </li>
    <li data-v-7e3a6e65="" class="active">
        <a data-v-7e3a6e65="" href="./5">5</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./6">6</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./7">7</a>
    </li>
    <li data-v-7e3a6e65="" class="">
        <a data-v-7e3a6e65="" href="./6" aria-label="Next">»</a>
    </li>
</ul>
```

## Testing

Tested with Karma, PhantomJS, Jasmine & Jasmine-Jquery

```
npm t
```
