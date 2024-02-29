<script setup lang="ts">
import { ref } from 'vue'
import { onLoad } from '@dcloudio/uni-app'
import CustomNavbar from './componets/CustomNavbar.vue'
import type { BannerItem } from '@/types/home'
import { getHomeBannerAPI } from '@/services/home'

const bannerList = ref<BannerItem[]>([])
const getHomeBannerData = async () => {
  const res = await getHomeBannerAPI()
  bannerList.value = res.result
}

onLoad(() => {
  getHomeBannerData()
})
</script>

<template>
  <CustomNavbar />
  <XtxSwiper :list="bannerList"></XtxSwiper>
  <view class="index">index</view>
</template>

<style lang="scss">
//
</style>
