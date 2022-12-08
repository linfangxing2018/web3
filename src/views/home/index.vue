<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-05 22:25:12
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2022-12-08 00:28:05
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
          <div class="switchBox">
            <div class="switch switchLef"> </div>
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
          .switchBox {
            width: 1250px;
            position: relative;
            margin: 0 auto;
            .switchLef {
              left: -64px;
              top: 50%;
              color: #fff;
            }
            .switch {
              width: 40px;
              height: 62px;
              line-height: 62px;
              text-align: center;
              background: hsla(0, 0%, 100%, 0.1);
              border: 1px solid hsla(0, 0%, 100%, 0.3);
              border-radius: 2px;
              position: absolute;
              margin-top: -300px;
              cursor: pointer;
            }
          }
        }
      }
    }
  }
</style>
