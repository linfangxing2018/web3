<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-05 22:25:12
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2022-12-14 22:09:14
 * @FilePath: \web3\src\views\home\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div class="home">
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
              <a-table :pagination="false" :columns="columns" :data-source="data">
                <template #bodyCell="{ column, record }">
                  <template v-if="column.key === 'index'">
                    <div class="rankBox">
                      {{ record.key }}
                    </div>
                  </template>
                  <template v-if="column.key === 'name'">
                    <div class="collectionRows">
                      <img
                        alt=""
                        src="https://upstairs-prod.s3.ap-southeast-1.amazonaws.com/uploads/2022_12_7/4/rc-upload-1670424223710-13-2022-12-0721.06.29.jpg"
                      />
                      <span class="tableText" style="width: 215px">{{ record.name }}</span>
                    </div>
                  </template>
                  <template v-else-if="column.key === 'minimum'">
                    <div class="tdNumberText">
                      <span>15.8</span>
                      <span class="textRise">+11.39%</span>
                    </div>
                  </template>
                  <template v-else-if="column.key === 'turnover'">
                    <div class="tdNumberText">
                      <span class="tableText">1,362.9 USDT</span>
                      <span class="textRise">+95.38%</span>
                    </div>
                  </template>
                  <template v-else-if="column.key === 'volume'">
                    <div class="tdNumberText">
                      <span class="tableText">52</span>
                      <span class="textRise">+95.38%</span>
                    </div>
                  </template>
                  <template v-else-if="column.key === 'publications'">
                    <div class="tdNumberText">
                      <span class="tableText">52%</span>
                    </div>
                  </template>
                  <template v-else-if="column.key === 'circulation'">
                    <div class="tdNumberText">
                      <span class="tableText">1000</span>
                    </div>
                  </template>
                </template>
              </a-table>
            </div>
          </div>
        </div>
        <div class="Upstairs">
          <div class="header"><span class="title">平台特点</span></div>
          <div class="introBox">
            <div class="introItem" v-for="(item, index) in 4" :key="item">
              <img
                src="https://upstairs-prod.s3.ap-southeast-1.amazonaws.com/uploads/2022_10_11//rc-upload-1665496481629-3-rc-upload-1665108676298-7-7.MetaverseVirtualWorld.png"
              />
              <div class="introTitle">独家IP合作资源</div>
              <div class="content">浏览您最喜爱的品牌和艺术家策划的优质的艺术作品。</div>
            </div>
          </div>
        </div>
      </div>
      <div class="footer">
        <div class="width1250">
          <div class="topElement">
            <div class="copyright">
              <img src="https://static-prod.upstairs.io/websites/www/assets/common/logo-icon.svg" alt="logo" />
              <div>将NFT提升到新的境界</div>
            </div>
            <div class="menuBox">
              <a class="menuItem">首页</a>
              <a class="menuItem">新品</a>
              <a class="menuItem">市场</a>
              <a class="menuItem">质押</a>
              <a class="menuItem">公告</a>
              <a class="menuItem" href="https://www.upstairs.io/announcement/?tab=faqs" target="_blank" rel="noopener noreferrer"
                >常见问题</a
              >
            </div>
            <div class="links">
              <div class="join">联系我们</div>
              <div class="ant-space ant-space-horizontal ant-space-align-center" style="gap: 14px">
                <div class="ant-space-item" style="">
                  <a href="https://t.me/upstairsmarketplace" target="_blank" rel="noopener noreferrer">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/tg.svg" alt="telegram" />
                  </a>
                </div>
                <div class="ant-space-item" style="">
                  <a href="https://www.instagram.com/upstairsnft/" target="_blank" rel="noopener noreferrer">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/ins.svg" alt="instagram" />
                  </a>
                </div>
                <div class="ant-space-item" style="">
                  <a href="https://twitter.com/UpstairsNFT" target="_blank" rel="noopener noreferrer">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/tw.svg" alt="twitter" />
                  </a>
                </div>
                <div class="ant-space-item" style="">
                  <a href="https://www.facebook.com/upstairsnft" target="_blank" rel="noopener noreferrer">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/fb.svg" alt="facebook" />
                  </a>
                </div>
                <div class="ant-space-item" style="">
                  <a href="https://www.discord.gg/upstairs" target="_blank" rel="noopener noreferrer">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/dc.svg" alt="dicsord" />
                  </a>
                </div>
                <div class="ant-space-item">
                  <a href="https://www.youtube.com/channel/UCIv9Im4uLzgdOfGLE1HMzPw" target="_blank" rel="noopener noreferrer">
                    <img src="https://static-prod.upstairs.io/websites/www/assets/common/ytb.svg" alt="youtube" />
                  </a>
                </div>
              </div>
            </div>
          </div>
          <div class="bottomElement">
            <span>一般查询及建议: contact@upstairs.io</span>
            <span class="division">|</span>
            <span>客服支持: support@upstairs.io</span>
            <span class="division">|</span>
            <span>© 2022 Upstairs Research, Pte Ltd</span>
            <span class="division">|</span>
            <a href="https://www.certik.com/projects/upstairs#audit" target="_blank" rel="noopener noreferrer">Audited by CERTIK</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
  import SvgIcon from '/@/components/SvgIcon/index.vue';
  import { useAppStore } from '/@/store/modules/app';

  const appStore = useAppStore();
  const columns = [
    {
      name: 'Index',
      title: '',
      dataIndex: 'index',
      key: 'index',
    },
    {
      name: 'Name',
      title: '系列',
      dataIndex: 'name',
      key: 'name',
    },
    {
      title: '地板价',
      dataIndex: 'minimum',
      key: 'minimum',
    },
    {
      title: '交易额',
      dataIndex: 'turnover',
      key: 'turnover',
    },
    {
      title: '销量',
      key: 'volume',
      dataIndex: 'volume',
    },
    {
      title: '刊登量',
      key: 'publications',
      dataIndex: 'publications',
    },
    {
      title: '流通量',
      key: 'circulation',
      dataIndex: 'circulation',
    },
  ];

  const data = [
    {
      key: '1',
      name: 'John Brown',
      age: 32,
      address: 'New York No. 1 Lake Park',
      tags: ['nice', 'developer'],
    },
    {
      key: '2',
      name: 'Jim Green',
      age: 42,
      address: 'London No. 1 Lake Park',
      tags: ['loser'],
    },
    {
      key: '3',
      name: 'Joe Black',
      age: 32,
      address: 'Sidney No. 1 Lake Park',
      tags: ['cool', 'teacher'],
    },
  ];
