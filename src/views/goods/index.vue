<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-05 21:53:31
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2023-01-03 23:46:18
 * @FilePath: \web3\src\App.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div id="children" class="goods">
    <section class="marketContainer">
      <div class="filterWrap" :class="{ filterActive: 0 }">
        <div class="filterHeader">
          <img class="filterOpenIcon" src="https://static-prod.upstairs.io/websites/www/assets/market/filter.svg" alt="filter" />
          <span>筛选</span>
          <img class="filterClose" src="https://static-prod.upstairs.io/websites/www/assets/market/close.svg" alt="close" />
        </div>
        <div class="filterRow">
          <span class="filterField">价格</span>
          <div>
            <a-input placeholder="最小" class="ant-input searchInput filterInput" type="text" value="" />
            <span class="filterConnect">到</span>
            <a-input placeholder="最大" class="ant-input searchInput filterInput" type="text" value="" />
          </div>
        </div>
        <div class="filterRow">
          <span class="filterField">物品类型</span>
          <img src="https://static-prod.upstairs.io/websites/www/assets/market/arrow-down.svg" alt="arrow" class="filterExpand" />
        </div>
        <a-checkbox-group class="checkGroup expanded" v-model:value="itemType" name="checkboxgroup">
          <a-row class="filterRow checkboxItem">
            <a-checkbox value="all" class="connectionCheck">全部</a-checkbox>
          </a-row>
          <a-row class="filterRow checkboxItem">
            <a-checkbox value="NFT" class="connectionCheck">NFT</a-checkbox>
          </a-row>
          <a-row class="filterRow checkboxItem">
            <a-checkbox value="none" class="connectionCheck">盲盒</a-checkbox>
          </a-row>
        </a-checkbox-group>
      </div>
      <div class="mainCont">
        <div class="headerRow">
          <div class="resultWrapper">
            <img src="https://static-prod.upstairs.io/websites/www/assets/market/refresh.svg" alt="refresh" />
            2559 个结果
          </div>
          <div class="headerRight">
            <div class="relative">
              <a-input class="search" v-model:value="searchValue" placeholder="请搜索物品名称" @search="onSearch" />
              <img src="/src/static/images/market/search.svg" alt="search" class="searchIcon" />
            </div>
            <a-select v-model:value="selectValue" class="select" :options="options" @change="handleChange" :dropdownStyle="dropdownStyle" />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>
<script setup lang="ts">
  import { ref, watch } from 'vue';
  const itemType = ref('');
  watch(itemType, (newVal) => {
    console.log(newVal, 'ddd');
  });
  const itemOptions = [
    { label: '全部', value: 'all' },
    { label: 'NFT', value: 'NFT' },
    { label: '盲盒', value: 'none' },
  ];

  const searchValue = ref('');
  const selectValue = ref('最新上架');
  const options = [{ value: '最新上架' }, { value: '价格从低到高' }, { value: '价格从高到低' }, { value: '稀有度从高到低' }];
  const dropdownStyle = {
    background: '#303048',
    'border-radius': '4px',
  };
</script>

<style lang="less" scoped>
  .goods {
    .marketContainer {
      width: 1250px;
      display: flex;
      justify-content: space-between;
      overflow: hidden;
      padding: 69px 0 0;
      position: relative;
      box-sizing: border-box;
      min-height: 100%;
      margin: 0 auto;
      .filterWrap {
        width: 335px;
        padding-top: 36px;
        overflow: hidden;
        transition: width 0.25s;
      }
      .filterActive {
        width: 0;
      }
      .filterHeader {
        width: 100%;
        height: 42px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding-bottom: 25px;
        border-bottom: 1px solid hsla(0, 0%, 100%, 0.08);
        text-align: left;
        margin-bottom: 4px;
        span {
          flex: 1 1;
          font-weight: 500;
          font-size: 14px;
          line-height: 14px;
          color: #fff;
        }
      }
      .filterOpenIcon {
        width: 16px;
        height: 16px;
        margin-right: 8px;
      }
      .filterClose {
        width: 12px;
        height: 12px;
        padding: 16px;
        box-sizing: content-box;
        margin-right: -16px;
        cursor: pointer;
      }
      .filterRow {
        margin-top: 20px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        .filterField {
          font-weight: 500;
          font-size: 14px;
          line-height: 22px;
          font-weight: 400;
          color: hsla(0, 0%, 100%, 0.5);
        }
        .searchInput {
          height: 36px;
          background: hsla(0, 0%, 100%, 0.05);
          border: 1px solid hsla(0, 0%, 100%, 0.12);
          border-radius: 4px;
          box-sizing: border-box;
          color: #fff;
        }
        .filterInput {
          width: 77px;
          padding-left: 16px;
          padding-right: 16px;
          background-color: transparent;
        }
        .filterConnect {
          margin: 0 8px;
          color: hsla(0, 0%, 100%, 0.5);
        }
      }
      .expanded {
        height: auto;
        opacity: 1;
      }
      .checkGroup {
        font-size: 14px;
        line-height: 22px;
        width: 100%;

        overflow: hidden;
        transition: height 0.25s ease-in-out, opacity 0.25s ease-in-out;
        font-weight: 400;
        .checkboxItem:first-child {
          margin-top: 16px;
        }
        .connectionCheck {
          color: #fff;
        }
      }

      .mainCont {
        position: relative;
        flex: 1 1;
        min-width: 608px;
        max-width: 1204px;
        padding-top: 36px;
        padding-left: 36px;
        padding-bottom: 60px;
      }
      .headerRow {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 24px;
      }
      .resultWrapper {
        display: flex;
        align-items: center;
        font-size: 14px;
        line-height: 22px;
        color: hsla(0, 0%, 100%, 0.5);
        img {
          width: 16px;
          height: 16px;
          margin-right: 10px;
          cursor: pointer;
        }
      }
      .headerRight {
        display: flex;
        justify-content: flex-end;
        align-items: center;
        position: relative;
        .search {
          position: relative;
          margin-right: 16px;
          width: 395px;
          height: 36px;
          background: hsla(0, 0%, 100%, 0.05);
          border: 1px solid hsla(0, 0%, 100%, 0.12);
          border-radius: 4px;
          box-sizing: border-box;
          color: #fff;
          padding-right: 42px;
        }
        .searchIcon {
          position: absolute;
          right: 15px;
          top: 50%;
          padding: 15px;
          transform: translateY(-50%);
          z-index: 1;
          width: 16px;
          box-sizing: content-box;
          max-width: 100%;
          cursor: pointer;
        }
      }
      .select {
        /deep/ .ant-select-selector {
          font-size: 14px;
          line-height: 36px;
          width: 200px;
          height: 36px;
          box-sizing: border-box;
          background: transparent;
          border: 1px solid hsla(0, 0%, 100%, 0.12);
          border-radius: 4px;
          font-weight: 600;
          color: #fff;
          padding: 0 16px;
        }
      }
    }
  }
</style>
