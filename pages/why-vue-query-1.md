---
layout: two-cols
transition: slide-up
---

# 為什麼使用 Vue Query？

<div class="text-lg mt-4">
傳統 API 管理的挑戰
</div>

<div v-click class="challenge-item">
  <div class="font-bold">繁複的請求狀態管理</div>
  <div class="text-sm opacity-80">需追蹤 loading、error、success 等多種狀態</div>
</div>

<div v-click class="challenge-item">
  <div class="font-bold">資料同步問題</div>
  <div class="text-sm opacity-80">如何確保所有元件顯示最新資料？</div>
</div>

<div v-click class="challenge-item">
  <div class="font-bold">手動處理快取</div>
  <div class="text-sm opacity-80">避免重複請求需要繁瑣的邏輯</div>
</div>

<div v-click class="challenge-item">
  <div class="font-bold">效能最佳化</div>
  <div class="text-sm opacity-80">減少不必要的 API 呼叫需要複雜策略</div>
</div>

::right::

<div class="mt-16 ml-4">
  <div v-click class="solution-diagram">
    <div class="text-center mb-2 font-bold">傳統方法</div>
    <div class="diagram traditional">
      <div class="box">手動狀態管理</div>
      <div class="arrow">↓</div>
      <div class="box">手動處理快取</div>
      <div class="arrow">↓</div>
      <div class="box">手動同步資料</div>
      <div class="arrow">↓</div>
      <div class="box">手動處理錯誤</div>
    </div>
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