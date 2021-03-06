# VuePress

## Basic VuePress Tutorial

### Index

Your Index is a `README.md`. There is a default VuePress template.

```
---
home: true
heroImage: /hero.png
actionText: CSS →
actionLink: /css/
features:
  - title: Code Snippet
    details: JavaScript, CSS
  - title: Document
    details: Note
  - title: Link
    details: Note
footer: Copyright © Jing, Li
---
```

### Router to Content Page

Routers are mapped to your file structure.

```
.
├── .vuepress
├── README.md // <- index
├── CSS // <- path : /css
│   └── README.md // <- index of /css
├── JS
│   └── README.md
├── NOTE
│   └── README.md
└── package.json
│
└── ...
```

#### Child route

Those `.md` files in the first hierarchy directory will be built as `.html` files and can be accessed.

eg.

```
├── CSS // <- path : /css
│   ├── README.md // <- index of /css
│   └── page-one.md // <- /css/page-one.html
```

### Sidebar of Content (Auto Sidebar for Single Pages)

The sidebar of content is auto generated by markdown titles.

There are two methods to set your content sidebar of all pages.

Method 1 - set in config.js

```
module.exports = {
  title: "Pika Code",
  description: "Front End Notebook",
  themeConfig: {
    ...
    sidebar: 'auto'
  }
};

```

Method 2 - set in specific page with yaml format

```
---
sidebar: auto
---
```

### Navigation

You can set your navigation items in `.vuepress/config.js`.

```
module.exports = {
  title: "Pika Code",
  description: "Front End Notebook",
  themeConfig: {
    nav: [
      { text: "CSS", link: "/css/" },
      { text: "JS", link: "/js/" },
      { text: "NOTE", link: "/note/" }
    ]
  }
};
```

#### [Child Nav](https://v2.vuepress.vuejs.org/reference/default-theme/config.html#navbar)

### HTML Head

- favicon
  Add a `favicon.ico` in `.vuepress/public`.

## Quick Start

1. install "VuePress + CodeSsanBox" template

2. [Update Directory Structures](https://vuepress.vuejs.org/guide/directory-structure.html#default-page-routing)

```
.
├── .vuepress
│   ├── components
│   ├── theme
│   │   └── Layout.vue
│   ├── public // <- put assets
│   ├── styles
│   ├── templates
│   ├── config.js // <- config your title, nav ...
│   └── enhanceApp.js
│
├── README.md // <- index
├── guide // <- path : /guide
│   ├── page-one.md // <- /guide/page-one.html
│   └── README.md // <- index of /guide
└── package.json
│
└── ...
```

3. Update Config

```
module.exports = {
  title: "Pika Code",
  description: "Front End Notebook",
  themeConfig: {
    nav: [
      { text: "CSS", link: "/css/" },
      { text: "JS", link: "/js/" },
      { text: "NOTE", link: "/note/" }
    ]
  }
};
```
