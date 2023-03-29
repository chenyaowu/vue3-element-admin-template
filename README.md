

## 项目介绍

[vue3-element-admin-template](https://github.com/chenyaowu/vue3-element-admin-template) 是基于 [vue3-element-admin](https://gitee.com/youlaiorg/vue3-element-admin)移除 vue-i18n、wangEditor 简化的 `Vue3` 版本后台管理框架，使用 Vue3、Vite4、TypeScript、Pinia、Element Plus 当前主流技术栈开发。

## 项目特色

- 基于 `vue-element-admin` 升级的 `Vue3` 版本，主流技术栈，无过度自定义封装，极易上手，减少学习成本；
- 配套 `Java` 后台接口，非 `Mock` 数据，[在线接口文档](https://www.apifox.cn/apidoc/shared-195e783f-4d85-4235-a038-eec696de4ea5/api-65851240)；
- 系统功能：用户、角色、菜单、字典管和部门管理等；
- 基础设施：动态路由，按钮权限，常用组件封装。

## 技术栈

| 技术栈 | 描述 | 官网 |
| --- | --- | --- |
| Vue3 | 渐进式 JavaScript 框架 | https://v3.cn.vuejs.org/ |
| TypeScript | JavaScript 的一个超集 | https://www.tslang.cn/ |
| Vite | 前端开发与构建工具 | https://cn.vitejs.dev/ |
| Element Plus | 基于 Vue 3，面向设计师和开发者的组件库 | https://element-plus.gitee.io/zh-CN/ |
| Pinia | 新一代状态管理工具 | https://pinia.vuejs.org/ |
| Vue Router | Vue.js 的官方路由 | https://router.vuejs.org/zh/ |


## 环境要求

- Node 环境

  版本：16+

- 开发工具

  VSCode

- 必装插件

  - Vue Language Features (Volar)
  - TypeScript Vue Plugin (Volar)

## 项目启动

```bash

# 安装依赖
npm install

# 项目运行
npm run dev

# 项目打包
npm run build:prod

```

## 项目部署

- 上传文件

  将打包生成在 `dist` 目录下的文件拷贝至 `/usr/share/nginx/html` 目录

- nginx.cofig 配置

  ```
  server {
      listen     80;
      server_name  localhost;

      location / {
          root /usr/share/nginx/html;
          index index.html index.htm;
      }

      # 代理转发 prod-api 标识至 vapi.youlai.tech
      location /prod-api/ {
          proxy_pass http://vapi.youlai.tech/;
      }
  }

  ```