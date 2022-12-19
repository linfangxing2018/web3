<!--
 * @Author: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @Date: 2022-12-05 21:53:32
 * @LastEditors: linfangxing2018 45490593+linfangxing2018@users.noreply.github.com
 * @LastEditTime: 2022-12-19 20:42:42
 * @FilePath: \web3\src\components\Header\index.vue
 * @Description: 这是默认设置,请设置`customMade`, 打开koroFileHeader查看配置 进行设置: https://github.com/OBKoro1/koro1FileHeader/wiki/%E9%85%8D%E7%BD%AE
-->
<template>
  <a-layout class="layout">
    <a-layout-header class="layout-header">
      <div class="navbox">
        <span class="logo">
          <img src="https://static-prod.upstairs.io/websites/www/assets/common/logo-icon.svg" alt="logo" />
        </span>
        <div class="beta">Beta</div>
        <div class="menuBox">
          <router-link
            :to="item.to"
            class="menuItem"
            :class="{ active: curActive === index }"
            @click="checkNav(index)"
            v-for="(item, index) in navList"
            :key="item.name"
            >{{ item.name }}
            <img
              v-if="item.name === '质押'"
              class="newTag___1Z4WJ"
              src="https://static-prod.upstairs.io/websites/www/assets/common/new_tag.svg"
              alt=""
              srcset=""
            />
          </router-link>
        </div>
        <div class="rightContent">
          <div class="selectLanguage">
            <a-dropdown
              ><a
                >简体中文
                <span role="img" aria-label="caret-down" class="anticon anticon-caret-down" style="margin-left: 8px">
                  <svg
                    viewBox="0 0 1024 1024"
                    focusable="false"
                    data-icon="caret-down"
                    width="1em"
                    height="1em"
                    fill="currentColor"
                    aria-hidden="true"
                  >
                    <path
                      d="M840.4 300H183.6c-19.7 0-30.7 20.8-18.5 35l328.4 380.8c9.4 10.9 27.5 10.9 37 0L858.9 335c12.2-14.2 1.2-35-18.5-35z"
                    />
                  </svg>
                </span>
              </a>
              <template #overlay>
                <a-menu>
                  <a-menu-item>
                    <a href="javascript:;">English</a>
                  </a-menu-item>
                  <a-menu-item>
                    <a href="javascript:;">简体中文</a>
                  </a-menu-item>
                </a-menu>
              </template></a-dropdown
            >
          </div>
          <div class="login">登录</div><div class="signup">注册</div>
        </div>
      </div>
    </a-layout-header>
  </a-layout>
</template>
<script setup lang="ts">
  import { ref } from 'vue';

  // import { useAppStore } from '/@/store';
  // import Header from '/@/components/Header/index.vue';

  // const selectedKeys = ref<string[]>(['1']);
  const navList = ref([
    {
      name: '首页',
      to: '/home',
    },
    {
      name: '新品',
      to: '/newProduct',
    },
    {
      name: '市场',
      to: '/home',
    },
    {
      name: '质押',
      to: '/home',
    },
    {
      name: '公告',
      to: '/home',
    },
  ]);
  const curActive = ref(0);
  const checkNav = (index: number) => {
    curActive.value = index;
  };
</script>

<style lang="less">
  .layout {
    a {
      color: #fff;
      text-decoration: none;
      background-color: transparent;
      outline: none;
      cursor: pointer;
      transition: color 0.3s;
    }
    .layout-header {
      background: rgba(19, 29, 41, 0.2);
      position: fixed;
      top: 0;
      left: 0;
      z-index: 99;
      display: flex;
      justify-content: center;
      width: 100%;
      height: 68px;
      line-height: 68px;
      backdrop-filter: blur(15px);
      padding: 0 50px;
      color: #fff;
      .navbox {
        display: flex;
        justify-content: space-between;
        width: 1250px;
        .logo {
          margin-right: 24px;
          color: #fff;
          font-weight: 700;
          cursor: pointer;
          img {
            width: 119px;
          }
        }
        .beta {
          width: 38px;
          height: 16px;
          border: 1px solid hsla(0, 0%, 100%, 0.5);
          border-radius: 2px;
          font-size: 11px;
          line-height: 14px;
          color: hsla(0, 0%, 100%, 0.5);
          text-align: center;
          margin-top: 28px;
          margin-left: -12px;
        }
        .menuBox {
          flex: 1 1;
          text-align: center;

          .menuItem {
            display: inline-block;
            margin: 0 16px;
            color: hsla(0, 0%, 100%, 0.7);
            position: relative;
            .newTag {
              margin: -5px 0 0 5px;
              vertical-align: middle;
              border-style: none;
            }
          }
          .active {
            color: #fff;
            font-weight: 500;
          }
        }
        .rightContent {
          display: flex;
          align-items: center;
          .selectLanguage {
            margin-right: 16px;
            a {
              .anticon {
                margin-left: 8px;
                display: inline-block;
                color: inherit;
                font-style: normal;
                line-height: 0;
                text-align: center;
                text-transform: none;
                vertical-align: -0.125em;
                text-rendering: optimizelegibility;
                -webkit-font-smoothing: antialiased;
              }
            }
          }
          .login {
            margin-right: 16px;
            height: 22px;
            line-height: 22px;
            color: #fff;
            cursor: pointer;
          }
          .signup {
            background: hsla(0, 0%, 100%, 0.2);
            border: 1px solid #fff;
            border-radius: 2px;
            height: 36px;
            line-height: 36px;
            font-weight: 400;
            font-size: 14px;
            color: #fff;
            padding: 0 10px;
            cursor: pointer;
          }
        }
      }
    }
  }
</style>
