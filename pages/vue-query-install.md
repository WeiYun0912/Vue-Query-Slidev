---
layout: two-cols
transition: fade-out
---

# Vue Query 安裝與設定



### 安裝套件

```bash {all}
# 安裝核心套件
npm install @tanstack/vue-query

# 安裝開發工具（選用）
npm install @tanstack/vue-query-devtools
```

::right::

<div class="text-sm mt-13 ml-10">

### 全域設定 (main.js)

```js {all}
import { createApp } from "vue";
import { VueQueryPlugin, QueryClient } from "@tanstack/vue-query";
import App from "./App.vue";

const app = createApp(App);
app.use(VueQueryPlugin);
app.mount("#app");
```

</div>