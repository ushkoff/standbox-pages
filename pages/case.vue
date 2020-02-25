<template>
<div>



  <div class="case-items">
     <div class="case-items__title">
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
      <span>Содержимое кейса</span>
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
    </div>
    <div class="case-items__list">
      <div
        v-for="n in 21"
        :key="n"
        class="case-item"
        :style="`background-image: url('${require('@/assets/img/skins/skindes-sprites.png')}')`"
        style="background-position: -900px 45%"
      >
        <img class="case-item__img" src="@/assets/img/examples/AK-Vulcan.png">
        <span class="case-item__type">AKR</span>
        <span class="case-item__name">Treasure Hunter</span>
      </div>
    </div>
  </div>

</div>
</template>

<script>
export default {
  components: {
    //
  }
}
</script>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';
@import '~assets/less/utils/_mixins';

// styles for .case-item in main.less

.case-items {
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
          .middle-title-diamond();
          background-color: @defPurpleBg;
        }
        .circle:last-child {
          .big-title-diamond();
          background-color: @defPurpleBg;
          margin-left: 14px;
        }
      }
      &:last-child {
        .circle:first-child {
          .big-title-diamond();
          background-color: @defPurpleBg;
        }
        .circle:last-child {
          .middle-title-diamond();
          background-color: @defPurpleBg;
          margin-left: 14px;
        }
      }
    }
  }
  &__list {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }
}

</style>
