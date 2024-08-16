<template>
  <div>
    <button class="btn" @click="handleBtn">点我获取code</button>
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
</script>
<style scoped>

</style>