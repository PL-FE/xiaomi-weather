<template>
  <view class="index-page h-full overflow-auto">
    <div class="absolute h-full w-full bg-amber z-[-1]">
      <div class="info">
        <span class="text-[200px]"> 27 </span>
      </div>
    </div>
    <div class="blank"></div>
    <!-- // 内容 -->
    <div
      class="box !mt-0 footer-bar h-[200px] box-border flex flex-col justify-around color-white pt-2"
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

    <div class="box h-[400px] color-white">两小时内乌江鱼</div>
  </view>
</template>

<script setup lang="ts"></script>

<style scoped>
.index-page {
  font-style: normal;
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
