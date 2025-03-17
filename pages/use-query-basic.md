---
layout: default
transition: slide-left
---
# Vue Query 基本用法

<div class="opacity-80 mb-4 text-sm">使用 <code>useQuery</code> 從 API 獲取資料並管理狀態</div>

````md magic-move {lines: true}
```html {all|2,11-14|10}
<script setup>
import { useQuery } from '@tanstack/vue-query'
import axios from 'axios'

const fetchTodos = async () => {
  const { data } = await axios.get('https://jsonplaceholder.typicode.com/todos')
  return data
}

const { data: todos, isLoading, isError } = useQuery({
  queryKey: ['todos'],     // 作為快取的唯一識別符
  queryFn: fetchTodos,     // API 請求函式
  staleTime: 60000,        // 資料保持新鮮的時間 (1分鐘)
  retry: 3                 // 失敗時重試次數
})
</script>
```

```html
<template>
  <div>
    <p v-if="isLoading">載入中...</p>
    <p v-else-if="isError">取得資料失敗</p>
    <ul v-else>
      <li v-for="todo in todos" :key="todo.id">{{ todo.title }}</li>
    </ul>
  </div>
</template>
```

````

<div class="mt-5">
    <div class="flex  gap-6 justify-around">
        <div class="benefit">
            <div class="text-blue-400 text-xs font-bold">自動狀態追蹤</div>
            <div class="text-xs">isLoading、isError 自動更新</div>
        </div>
        <div class="benefit">
            <div class="text-blue-400 text-xs font-bold">資料自動綁定</div>
            <div class="text-xs">data 會自動更新，無需 ref()</div>
        </div>
        <div class="benefit">
            <div class="text-blue-400 text-xs font-bold">內建快取</div>
            <div class="text-xs">相同 queryKey 共享資料</div>
        </div>
        <div class="benefit">
            <div class="text-blue-400 text-xs font-bold">可擴展配置</div>
            <div class="text-xs">豐富的選項自定義行為</div>
        </div>
    </div>
</div>

<style>
.benefit {
  padding: 10px;
  background-color: rgba(255, 255, 255, 0.05);
  border-radius: 6px;
  border-top: 2px solid #3b82f6;
  width: 95%;
}
</style>