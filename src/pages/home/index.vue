<template>
  <div>
    <button class="btn" @click="handleBtn">点我获取code</button>
    <button class="btn" @click="handleSub">一次性订阅消息</button>
    <button open-type="getPhoneNumber" @getphonenumber="handlePhone">手机号快速验证</button>
  </div>
</template>

<script setup lang="ts">
const handleBtn = () => {
  uni.login({
    success: res => {
      console.log(res)
    }
  })
}

const handleSub = () => {
  uni.requestSubscribeMessage({
    tmplIds: ['Gp5FiHAZ8ym599r7gRFP9EYDKVhYg9nC20T0wXwQISA'],
    success (res) {
      console.log(res)
    }
  })
}

const handlePhone = (e: any) => {
    console.log('code', e.detail.code)  // 动态令牌
    console.log('msg', e.detail.errMsg) // 回调信息（成功失败都会返回）
    console.log('error', e.detail.errno)  // 错误码（失败时返回）
}
</script>
<style scoped>

</style>