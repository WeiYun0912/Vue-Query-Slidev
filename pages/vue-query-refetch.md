---
layout: default
transition: fade
---

# 資料重新獲取機制

<div class="opacity-80 mb-6 text-sm">控制 API 數據何時重新獲取</div>

<div class="grid grid-cols-3 gap-4">
<div v-click>
<div class="setting-card">
  <div class="text-lg font-bold mb-3 text-blue-400">staleTime</div>
  <div class="mb-4 text-sm">控制資料從 Fresh 變成 Stale 的時間</div>
  
  ```js
  const { data } = useQuery({
    queryKey: ['todos'],
    queryFn: fetchTodos,
    staleTime: 3000, // 3秒後變為 Stale
  })
  ```
  
  <div class="tip mt-2">
    <div class="text-xs font-bold">提示</div>
    <div class="text-xs mt-1">設為 Infinity 讓資料永不過期</div>
  </div>
</div>
</div>

<div v-click>
<div class="setting-card">
  <div class="text-lg font-bold mb-3 text-blue-400">refetchOnWindowFocus</div>
  <div class="mb-4 text-sm">控制頁面重新聚焦時是否重新請求</div>
  
  ```js
  const { data } = useQuery({
    queryKey: ['todos'],
    queryFn: fetchTodos,
    refetchOnWindowFocus: false
  })
  ```
  
  <div class="tip mt-2">
    <div class="text-xs font-bold">使用場景</div>
    <div class="text-xs mt-1">資料變動頻率低或用戶體驗優先時關閉</div>
  </div>
</div>
</div>

<div v-click>
<div class="setting-card">
  <div class="text-lg font-bold mb-3 text-blue-400">gcTime</div>
  <div class="mb-4 text-sm">控制資料在快取中保留多久</div>
  
  ```js
  const { data } = useQuery({
    queryKey: ['todos'],
    queryFn: fetchTodos,
    gcTime: 5 * 60 * 1000 // 5分鐘
  })
  ```
  
  <div class="tip mt-2">
    <div class="text-xs font-bold">記憶體管理</div>
    <div class="text-xs mt-1">避免設定過長導致記憶體佔用過高</div>
  </div>
</div>
</div>
</div>

<div class="mt-8 lifecycle-visual" v-click>
<div class="time-bar">
  <div class="time-marker">0s</div>
  <div class="time-section fetching">
    <div class="time-label">Fetching</div>
  </div>
  <div class="time-section fresh">
    <div class="time-label">Fresh (staleTime)</div>
  </div>
  <div class="time-section stale">
    <div class="time-label">Stale</div>
  </div>
  <div class="time-section inactive">
    <div class="time-label">Inactive</div>
  </div>
  <div class="time-section gc">
    <div class="time-label">垃圾回收 (gcTime)</div>
  </div>
  <div class="time-marker">時間軸</div>
</div>
</div>

<style>
.setting-card {
  padding: 16px;
  border-radius: 8px;
  background-color: rgba(255, 255, 255, 0.05);
  height: 100%;
  transition: all 0.3s ease;
}
.setting-card:hover {
  transform: translateY(-3px);
}
.tip {
  background-color: rgba(59, 130, 246, 0.1);
  border-left: 3px solid rgba(59, 130, 246, 0.5);
  padding: 6px 8px;
  border-radius: 0 4px 4px 0;
}
.lifecycle-visual {
  margin-top: 30px;
}
.time-bar {
  position: relative;
  height: 60px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  width: 100%;
}
.time-marker {
  position: absolute;
  top: -15px;
  font-size: 12px;
  color: #888;
}
.time-marker:first-child {
  left: 0;
}
.time-marker:last-child {
  right: 0;
}
.time-section {
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}
.time-label {
  font-size: 11px;
  white-space: nowrap;
  position: absolute;
  bottom: -20px;
  text-align: center;
  width: 100%;
}
.fetching {
  width: 5%;
  background-color: rgba(99, 102, 241, 0.3);
  border-radius: 4px 0 0 4px;
}
.fresh {
  width: 15%;
  background-color: rgba(52, 211, 153, 0.3);
}
.stale {
  width: 25%;
  background-color: rgba(251, 191, 36, 0.3);
}
.inactive {
  width: 25%;
  background-color: rgba(156, 163, 175, 0.3);
}
.gc {
  width: 30%;
  background-color: rgba(239, 68, 68, 0.2);
  border-radius: 0 4px 4px 0;
}
</style>
