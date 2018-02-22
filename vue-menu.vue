<template>
  <div>
    <div
      class="o-grid__col menu-wrapper u-block@md u-block@lg u-block@xl"
      :class="getClass"
    >
      <slot />
      <a
        class="btn-close u-hidden@md u-block@xs u-block@sm"
        @click="toggleMenu()"
      ><i class="fa fa-close"/></a>
    </div>
    <div class="o-grid__col u-hidden@md u-block@xs u-block@sm">
      <a
        href="#"
        class="menu-trigger"
        @click="toggleMenu()"
      >
        menu <i class="fa fa-bars"/>
      </a>
    </div>
  </div>
</template>
<script>

export default {
  props: {
  },
  data(){
    return {
      open: false
    }
  },
  computed: {
    getClass(){
      if (this.open === true) {
        return 'menu-wrapper menu-wrapper--open'
      } else {
        return 'menu-wrapper'
      }
    }
  },
  methods: {
    toggleMenu(){
      if (this.open) {
        document.body.classList.remove('no-scroll')
        this.open = false
      } else {
        document.body.classList.add('no-scroll')
        this.open = true
      }
    }
  }
}
</script>
<style lang="scss">
.menu-wrapper {
  display: none;
  .menu {
     list-style-type: none;
     margin: 0 15px 0 0;
     li {
       display: inline-block;
       a {
         display: inline-block;
         text-decoration: none;
         padding: 0 20px;
         line-height: 22px;

       }
       &:last-child a {
         border-right: 0 none;
       }
     }
   }
}

@media screen and (max-width: 800px) {
  .menu-wrapper {
    position: fixed;
    z-index: 100;
    top: 0;
    left: calc( -100% - 85px );
    width: 100vw;
    height: 100vh;
    display: block;
    padding: 65px 20px 20px 20px;
    transition: left 500ms ease;
    &--open {
      left: 0;
    }
    .search-box {
      position: relative;
    }
    .menu {
      margin: 20px 0 0 0;
      li {
        display: block;
        text-align: left;
        a {
          border: 0 none;
        }
      }
    }
  }
}

.menu-trigger:link,
.menu-trigger:hover,
.menu-trigger:active,
.menu-trigger:visited {
  height: 30px;
  line-height: 30px;
  text-transform: uppercase;
  text-decoration: none;
  i {
    margin-left: 10px;
  }
}
.btn-close {
  position: absolute;
  top: 65px;
  right: 10px;
  width: 40px;
  height: 40px;
  text-align: center;
  i:before{
    font-size: 28px;
  }
}
</style>