</script>

<style lang="less" scoped>
  .home {
    display: flex;
    flex-direction: column;
    align-items: center;
    min-height: 100vh;

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
            /deep/ .ant-table {
              color: #fff;
              font-size: 14px;
              border-spacing: 0 12px;
              background: transparent;
              // background: #181a27 !important;
              thead {
                border-radius: 4px;
                margin-bottom: 12px;
              }
              .ant-table-thead > tr > th {
                background: #20242a;
                border-bottom: 0;
                padding: 11px 16px;
                color: #fff;
              }
              .ant-table-tbody > tr > td:first-child {
                border-left: 1px solid hsla(0, 0%, 100%, 0.12);
                border-radius: 4px 0 0 4px;
                padding: 11px 4px 11px 24px;
              }
              .ant-table-tbody > tr > td {
                transition: all 0.3s;
                padding: 11px 16px;
                border: 0;
                height: 80px;
                border-top: 1px solid hsla(0, 0%, 100%, 0.12);
                border-bottom: 1px solid hsla(0, 0%, 100%, 0.12);
                background: #181a27;
                position: relative;
              }
              .ant-table-tbody > tr > td:before {
                position: absolute;
                top: 50%;
                right: 0;
                width: 1px;
                height: 46px;
                background: linear-gradient(180deg, hsla(0, 0%, 100%, 0), #fff 48.04%, hsla(0, 0%, 100%, 0));
                transform: translateY(-50%);
                transition: background 0.3s;
                content: '';
                opacity: 0.25;
              }
            }

            .rankBox {
              width: 100%;
              height: 100%;
              display: flex;
              align-items: center;
              justify-content: center;
              font-weight: 600;
              font-size: 20px;
              line-height: 30px;
            }
            .collectionRows {
              display: flex;
              align-items: center;
              justify-content: flex-start;
              color: #fff;
              img {
                width: 58px;
                height: 58px;
                margin-right: 12px;
                border-radius: 4px;
              }
              .tableText {
                display: inline-block;
                overflow: hidden;
                text-overflow: ellipsis;
                white-space: nowrap;
                max-width: 100%;
              }
            }
            .textRise {
              color: #0fe2bc;
              margin-left: 12px;
            }
            .tdNumberText {
              display: flex;
              align-items: center;
              justify-content: flex-start;
            }

            .tableText {
              display: inline-block;
              overflow: hidden;
              text-overflow: ellipsis;
              white-space: nowrap;
              max-width: 100%;
            }
          }
        }
        .Upstairs {
          width: 1250px;
          margin: 0 auto;
          padding: 44px 0 0;
          .header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 24px;
            .title {
              font-weight: 500;
              font-size: 32px;
              line-height: 50px;
              color: #fff;
            }
          }
          .introBox {
            padding: 32px 24px 32px 36px;
            background: linear-gradient(180deg, rgba(126, 70, 242, 0.15), rgba(126, 70, 242, 0) 48.51%),
              linear-gradient(180deg, rgba(28, 19, 70, 0.45), rgba(31, 32, 69, 0.45)), #11161c;
            border-radius: 10px;
            display: flex;
            justify-content: space-between;
            .introItem {
              width: 268px;
              img {
                width: 70px;
                height: 70px;
              }
              .introTitle {
                font-weight: 500;
                font-size: 20px;
                line-height: 36px;
                color: #fff;
                margin: 20px 0 6px;
              }
              .content {
                font-weight: 400;
                font-size: 14px;
                line-height: 20px;
                color: hsla(0, 0%, 100%, 0.5);
              }
            }
          }
        }
      }
      .footer {
        right: 0;
        bottom: 0;
        left: 0;
        display: flex;
        justify-content: center;
        width: 100%;
        height: 178px;
        margin-bottom: 0;
        color: hsla(0, 0%, 100%, 0.5) !important;
        font-weight: 400;
        font-style: normal;
        background-color: #061832 !important;
        .width1250 {
          width: 1250px;
          height: 178px;
          padding: 30px 0 0;
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          .topElement {
            display: flex;
            justify-content: flex-start;
            height: 123px;
            border-bottom: 1px solid hsla(0, 0%, 76.9%, 0.1);
            .copyright {
              width: 240px;
              img {
                margin-bottom: 20px;
              }
            }
            .menuBox {
              flex: 1 1;
              text-align: center;
              .menuItem {
                display: inline-block;
                color: #fff;
                position: relative;
                margin: 0 8px;
              }
            }
            .links {
              width: 250px;
              position: relative;
              .join {
                margin-bottom: 14px;
              }
            }
          }
          .bottomElement {
            height: 54px;
            margin-top: 16px;
            .division {
              margin: 0 12px;
            }
          }
        }
      }
    }
  }
</style>
