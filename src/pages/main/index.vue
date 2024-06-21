<template>
  <view
    class="index-page h-full overflow-auto"
    @scroll="handleScroll"
    ref="pageRef"
  >
    <div class="absolute h-full w-full bg-amber z-[-1]">
      <div class="info">
        <span class="text-[200px]" ref="infoRef"> 27 </span>
      </div>
    </div>

    <!-- // 内容 -->
    <div class="index-body h-full">
      <div class="scroll-box blank" ref="blankRef"></div>
      <div
        class="box scroll-box !mt-0 footer-bar h-[200px] box-border flex flex-col justify-around color-white pt-2"
      >
        <div v-for="it in 3" :key="it" text-center flex justify-around>
          <span>今天小雨</span>
          <span>云</span>
          <span>22-24</span>
        </div>
        <div>
          <div class="btn bg-[#858e9d] p-3 mx-4 rounded-3 text-center">
            查看近日天气
          </div>
        </div>
      </div>
      <div class="box h-[100px] color-white">两小时内乌江鱼</div>

      <div class="box h-[700px] color-white">两小时内乌江鱼</div>
    </div>
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface ComponentWithRef {
  $el: HTMLElement
}
const infoRef = ref<HTMLInputElement | null>(null)
const pageRef = ref<ComponentWithRef | null>(null)
const blankRef = ref<HTMLInputElement | null>(null)
const handleScroll = () => {
  if (pageRef.value && infoRef.value && infoRef.value) {
    const { scrollTop } = pageRef.value.$el
    const clientHeight = blankRef.value?.clientHeight
    let rad = scrollTop / 270
    if (clientHeight) {
      rad = scrollTop / clientHeight
    }
    infoRef.value.style.display = 'inline-block'
    infoRef.value.style.transform = `scale(${1 - rad * 0.2})`
    infoRef.value.style.opacity = `${1 - rad}`
  }
}
</script>

<style scoped>
.index-page {
  font-style: normal;
  scroll-snap-type: y proximity;
}
.index-body .scroll-box {
  scroll-snap-align: start;
}
.blank {
  height: calc(100% - 220px);
}
.box {
  margin: 24rpx;
  background-color: #6f7a8b;
  border-radius: 20px;
}
</style>
