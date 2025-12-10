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
| 2025-12-10 | Added website analytics | |
| 2025-12-09 | Added blogroll | |

# ⚙️ Configuration Guide

Below is a quick setup reference for analytics & comments.

All configuration lives in: **`config/_default/params.yml`**.

## 📊 1. Website Analytics

### 1.1 Umami Analytics

Enable:

```yml
enableUmamiAnalytics: true
```

Configure:

```yml
umamiAnalytics:
  websiteid: "your-website-id"
  domain: "your-domain"
  dataDomains: "your-data-domains"
  scriptName: "your-script-name"
  enableTrackEvent: true
```

### 1.2 Microsoft Clarity

Enable:

```yml
enableMicrosoftClarity: true
```

Configure:

```yml
microsoftClarity:
  websiteid: "your-websiteid"
```

## 💬 2. Comment System

### 2.1 Giscus (Auto theme + auto language)

This repository includes enhancements to allow:

* ✔ Automatic language detection
* ✔ Automatic switching between Light / Dark mode

Enable comments:

```yml
comments: true
```

Add your own config:

```yml
giscus:
  repo: "[your-repo]"
  repoId: "[your-repoId]"
  categoryId: "[your-categoryId]"
  category: "Announcements"
  mapping: "pathname"
  strict: "0"
  reactionsEnabled: "1"
  emitMetadata: "0"
  inputPosition: "top"
```
