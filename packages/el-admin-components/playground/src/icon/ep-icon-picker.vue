<template>
  <el-row>
    支持所有Iconify sets：
    <el-link href="https://icon-sets.iconify.design/">Iconify</el-link>
  </el-row>
  <div>直接使用icon="{collection}:{name}"的方式进行使用</div>
  <span> icon: <Iconify :icon="iconRef" :style="style"></Iconify> </span>
  <p></p>
  <VpIconPicker @submit="handleSubmit"></VpIconPicker>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import type { CSSProperties } from 'vue'
import { VpIconPicker } from 'el-admin-components'

const iconRef = ref('ep:qian')
const style = ref<CSSProperties>({})

const handleSubmit = (data: any) => {
  const { icon, fontSize, color } = data
  iconRef.value = icon
  style.value = {
    fontSize: `${fontSize}px`,
    color
  }
}
</script>

<style scoped></style>
