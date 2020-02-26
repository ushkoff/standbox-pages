<template>
<div class="user-sidebar">
  <div class="user-sidebar__logo">
    <a href="/">Standbox</a>
  </div>
  <!-- <a href="vk.com" class="user-sidebar__login">
    <img src="@/assets/img/app/social-icons/vk-login.svg">
    <span>Войти</span>
  </a> -->
  <div class="user-sidebar__user-info">
    <a href="#" class="logout-btn">
      <img src="@/assets/img/app/logout.svg" alt="logout">
    </a>
    <div class="user">
      <img src="@/assets/img/examples/user-avatar.png" class="user__avatar">
      <div>
        <div class="user__name text-break">Илья C.</div>
        <a href="#" class="user__balance">10.999₽</a>
      </div>
    </div>
  </div>
  <div class="user-sidebar__menu">
    <ul>
      <li>
        <a href="/"><img src="@/assets/img/app/menu-icons/home.svg">Главная</a>
      </li>
      <li>
        <a href="/case"><img src="@/assets/img/app/menu-icons/clipboard-text.svg">Контракты</a>
      </li>
      <li>
        <a href="/profile"><img src="@/assets/img/app/menu-icons/user.svg">Профиль</a>
      </li>
      <li>
        <a href="/"><img src="@/assets/img/app/menu-icons/plus-circle.svg">Пополнение</a>
      </li>
    </ul>
  </div>
</div>
</template>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';

.user-sidebar {
  background-color: @defBlackTrans;
  width: 220px;
  height: 100%;
  position: fixed;
  left: 0;
  top: 0;
  bottom: 0;
  border-right: 1px solid @defGreyBorder;
  &__logo {
    width: 100%;
    height: 90px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-bottom: 1px solid @defGreyBorder;
    a {
      display: block;
      font-family: Roboto Condensed;
      font-style: normal;
      font-weight: bold;
      font-size: 24px;
      text-transform: uppercase;
      color: #fff;
      text-decoration: none;
    }
  }
  &__login {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: @defPurpleBg;
    height: 90px;
    border-bottom: 5px solid @defPurpleBorder;
    text-decoration: none;
    span {
      margin-left: 10px;
      font-family: Roboto Condensed;
      font-style: normal;
      font-weight: bold;
      font-size: 24px;
      text-transform: uppercase;
      color: @defFontYellow;
    }
  }
  &__user-info {
    padding: 10px;
    width: 100%;
    border-bottom: 1px solid @defGreyBorder;
    .logout-btn {
      cursor: pointer;
      position: absolute;
      right: 10px;
    }
    .user {
      display: flex;
      align-items: center;
      padding: 7px;
      margin-top: 20px;
      margin-bottom: 15px;
      &__avatar {
        margin-right: 15px;
        width: 50px;
        height: 50px;
        clip-path: polygon(25px 0px, 50px 25px, 25px 50px, 0px 25px);
      }
      &__name {
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        color: #fff;
        margin-bottom: 10px;
        word-break: break-word;
        padding-right: 10px;
      }
      &__balance {
        position: relative;
        background-color: @defPurpleBg;
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: bold;
        font-size: 24px;
        color: @defFontYellow;
        text-decoration: none !important;
        margin-left: 10px;
        &:before {
          z-index: -1;
          content: '';
          width: 20.5px;
          height: 20.5px;
          background-color: @defPurpleBg;
          position: absolute;
          left: -10px;
          top: 4px;
          transform: rotate(45deg)
        }
        &:after {
          z-index: -1;
          content: '';
          width: 20.5px;
          height: 20.5px;
          background-color: @defPurpleBg;
          position: absolute;
          right: -10px;
          top: 4px;
          transform: rotate(45deg)
        }
        &:hover {
          background-color: @defPurpleBgHover;
          &:before, &:after {
            background-color: @defPurpleBgHover;
          }
        }
      }
    }
  }
  &__menu {
    padding-top: 5px;
    ul { padding: 0 }
    ul li {
      list-style: none;
      display: flex;
      align-items: center;
      border-bottom: 4px solid transparent;
      a {
        display: flex;
        align-items: center;
        img {
          width: 24px;
          height: 24px;
          margin-right: 10px;
        }
        width: 100%;
        height: 100%;
        padding: 5px 17px 2px 17px;
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 25px;
        color: #fff;
        text-decoration: none;
      }
      &:hover {
        background-color: @defPurpleBgHover;
        border-bottom: 4px solid @defPurpleBorder;
      }
    }
  }
}

</style>
