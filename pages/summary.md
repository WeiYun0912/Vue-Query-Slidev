---
layout: default
class: text-center
transition: fade
---

# 總結

<div class="opacity-80 mb-6 text-lg">Vue Query 的主要優勢</div>

<div class="grid grid-cols-2 gap-8 mt-10">
<div v-click>
<div class="summary-card">
  <div class="summary-icon">🚀</div>
  <div class="summary-title">簡化 API 狀態管理</div>
  <div class="summary-desc">自動處理 loading、error、success 狀態，<br>減少 boilerplate code</div>
</div>
</div>

<div v-click>
<div class="summary-card">
  <div class="summary-icon">🔄</div>
  <div class="summary-title">優化請求策略</div>
  <div class="summary-desc">透過 staleTime、gcTime 控制快取生命週期</div>
</div>
</div>

<div v-click>
<div class="summary-card">
  <div class="summary-icon">🔄</div>
  <div class="summary-title">自動資料同步</div>
  <div class="summary-desc">多元件之間自動保持數據一致性</div>
</div>
</div>

<div v-click>
<div class="summary-card">
  <div class="summary-icon">💡</div>
  <div class="summary-title">提升使用者體驗</div>
  <div class="summary-desc">樂觀更新、分頁優化讓操作更順暢</div>
</div>
</div>
</div>

<style>
.summary-card {
  padding: 20px;
  border-radius: 10px;
  background-color: rgba(255, 255, 255, 0.05);
  height: 100%;
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.summary-card:hover {
  transform: translateY(-5px);
  background-color: rgba(255, 255, 255, 0.08);
}
.summary-icon {
  font-size: 28px;
  margin-bottom: 15px;
}
.summary-title {
  font-weight: bold;
  margin-bottom: 8px;
  text-align: center;
}
.summary-desc {
  text-align: center;
  opacity: 0.8;
  font-size: 14px;
}
.suitable-scenarios {
  margin-top: 40px;
}
.scenario-title {
  font-weight: bold;
  margin-bottom: 15px;
  font-size: 18px;
}
.scenarios {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
}
.scenario {
  padding: 8px 16px;
  background-color: rgba(59, 130, 246, 0.1);
  border-radius: 20px;
  font-size: 14px;
}
</style>
