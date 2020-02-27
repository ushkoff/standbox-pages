<template>
<div class="roulette">
  <div class="roulette__case-title">
    <div class="circles">
      <div class="circle"></div>
      <div class="circle"></div>
    </div>
    <span>Обычный</span>
    <div class="circles">
      <div class="circle"></div>
      <div class="circle"></div>
    </div>
  </div>
  <span class="roulette__case-type">Кейс</span>
  <div
    class="roulette__spinner"
    :style="`background-image: url('${require('@/assets/img/pages/frame.svg')}')`"
  >
    <div class="roulette__spinner__items-list">
      <div ref="spinContainer" :style="containerStyles"></div>
        <div
          v-for="item in items"
          :key="item.id"
          class="roulette__spinner__items-list__item"
          :class="{ blue: item.quality === 'blue', green: item.quality === 'green', purple: item.quality === 'purple', red: item.quality === 'red', yellow: item.quality === 'yellow' }"
        >
          <!-- уже прописано -->
          <!--  YELLOW border-color: #FFD600; box-shadow: inset 0px 2px 50px 0 rgba(100, 88, 0, 0.75) -->
          <!--  RED border-color: #FF0000; box-shadow: inset 0px 2px 50px 0 rgba(255, 0, 0, 0.25) -->
          <!--  PURPLE border-color: #EB00FF; box-shadow: inset 0px 2px 50px 0 rgba(92, 0, 100, 0.75) -->
          <!--  GREEN border-color: #5CBAC7; box-shadow: inset 0px 2px 50px 0 rgba(36, 73, 78, 0.75) -->
          <!--  BLUE border-color: #026FF4; box-shadow: inset 0px 2px 50px 0 rgba(1, 44, 96, 0.75) -->
          <img class="item-img" :src="require(`@/assets/${item.img}`)">
          <span class="item-type">{{ item.type }}</span>
          <span class="item-name">{{ item.name }}</span>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
import rouletteConfig from '@/config/roulette'

export default {
  name: 'roulette',
  props: [
    'dropedItemId',
    'dropedItemType',
    'dropedItemName',
    'dropedItemImg',
    'dropedItemQuality'
  ],
  data: () => ({
    itemWidth: 192,
    spinTime: rouletteConfig.spinTime,
    spinDelay: 50,

    items: [

      // 70 items before drop

      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 2, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 3, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 4, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 5, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'blue' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
      { id: 1, type: 'AKR', name: 'Treasure Hunter', img: 'img/examples/AK-Vulcan.png', quality: 'green' },
      { id: 2, type: 'M4A4', name: 'Desolate Space', img: 'img/examples/M4A4-DesolateSpace.png', quality: 'purple' },
      { id: 3, type: 'AWP', name: 'Asiimov', img: 'img/examples/AWP-Asiimov.png', quality: 'red' },
    ]
  }),
  computed: {
    containerStyles () {
      return {
        marginLeft: '0',
        transition: 'none',
        width: `${this.itemWidth * this.items.length}px`
      }
    },
    marginToSpin () {
      return this.itemWidth * 60 - 190
    }
  },
  methods: {
    roll () {
      let dropedItem = {
        id: this.dropedItemId,
        type: this.dropedItemType,
        name: this.dropedItemName,
        img: this.dropedItemImg,
        quality: this.dropedItemQuality
      }
      this.items.splice(69, 1, dropedItem)

      setTimeout(() => {
        this.$refs.spinContainer.style.marginLeft = `-${this.marginToSpin}px`
        this.$refs.spinContainer.style.transition = `margin-left ${this.spinTime / 1000}s cubic-bezier(0.215, 0.61, 0.355, 1)`
      }, this.spinDelay)
    }
  }
}
</script>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';
@import '~assets/less/utils/_mixins';

.roulette {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  &__case-title {
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
  &__case-type {
    font-family: Roboto Condensed;
    font-style: normal;
    font-weight: normal;
    font-size: 16px;
    text-transform: uppercase;
    color: #C5C5C5;
  }
  &__spinner {
    width: 1028px;
    height: 144px;
    margin-top: 103px;
    margin-bottom: 45px;
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    overflow: hidden;
    &__items-list {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: nowrap;
      height: 100%;
      // padding-left: 190px;
      clip-path: polygon(46px 72px, 112px 0, 917px 0, 982px 72px, 917px 144px, 112px 144px);
      &__item {
        z-index: -1;
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        box-sizing: border-box;
        border: 2px solid #fff;
        height: 120px;
        width: 210px;
        margin-left: 3px;
        .item-img {
          width: 185px;
          transform: rotate(15deg);
          z-index: -1;
        }
        .item-type {
          position: absolute;
          left: 7px;
          bottom: 23px;
          font-family: Roboto Condensed;
          font-style: normal;
          font-weight: normal;
          font-size: 16px;
          color: #fff;
        }
        .item-name {
          position: absolute;
          left: 7px;
          bottom: 6px;
          font-family: Roboto Condensed;
          font-style: normal;
          font-weight: normal;
          font-size: 14px;
          color: rgba(255, 255, 255, 0.7);
        }
      }
      &__item.blue { border-color: #026FF4; box-shadow: inset 0px 2px 50px 0 rgba(1, 44, 96, 0.75) }
      &__item.green { border-color: #5CBAC7; box-shadow: inset 0px 2px 50px 0 rgba(36, 73, 78, 0.75) }
      &__item.purple { border-color: #EB00FF; box-shadow: inset 0px 2px 50px 0 rgba(92, 0, 100, 0.75) }
      &__item.red { border-color: #FF0000; box-shadow: inset 0px 2px 50px 0 rgba(255, 0, 0, 0.25) }
      &__item.yellow { border-color: #FFD600; box-shadow: inset 0px 2px 50px 0 rgba(100, 88, 0, 0.75) }
    }
  }
}
</style>
