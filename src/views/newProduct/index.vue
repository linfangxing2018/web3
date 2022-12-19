<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-19 20:42:15
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2022-12-19 22:30:11
 * @FilePath: \web3\src\views\newProduct\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div id="children" class="new-product">
    <div class="wrapper">
      <section class="content">
        <a-row :gutter="[12]">
          <a-col :span="12">
            <div class="imgDiv">
              <div>
                <img
                  class="mainImg"
                  src="https://upstairs-prod.s3.ap-southeast-1.amazonaws.com/uploads/2022_12_7/4/rc-upload-1670424223710-13-2022-12-0721.06.29.jpg?timestamp=1671453294606"
                />
              </div>
            </div>
          </a-col>
          <a-col :span="12">
            <article class="baseInfo">
              <div>
                <h1 class="title" title="蒲公英">蒲公英</h1>
                <p
                  class="des"
                  title="设计理念：蒲公英： Crypto世界中正义的反叛精神与百折不挠的态度JZL Garden 的首期 NFT 系列作品叫做“蒲公英”，受亚里士多德的启发，创作出 1066 个稀有度不同的人物。蒲公英的设计理念代表了 Crypto世界中正义的反叛精神与百折不挠的态度。
"
                  >设计理念： 蒲公英： Crypto世界中正义的反叛精神与百折不挠的态度 JZL Garden 的首期 NFT
                  系列作品叫做“蒲公英”，受亚里士多德的启发，创作出 1066 个稀有度不同的人物。蒲公英的设计理念代表了
                  Crypto世界中正义的反叛精神与百折不挠的态度。
                </p>
              </div>
              <section class="stepBox">
                <section class="stepCont">
                  <section class="stepInfo">
                    <span class="field">发行方 :</span>
                    <span class="value">JZL Garden</span>
                  </section>
                  <section class="stepInfo">
                    <span class="field">类型 :</span>
                    <span class="value">发售</span>
                  </section>
                  <section class="stepInfo">
                    <span class="field">合约 :</span>
                    <span class="value">0x739948170906d02aab34dcF6909361C0368E180e</span>
                  </section>
                  <section class="stepInfo">
                    <span class="field">总量 :</span>
                    <span class="value">997</span>
                  </section>
                  <section class="steps">
                    <div class="step active" v-for="(item, index) in 3" :key="item">
                      <div class="stepIcon">{{ item }}</div>
                      <div class="stepContent">
                        <p class="stepTitle" title="第一轮白名单">第一轮白名单</p>
                        <p class="stepTime">2022/12/08 20:00:00(UTC+8)</p>
                      </div>
                    </div>
                  </section>
                </section>
              </section>
              <div class="btnDiv">
                <div style="height: 24px"></div>
                <div class="currentSale">第三轮公开发售</div>
                <section class="priceInfo">
                  <div class="priceBox">
                    <p class="infoName">价格</p>
                    <span class="infoNum">15USDT</span>
                  </div>
                  <div>
                    <p class="infoName">发售数量</p>
                    <span class="infoNum">997 / 997</span>
                  </div>
                  <div>
                    <p class="infoName">限购数量</p>
                    <span class="infoNum">100</span>
                  </div>
                </section>
                <div class="upButton ghostBtn detailBtn"><div>发售结束，去市场</div></div>
                <div class="upButton ghostBtn detailBtn infoBtn"><div>详情</div></div>
              </div>
            </article>
          </a-col>
        </a-row>
        <section class="productContainer">
          <div id="productTab" style="background: none; backdrop-filter: none; height: 68px">
            <h3 class="productTitle">全部系列</h3>
            <div>
              <a-button type="primary" class="btn active">
                <span>全 部</span>
              </a-button>
              <a-button type="button" class="btn false">
                <span>即将开始</span>
              </a-button>
              <a-button type="button" class="btn false">
                <span>已发售</span>
              </a-button>
            </div>
          </div>
          <div class="productRow">
            <Product v-for="(item, index) in 8" :key="item" />
          </div>
        </section>
      </section>
    </div>
  </div>
</template>

<script setup lang="ts">
  import Product from '/@/components/Product/index.vue';
</script>

