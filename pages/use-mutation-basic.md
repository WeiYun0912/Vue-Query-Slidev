---
layout: default
transition: fade
---

# useMutation 基本用法

<div class="opacity-80 mb-6 text-sm">處理 API 的<strong>新增</strong>、<strong>修改</strong>或<strong>刪除</strong>操作</div>

````md magic-move {lines: true}
```html {all|2,12-15,17-19} twoslash
<script setup>
  import { useMutation } from "@tanstack/vue-query";
  import axios from "axios";

  // 定義 API 請求函式
  const createTodo = async (newTodo) => {
    const { data } = await axios.post("http://localhost:3002/todos", newTodo);
    return data;
  };

  // 使用 useMutation 管理請求
  const { mutate, isPending, isError, isSuccess } = useMutation({
    mutationFn: createTodo,
    // 其他配置選項...
  });

  const handleCreateTodo = () => {
    mutate({ title: "新待辦事項" });
  };
</script>
```

```html
<template>
  <div>
    <button @click="handleCreateTodo" :disabled="isPending">
      {{ isPending ? "新增中..." : "新增 Todo" }}
    </button>
    <p v-if="isSuccess">成功新增！</p>
    <p v-if="isError">發生錯誤，請稍後再試</p>
  </div>
</template>
```
````
<div v-click class="text-sm bg-blue-500 bg-opacity-10 p-4 rounded border border-blue-200 border-opacity-20 mt-4">
<div class="font-bold text-blue-400">關鍵優勢</div>
<div class="grid grid-cols-2 gap-4 mt-2">
  <div>
    <div class="font-bold text-xs">自動狀態管理</div>
    <div class="text-xs">isPending、isSuccess、isError 自動更新，無需手動處理</div>
  </div>
  <div>
    <div class="font-bold text-xs">內建生命週期</div>
    <div class="text-xs">onMutate、onSuccess、onError、onSettled 等生命週期方法</div>
  </div>
</div>
</div>
