```shell
# 新建 react 项目

$npx create-react-app storybook-demo

$cd storybook-demo

#初始化 storybook
￥npx -p @storybook/cli sb init

# Run the test runner (Jest) in a terminal:
yarn test --watchAll

# Start the component explorer on port 6006:
yarn storybook

# Run the frontend app proper on port 3000:
yarn start

# 下载设计资源
npx degit chromaui/learnstorybook-code/src/assets/font src/assets/font
npx degit chromaui/learnstorybook-code/src/assets/icon src/assets/icon

```

storybook 中有两个基本的组织级别，component 及其 child stories

将每个 story 视为 component 的排列，可以根据需要为每个组件创建尽可能多的 story

- component
  - story
  - story
  - story

为了告知 storybook 我们正在记录的 component，我们创建一个 default 默认导出，其中包含

- component - 组件本身
- title 如何在 storybook 侧边栏引用组件

为了定义 stories，为每个测试状态导出一个函数用于生成一个 story，story 是一个根据传入的 state 返回一个已渲染的函数，像是无状态组件

Template.bind({})是一个可以用于复制函数的 Javascript 标准技术，使用此技术允许每个导出的 story 都使用相同的实现，但能够设置自己的属性。

arg 被修改，组件会实时更新

## 配置

preview.js

parameters 通常用于控制 storybook 的功能和插件的行为

actions 允许我们创建被点击时显示在 storybook 界面的 actions 面板的回调。

## 快照测试