<style lang="less" scoped>
  .new-product {
    .wrapper {
      padding: 105px 0 82px;
      .content {
        width: 1250px;
        display: flex;
        flex-direction: column;
        box-sizing: border-box;
        margin: 0 auto;
        .imgDiv {
          width: 100%;
          height: 613px;
          background: linear-gradient(#181a27 0 0) padding-box,
            linear-gradient(119.17deg, rgba(0, 230, 161, 0.144) 4.16%, rgba(126, 70, 242, 0.45) 87.53%) border-box;
          border: 1px solid transparent;
          -webkit-backdrop-filter: blur(47.0455px);
          backdrop-filter: blur(47.0455px);
          border-radius: 8px;
          position: relative;
          padding: 64px;
          .mainImg {
            width: 100%;
            max-width: 100%;
            max-height: 100%;
            border-radius: 8px;
          }
        }
        .baseInfo {
          .title {
            font-family: 'Saira';
            font-style: normal;
            font-weight: 500;
            font-size: 40px;
            line-height: 60px;
            color: #fff;
            margin-bottom: 8px;
            width: 100%;
            overflow: hidden;
            text-overflow: ellipsis;
            white-space: nowrap;
          }
          .des {
            font-family: 'Saira';
            font-style: normal;
            font-weight: 400;
            font-size: 14px;
            line-height: 22px;
            color: hsla(0, 0%, 100%, 0.5);
            margin-bottom: 20px;
            overflow: hidden;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp: 3;
            -webkit-box-orient: vertical;
          }
          .stepBox {
            width: 100%;
            min-height: 114px;
            border-radius: 8px;
            background: linear-gradient(119.17deg, rgba(0, 230, 161, 0.176) 4.16%, rgba(126, 70, 242, 0.55) 87.53%) 50%/100% no-repeat;
            padding: 1px;
            .stepCont {
              background-color: #181a27;
              background-image: url(https://static-dev.upstairs.io/websites/www/assets/news/step-bg.jpeg);
              background-repeat: no-repeat;
              background-position: 50%;
              background-size: 100%;
              padding: 20px 24px;
              border-radius: 8px;
              .stepInfo:not(:last-child) {
                margin-bottom: 4px;
              }
              .stepInfo {
                display: flex;
                align-items: flex-start;
                justify-content: flex-start;
                font-weight: 500;
                font-size: 14px;
                line-height: 22px;
                .field {
                  width: 102px;
                  text-align: left;
                  color: hsla(0, 0%, 100%, 0.5);
                }
                .value {
                  color: #fff;
                  font-weight: 400;
                  display: flex;
                  flex-direction: column;
                  align-items: flex-start;
                }
              }
              .steps {
                display: inline-flex;
                max-width: 100%;
                align-items: center;
                position: relative;
                margin-top: 20px;
                margin-left: 32px;
                .step:not(:first-child) {
                  padding-left: 80px;
                }
                .step {
                  display: flex;
                  flex-direction: column;
                  position: relative;
                  min-height: 92px;
                  font-weight: 500;
                  .stepIcon {
                    background: linear-gradient(0deg, #4680f2, #00e6a1);
                    color: #fff;
                    position: relative;
                    z-index: 1;
                    width: 36px;
                    height: 36px;
                    line-height: 36px;
                    font-size: 20px;
                    // color: #000;
                    text-align: center;
                    border-radius: 100%;
                    // background: linear-gradient(357.61deg, #a5bcfd 1.83%, #f6f4c9 98%);
                  }
                  .stepContent {
                    min-height: 56px;
                    position: absolute;
                    top: 36px;
                    text-align: center;
                    margin-left: 18px;
                    margin-top: 4px;
                    transform: translateX(-50%);
                    .stepTitle {
                      font-weight: 500;
                      font-size: 14px;
                      line-height: 22px;
                      color: #fff;
                      margin-bottom: 0;
                      width: 118px;
                      overflow: hidden;
                      text-overflow: ellipsis;
                      white-space: nowrap;
                    }
                    .stepTime {
                      font-weight: 500;
                      font-size: 12px;
                      line-height: 14px;
                      font-weight: 400;
                      color: hsla(0, 0%, 100%, 0.5);
                      margin-bottom: 0;
                    }
                  }
                }
              }
              .steps:after {
                content: ' ';
                display: block;
                position: absolute;
                height: 4px;
                left: 0;
                top: 16px;
                width: 100%;
                background: linear-gradient(0deg, #4680f2, #00e6a1);
              }
            }
          }
          .btnDiv {
            background: #181a27;
            backdrop-filter: blur(20px);
            border-radius: 8px;
            padding: 0 24px;
            margin-top: 20px;
            .currentSale {
              width: 105px;
              height: 20px;
              font-style: italic;
              font-weight: 500;
              font-size: 12px;
              line-height: 20px;
              text-align: center;
              color: #fff;
              background-image: url(https://static-dev.upstairs.io/websites/www/assets/news/saleBg.png);
              background-size: cover;
              white-space: nowrap;
              text-overflow: ellipsis;
              overflow: hidden;
              margin-bottom: 16px;
            }
            .priceInfo {
              display: flex;
              align-items: flex-start;
              div:not(:first-child) {
                margin-left: 48px;
              }
              .priceBox {
                display: flex;
                flex-direction: column;
              }
              .infoName {
                font-weight: 500;
                font-size: 14px;
                line-height: 22px;
                color: hsla(0, 0%, 100%, 0.5);
                margin-bottom: 4px;
                font-weight: 400;
              }
              .infoNum {
                color: #0fe2bc;
                font-family: 'Saira';
                font-style: normal;
                font-weight: 500;
                font-size: 24px;
                line-height: 32px;
              }
            }
            .detailBtn {
              margin: 20px 0 24px;
              height: 50px;
            }
            .detailBtn > div {
              padding: 10px 30px;
            }
            .infoBtn {
              margin-left: 16px;
            }
          }
        }
        .productContainer {
          margin-top: 42px;
          #productTab {
            background: none;
            backdrop-filter: none;
            height: 68px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 68px;
            z-index: 1;
            .productTitle {
              font-weight: 500;
              font-size: 32px;
              line-height: 36px;
              color: #fff;
              margin-bottom: 0;
            }

            .btn {
              height: 40px;
              color: #fff;
              font-weight: 400;
              font-size: 20px;
              line-height: 30px;
              background: transparent;
              border: 0;
              border-radius: 8px;
              margin-right: 12px;
            }
            .active {
              font-weight: 500;
              background: linear-gradient(90deg, #7e46f2, #00e6a1);
            }
          }
          .productRow {
            min-height: 543px;
            display: grid;
            justify-content: space-between;
            grid-template-columns: repeat(auto-fill, 393px);
            grid-gap: 10px;
          }
        }
      }
    }
  }
</style>
