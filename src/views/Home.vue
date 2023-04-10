<template>
  <div>
    <Topnav />
    <div class="banner">
      <div class="dada">
        <svg class="icon">
          <use xlink:href="#icon-dada"></use>
        </svg>
      </div>
      <h1>DaDa UI</h1>
      <h2>一个面向学习者的 UI 框架</h2>
      <p class="actions">
        <a href="https://github.com">GitHub</a>
        <router-link to="/doc/intro">开始</router-link>
      </p>
    </div>
  </div>
</template>
<script lang="ts">
import Topnav from "../components/Topnav.vue";
export default {
  components: { Topnav },
};
</script>
<style lang="scss" scoped>
.banner {
  color: #38482a;
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  >h1 {
    font-weight: bold;
    margin-bottom: 16px;
  }

  >.dada {
    >svg {
      margin-top: 16px;
      width: 200px;
      height: 200px;
      fill: #38482a;
    }
  }

  >.actions {
    padding: 32px 0;

    a {
      margin: 0 8px;
      background: #e5641e;
      color: white;
      display: inline-block;
      line-height: 32px;
      border-radius: 4px;
      padding: 4px 24px;
    }
  }
}
</style>