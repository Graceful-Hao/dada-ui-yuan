<template>
  <div class="topnav">
    <router-link to="/" class="logo">
      <svg class="icon">
        <use xlink:href="#icon-huluobu"></use>
      </svg>
      DaDa
    </router-link>
    <ul class="menu">
      <li>
        <router-link to="/doc">介绍</router-link>
      </li>
    </ul>
    <span class="toggleAside" @click="toggleMenu">
      <svg class="icon">
        <use xlink:href="#icon-menu1"></use>
      </svg>
    </span>
  </div>
</template>
<script lang="ts">
import { inject, Ref } from "vue";
export default {
  setup() {
    const menuVisible = inject<Ref<boolean>>("menuVisible"); // get
    const toggleMenu = () => {
      menuVisible!.value = !menuVisible!.value;
    };
    return { toggleMenu };
  },
};
</script>
<style lang="scss" scoped>
.topnav {
  display: flex;
  padding: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  justify-content: center;
  align-items: center;
  border-bottom: 1px solid rgba(60, 60, 60, .12);
  color: #38482a;
  background: white;


  >.logo {
    max-width: 6em;
    margin-right: auto;

    >svg {
      width: 32px;
      height: 32px;
    }
  }

  >.menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;

    >li {
      margin: 0 1em;
    }
  }

  >.toggleAside {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 24px;
    height: 22px;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: none;

    .iconfont {
      position: relative;
      top: 1px;
      font-size: 24px;
    }
  }

  @media (max-width: 500px) {
    >.menu {
      display: none;
    }

    >.logo {
      margin: 0 auto;
    }

    >.toggleAside {
      display: inline-block;
    }
  }
}
</style>