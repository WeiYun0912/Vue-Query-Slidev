---
layout: two-cols
transition: slide-up
---

# 傳統 API 請求的基本寫法

使用 Vue 3 Composition API 與 axios 的典型寫法如下：

```html {all}
<script setup>
// 建立狀態變數
const todos = ref([])
const isLoading = ref(false)
const isError = ref(false)
const error = ref(null)

// 獲取資料函數
const fetchTodos = async () => {
  isLoading.value = true
  isError.value = false
  error.value = null
  ...
}

// 生命週期處理
onMounted(() => {
  fetchTodos()
})
</script>
```

::right::

<div class="mt-22 ml-10">

在這個基本寫法中，我們需要：

1. <span v-mark.red="3">手動建立多個狀態變數</span> (todos, isLoading, isError, error)
2. 自行處理載入、錯誤和成功狀態
3. 在生命週期鉤子中手動調用請求函數
4. 手動實作 UI 條件渲染邏輯

這種寫法在簡單應用中可行，但隨著應用複雜度增加，會產生許多問題。
</div>
