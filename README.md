### vite
npm init
npm i vite -D

### 添加vue
npm i vue -S

npm i @vitejs/plugin-vue -D  // 结合vite配置vue的文件

### 创建html、src文件夹
1. html为html5格式，并且添加id为app的div以及body末尾引入 main.js,引入方式为`type="module"`（暂不考虑main.ts，待接通elementplus中的 `messageBox` 响应式后再接入）
2. src中先创建 `main.js` 作为 `entry` 
3. src中创建`App.vue` 作为单文件页面的入口组件
4. 根目录上创建`vite.config.js`，并且写入vue的配置

        // vite.config.js
        import vue from '@vitejs/plugin-vue'

        export default {
        plugins: [vue()],
        }

### main.js创建Vue实例

    // vue初始化方法引入
    import {createApp} from "vue";
    // elementplus
    import ElementPlus from 'element-plus';
    import 'element-plus/dist/index.css';
    // 单文件入口
    import App from './App.vue';

    // 创建实例
    const app=createApp(App)

    // 引用组件和挂载
    app.use(ElementPlus).mount("#app")

### 引入element-plus并解决MessageBox倒计时无效问题

npm i element-plus -S

1. main.js 引入element-plus（实践按需加载（2个方法）、icon添加）

        import ElementPlus from 'element-plus';
        import 'element-plus/dist/index.css';

2. vue文件引入 MessageBox

import { ElMessageBox } from 'element-plus'

3. 利用渲染函数 h，并且一定要用一个方法return该渲染函数

elMessage.alert(()=>{return h('div',messageBoxOptions.message)},"title",{})



---------

## 新纪元——备忘录

### 需求

1. 每天提醒
1. 进入则显示列表（文件夹）
1. 文件夹内备忘列表
3. 点击列表详情
4. 详情内添加表单功能
4. 日期备忘提醒
5. 详情内语音记录
5. 详情内手写
6. 详情内快速输入
7. 详情内更多（添加备注、打印或生成PDF、重命名、设置为）
8. 记录账号密码等（加密）



### 新纪元——类微信截屏提取文字功能



### 聊天语音平台