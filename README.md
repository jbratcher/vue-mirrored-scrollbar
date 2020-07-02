<p align="center">
  <a href="" rel="noopener">
 <img width=200px height=200px src="https://i.imgur.com/iyqDOfi.png" alt="Project logo"></a>
</p>

<h3 align="center">Nuxt Content Static Starter</h3>

<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![GitHub Issues](https://img.shields.io/github/issues/jbratcher/nuxt-content-static-starter.svg)](https://github.com/jbratcher/nuxt-content-static-starter/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/jbratcher/nuxt-content-static-starter.svg)](https://github.com/jbratcher/nuxt-content-static-starter/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

---

<p align="center">A fully configured PWA for Nuxt using Nuxt Content and static site generation.

Quickly bootstrap a blog, CMS, or static site using the power of Nuxt, Nuxt Content, and static site generation. Development amplified using the Vuetify UI library. One click Netlify deployment. Optimized for performance. Production ready.
<br>

</p>

## Table of Contents

- [About](#about)
- [Getting Started](#getting_started)
- [Deployment](#deployment)

## About <a name = "about"></a>

This starter project was designed to bootstrap the development of a modern, headless CMS blog or static website. Using the power of Nuxt, you get a PWA that is pre-configured to maximize performance and SEO opportunities out of the box.

Vuetify is used for the UI library and this project features responsive fonts, theme caching, a global breakpoint fix and much more.

This project is also set to work with Netlify which offers a free starter plan for hosting personal projects, hobby sites, and experiments for free.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/jbratcher/nuxt-content-static-starter)

Other features:

- Docker support
- Vuetify breakpoint fix
- Vuetify theme caching for performance
- Custom scroll directive for main nav

## Prerequisites

You will need to have Node and npm installed.

## Getting Started <a name = "getting_started"></a>

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. Deployment is dead simple using Netlify. Just one click for initial deployment and automatic deploys when you push new changes to Github.

The quickest way to get started is with Netlify's hyper-convenient **one-click Deploy To Netlify**, which will automatically create an instance of this project on your GitHub account and deploy it instantly to Netlify.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/jbratcher/nuxt-content-static-starter)

For local development:

1. Clone the repository locally and cd into the directory.

```bash
git clone https://github.com/jbratcher/nuxt-content-static-starter

cd nuxt-content-static-starter
```

2. Install dependencies.

```bash
yarn install
```

3. Run the project for local dev. This will start a hot-reloading server at `localhost:3000`.

```bash
yarn dev
```

4. Build the app for server-side rendered deployment. See more about **Universal SSR** in the [Nuxt.js docs](https://nuxtjs.org/guide#server-rendered-universal-ssr-).

```bash
yarn build

# And to serve that deployment...
yarn start
```

5. Generate a fully pre-rendered static site. See more [in the docs](https://nuxtjs.org/guide#static-generated-pre-rendering-).

```bash
yarn generate
```

## Docker

There is basic docker support for those who prefer to develop this way. The full usage docs are in the Dockerfile.

```bash
# Build command
docker build -t nuxt:nginx .

# Serve command
docker run --name basic_nuxt --rm -d -p 3333:80 nuxt:nginx
```

This will serve the app on localhost:3333

### Start Creating

At this point you should be able to start customizing the application to your requirements.
