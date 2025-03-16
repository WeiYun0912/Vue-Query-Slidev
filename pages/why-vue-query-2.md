---
layout: two-cols
transition: slide-up
---

# 為什麼使用 Vue Query？

<div class="text-lg mt-4">
使用 Vue Query 可以解決以下問題：
</div>

<div v-click class="challenge-item">
  <div class="font-bold">請求狀態管理</div>
  <div class="text-sm opacity-80">直接在元件中使用 loading、error、success 等多種狀態</div>
</div>

<div v-click class="challenge-item">
  <div class="font-bold">資料同步</div>
  <div class="text-sm opacity-80">直接在元件中使用最新資料</div>
</div>

<div v-click class="challenge-item">
  <div class="font-bold">自動處理快取</div>
  <div class="text-sm opacity-80">自動快取避免重複請求</div>
</div>

<div v-click class="challenge-item">
  <div class="font-bold">效能最佳化</div>
  <div class="text-sm opacity-80">減少不必要的 API 呼叫</div>
</div>

::right::

<div v-click class="solution-diagram mt-16">
  <div class="text-center mb-2 font-bold text-blue-500">Vue Query</div>
  <div class="diagram vue-query">
    <div class="box vq">自動狀態管理</div>
    <div class="arrow">↓</div>
    <div class="box vq">自動快取</div>
    <div class="arrow">↓</div>
    <div class="box vq">資料同步</div>
    <div class="arrow">↓</div>
    <div class="box vq">錯誤處理</div>
  </div>
</div>


<style>
.challenge-item {
  margin-top: 12px;
  padding: 10px;
  border-left: 3px solid #3b82f6;
  background-color: rgba(255, 255, 255, 0.05);
}
.solution-diagram {
  transition: all 0.3s ease;
}
.diagram {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.box {
  padding: 8px 12px;
  border-radius: 6px;
  background-color: rgba(255, 255, 255, 0.1);
  width: 90%;
  text-align: center;
  margin: 4px 0;
}
.arrow {
  color: #888;
  margin: 2px 0;
}
.box.vq {
  background-color: rgba(59, 130, 246, 0.15);
  border: 1px solid rgba(59, 130, 246, 0.3);
}
</style>