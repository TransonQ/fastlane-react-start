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

# 从新建项目开始

---

# create-react-app

<br/>

```
npx create-react-app [项目名字]
```

<br/>

- 基于 webpack
- 官方推荐
- 具备完备的生产打包能力
- 开箱即用
- 默认隐藏配置文件, 两种方式自定义配置
  - eject: 操作不可逆, 暴露所有 webpack 配置
  - craco: 第三方库, 通过制定配置文件覆盖 CRA 内部的配置

<br/>

[create-react-app 文档](https://create-react-app.dev/docs/getting-started)

[基于 CRA 的规范自制模版](https://github.com/quanscheng/react-template)

---

# vite

<br/>

```bash
npm create vite@latest my-vue-app -- --template react # npm7+ ,7 以下则不需要中间的双杠'--'
```

<br/>

- 基于 Rollup
- 官方新文档称之为'流行的 CRA 替代品'
- ESM 模块
- 开发体验舒适
- 配置化快捷, 同时需要注意 ESM 不支持 `__dirname` 需要自行配置 (场景: path alias)

[vite 文档](https://cn.vitejs.dev/)

[基于 Vite 的规范自制模版](https://github.com/quanscheng/react-vite-template)

---

# 根元素

<br/>
index.js

```jsx {all|4|5|all}
import ReactDOM from "react-dom/client"
import App from "./App"

const root = ReactDOM.createRoot(
  document.getElementById("root")
)
root.render(<App />)
```

- 这个 `<div id="root"></div>` 节点被称为根节点, 是 react 渲染树的起点.

- root 可以被放在 body 标签的任何位置.

- React 会将这个标签内的所有内容替换成后续开发的各种组件

- 通俗理解就是整个应用其实就是在一个 id 是 root 的 div 里面来回切换内容 -- 单页面应用的由来

---

<img border="rounded" src="/assets/React.png" >

---

# 编写 jsx

```jsx {all|1|2|4,5|3,6|all}
function AboutPage() {
  return (
    <>
      <h1>About</h1>
      <p>
        Hello there.
        <br />
        How do you do?
      </p>
    </>
  )
}
```

- 单个组件只能返回一个 jsx.

- 如果需要包装多个 jsx 那么需要包装在同一个父级标签

- 如果不希望增加多余的标签 可以使用 `<></>` 空标签包起来

---

# 样式

<br/>
行内样式

```jsx
 <div style={ { maxHeiget:100 } }></div>
 <div style={ { maxHeiget:'100vh' } }></div>
```

- 当 jsx 内部需要传递变量,会解析 jsx 里面`{}`中的内容
- 行内表达式需要传递 css 对象
- css 对象中的 css 属性必须全部转换成小驼峰写法
- css 对象中属性值接受两种基本类型: Number 和 String
- 纯数字表示默认单位 px , 指定单位需要写成字符串

类名

```jsx
<div className=""></div>
```

- react 为了不跟原生 classname 冲突,添加类名的写法做了驼峰处理

---

# 渲染数据

<iframe src="https://codesandbox.io/embed/react-jsx-demo-1-wwuwcx?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:400px; border:0; border-radius: 4px; overflow:hidden;"
     title="react-jsx-demo-1"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

---

# 条件渲染

<iframe src="https://codesandbox.io/embed/react-jsx-demo-2-129z4q?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:400px; border:0; border-radius: 4px; overflow:hidden;"
     title="react-jsx-demo-2"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

---

# 跟新视图和事件处理

<iframe src="https://codesandbox.io/embed/react-jsx-demo-3-dtelpe?fontsize=14&hidenavigation=1&theme=dark"
     style="width:100%; height:400px; border:0; border-radius: 4px; overflow:hidden;"
     title="react-jsx-demo-3"
     allow="accelerometer; ambient-light-sensor; camera; encrypted-media; geolocation; gyroscope; hid; microphone; midi; payment; usb; vr; xr-spatial-tracking"
     sandbox="allow-forms allow-modals allow-popups allow-presentation allow-same-origin allow-scripts"
   ></iframe>

---

# 渲染列表

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
const head = <h1>this is Heading1, id={head_id}</h1>

// 唯一标识 key
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

# Hydrogen.js

[web 开发视图](https://www.yuque.com/docs/share/0751af65-b404-40a9-9221-bd424ebe0e70)

> Node 16.14.0+

- 创建并运行 demo
- 项目结构
- 渲染内容
- 添加 tailwindcss
- fetch data
  - graphQL Storefront API
  - useShopQuery
- 基于文件的路由系统
- 产品页的增/删/改/查
- 购物车业务模块
