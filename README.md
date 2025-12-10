# About this repository

A blog built based on [Hugo PaperMod](https://github.com/rickeygong/hugo-PaperMod), with some styles modified according to personal preferences.

Most of the styling modifications I made reference the [Astro Paper](https://github.com/satnaing/astro-paper) theme because it looks so great.

## Running Locally

1. Clone this repository.

2. Inside the folder of your Hugo site 'hugo-papermod-cus', run:

```bash
git submodule update --init --recursive
```

## Let's see what it looks like

- Light mode:

![Light mode home page](/assets/images/readmeHomePage-L.webp)

- Dark mode:

![Dark mode home page](/assets/images/readmeHomePage-D.webp)

## Changelog

( 😎 I'll write it if I remember to. )

| Date | Description | Notes |
| :--- | :--- | :--- |
| 2025-12-10 | Added Website Analytics |  |
| 2025-12-09 | Added blogroll |  |

## Configuration

### 1. Website Analytics

#### 1.1 Umami Analytics

1. Set `enableUmamiAnalytics` to `true`.
2. To add your own information, edit the `config/production/params.yml` file.

```yml
enableUmamiAnalytics: true
umamiAnalytics:
  websiteid: "your-web-site-id"
  domain: "your-domain"
  dataDomains: "your-data-domains"
  scriptName: "your-script-name"
  enableTrackEvent: true
```
