<script setup lang="ts">

</script>
<template>
  <div class="min-h-screen bg-blue-50 flex flex-col justify-center items-center text-center">
    <h1 class="text-4xl font-bold text-blue-800 mb-6">第134回 海城祭</h1>
    <p class="text-lg text-blue-600 mb-4">
      2024年9月21日～9月23日に開催される、海城祭へようこそ！
    </p>
    <p class="text-base text-gray-700">
      今年も盛りだくさんのイベントをご用意しております。友達や家族と一緒にお楽しみください！
    </p>
    <div class="mt-8">
      <button @click="showDetails" class="px-4 py-2 bg-blue-700 text-white rounded hover:bg-blue-800">
        詳細を見る
      </button>
    </div>
    <div v-if="show" class="mt-4 text-gray-600">
      <p>場所: 海城学園</p>
      <p>時間: 10:00～16:00</p>
      <p>入場料: 無料</p>
    </div>
  </div>
</template>