---
# try also 'default'/'seriph' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /assets/react-bg.png
# apply any windi css classes to the current slide
class: 'text-center'
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

<img border="rounded" src="/assets/React-mind-01.png">

---

# UI

<div grid="~ cols-2 gap-2" m="-t-2">

<span>html</span>

<span>js</span>

```html {1|2|3|all}
<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>
```

```html {1|2|3|all}
<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>
```

</div>

---

<img border="rounded" src="/assets/Hydrogen-mind.png" class="h-120 row-reverse">
