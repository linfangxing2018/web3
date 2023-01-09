<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2023-01-05 22:03:23
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2023-01-10 00:10:04
 * @FilePath: \web3\src\views\announcement\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%A
-->
<template>
  <div class="wrapper">
    <section class="announceWeb">
      <div class="announceHeader"><div class="title">公告</div></div>

      <a-card class="announceCard" style="width: 100%" :tab-list="tabList" :active-tab-key="key" @tabChange="(key) => onTabChange(key)">
        <div class="tableDiv" id="scrollArea">
          <div class="noticeBox">
            <div class="leftDesc">
              <div class="titleBox">
                <span class="title">全新质押活动2.0 规则发布</span>
              </div>
              <div class="tab" style="color: rgb(63, 105, 255); background: rgba(63, 105, 255, 0.08)">活动公告</div>
            </div>
            <div class="time">2023/01/06 12:00:00(UTC+8)</div>
          </div>
        </div>
      </a-card>
    </section>
  </div>
</template>

<script setup lang="ts">
  import { ref } from 'vue';
  const tabList = [
    {
      key: 'all',
      tab: '全部',
    },
    {
      key: 'active',
      tab: '活动公告',
    },
    {
      key: 'project',
      tab: '合成公告',
    },
  ];
  const key = ref('all');
  const onTabChange = (value: string) => {
    key.value = value;
  };
</script>

<style lang="less" scoped>
  .wrapper {
    width: 1250px;
    margin: 0 auto;
    padding: 105px 0 55px;
    overflow: auto;
    min-height: 100vh;
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
      .tableDiv {
        width: 100%;
        color: #fff;
        .noticeBox {
          display: flex;
          justify-content: space-between;
          align-items: center;
          margin-bottom: 20px;
          cursor: pointer;
          .leftDesc {
            flex: 1 1;
            display: flex;
            justify-content: space-between;
            align-items: center;
            .title {
              display: block;
              width: 760px;
              font-weight: 500;
              font-size: 14px;
              line-height: 22px;
              overflow: hidden;
              white-space: nowrap;
              text-overflow: ellipsis;
            }
            .tab {
              padding: 0 8px;
              font-weight: 500;
              font-size: 12px;
              line-height: 22px;
              border-radius: 2px;
            }
          }
          .time {
            width: 206px;
            text-align: right;
            color: hsla(0, 0%, 100%, 0.5);
          }
        }
      }
    }
    /deep/.ant-card-head {
      background: transparent;
      border: none;
      padding: 0;
      font-family: 'Saira';
      font-style: normal;
      font-weight: 500;
      font-size: 16px;
      line-height: 30px;
      min-height: 38px;
    }
    /deep/ .ant-tabs-nav-list {
      color: hsla(0, 0%, 100%, 0.7);
    }
    /deep/ .ant-tabs-top > .ant-tabs-nav {
      margin-bottom: 0;
    }
    /deep/ .ant-tabs-top {
      clear: both;
      margin-bottom: -17px;
      color: #fff;
      font-weight: 400;
      font-size: 14px;
    }
    /deep/ .ant-tabs-large > .ant-tabs-nav .ant-tabs-tab {
      padding: 6px 0;
    }
    /deep/ .ant-tabs-tab-btn:hover {
      color: #fff;
    }
    /deep/ .ant-tabs-nav::before {
      border-bottom: none;
    }

    /deep/ .ant-tabs-tab-btn {
      font-size: 14px;
      line-height: 22px;
      padding: 0 18px;
    }
    /deep/ .ant-tabs-tab-active {
      .ant-tabs-tab-btn {
        color: #fff;
        text-shadow: 0 0 0.25px currentcolor;
      }
    }
    /deep/ .ant-tabs-nav .ant-tabs-tab:before {
      position: absolute;
      top: -1px;
      left: 0;
      width: 100%;
      border-top: 2px solid transparent;
      border-radius: 2px 2px 0 0;
      transition: all 0.3s;
      content: '';
      pointer-events: none;
    }
    /deep/ .ant-tabs-ink-bar {
      background: linear-gradient(90deg, #7e46f2, #00e6a1);
      border-radius: 8px;
    }
    /deep/ .ant-tabs-tab + .ant-tabs-tab {
      margin: 0;
    }
    /deep/ .ant-card-body {
      padding: 24px 0 0;
    }
  }
</style>
