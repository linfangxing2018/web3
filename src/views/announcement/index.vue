<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2023-01-05 22:03:23
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2023-01-05 22:10:22
 * @FilePath: \web3\src\views\announcement\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%A
-->
<template>
  <div class="wrapper">
    <section class="announceWeb">
      <div class="announceHeader"><div class="title">公告</div></div>
      <a-card class="announceCard">
        <div></div>
      </a-card>
    </section>
  </div>
</template>

<script>
  export default {};
</script>

<style lang="less" scoped>
  .wrapper {
    width: 1250px;
    margin: 0 auto;
    padding: 105px 0 55px;
    overflow: auto;
    min-height: 100%;
    .announceWeb {
      width: 100%;
      background: #191b29;
      padding: 28px 24px 16px;
    }
    .announceHeader {
      padding-bottom: 16px;
      border-bottom: 1px solid hsla(0, 0%, 100%, 0.08);
      display: flex;
      align-items: center;
      margin-bottom: 23px;
      .title {
        display: flex;
        align-items: center;
        font-family: 'Saira';
        font-style: normal;
        font-weight: 500;
        font-size: 20px;
        line-height: 20px;
        margin-right: 16px;
        cursor: pointer;
        color: #fff;
      }
    }
    .announceCard {
      width: 100%;
      background: transparent;
      border: 0;
    }
  }
</style>
