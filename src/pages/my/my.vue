<script setup lang="ts">
import { useMemberStore } from '@/stores'
import '@/utils/http'
const memberStore = useMemberStore()

const getDate = () => {
  uni.request({
    method: 'GET',
    url: '/home/banner',
  })
}
</script>

<template>
  <view class="my">
    <view>会员信息：{{ memberStore.profile }}</view>
    <button
      @tap="
        memberStore.setProfile({
          nickname: '小兔鲜',
        })
      "
      size="mini"
      plain
      type="primary"
    >
      保存用户信息
    </button>
    <button @tap="memberStore.clearProfile()" size="mini" plain type="warn">清理用户信息</button>
    <button @tap="getDate">请求</button>
  </view>
</template>

<style lang="scss">
//
</style>
