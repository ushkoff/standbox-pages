<template>
<div class="items-sidebar">
  <div class="items-sidebar__buttons">
    <div class="btn" :class="{ 'active': activeBtn }" @click="activeBtn = !activeBtn">
      <img src="@/assets/img/app/livedrop/diamond.svg">
    </div>
    <div class="btn" :class="{ 'active': !activeBtn }" @click="activeBtn = !activeBtn">
      <img src="@/assets/img/app/livedrop/view-module.svg">
    </div>
  </div>
  <div class="items-sidebar__livedrop">
    <!-- <div
      class="items-sidebar__livedrop__item"
      :style="`background-image: url('${require('@/assets/img/app/livedrop/livedrop-sprites.png')}')`"
      :class="{ blue: correctItem.quality === 'blue', green: correctItem.quality === 'green', purple: correctItem.quality === 'purple', red: correctItem.quality === 'red', yellow: correctItem.quality === 'yellow' }"
      @mouseover="activeAddInfo = true"
    >
      <div
        class="items-sidebar__livedrop__item--img"
        :style="`background-image: url('${require(`@/assets/${correctItem.img}`)}')`"
      >
      </div>
      <span class="items-sidebar__livedrop__item--name">{{ correctItem.name }}</span>

      <div class="items-sidebar__livedrop__item--info" v-if="activeAddInfo">
        <div class="user-info">
          <img :src="require(`@/assets/${correctItem.userImg}`)">
          <span>{{ correctItem.userName }}</span>
        </div>
        <img :src="require(`@/assets/${correctItem.caseImg}`)" class="case-img">
        <span class="case-type">{{ correctItem.caseName }}</span>
      </div>
    </div> -->

    <div
      v-for="item in items"
      :key="item.id"
      class="items-sidebar__livedrop__item"
      :style="`background-image: url('${require('@/assets/img/app/livedrop/livedrop-sprites.png')}')`"
      :class="{ blue: item.quality === 'blue', green: item.quality === 'green', purple: item.quality === 'purple', red: item.quality === 'red', yellow: item.quality === 'yellow' }"
      @mouseover="showAdditionalInfo"
      @mouseleave="hideAdditionalInfo"
    >
      <!-- уже прописано -->
      <!--  YELLOW background-position: -583px -->
      <!--  RED background-position: -438px -->
      <!--  PURPLE background-position: -295px -->
      <!--  GREEN background-position: -153px -->
      <!--  BLUE background-position: -9px -->
      <div
        class="items-sidebar__livedrop__item--img"
        :style="`background-image: url('${require(`@/assets/${item.img}`)}')`"
      >
      </div>
      <span class="items-sidebar__livedrop__item--name">{{ item.name }}</span>
      <div class="items-sidebar__livedrop__item--info">
        <div class="user-info">
          <img :src="require(`@/assets/${item.userImg}`)">
          <span>{{ item.userName }}</span>
        </div>
        <img :src="require(`@/assets/${item.caseImg}`)" class="case-img">
        <span class="case-type">{{ item.caseName }}</span>
      </div>
    </div>

  </div>
</div>
</template>

<script>
export default {
  data: () => ({
    activeBtn: true,
    activeAddInfo: true,
    items: [
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 2, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 3, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 4, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 5, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 6, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 7, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 8, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 9, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 10, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 11, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 12, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 13, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
      { id: 14, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple', userName: 'Dobrya4ello', userImg: 'img/examples/user-avatar.png', caseName: 'Обычный', caseImg: 'img/examples/csgo-case.png' },
    ]
  }),
  methods: {
    showAdditionalInfo (e) {
      e.currentTarget.lastChild.style.display = 'flex'
    },
    hideAdditionalInfo (e) {
      e.currentTarget.lastChild.style.display = 'none'
    }
  }
}
</script>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';

.items-sidebar {
  background-color: @defBlackTrans;
  @media screen and (max-width: @minWindowWidth) {
    background-color: rgba(0, 0, 0, 0.75)
  }
  width: 128px;
  height: 100%;
  position: fixed;
  right: 0;
  top: 0;
  bottom: 0;
  border-left: 1px solid @defGreyBorder;
  &__buttons {
    display: flex;
    .btn {
      width: 50%;
      height: 34px;
      color: #fff;
      background-color: #292929;
      text-align: center;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .btn.active {
      background-color: @defPurpleBg;
    }
  }
  &__livedrop {
    padding-right: 3px;
    &__item {
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: flex-end;
      width: 100%;
      height: 80px;
      padding-bottom: 3px;
      margin-top: 4px;
      background-size: auto 128%;
      background-repeat: no-repeat;
      text-align: center;
      position: relative;
      &--img {
        position: absolute;
        width: 95%;
        height: 95%;
        background-repeat: no-repeat;
        background-size: contain;
        background-position: center 45%;
        transform: rotate(15deg);
      }
      &--name {
        display: block;
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 16px;
        color: rgba(255, 255, 255, 0.7);
      }

      &--info {
        display: none;
        align-items: center;
        justify-content: space-between;
        flex-direction: column;
        position: absolute;
        left: -175px;
        top: -30px;
        height: 139px;
        width: 139px;
        border: 1px solid @defYellowBorder;
        background: rgba(41, 13, 77, 0.5);
        padding-top: 5px;
        padding-bottom: 8px;
        &:after {
          content: '';
          position: absolute;
          right: -16px;
          top: 50%;
          margin-top: -15px;
          width: 30px;
          height: 30px;
          background: rgba(41, 13, 77, 1);
          transform: rotate(45deg);
          border-top: 1px solid @defYellowBorder;
          border-right: 1px solid @defYellowBorder;
        }
        .user-info {
          display: flex;
          align-items: center;
          img {
            margin-right: 5px;
            width: 20px;
            height: 20px;
            clip-path: polygon(10px 0px, 20px 10px, 10px 20px, 0px 10px);
          }
          span {
            font-family: Roboto Condensed;
            font-style: normal;
            font-weight: normal;
            font-size: 14px;
            line-height: 16px;
            color: #fff;
            white-space: nowrap;
            max-width: 75px;
            overflow: hidden;
          }
        }
        .case-img {
          display: block;
          height: 75px;
        }
        .case-type {
          font-family: Roboto Condensed;
          font-style: normal;
          font-weight: normal;
          font-size: 16px;
          color: @defFontYellow;
        }
      }
    }

    &__item.blue { background-position: -9px }
    &__item.green { background-position: -153px }
    &__item.purple { background-position: -295px }
    &__item.red { background-position: -438px }
    &__item.yellow { background-position: -583px }
  }
}
</style>
