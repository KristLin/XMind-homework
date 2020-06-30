# 项目说明

本项目为[XMind 前端面试作业](https://github.com/xmindltd/hiring/blob/master/frontend-1/README.md)

# 目录说明

- `XMind-wireframe.pdf`：线框图

# 技术栈选择

- Vue.js
- Vue-Router
- Vuex
- Element

# 开发思路

- 设计线框图：主页，数据添加页，分类添加页，详细统计页
- 代码实现
  - 主页（首要）
  - 数据添加页（首要）
  - 分类添加页（次要）
  - 详细统计页（次要）
- 部署到云上（次要）

# 遇到的问题

### 除主页外，其他页面是以 dialog/modal 的方式展示还是独立页面?

可以将这些页面封装为组件（component），这样以后如需实现弹窗方法可直接调用。

### VSCode 中 Eslint-Standard 和 Prettier 的冲突问题（函数名后加空格）

# 开发日志

### 2020-06-29 夜里

- 建立 github 仓库
- 编辑 readme
- 设计线框图

### 2020-06-30

- 创建 vue 脚手架工程(es6-sass-eslint_standard)
