<template>
<header>
  <div class="header-list">
    <div class="header-list__item">
      <img src="@/assets/img/app/header/case.svg">
      <div>
        <div class="header-list__item--number">140 320 232</div>
        <div class="header-list__item--name">Кейсов открыто</div>
      </div>
    </div>
    <div class="header-list__item">
      <img src="@/assets/img/app/header/clipboard-text.svg">
      <div>
        <div class="header-list__item--number">11 003 001</div>
        <div class="header-list__item--name">Контрактов</div>
      </div>
    </div>
    <div class="header-list__item">
      <img src="@/assets/img/app/header/user.svg">
      <div>
        <div class="header-list__item--number">2 500 000</div>
        <div class="header-list__item--name">Пользователей</div>
      </div>
    </div>
    <div class="header-list__item">
      <img src="@/assets/img/app/header/eye.svg">
      <div>
        <div class="header-list__item--number">1 100</div>
        <div class="header-list__item--name">Онлайн</div>
      </div>
    </div>
  </div>
  <div class="header-social">
    <div class="header-social__link">
      <a href="https://vk.com/" target="blank"><img src="@/assets/img/app/social-icons/vk.svg"></a>
    </div>
    <div class="header-social__link">
      <a href="#" target="blank"><img src="@/assets/img/app/social-icons/youtube.svg"></a>
    </div>
    <div class="header-social__link">
      <a href="#" target="blank"><img src="@/assets/img/app/social-icons/instagram.svg"></a>
    </div>
    <div class="header-social__link">
      <a href="#" target="blank"><img src="@/assets/img/app/social-icons/telegram.svg"></a>
    </div>
  </div>
</header>
</template>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid @defGreyBorder;
  padding-top: 16px;
  padding-left: 50px;
  padding-right: 48px;
  padding-bottom: 24px;
  .header-list {
    display: flex;
    align-items: center;
    .header-list__item {
      display: flex;
      align-items: center;
      margin-left: 60px;
      &:first-child { margin-left: 0 }
      img {
        width: 70px;
        height: 70px;
        margin-right: 9px;
      }
      &--number {
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: bold;
        font-size: 24px;
        line-height: 28px;
        color: @defFontYellow;
      }
      &--name {
        margin-top: 3px;
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 16px;
        color: #FFFFFF;
      }
    }
  }
  .header-social {
    display: flex;
    align-items: center;
  }
}
</style>
