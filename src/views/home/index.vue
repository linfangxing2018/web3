<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-05 22:25:12
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2022-12-09 00:00:44
 * @FilePath: \web3\src\views\home\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div class="home">
    <Header />
    <div id="children">
      <div class="h-container">
        <div class="banBox">
          <a-carousel autoplay>
            <div v-for="(item, index) in 4" :key="item">
              <div style="width: 100%; display: inline-block; vertical-align: bottom">
                <div
                  class="bannerBox"
                  style="
                    background-image: url('https://upstairs-prod.s3.ap-southeast-1.amazonaws.com/uploads/2022_12_7/1527/rc-upload-1670328135787-23-CHI.jpg');
                  "
                ></div
              ></div>
            </div>
          </a-carousel>
        </div>
        <div class="notice">
          <div class="TopBorder"></div>
          <div class="broadcast">
            <div class="broadcastWid">
              <div class="broadcastImg">
                <!-- <div class="imgSound"> <img src="https://static-prod.upstairs.io/websites/www/assets/home/sound.svg" /> </div> -->
                <div class="noticeBox">
                  <span class="noticeItem"><span style="width: 280px"></span>Upstairs x JZL《蒲公英》系列 第二轮 白名单发售现已上线!</span>
                  <span class="noticeItem">Upstairs x JZL《蒲公英》系列 第一轮 白名单发售现已上线!</span>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="Products">
          <div class="header"
            ><span class="title">新品</span><div class="upButton___74pJX ghostBtn___1fAeP viewBtn"><div>查看全部</div></div></div
          >
          <div class="productBox">
            <div class="Product" v-for="(item, index) in 3" :key="item" style="width: 393px; height: 477px">
              <img
                class="bigImg"
                src="https://upstairs-prod.s3.ap-southeast-1.amazonaws.com/uploads/2022_12_7/4/rc-upload-1670424223710-13-2022-12-0721.06.29.jpg"
              />
              <div class="mask" style="padding: 0px">
                <div class="imgBox">
                  <div>
                    <img
                      class="smallImg"
                      src="https://upstairs-prod.s3.ap-southeast-1.amazonaws.com/uploads/2022_12_7/4/rc-upload-1670424223710-13-2022-12-0721.06.29.jpg"
                      alt=""
                    />
                  </div>
                  <div class="timeLine">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/clock.svg" />2022/12/0914:00:00(UTC+8)
                  </div>
                </div>
                <div class="intro">
                  <div class="nameLine">
                    <div class="firstLine">
                      <span class="key">蒲公英</span>
                      <span class="type">发售</span>
                    </div>
                    <span class="value">JZL Garden</span>
                  </div>
                  <div class="textLine">
                    <span class="key">总量</span>
                    <span class="value">997</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div>
          <div class="Trending">
            <div class="header">
              <span class="title"> 热门<span class="times">24小时</span></span>
              <div class="upButton ghostBtn marketBtn">
                <div>去市场</div>
              </div>
            </div>
            <div class="trendingListBox">
              <a-table :dataSource="dataSource" :columns="columns" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  import SvgIcon from '/@/components/SvgIcon/index.vue';
  import { useAppStore } from '/@/store/modules/app';

  import Header from '/@/components/Header/index.vue';

  const appStore = useAppStore();
</script>

