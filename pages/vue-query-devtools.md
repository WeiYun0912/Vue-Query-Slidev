---
layout: default
transition: fade-out
---

# 開發工具視覺化

```html {all}
<script setup>
  import { VueQueryDevtools } from "@tanstack/vue-query-devtools";
</script>

<template>
  <VueQueryDevtools />
</template>
```

<div class="grid grid-cols-2 gap-4 mt-4">
    <div v-click>
        <img src="https://i.imgur.com/zVtR7dz.png" class="w-full rounded shadow-md" />
        <div class="text-xs mt-1 opacity-70 text-center">DevTools Panel Button</div>
    </div>
    <div v-click>
        <img src="https://i.imgur.com/c3SNwQu.png" class="w-full rounded shadow-md" />
        <div class="text-xs mt-1 opacity-70 text-center">Visualize Query Status</div>
    </div>
</div>
