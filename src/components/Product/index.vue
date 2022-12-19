<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-19 20:42:15
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2022-12-19 22:26:52
 * @FilePath: \web3\src\views\newProduct\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <div class="Product" style="width: 393px; height: 477px">
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
</template>

<script setup lang="ts"></script>

<style lang="less" scoped>
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
</style>
