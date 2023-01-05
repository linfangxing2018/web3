<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-05 21:53:31
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2023-01-05 21:56:59
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
        <div class="marketCont">
          <div class="Product marketProduct" v-for="(item, index) in 14" :key="item" style="width: 277px; height: 339px">
            <div class="mask marketProductMask" style="padding: 9px 9px 12px">
              <div class="imgBox">
                <div>
                  <img
                    class="smallImg"
                    src="https://upstairs-prod.s3.ap-southeast-1.amazonaws.com/nfts/0x721cCd3E9b13D2Db47002892e048C1D9537a0d14/image/1785?mystery=false&amp;opened=true"
                  />
                </div>
                <div class="rankPcLine">
                  <img src="https://static-prod.upstairs.io/websites/www/assets/account/rank.svg" alt="" />
                  稀有度 678
                </div>
              </div>
              <div class="productContWrap">
                <div class="productDesc">
                  <div class="productName">Mutant Kiddo #1785</div>
                  <div class="productDescRow">
                    <span class="descField">Upstairs</span>
                    <span class="descValue">30 USDT</span>
                  </div>
                </div>
                <div class="cartOperations">
                  <div class="cartItem">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/flash.svg" alt="flash" />
                    立即购买
                  </div>
                  <div class="splitCart"></div>
                  <div class="cartItem">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/cart.svg" alt="cart" />
                    加入购物车
                  </div>
                </div>
              </div>
            </div>
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
    div {
      display: block;
    }
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

      .marketCont {
        padding: 0 0 60px;
        height: 100%;
        display: grid;
        justify-content: space-between;
        grid-template-columns: repeat(auto-fill, 277px);
        grid-template-rows: repeat(auto-fill, 339px);
        grid-row-gap: 24px;
        .marketProduct {
          font-weight: 500;
          font-size: 14px;
          line-height: 22px;
          grid-gap: 12px;
          margin-top: 0;

          .cartOperations {
            display: none;
            position: absolute;
            top: 0;
            bottom: 0;
            width: 100%;
            font-weight: 500;
            font-size: 14px;
            line-height: 22px;
            .cartItem {
              flex: 1 1;
              cursor: pointer;
              text-align: center;
              display: flex;
              align-items: center;
              justify-content: center;
              img {
                margin-right: 10px;
              }
            }
            .splitCart {
              width: 1px;
              height: 46px;
              background: linear-gradient(180deg, hsla(0, 0%, 100%, 0), #fff 48.04%, hsla(0, 0%, 100%, 0));
              opacity: 0.25;
            }
          }
        }

        .Product:hover {
          .cartOperations {
            z-index: 1000;
            display: flex;
            background: linear-gradient(#181a27 0 0) padding-box,
              linear-gradient(119.17deg, rgba(0, 230, 161, 0.144) 4.16%, rgba(126, 70, 242, 0.45) 87.53%) border-box;
          }
        }
        .Product {
          position: relative;
          transition: all 0.6s;
          cursor: pointer;
          .mask {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            color: #fff;
            backdrop-filter: blur(60px);
            .imgBox {
              position: relative;
              .smallImg {
                width: 100%;
                height: 257px;
                border-radius: 8px;
              }
              .rankPcLine {
                position: absolute;
                left: 12px;
                top: 12px;
                padding: 5px 10px;
                display: flex;
                align-items: center;
                font-weight: 500;
                font-size: 14px;
                line-height: 22px;
                color: #fff;
                background: rgba(48, 63, 82, 0.5);
                backdrop-filter: blur(10px);
                border-radius: 8px 0;
                img {
                  display: inline-block;
                  width: 16px;
                  height: 16px;
                  margin-right: 6px;
                }
              }
            }
            .productContWrap {
              position: relative;
            }
          }
          .marketProductMask {
            border-radius: 8px;
            border: 1px solid transparent;
            background: linear-gradient(#181a27 0 0) padding-box,
              linear-gradient(119.17deg, rgba(0, 230, 161, 0.144) 4.16%, rgba(126, 70, 242, 0.45) 87.53%) border-box;
          }
        }
        .productName {
          font-weight: 500;
          white-space: nowrap;
          text-overflow: ellipsis;
          overflow: hidden;
        }
        .productDescRow {
          display: flex;
          justify-content: space-between;
          align-items: center;
          margin-top: 2px;
          .descField {
            color: hsla(0, 0%, 100%, 0.5);
            font-weight: 400;
          }
          .descValue {
            color: #0fe2bc;
            font-weight: 500;
          }
        }
      }
    }
  }
</style>
