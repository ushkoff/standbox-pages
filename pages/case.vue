<template>
<div>

  <Roulette
    v-if="spin"
    ref="roulette"
    :dropedItemId="dropedItem.id"
    :dropedItemType="dropedItem.type"
    :dropedItemName="dropedItem.name"
    :dropedItemImg="dropedItem.img"
    :dropedItemQuality="dropedItem.quality"
  >
  </Roulette>

  <div class="open-case" v-if="openCaseInfo">
    <div class="open-case__title">
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
      <span>Ножевой</span>
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
    </div>
    <span class="open-case__type">Кейс</span>
    <div
      class="open-case__img"
      :style="`background-image: url('${require('@/assets/img/cases/knife-case.png')}')`"
    >
      <img class="open-case__img__arrow arrow-left" src="@/assets/img/pages/arrows.svg">
      <img class="open-case__img__arrow arrow-right" src="@/assets/img/pages/arrows.svg">
    </div>
    <button
      class="open-case__btn"
      @click="startRoulette"
    >
      Открыть кейс за <span>500₽</span>
    </button>
    <div class="open-case__times">
      <ul>
        <li>x1</li>
        <li class="active">x2</li>
        <li>x3</li>
        <li>x4</li>
        <li>x5</li>
        <li>x10</li>
      </ul>
    </div>
  </div>

  <div class="case-opened" v-if="dropedInfo">
    <div class="case-opened__title">
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
      <span>{{ dropedItem.name }}</span>
      <div class="circles">
        <div class="circle"></div>
        <div class="circle"></div>
      </div>
    </div>
    <span class="case-opened__type">{{ dropedItem.type }}</span>
    <div
      class="case-opened__item"
      :class="{ blue: dropedItem.quality === 'blue', green: dropedItem.quality === 'green', purple: dropedItem.quality === 'purple', red: dropedItem.quality === 'red', yellow: dropedItem.quality === 'yellow' }"
      :style="`background-image: url('${require('@/assets/img/pages/skindrop-sprites.png')}')`"
    >
      <!-- уже прописано -->
      <!--  YELLOW background-position: -4155px -100px -->
      <!--  RED background-position: -3120px -100px -->
      <!--  PURPLE background-position: -2080px -100px -->
      <!--  GREEN background-position: -1035px -100px -->
      <!--  BLUE background-position: -0px -100px -->
      <div
        class="case-opened__item__img"
        :style="`background-image: url('${require(`@/assets/${dropedItem.img}`)}`"
      >
      </div>
    </div>
    <div class="case-opened__buttons">
      <button class="case-opened__buttons--grey">Попробовать ещё</button>
      <button class="case-opened__buttons--purple">Продать за <span>{{ dropedItem.cost }}</span></button>
      <button class="case-opened__buttons--grey">На главную</button>
    </div>
  </div>

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
        v-for="item in caseItems"
        :key="item.id"
        class="case-item"
        :style="`background-image: url('${require('@/assets/img/pages/skindes-sprites.png')}')`"
        :class="{ blue: item.quality === 'blue', green: item.quality === 'green', purple: item.quality === 'purple', red: item.quality === 'red', yellow: item.quality === 'yellow' }"
      >
        <!-- уже прописано -->
        <!--  YELLOW background-position: -900px 45% -->
        <!--  RED background-position: -675px 45% -->
        <!--  PURPLE background-position: -455px 45% -->
        <!--  GREEN background-position: -230px 45% -->
        <!--  BLUE background-position:-10px 45% -->
        <div
          class="case-item__img"
          :style="`background-image: url('${require(`@/assets/${item.img}`)}')`"
        >
        </div>
        <span class="case-item__type">{{ item.type }}</span>
        <span class="case-item__name">{{ item.name }}</span>
      </div>
    </div>
  </div>

</div>
</template>

<script>
import Roulette from '@/components/case-opening/Roulette'
import rouletteConfig from '@/config/roulette'

export default {
  data: () => ({
    openCaseInfo: true,
    spin: false,
    spinTime: rouletteConfig.spinTime,
    afterSpinDelay: rouletteConfig.afterSpinDelay,
    dropedInfo: false,

    dropedItem: {
      id: 1337,
      type: 'AWP',
      name: 'FINAL DROP',
      img: 'img/examples/M4A4-DesolateSpace.png',
      quality: 'yellow',
      cost: '10.500₽'
    },

    caseItems: [
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 2, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 3, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 4, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 5, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 6, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 7, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 8, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 9, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 10, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 11, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 12, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 13, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 14, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 15, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 16, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 17, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 18, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 19, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 20, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 21, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
    ]
  }),
  components: {
    Roulette
  },
  computed: {
    fullSpinTime () {
      return this.spinTime + this.afterSpinDelay
    }
  },
  methods: {
    startRoulette () {
      this.openCaseInfo = false
      this.spin = true
      this.$nextTick(() => {
        this.$refs.roulette.roll()
      })
      setTimeout(() => {
        this.spin = false
        this.dropedInfo = true
      }, this.fullSpinTime)
    }
  }
}
</script>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';
@import '~assets/less/utils/_mixins';

