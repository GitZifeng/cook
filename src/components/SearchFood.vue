<script lang="ts" setup>
import { useRecipeStore } from '~/store/recipe'
const rStore = useRecipeStore()

const clearKeyword = () => {
  rStore.keyword = ''
}
</script>

<template>
  <div m="auto b-2" max-w="500px">
    <div relative text-xs>
      <div v-show="rStore.keyword" cursor="pointer" absolute right-2 inline-flex justify="center" items-center h="full" opacity="70" @click="clearKeyword">
        <div i-ri-close-line />
      </div>
      <input
        id="input"
        v-model="rStore.keyword"
        placeholder="关键字过滤"
        aria-label="搜索关键字"
        type="text"
        autocomplete="false"
        p="x4 y2"
        w="full"
        text="center"
        bg="transparent"
        border="~ rounded gray-200 dark:gray-700"
        class="focus:(dark:gray-500)"
      >
      <label class="hidden" for="input">快速搜索</label>
    </div>
  </div>
</template>
