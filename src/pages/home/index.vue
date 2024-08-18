<template>
  <div>
    <button class="btn" @click="handleBtn">点我获取code</button>
    <button class="btn" @click="handleSub">一次性订阅消息</button>
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
</script>
<style scoped>

</style>