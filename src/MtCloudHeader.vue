<template>
  <div class="mt-cloud-header top">
    <div class="Widget logo ">
      <a href="javascript:;">
        <img src="./assets/images/logo.png" alt="" title="美图云">
      </a>
    </div>
    <div class="Widget left-menu">
      <li><a href="#">总览</a></li>
      <li class="drop-down">
        <a href="#">产品与服务
          <span class="triangle_border_down">
                </span>
        </a>
        <ul class="drop-down-content">
          <li><a href="#">Vector平台</a></li>
        </ul>
      </li>
    </div>
    <div class="Widget right-menu">
      <li class="user drop-down">
        <a href="#" :title="userName"><i class="icon-user"></i><span>{{userName}}</span>
        <span class="triangle_border_down">
        </span>
        </a>
        <ul class="drop-down-content">
          <li><a href="#" @click="handleLogout">退出</a></li>
        </ul>
      </li>
      <li class="help"><a href="http://yun.meitu-int.com/document/"><i class="icon-help"></i>帮助</a></li>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'MtCloudHeader',
    props: {
      userName: {
        type: String,
        required: true
      },
    },
    data() {
      return {
        run: false,
      }
    },
    methods: {
      handleLogout() {
        this.$emit('logout');
      }
    },
    watch: {},
    mounted() {
    }
  }
</script>


<style type="text/scss" lang="scss">
  * {
    margin: 0;
    padding: 0;
  }
  li {
    list-style-type: none;
  }
  $height: 48px;
  $top-title-hover-color: #1C80FF;
  $top-title-hover-menu-color: #2E2A38;
  $menu-background-color: #383345;

  .mt-cloud-header.top {
    position: fixed;
    z-index: 3;
    top: 0;
    left: 0;
    right: 0;
    min-width: 1200px;
    height: $height;
    padding: 0;
    background: $menu-background-color;
    box-shadow: 0 2px 8px rgba(128, 142, 150, 0.2);
    color: white;
    font-size: 14px;
    .Widget.logo {
      float: left;
      display: block;
      box-sizing: border-box;
      width: 156px;
      height: inherit;
      a {
        position: relative;
        display: table-cell;
        height: inherit;
        margin: 0 auto;
        text-align: center;
        vertical-align: middle;
        img {
          display: inline-block;
          height: 30px;
          vertical-align: middle;
          margin: 0 auto;
          margin-left: 25px;
        }
      }
    }
    .Widget.left-menu {
      float: left;
      width: 400px;
      & > li {
        float: left;
        a {
          display: block;
          text-decoration: none;
          width: 140px;
          height: 48px;
          text-align: center;
          line-height: 50px;
          color: #929097;
          background: $menu-background-color;
          &:hover {
            color: white;
            background-color: $top-title-hover-menu-color;
            .triangle_border_down {
              border-color: white transparent transparent;
            }
          }
        }
      }
      .drop-down {
        position: relative;
        .triangle_border_down {
          width: 0;
          height: 0;
          border-width: 4px 4px 0;
          border-style: solid;
          border-color: #929097 transparent transparent;
          position: absolute;
          top: 23px;
          right: 20px;
        }
      }
      .drop-down-content {
        padding: 0;
        display: none;
        position: absolute;
      }
      .drop-down:hover .drop-down-content {
        display: block;
      }
      .drop-down:hover a {
        background-color: $top-title-hover-menu-color;
      }
    }
    .Widget.right-menu {
      float: right;
      width: 400px;
      & > li {
        float: right;
        a {
          display: block;
          position: relative;
          text-decoration: none;
          width: 140px;
          height: 48px;
          text-align: center;
          line-height: 50px;
          color: #929097;
          background: $menu-background-color;
          &:hover {
            color: white;
            background-color: $top-title-hover-menu-color;
            .triangle_border_down {
              border-color: white transparent transparent;
            }
            .icon-help {
              background-image: url(./assets/images/icon-help-hover.png);
            }
            .icon-user {
              background-image: url(./assets/images/icon-user-hover.png);
            }
          }
          .icon-help {
            position: absolute;
            margin-top: 17px;
            margin-left: -19px;
            width: 16px;
            height: 16px;
            background-image: url(./assets/images/icon-help.png);
            background-size: 100% 100%;
          }
          .icon-user {
            position: absolute;
            margin-top: 17px;
            margin-left: -23px;
            width: 16px;
            height: 16px;
            background-image: url(./assets/images/icon-user.png);
            background-size: 100% 100%;

          }
        }

      }
      .help a {
        text-align: right;
        width: 50px;
        padding-right: 10px;
      }
      .user a {
        max-width: 160px;
        span {
          display: inline-block;
          max-width: 80px;
          text-overflow: ellipsis;
          overflow: hidden;
          white-space: nowrap;
        }
      }
      .drop-down {
        position: relative;
        .triangle_border_down {
          position: absolute;
          margin-top: 24px;
          margin-left: 4px;
          width: 0;
          height: 0;
          border-width: 4px 4px 0;
          border-style: solid;
          border-color: #929097 transparent transparent;

        }
      }
      .drop-down-content {
        padding: 0;
        display: none;
        position: absolute;
      }
      .drop-down:hover .drop-down-content {
        display: block;
      }
      .drop-down:hover a {
        background-color: $top-title-hover-menu-color;
      }
    }

  }
</style>
