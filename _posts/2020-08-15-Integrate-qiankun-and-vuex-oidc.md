---
layout: post
title:  "Integrate qiankun and vuex-oidc"
date:   2020-08-15
published: false
---

## Objective

I have an existing Vue.js app that have [vuex-oidc](https://github.com/perarnborg/vuex-oidc) and want to migrate it into [single-spa](https://single-spa.js.org/) to apply a micro-frontend framework.

The framework [qiankun](https://github.com/umijs/qiankun) is a wrapper on single-spa, and it is mentioned as a [recommended setup](https://single-spa.js.org/docs/recommended-setup#alternatives) on single-spa website. So I decided to use qiankun for the single-spa migration.

## Basic configuration

You need to [implement lifecycle functions](https://single-spa.js.org/docs/migrating-existing-spas#1-implementing-lifecycle-functions) to get your micro app loaded. This is enough if your app is a standard Vue.js app.

## Extra configuration

If you have vuex-oidc in your Vue.js app. You might see oidc-callback not processed or a redirection loop when authentication. You might need the below two steps.

### Add `base` to the vue-router

Because your app becomes a micro frontend app, so its url will be nested. Add `base` to your vue-router otherwise the route won't match.

### Add `routeBase` to oidc store

vuex-oidc use this to recoganise the callback url. If this is not set properly, the `router.beforeEach()` will get called forever, i.e. you will see a redirect loop for callback.