<style lang="less" scoped>
  .home {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;

    background-color: #11161c;
    #children {
      flex: 1 0 auto;
      width: 100%;
      height: calc(100vh - 68px);
      overflow: auto;
      .ghostBtn {
        padding: 2px;
        background: linear-gradient(90deg, #7e46f2, #00e6a1);
      }
      .upButton {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        box-sizing: border-box;
        color: #fff;
        font-weight: 500;
        font-size: 20px;
        border-radius: 8px;
        cursor: pointer;
      }
      .h-container {
        display: flex;
        flex-direction: column;
        overflow: auto;
        .banBox {
          .ant-carousel :deep(.slick-slide) {
            outline: none;
            width: 2554px;
          }
          .bannerBox {
            height: 595px;
            background-repeat: no-repeat;
            background-position: 50%;
            background-size: cover;
          }
        }
        .notice {
          .TopBorder {
            width: 100%;
            border-top: 1px solid;
            border-image: linear-gradient(90.2deg, rgba(0, 230, 161, 0.5) 0.17%, rgba(160, 114, 255, 0.5) 101.35%) 1;
          }
          .broadcast {
            width: 100%;
            height: 60px;
            overflow: hidden;
            border-bottom: 1px solid;
            border-image: linear-gradient(90.2deg, rgba(160, 114, 255, 0.5) 0.17%, rgba(0, 230, 161, 0.5) 101.35%) 1;
            .broadcastWid {
              width: 1250px;
              height: 100%;
              display: flex;
              align-items: center;
              justify-content: flex-end;
              margin: 0 auto;
              .broadcastImg {
                width: 1120px;
                display: flex;
                justify-content: flex-start;
                position: relative;
                overflow: hidden;
                .imgSound {
                  width: 30px;
                  background: #12161c;
                  z-index: 1;
                  img {
                    vertical-align: middle;
                    border-style: none;
                  }
                }
                @keyframes move {
                  0% {
                    transform: translateZ(0);
                  }
                  100% {
                    transform: translate3d(-50%, 0, 0);
                  }
                }
                .noticeBox {
                  min-width: calc(100% - 30px);
                  overflow: hidden;
                  // position: absolute;
                  white-space: nowrap;
                  line-height: 1.5715;
                  animation: move 30s linear infinite;
                  span {
                    max-width: 810px;
                    display: inline-block;
                    overflow: hidden;
                    text-overflow: ellipsis;
                  }
                }
                .noticeItem {
                  white-space: nowrap;
                  margin-right: 40px;
                  font-size: 20px;
                  line-height: 30px;
                  color: hsla(0, 0%, 100%, 0.5);
                  cursor: pointer;
                }
              }
            }
          }
        }
        .Products {
          width: 1250px;
          margin: 0 auto;
          padding-top: 56px;
          .header {
            display: flex;
            justify-content: space-between;
            .title {
              font-weight: 500;
              font-size: 32px;
              line-height: 50px;
              color: #fff;
            }
            .viewBtn {
              width: 150px;
              height: 50px;
              font-weight: 500;
              font-size: 20px;
              line-height: 31px;
              color: #fff;
              display: inline-flex;
              align-items: center;
              justify-content: center;
              box-sizing: border-box;
              padding: 2px;
              background: linear-gradient(90deg, #7e46f2, #00e6a1);
              border-radius: 8px;
            }
          }
          .productBox {
            display: grid;
            justify-content: space-between;
            grid-template-columns: repeat(auto-fill, 393px);
            .Product {
              position: relative;
              transition: all 0.6s;
              cursor: pointer;
              margin-top: 24px;
              .bigImg {
                border-radius: 13px;
                width: 100%;
                height: 100%;
              }
              .mask {
                position: absolute;
                top: 0;
                left: 0;
                display: flex;
                flex-direction: column;
                justify-content: space-between;
                color: #fff;
                background: linear-gradient(102.21deg, rgba(26, 27, 48, 0.85) 6.93%, rgba(33, 34, 60, 0.85) 92.28%);
                border-radius: 10px;
                backdrop-filter: blur(60px);
                width: 100%;
                height: 100%;
                .imgBox {
                  position: relative;
                  .smallImg {
                    width: 100%;
                    height: 392px;
                    border-radius: 10px 10px 0 0;
                  }
                  .timeLine {
                    width: 100%;
                    height: 36px;
                    position: absolute;
                    bottom: 0;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    background: rgba(48, 63, 82, 0.5);
                    -webkit-backdrop-filter: blur(20px);
                    backdrop-filter: blur(20px);
                  }
                }
                .intro {
                  padding: 16px;
                  display: flex;
                  justify-content: space-between;
                  .nameLine {
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    .firstLine {
                      display: flex;
                      align-items: center;
                      .key {
                        font-weight: 500;
                        font-size: 18px;
                        line-height: 28px;
                        max-width: 178px;
                        white-space: nowrap;
                        overflow: hidden;
                        text-overflow: ellipsis;
                      }
                      .type {
                        padding: 0 6px;
                        font-weight: 400;
                        font-size: 14px;
                        line-height: 20px;
                        margin-left: 8px;
                        border-radius: 2px;
                        height: 20px;
                        background: radial-gradient(72.76% 105.12% at 54.85% 4.64%, #fd5f52 0, #cf3729 100%);
                      }
                    }
                  }
                  .textLine {
                    display: flex;
                    flex-direction: column;
                    justify-content: space-between;
                    .key {
                      font-weight: 400;
                      font-size: 14px;
                      line-height: 28px;
                      color: hsla(0, 0%, 100%, 0.5);
                    }
                    .value {
                      font-weight: 500;
                      font-size: 14px;
                      line-height: 22px;
                      color: #0fe2bc;
                    }
                  }
                }
              }
            }
          }
        }
        .Trending {
          width: 1250px;
          margin: 0 auto;
          padding: 56px 0 0;
          .header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 12px;
            .title {
              font-weight: 500;
              font-size: 32px;
              line-height: 50px;
              color: #fff;
              .times {
                font-weight: 500;
                font-size: 20px;
                line-height: 50px;
                color: hsla(0, 0%, 100%, 0.5);
                margin-left: 12px;
                vertical-align: top;
              }
            }
            .marketBtn {
              width: 166px;
              height: 50px;
            }
          }
          .trendingListBox {
          }
        }
      }
    }
  }
</style>
