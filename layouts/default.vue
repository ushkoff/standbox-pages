<template>
  <div>
    <UserSidebar />

    <div class="container">
      <HeaderCustom />
      <nuxt />
      <FooterCustom />
    </div>

    <ItemsSidebar />
  </div>
</template>

<script>
import HeaderCustom from '@/components/app/Header'
import FooterCustom from '@/components/app/Footer'
import UserSidebar from '@/components/app/UserSidebar'
import ItemsSidebar from '@/components/app/ItemsSidebar'

export default {
  name: 'default-layout',
  components: {
    HeaderCustom,
    FooterCustom,
    UserSidebar,
    ItemsSidebar
  }
}
</script>

<style lang="less" scoped>
@import '~assets/less/utils/_vars';

.container {
  padding-left: 212px;
  padding-right: 120px;
}
</style>
