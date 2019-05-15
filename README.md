# vue蒙版组件
![](//cdn.51talk.com/apollo/images/cfc911ac9e302b1ea4c477254461856e.png)
## install
NPM
```
npm install @nat/vue-overlay --save
```
## 用法
```
<template lang="html">
     <div class="features">
                <button @click="isShow = !isShow">显示</button>
                <overlay :z-index="2000" v-model="isShow"></overlay>
            </div>
</template>
```
```
<script>
    import overlay from '@nat/vue-overlay';

    export default {
        components: {
            overlay
        }
    };
</script>
```
## 启动
```
npm run dev
```
## 编译
```
npm run build-lib
```
## 开发环境调试
docs/pages目录中的test.vue文件中引入组件，启动本地服务调试
```
npm run dev
```