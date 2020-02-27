<template>
<div>
  <div class="special-cases">
    <a
      href="/case"
      class="special-cases__case special-cases__case--green case-block"
      :style="`background-image: url('${require('@/assets/img/cases/everyday-case.png')}')`"
    >
      <div class="case-name">
        <div class="circle"></div>
        <span>Everyday</span>
        <div class="circle"></div>
      </div>
      <div class="case-costs">
        <span>Бесплатный Кейс</span>
      </div>
    </a>
    <a
      href="/case"
      class="special-cases__case special-cases__case--blue case-block"
      :style="`background-image: url('${require('@/assets/img/cases/free4like-case.png')}')`"
    >
      <div class="case-name">
        <div class="circle"></div>
        <span>Free4Like</span>
        <div class="circle"></div>
      </div>
      <div class="case-costs">
        <span>Бесплатный Кейс</span>
      </div>
    </a>
  </div>

  <div class="all-cases">
    <div class="all-cases__title">
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
      <span>Фирменные кейсы</span>
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
    </div>

    <div class="all-cases__cases">
      <a
        v-for="n in 10"
        :key="n"
        href="/case"
        class="case-block"
        :style="`background-image: url('${require('@/assets/img/cases/epic-case.png')}')`"
      >
        <div class="case-name">
          <div class="circle"></div>
          <span>EPIC</span>
          <div class="circle"></div>
        </div>
        <div class="case-costs">
          <span>1 500₽</span>
        </div>
      </a>
    </div>
  </div>

</div>
</template>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';
@import '~assets/less/utils/_mixins';

.special-cases {
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 18px;
  &__case {
    .case-costs span { font-weight: 400 !important }
    &--green {
      .case-name .circle { background-color: @defFontGreen !important }
      .case-costs span { color: @defFontGreen !important }
      &:hover {
        .case-name .circle { box-shadow: 0px 0px 20px 3px @defFontGreen !important }
        .case-costs span { text-shadow: 0px 0px 15px @defFontGreen !important }
      }
    }
    &--blue {
      .case-name .circle { background-color: @defFontBlue !important }
      .case-costs span { color: @defFontBlue !important }
      &:hover {
        .case-name .circle { box-shadow: 0px 0px 20px 3px @defFontBlue !important }
        .case-costs span { text-shadow: 0px 0px 15px @defFontBlue !important }
      }
    }
  }
}

.case-block {
  text-decoration: none;
  cursor: pointer;
  width: 280px;
  height: 333px;
  background-color: transparent;
  text-align: center;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
  padding: 20px;
  margin-top: 20px;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  .case-name {
    display: flex;
    align-items: center;
    justify-content: center;
    .circle {
      .small-title-diamond()
    }
    span {
      display: block;
      font-family: Roboto Condensed;
      font-style: normal;
      font-weight: normal;
      font-size: 18px;
      text-transform: uppercase;
      color: #FFFFFF;
      margin: 0 20px;
    }
  }
  .case-costs {
    span {
      color: @defFontYellow;
      font-family: Roboto Condensed;
      font-style: normal;
      font-weight: bold;
      font-size: 24px;
    }
  }
  &:hover {
    background-color: @defBlackTrans;
    .case-name {
      .circle { box-shadow: 0px 0px 20px 3px @defFontYellow }
    }
    .case-costs {
      span { text-shadow: 0px 0px 15px @defFontYellow }
    }
  }
}

.all-cases {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding-bottom: 250px;
  &__title {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 40px;
    margin-bottom: 20px;
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
          .middle-title-diamond()
        }
        .circle:last-child {
          .big-title-diamond();
          margin-left: 14px;
        }
      }
      &:last-child {
        .circle:first-child {
          .big-title-diamond()
        }
        .circle:last-child {
          .middle-title-diamond();
          margin-left: 14px;
        }
      }
    }
  }
  &__cases {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }
}

</style>
