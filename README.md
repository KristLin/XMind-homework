# 项目说明

本项目为[XMind 前端面试作业](https://github.com/xmindltd/hiring/blob/master/frontend-1)

# 开发环境

- 系统：MacOS
- Node: v12.16.1
- NPM: 6.13.4
- Vue: 4.4.6

# 目录说明

- `XMind-wireframe.pdf`: 线框图
- `data`: 测试用的数据
- `dist`: 发布内容及配置, 用于部署在 Heroku
- `screenshots`: 项目部分截图展示

# 技术栈选择

- Vue.js
- Vue-Router
- Vuex
- Element
- Heroku

# 部署运行

### 本地运行

- 下载后进入文件夹，通过`npm install`安装所需依赖
- 打开浏览器输入`localhost:8080`开始使用

### 云端 Demo

- [LiveDemo](https://tally-book.herokuapp.com) (可能需要 VPN)
- 或浏览器访问 https://tally-book.herokuapp.com

### 说明

- 导入数据格式请参考[XMind 前端面试作业](https://github.com/xmindltd/hiring/blob/master/frontend-1)

# 部分项目页面展示

### 主页面

![image](https://github.com/KristLin/XMind-tally-book/blob/master/screenshots/screenshot-home.png)

### 详细统计页

![image](https://github.com/KristLin/XMind-tally-book/blob/master/screenshots/screenshot-chart.png)

# 开发进度

- [x] 线框图：主页，数据添加页，分类添加页，详细统计页
- 功能实现
  - 主页
    - [x] 账单数据导入
    - [x] 账单数据导出
    - [x] 账单分类数据导入
    - [x] 账单数据展示
    - [x] 账单分类名称切换显示
    - [x] 账单类型名称切换显示
    - [x] 选择月份按钮
    - [x] 数据关键字过滤
    - [x] 跳转添加数据页面
    - [x] 跳转详细统计页面
  - 数据添加页
    - [x] 选择分类按钮
    - [x] 跳转添加分类页面
    - [x] 所选分类的类型展示
    - [x] 时间输入
    - [x] 金额输入
    - [x] 跳转主页
    - [x] 添加数据
  - 分类添加页
    - [x] ID 输入
    - [x] 名称输入
    - [x] 类型选择
    - [x] 跳转数据添加页面
    - [x] 添加分类
  - 详细统计页
    - [x] 显示月份标题
    - [x] 显示切换按钮组
    - [x] 显示扇形统计图
    - [x] 跳转主页
- [x] 部署到云上

# 遇到的问题

### el-upload 组件的排版问题

`el-upload`组件中的按钮无法像单独按钮一样排版，故选择隐藏内部按钮，使用外部按钮调用其 click 方法。

### 动态改变表格内容显示（如显示分类名称而不是 ID）

通过深拷贝生成新的账单数据集，通过操作该数据集改变展示内容而不影响原数据。占用内存增加，但降低数据操作难度和频率。

### 导入数据的功能代码较长，且导入分类和导入账单功能类似

将导入功能封装到自己定义组件 `UploadBtn`，通过传入自定义 ID 避免调用时的冲突。

### 在详细统计页面，当改变页面大小时, echarts 图像位置不会动态调整

### 原设计图中没有设计时间输入(考虑直接选取当前时间)，后续发现这个设计不合理，需要加上时间输入

# 开发日志

### 2020-06-30

- 建立 github 仓库
- 编辑 readme
- 设计线框图
- 创建 vue 脚手架工程(es6-sass-eslint_standard)
- 配置开发环境（vscode，prettier，eslint 等）

### 2020-07-01

- 线框图主页小部分美化改动（多选框排版，输入按钮布局）
- 开发主页（响应式布局，输入组件，功能按钮）
- 实现上传文件功能
- 实现上传 csv 文件的解析

### 2020-07-02

- 实现导入数据的展示
- 使用 moment 实现时间格式的转换
- 实现对时间数据的提取，将其添加到选择月份的下拉选项中
- 将导入按钮封装为组件，导入分类数据和账单数据可以复用组件
- 修复重复上传时无响应的问题(需要使用 refs 调用`el-upload`的 `clearFiles()`)
- 实现根据选择月份对结果进行过滤
- 计算当前展示数据的总支出和总收入
- 实现切换分类名称和类型名称

### 2020-07-03

- 将下拉按钮封装为组件，选择月份和添加数据时的选择分类可以复用
- 将数据展示 table 封装为组件，精简主页文件代码
- 完善数据添加页面的开发
- 实现 Vuex 存储数据和添加数据

### 2020-07-04

- 更正线框图中的错字
- 引入 echart 并完成数据统计页面的开发
- 将多页面需要引用的数据存入 Vuex，简化代码
- 为页面组件添加样式，区分功能并美化界面
- 在数据添加页面加入时间输入
- 实现主页关键字过滤功能

### 2020-07-05

- 引入 export-from-json 实现数据导出功能
- 对数据添加页面的输入进行校验和提示
- 添加全部月份到选择月份的下拉菜单
- 发布项目到 Heroku

# 项目展望

- 虽然项目中已通过对页面跳转按钮进行合理禁用避免了非法访问， 但用户可以通过地址栏直接访问任意页面，需要路由守卫等方法处理非法的页面访问（如未导入数据就进入详细统计页面）
- 将数据存储到本地，避免用户刷新数据丢失的情况
- 让详细统计中的图标随屏幕尺寸自动调整
- 使用 Element-UI 的 vlidators 对输入进行系统校验、提示