.open-case {
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
  &__img {
    height: 310px;
    width: 400px;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    margin-top: 25px;
    position: relative;
    &__arrow {
      position: absolute;
      top: 28%;
    }
    .arrow-left {
      left: -79%;
      @media screen  and (max-width: 1500px) {
        left: -55%;
      }
    }
    .arrow-right {
      right: -79%;
      transform: rotate(180deg);
      @media screen  and (max-width: 1500px) {
        right: -55%;
      }
    }
  }
  &__btn {
    position: relative;
    cursor: pointer;
    outline: none;
    border: none;
    width: 295px;
    height: 65px;
    background-color: @defPurpleBg;
    border-bottom: 4px solid @defPurpleBorder;
    font-family: Roboto Condensed;
    font-style: normal;
    font-weight: normal;
    font-size: 24px;
    color: #FFFFFF;
    margin-top: 33px;
    span {
      font-weight: bold;
      color: @defFontYellow;
    }
    &:before, &:after {
      z-index: -1;
      box-sizing: border-box;
      position: absolute;
      content: '';
      width: 45.5px;
      height: 45.5px;
      background-color: @defPurpleBg;
      border-bottom: 4px solid @defPurpleBorder;
    }
    &:before {
      top: 9px;
      left: -23px;
      transform: rotate(45deg);
    }
    &:after {
      top: 9px;
      right: -23px;
      transform: rotate(-45deg);
    }
    &:hover {
      background-color: @defPurpleBgHover;
      &:before, &:after { background-color: @defPurpleBgHover; }
    }
  }
  &__times {
    height: 38px;
    width: 295px;
    border-top: 1px solid @defPurpleBorder;
    border-bottom: 1px solid @defPurpleBorder;
    margin-top: 22px;
    ul {
      height: 100%;
      list-style: none;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      li {
        height: 100%;
        box-sizing: border-box;
        cursor: pointer;
        font-family: Roboto Condensed;
        font-style: normal;
        font-weight: normal;
        font-size: 18px;
        line-height: 38px;
        color: #fff;
        padding: 0 15px;
        border-left: 1px solid @defPurpleBorder;
        &:first-child {
          border-left: none;
          position: relative;
          &:before {
            box-sizing: border-box;
            z-index: -1;
            content: '';
            position: absolute;
            width: 27px;
            height: 27px;
            top: 4.25px;
            left: -14px;
            border-left: 1px solid @defPurpleBorder;
            border-bottom: 1px solid @defPurpleBorder;
            transform: rotate(45deg);
            clip-path: polygon(-1px 27px, 1px 0, 29px 28px);
          }
        }
        &:last-child {
          position: relative;
          &:after {
            box-sizing: border-box;
            z-index: -1;
            content: '';
            position: absolute;
            width: 27px;
            height: 27px;
            top: 4.25px;
            right: -14px;
            border-right: 1px solid @defPurpleBorder;
            border-bottom: 1px solid @defPurpleBorder;
            transform: rotate(-45deg);
            clip-path: polygon(27px -1px, 28px 28px, -1px 27px);
          }
        }
        &:hover {
          background-color: rgba(109, 28, 212, 0.33);
          &:before, &:after {
            background-color: rgba(109, 28, 212, 0.33);
          }
        }
      }
      li.active {
        box-sizing: border-box;
        background-color: @defPurpleBg;
        border-bottom: 3px solid @defPurpleBorder;
        &:before, &:after {
          background-color: @defPurpleBg;
          border-bottom: 3px solid @defPurpleBorder;
        }
      }
    }
  }
}

.case-opened {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-bottom: 34px;
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
  &__item {
    background-repeat: no-repeat;
    background-size: auto 520px;
    height: 300px;
    &__img {
      width: 530px;
      height: 300px;
      margin-top: 45px;
      background-repeat: no-repeat;
      background-size: contain;
      background-position: center;
    }
  }

  &__item.blue { background-position: -0px -100px }
  &__item.green { background-position: -1035px -100px }
  &__item.purple { background-position: -2080px -100px }
  &__item.red { background-position: -3120px -100px }
  &__item.yellow { background-position: -4155px -100px }

  &__buttons {
    margin-top: 66px;
    width: 882px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    &--purple, &--grey {
      position: relative;
      cursor: pointer;
      outline: none;
      border: none;
      width: 240px;
      height: 65px;
      background-color: @defPurpleBg;
      border-bottom: 4px solid @defPurpleBorder;
      font-family: Roboto Condensed;
      font-style: normal;
      font-weight: normal;
      font-size: 24px;
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
        width: 45.5px;
        height: 45.5px;
        background-color: @defPurpleBg;
        border-bottom: 4px solid @defPurpleBorder;
      }
      &:before {
        top: 9px;
        left: -23px;
        transform: rotate(45deg);
      }
      &:after {
        top: 9px;
        right: -23px;
        transform: rotate(-45deg);
      }
      &:hover {
        background-color: @defPurpleBgHover;
        &:before, &:after { background-color: @defPurpleBgHover; }
      }
    }
    &--grey {
      width: 210px;
      background-color: @defGreyBorder;
      border-color: #222122;
      &:before, &:after {
        background-color: @defGreyBorder;
        border-color: #222122;
      }
      &:hover {
        background-color: @defGreyBgHover;
        &:before, &:after { background-color: @defGreyBgHover }
      }
    }
  }
}

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
    margin-top: 52px;
    margin-bottom: 5px;
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
