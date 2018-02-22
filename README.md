vue-menu
=============

Simple response menu

## Installation

### npm

``` sh
npm install --save vue-menu
```
### yarn

``` sh
yarn add vue-menu
```

## Usage

```HTML
<body>
  <header>    
    <site-menu>
      <optional-sub-components></optional-sub-components>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Information</a></li>
        <li><a href="#">Contact</a></li>      
      </ul>
    </site-menu>
  </header>
</template>
```

```javascript
<script>
import siteMenu from 'vue-menu'

export default {
  name: 'app',
  data () {
    return {
    }
  },
  components: {
    siteMenu
  },
  methods: {
  }
}
</script>
```

## TODOs

- default colors or variables import