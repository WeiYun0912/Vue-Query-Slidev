---
layout: default
transition: fade-out
---

# Vue Query 資料生命週期

<div class="opacity-80 mb-4 text-sm">瞭解 Vue Query 如何管理資料狀態</div>

<div v-click>
<div class="lifecycle-diagram">
  <div class="state fresh">
    <div class="state-title">Fresh</div>
    <div class="state-desc">資料新鮮，不會重新請求</div>
  </div>
  <div class="state-arrow">→</div>
  <div class="state stale">
    <div class="state-title">Stale</div>
    <div class="state-desc">資料已過期，但仍可使用</div>
  </div>
  <div class="state-arrow">→</div>
  <div class="state inactive">
    <div class="state-title">Inactive</div>
    <div class="state-desc">未被使用，等待回收</div>
  </div>
</div>
</div>

<div class="grid grid-cols-3 gap-4 mt-8">
<div v-click>
<div class="state-card fresh-card">
  <div class="flex items-center mb-2">
    <div class="dot fresh-dot"></div>
    <div class="text-lg font-bold ml-2">Fresh</div>
  </div>
  <div class="text-sm">
    <ul class="pl-4">
      <li>資料是新鮮的，可靠</li>
      <li>不會<span v-mark.red="3">自動重新請求</span></li>
      <li>依據 staleTime 轉變為 Stale</li>
      <li>需手動 refetch 才會更新</li>
    </ul>
  </div>
</div>
</div>

<div v-click>
<div class="state-card stale-card">
  <div class="flex items-center mb-2">
    <div class="dot stale-dot"></div>
    <div class="text-lg font-bold ml-2">Stale</div>
  </div>
  <div class="text-sm">
    <ul class="pl-4">
      <li>資料已經「不新鮮」</li>
      <li>當<span v-mark.red="3">元件重新載入</span>時更新</li>
      <li>當頁面重新聚焦時更新</li>
      <li>依然可用，但會嘗試更新</li>
    </ul>
  </div>
</div>
</div>

<div v-click>
<div class="state-card inactive-card">
  <div class="flex items-center mb-2">
    <div class="dot inactive-dot"></div>
    <div class="text-lg font-bold ml-2">Inactive</div>
  </div>
  <div class="text-sm">
    <ul class="pl-4">
      <li>目前無元件使用此資料</li>
      <li>依據 <span v-mark.red="3">gcTime</span> 進入回收機制</li>
      <li><span v-mark.red="3">回收前仍存在於快取中</span></li>
      <li>再次使用時可立即取用</li>
    </ul>
  </div>
</div>
</div>
</div>

<style>
.lifecycle-diagram {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}
.state {
  padding: 12px;
  border-radius: 8px;
  width: 200px;
  text-align: center;
}
.state-arrow {
  margin: 0 15px;
  font-size: 20px;
  color: #888;
}
.state-title {
  font-weight: bold;
  margin-bottom: 5px;
}
.state-desc {
  font-size: 14px;
  opacity: 0.8;
}
.fresh {
  background-color: rgba(52, 211, 153, 0.2);
  border: 1px solid rgba(52, 211, 153, 0.3);
}
.stale {
  background-color: rgba(251, 191, 36, 0.2);
  border: 1px solid rgba(251, 191, 36, 0.3);
}
.inactive {
  background-color: rgba(156, 163, 175, 0.2);
  border: 1px solid rgba(156, 163, 175, 0.3);
}
.state-card {
  padding: 16px;
  border-radius: 8px;
  height: 100%;
}
.fresh-card {
  background-color: rgba(52, 211, 153, 0.1);
  border: 1px solid rgba(52, 211, 153, 0.2);
}
.stale-card {
  background-color: rgba(251, 191, 36, 0.1);
  border: 1px solid rgba(251, 191, 36, 0.2);
}
.inactive-card {
  background-color: rgba(156, 163, 175, 0.1);
  border: 1px solid rgba(156, 163, 175, 0.2);
}
.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}
.fresh-dot { background-color: rgb(52, 211, 153); }
.stale-dot { background-color: rgb(251, 191, 36); }
.inactive-dot { background-color: rgb(156, 163, 175); }
ul li {
  margin-bottom: 6px;
}
</style>
