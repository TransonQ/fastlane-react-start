---
# try also 'default'/'seriph' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: "text-center"
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: true
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS (experimental)
css: unocss
---

# Fastlane React Start

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Transon <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/quanscheng/fastlane-react-start" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---
layout: cover
---

# 从新建项目开始

---

# create-react-app

<br/>

```
npx create-react-app [项目名字]
```
<br/>

- 基于webpack
- 官方推荐
- 具备完备的生产打包能力
- 开箱即用
- 默认隐藏配置文件,两种方式自定义配置
  - eject: 操作不可逆,暴露所有webpack配置
  - craco: 第三方库,通过制定配置文件覆盖CRA内部的配置

<br/>

[create-react-app文档](https://create-react-app.dev/docs/getting-started)

[基于CRA的规范自制模版](https://github.com/quanscheng/react-template)

---

# vite

<br/>

```bash
npm create vite@latest my-vue-app -- --template react # npm7+ ,7以下则不需要中间的双杠'--'
```

<br/>

- 基于Rollup
- 官方新文档称之为'流行的CRA替代品'
- ESM模块
- 开发体验舒适
- 配置化快捷, 同时需要注意 ESM 不支持 `__dirname` 需要自行配置( 场景: path alias )

[vite 文档](https://cn.vitejs.dev/)

[基于Vite的规范自制模版](https://github.com/quanscheng/react-vite-template)





---

![react](assets/React.png)

---

# JSX

<Col2>

<p>html</p>

<p>js</p>

```html {all|2-4|all}
<ul>
  <li>item1</li>
  <li>item2</li>
  <li>item3</li>
</ul>
```

```js {}
function fn(list = []) {
  return list.map(({ id, label }) => label)
}

const objArray = [
  { id: 1, label: "item1" },
  { id: 2, label: "item2" },
  { id: 3, label: "item3" },
]

fn(objArray) // ['item1', 'item2', 'item3']
```

</Col2>

---

# JSX

<Col2>

```js {all}
const head_id = 89757
const objArray = [
  { id: 1, label: "item1" },
  { id: 2, label: "item2" },
  { id: 3, label: "item3" },
]
// `{ }` 你可以在大括号内放置任何有效的 JavaScript 表达式
const head = <h1>this is Heading1, id={head_id}</h1>

// 遍历数组渲染特定属性值的时候,
// 应该确保每个返回的的项都有唯一标识 key
const list = objArray.map(({ id, label }) => (
  <li key={id}>{label}</li>
))

// 渲染到组件
function ComponentA() {
  return (
    <>
      {head}
      <ol>{list}</ol>
    </>
  )
}
```

[<img border="rounded" src="/assets/RenderJSX1.png" mt="30">](https://codesandbox.io/s/jsx-demo-1-yp3slu?file=/src/App.js)

</Col2>

---

<img border="rounded" src="/assets/Hydrogen-mind.png" class="h-120 row-reverse">
