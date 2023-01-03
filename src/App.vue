<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-05 21:53:31
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2023-01-03 23:37:49
 * @FilePath: \web3\src\App.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <Header />

  <router-view />
</template>
<script setup lang="ts">
  import Header from '/@/components/Header/index.vue';
</script>

<style lang="less">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    /* background-color: var(--color-bg-1); */
    background-color: #11161c;
  }
  html {
    /* 方便unocss计算：1单位 = 0.25rem = 1px */
    /* font-size: 4px; */
  }
  #children {
    flex: 1 0 auto;
    width: 100%;
    /* height: calc(100vh - 68px); */
    min-height: 100vh;
    overflow: auto;
  }
  .ghostBtn {
    padding: 2px;
    background: linear-gradient(90deg, #7e46f2, #00e6a1);
  }
  .ghostBtn > div {
    background: #11161c;
    border-radius: 6px;
  }
  .upButton {
    display: inline-flex;
    align-items: center;
    box-sizing: border-box;
    color: #fff;
    font-weight: 500;
    font-size: 20px;
    border-radius: 8px;
    cursor: pointer;
    text-align: center;
  }
  .upButton > div {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    white-space: nowrap;
  }
  .ant-select-dropdown .ant-select-item {
    color: #fff;
    background-color: #1d212e;
    min-height: 46px;
    line-height: 36px;
  }

  .ant-select-dropdown .ant-select-item-option-active:not(.ant-select-item-option-disabled) {
    background: hsla(0, 0%, 100%, 0.1);
    box-shadow: 0 4px 8px rgb(0 0 0 / 10%);
  }
</style>
