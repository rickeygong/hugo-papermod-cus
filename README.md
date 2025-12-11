## ✨ About This Repository

A personal blog built with **[Hugo PaperMod](https://github.com/adityatelange/hugo-PaperMod/)**, with additional styling inspired by
**[Astro Paper](https://github.com/satnaing/astro-paper)** — because it looks amazing.

This repository includes:

* 🎨 Custom styling on top of PaperMod
* 💬 Theme-adaptive Giscus comments
* 📊 Built-in web analytics (Umami + Clarity)

## 🖼️ Preview

### 🌞 Light Mode

![Light mode home page](/assets/images/readmeHomePage-L.webp)

### 🌙 Dark Mode

![Dark mode home page](/assets/images/readmeHomePage-D.webp)

---

## 🚀 Running Locally

(1) Clone this repository.

```bash
https://github.com/rickeygong/hugo-papermod-cus.git
```

(2) Inside the folder of your Hugo site 'hugo-papermod-cus', run:

```bash
git submodule update --init --recursive
```

(3) run

```bash
hugo server
```

## 🗂️ Changelog

( 😎 *I’ll try my best to keep it updated… maybe.* )

| Date | Description | Notes |
| :--- | :--- | :--- |
| 2025-12-10 | Added Giscus comments | |
| 2025-12-10 | Added website analytics | |
| 2025-12-09 | Added blogroll | |

# ⚙️ Configuration Guide

Below is a quick setup reference for analytics & comments.

All configuration lives in: **`config/_default/params.yml`**.

## 📊 1. Website Analytics

```yml
analytics:
  enabled: false
  umami:
    enabled: false
    websiteid: 'your-websiteid'
    src: 'https://cloud.umami.is/script.js'
    domains: 'your-domains'
    enableTrackEvent: true
    scriptName: ''
    dataDomains: ''
  clarity:
    enabled: false
    analytics: 'your-analytics'
  google:
    enabled: false
    id: 'your-id'
```

## 💬 2. Comment System

### 2.1 Giscus (Auto theme + auto language)

This repository includes enhancements to allow:

* ✔ Automatic language detection
* ✔ Automatic switching between Light / Dark mode

Enable comments, add your own config:

```yml
comments:
  enabled: true
  system: 'giscus'
  giscus:
    repo: 'your-repo'
    repoId: 'your-repoId'
    categoryId: 'your-categoryId'
    category: 'Announcements'
    mapping: 'pathname'
    strict: '0'
    reactionsEnabled: '1'
    emitMetadata: '0'
    inputPosition: 'top'
    lang: 'zh-CN'
```
