<template>
<div>
  <div class="user-profile">
    <div class="user-profile__title">
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
      <span>HATSON_TM</span>
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
    </div>
    <span class="user-profile__type">Профиль</span>
    <div class="user-profile__stat">

      <div class="first-block">
        <div class="user-profile__stat__block">
          <span class="num">5 000</span>
          <span class="type">Кейсов</span>
        </div>
        <div class="user-profile__stat__block">
          <span class="num">5 000</span>
          <span class="type">Контрактов</span>
        </div>
      </div>

      <div class="user-profile__img__container">
        <div
          class="img"
          :style="`background-image: url('${require('@/assets/img/examples/user-avatar.png')}')`"
        >
        </div>
      </div>

      <div class="last-block">
        <div class="user-profile__stat__block">
          <div
            class="skin-img"
            :style="`background-image: url('${require('@/assets/img/examples/AK-Vulcan.png')}')`"
          >
          </div>
          <span class="type">Топовый дроп</span>
        </div>
        <div class="user-profile__stat__block">
          <div
            class="case-img"
            :style="`background-image: url('${require('@/assets/img/examples/csgo-case.png')}')`"
          >
          </div>
          <span class="type">Любимый кейс</span>
        </div>
      </div>

    </div>
  </div>

  <div class="user-drop">
    <div class="user-drop__buttons">
      <button class="user-drop__buttons--purple">Продать всё за <span>10.000₽</span></button>
      <button class="user-drop__buttons--grey">Забрать всё</button>
    </div>
    <div class="user-drop__items">
      <div
        v-for="n in 21"
        :key="n"
        class="case-item"
        :style="`background-image: url('${require('@/assets/img/pages/skindes-sprites.png')}')`"
        style="background-position: -900px 45%"
      >
        <!--  YELLOW -900px -->
        <!--  RED -675px -->
        <!--  PURPLE -455px -->
        <!--  GREEN -230px -->
        <!--  BLUE -10px -->
        <div class="case-item__buttons">
          <img src="@/assets/img/pages/plus-inv.svg">
          <img src="@/assets/img/pages/minus-inv.svg">
        </div>
        <img class="case-item__img" src="@/assets/img/examples/AK-Vulcan.png">
        <span class="case-item__type">AKR</span>
        <span class="case-item__name">Treasure Hunter</span>
      </div>
    </div>
  </div>

</div>
</template>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';
@import '~assets/less/utils/_mixins';

.user-profile {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  &__title {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 40px;
    margin-bottom: 8px;
    span {
      font-family: Roboto Condensed;
      font-style: normal;
      font-weight: bold;
      font-size: 24px;
      text-transform: uppercase;
      color: #fff;
      margin: 0 22px;
    }
    .circles {
      display: flex;
      align-items: center;
      &:first-child {
        .circle:first-child {
          .middle-title-diamond();
        }
        .circle:last-child {
          .big-title-diamond();
          margin-left: 14px;
        }
      }
      &:last-child {
        .circle:first-child {
          .big-title-diamond();
        }
        .circle:last-child {
          .middle-title-diamond();
          margin-left: 14px;
        }
      }
    }
  }
  &__type {
    font-family: Roboto Condensed;
    font-style: normal;
    font-weight: normal;
    font-size: 16px;
    text-transform: uppercase;
    color: #C5C5C5;
  }
  &__img__container {
    position: relative;
    height: 188px;
    width: 188px;
    margin-left: 150px;
    margin-right: 100px;
    .img {
      display: flex;
      justify-content: center;
      align-items: center;
      clip-path: polygon(95px 0px, 190px 95px, 95px 190px, 0px 95px);
      height: 188px;
      width: 188px;
      background-position: center;
      background-size: cover;
      background-repeat: no-repeat;
    }
    @media screen and (max-width: 1625px) {
      margin-left: 70px;
      margin-right: 20px;
    }
  }
  &__stat {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-top: 20px;
    position: relative;
    right: -82px;
    @media screen and (max-width: 1625px) {
      right: -37px;
    }
    .first-block, .last-block {
      display: flex;
      justify-content: center;
      align-items: center;
    }
    &__block {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      .skin-img {
        width: 270px;
        height: 75px;
        transform: rotate(15deg);
        margin-bottom: 32px;
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        @media screen and (max-width: 1625px) {
          width: 200px;
          height: 50px;
        }
      }
      .case-img {
        width: 175px;
        height: 120px;
        margin: 15px;
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        @media screen and (max-width: 1625px) {
          width: 125px;
          height: 80px;
        }
      }
      .num {
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 48px;
        color: @defFontYellow;
      }
      .type {
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        text-transform: uppercase;
        color: #fff;
      }
    }
    .first-block {
      .user-profile__stat__block {
        &:first-child {
          margin-right: 80px;
        }
        @media screen and (max-width: 1625px) {
          &:first-child {
            margin-right: 50px;
          }
        }
      }
    }
    .last-block {
      .user-profile__stat__block {
        &:last-child {
          margin-bottom: 42px;
          margin-left: 30px;
          @media screen and (max-width: 1625px) {
            margin-bottom: 28px;
          }
        }
      }
    }
  }
}

.user-drop {
  margin-top: 33px;
  &__buttons {
    margin-left: 100px;
    margin-top: 66px;
    display: flex;
    &--purple, &--grey {
      position: relative;
      cursor: pointer;
      outline: none;
      border: none;
      height: 42px;
      background-color: @defPurpleBg;
      font-family: Roboto Condensed;
      font-style: normal;
      font-weight: normal;
      font-size: 18px;
      color: #FFFFFF;
      span {
        font-weight: bold;
        color: @defFontYellow;
      }
      &:before, &:after {
        z-index: -1;
        box-sizing: border-box;
        position: absolute;
        content: '';
        width: 30.5px;
        height: 30.5px;
        background-color: @defPurpleBg;
      }
      &:before {
        top: 6px;
        left: -15px;
        transform: rotate(45deg);
      }
      &:after {
        top: 6px;
        right: -15px;
        transform: rotate(-45deg);
      }
      &:hover {
        background-color: @defPurpleBgHover;
        &:before, &:after { background-color: @defPurpleBgHover; }
      }
    }
    &--grey {
      margin-left: 65px;
      background-color: @defGreyBorder;
      &:before, &:after {
        background-color: @defGreyBorder;
      }
      &:hover {
        background-color: @defGreyBgHover;
        &:before, &:after { background-color: @defGreyBgHover }
      }
    }
  }
  &__items {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    margin-top: 5px;
    .case-item {
      position: relative;
      &__buttons {
        display: none;
        position: absolute;
        right: 8px;
        top: -15px;
        img { cursor: pointer }
        img:last-child {
          margin: 0;
        }
      }
      &:hover {
        .case-item__buttons {
          display: flex;
        }
      }
    }
  }
}

</style>
