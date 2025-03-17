---
layout: default
transition: slide-up
---

# 什麼是 Vue Query？

<div class="text-lg opacity-80 mb-6 mt-2">
Vue Query 是一個<span class="text-blue-500 font-bold">伺服器狀態管理</span>工具，幫助我們自動管理 API 資料
</div>

<div class="grid grid-cols-2 gap-8 mt-8">
<div>
<div v-click class="feature-card">
  <div class="text-lg font-bold mb-2 text-blue-500">自動管理請求狀態</div>
  <div>自動處理 <span v-mark.red="3">loading、error、success</span> 狀態，減少 boilerplate code</div>
</div>

<div v-click class="feature-card mt-4">
  <div class="text-lg font-bold mb-2 text-blue-500">提供快取機制</div>
  <div>快取<span v-mark.red="3">避免重複請求</span>，可依需求客製化快取策略</div>
</div>
</div>

<div>
<div v-click class="feature-card">
  <div class="text-lg font-bold mb-2 text-blue-500">自動同步資料</div>
  <div>確保所有元件顯示最新資料，無需手動處理更新邏輯</div>
</div>

<div v-click class="feature-card mt-4">
  <div class="text-lg font-bold mb-2 text-blue-500">內建錯誤處理</div>
  <div>提供重試機制與錯誤狀態管理，提升應用穩定性</div>
</div>
</div>
</div>

<style>
.feature-card {
  padding: 20px;
  border-radius: 8px;
  background-color: rgba(255, 255, 255, 0.1)
}
.component.active {
  background-color: rgba(59, 130, 246, 0.2);
  border: 1px solid rgba(59, 130, 246, 0.4);
}
.component.small {
  padding: 8px;
  width: 48%;
}
.comp-title {
  font-weight: bold;
  font-size: 14px;
  margin-bottom: 6px;
}
.comp-code {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  opacity: 0.8;
}
.comp-arrow {
  text-align: center;
  color: #3b82f6;
  margin-top: 4px;
}
.cache {
  padding: 12px;
  background-color: rgba(16, 185, 129, 0.1);
  border: 1px solid rgba(16, 185, 129, 0.2);
  border-radius: 6px;
  margin-bottom: 16px;
}
.cache-title {
  font-weight: bold;
  font-size: 14px;
  margin-bottom: 6px;
}
.query-key {
  font-family: 'JetBrains Mono', monospace;
  font-size: 11px;
  color: #10b981;
}
.components-row {
  display: flex;
  justify-content: space-between;
}
.sync-arrows {
  display: flex;
  justify-content: space-between;
  margin-bottom: 10px;
}
.sync-arrow-left, .sync-arrow-right {
  color: #10b981;
}
.tip-box {
  background-color: rgba(251, 191, 36, 0.1);
  border-left: 3px solid rgba(251, 191, 36, 0.4);
  padding: 12px;
  border-radius: 0 6px 6px 0;
}
.tip-title {
  font-weight: bold;
  font-size: 14px;
  margin-bottom: 8px;
}
.tip-list {
  padding-left: 16px;
  font-size: 12px;
}
.tip-list li {
  margin-bottom: 4px;
}
</style>