# Contents
- [Summary](#summary)
- [More About Me](#more-about-me)
  - [My Website](#my-website)
  - [Resume](#resume)
  - [Linked In (more info on professional experience)](#linked-in)
  - [My Gitlab Server](#my-gitlab-server)
    - [Dev Ops & CI/CD](#dev-ops)
  - [Other Services I Run On My Server](#other-services-i-run-on-my-server)
- [Projects](#projects)
  - [Foursee](#foursee)
  - [Simple GPA Calculator](#min-max-gpa-calculator)
  - [Fantasy Pay](#fantasy-pay)
  - [Vue App](#vue-app)
 - [Open Source Contributions](#open-source-contributions)
   - [React.js](#react.js)
   - [Vue.js](#vue.js)
   - [Feathers.js](#feathers.js)
   - [Misc](#misc)
  

# Summary
This is a list of some of the awesome stuff that I've done. Okay, not all of it would qualify for a true [Awesome List](https://github.com/sindresorhus/awesome#readme), so maybe this is more of just a list... Oh well. See below for some of the stuff I've done, places to find more info on me and more!


# More About Me

### My Website
www.nickbolles.com
- [Source](https://gitlab.dev.nickbolles.com/nbolles/www_nickbolles_com)
- [CI/CD](https://gitlab.dev.nickbolles.com/nbolles/www_nickbolles_com/pipelines)
- [Docker containers](https://gitlab.dev.nickbolles.com/nbolles/www_nickbolles_com/container_registry)
- [More details in the projects Readme.md](https://gitlab.dev.nickbolles.com/nbolles/www_nickbolles_com/blob/master/README.md)

#### Summary
My personal website has a little bit of information about me as well as links to my most up-to-date resume, my Linked In account, github account and my Gitlab server that I host on my home server. 

##### Highlights
- Full fledged PWA (try loading it up, then turn off your internet and re-load it. Everything except for the contact form should work)
- [Lighthouse perf score of 88](https://gitlab.dev.nickbolles.com/nbolles/www_nickbolles_com/issues/13)
- CI/CD on every commit
- Hosted on my home server (powered by [Unraid](https://www.unraid.net/), [Docker](https://www.docker.com/), [Traefik](https://traefik.io/) and [Lets Encrypt](https://letsencrypt.org/))

#### Built With
- Nuxt.js (Vue.js)
- Typescript
- Vuetify - UI Library
- ScrollMagic - Animation Library
- GSAP - Animation Library
- VSCode

### Resume
While this document and everything in it is a good overview of my non-professional experience, my resume and LinkedIn are better overviews of my professional experience. My resume can always be found on my website. Whenever I make updates they're available on my site.

https://www.nickbolles.com/Nicholas%20Bolles%20Resume.pdf

### Linked In
https://www.linkedin.com/in/nickbolles/

### My Gitlab Server
[gitlab.dev.nickbolles.com/explore/projects](https://gitlab.dev.nickbolles.com/explore/projects)

I host a [Gitlab CE](https://about.gitlab.com/) server on my home server (powered by [Unraid](https://www.unraid.net/), [Docker](https://www.docker.com/), [Traefik](https://traefik.io/) and [Lets Encrypt](https://letsencrypt.org/)). Because all of the data is hosted locally, I keep most of my code on my gitlab server. Most of the links in this page link there. 

#### Dev Ops
One of the coolest things about running my own gitlab server, and having a docker based home server, is the dev ops and auto review apps. This means that I can setup Gitlab CI/CD to spin up a docker container that will do testing, building, performance testing etc. on every commit, as well as deploy to a docker container and automatically setup the routing with Traefik and set up HTTPS with Let's Encrypt.

For example, when I commit a change to my website it runs through 3 phases
1. Build the app, which will check for any build issues, especially with Typescript (this is seperate because Docker hides some build issues sometimes, not quite sure why)
3. Build a docker container for the app
5. Deploy the docker container with Traefik configured to setup Lets Encrypt automagically

### Other Services I Run On My Server
- Gitlab - https://gitlab.dev.nickbolles.com/explore/projects
- Gitlab dev ops runners
- Private NPM registry - https://npm.nickbolles.com/
- Jira
- MongoDB
- MariaDB
- Postgresql
- Redis
- InfluxDB
- Elastic Search & Kibana
- Nextcloud
- Multiple [code-server](https://github.com/cdr/code-server) instances for development
- Tons of other stuff, Docker is awesome!


# Projects

## Foursee
- [Source](https://gitlab.dev.nickbolles.com/foursee)

#### Summary
Foursee is an app to help students (mostly me) see the effects of every point of every assignment on their grade for that course, their semester GPA and their overall GPA. I can't count how many times myself or friends grabbed a calculator and tried our best to calculate this. If we just had an app to keep track of it and show us the minimum and maximum grades we can get and what the bigger effect would be if we got those grades, it would save a bunch of time that we could be spending on studying!

This was the first app that I really dove into. I learned a ton and re-wrote it like 6 times. I just wanted to learn how to do it right. In it's current state it's actually very well organized and has some really cool patterns to keep the code really DRY. It isn't complete, but there is a rendering on the [app's readme](https://gitlab.dev.nickbolles.com/foursee/foursee-app/blob/development/readme.md) of what it looks like in action.

#### Built With
- Client
  - Angular 1.x (1.5.9 to be exact)
  - Angular Material
  - Angular Animate (ngAnimate) and custom animation code on top
  - Typescript
  - SASS
  - D3
  - Ui Router
  - Moment.js
  - Gulp
  - Webpack
  - Jasmine
  - Karma
  - Typedoc
  - Cordova
  - @nb/eduItemModel - [Private NPM Link](http://npm.nickbolles.com/#/detail/@nb/eduitemmodel)
    - This is the model backing the project. It's huge, and uses an Observable data model ([@nb/nbobservable](http://npm.nickbolles.com/#/detail/@nb/nbobservable)) and proxies ([MDN Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy) - [npm module @nb/nbproxy](http://npm.nickbolles.com/#/detail/@nb/nbproxy)) to notify observers, **much like [Vue.js V3.0 will do](https://medium.com/the-vue-point/plans-for-the-next-iteration-of-vue-js-777ffea6fabf)**
- Server
  - Node.js
  - Express.js
  - Passport.js
  - Typescript
  - Nodemailer
  - Handlebars
  - Moment.js
  - Mongoose (and Mongodb)
  - Socket.IO
  - Winston.js
  
## Min-max GPA Calculator
- [Live Link](https://nickbolles.github.io/minmaxgpacalc/)
- [Source](https://github.com/NickBolles/minmaxgpacalc)

#### Summary
This is a simple calculator that calculates your minimum and maximum attainable GPA given your current credits, GPA and how many credits you have left. 

#### Built With
- Angular 2+
- Angular Material 2
- Angular CLI
- Typescript
- SASS
- D3
- RXJS

## Fantasy Pay
- [Source](https://gitlab.dev.nickbolles.com/nbolles/fantasypayserver)
- [More details in the projects Readme.md](https://gitlab.dev.nickbolles.com/nbolles/fantasypayserver/blob/master/README.md)

#### Summary
This app was the start of an entrepreneurial effort by a friend of mine. It was going to be a service for collecting and dispersing Fantasy Football and other contest based payments. Unfortunetly we got a ways down the road and realized that the business model had some issues, financially and legally, so we decided to stop the project.

I took this opportunity to dive into Angular 2+ and typescript. I learned a ton and really got into advanced Typescript usage. 

#### Built With
- Client
  - Angular 2+ (4.x)
  - Angular Material 2
  - Angular Animate
  - Angular CDK
  - Angular CLI
  - Typescript
  - SASS
  - RXJS
  - NGRX store
  - Animate.css
  - D3
  - Moment.js
  - Stripe (payments)
  - Jasmine
  - Karma
  - Typedoc
- Server
  - Node.js
  - Express.js
  - Passport.js
  - Typescript
  - Nodemailer
  - Mongoose (and Mongodb)
  - Socket.IO

## Vue App
Source: https://gitlab.dev.nickbolles.com/Matt-n-nick/app

Demo: (currently login is not working because of a package version issue) https://develop-matt-n-nick-app.dev.nickbolles.com

#### Summary
This is an app that I've been working on with a buddy, Matt, to teach him a bit about how to code websites. We are both using it as an opportunity to learn Vue.js more in-depth as well as Feathers.js as the backend. 

Originally we went down a route of making this an app for recording and reviewing specific meals at restaraunts so that I can actually remember that I don't like the Chicken Parmigiana from Olive garden... Since then we've kinda just been approaching it as a learning experience and will probably use it as a base for something else in the near future.

#### Built With
- Client
  - Nuxt.js (Vue.js)
  - Typescript
  - Vuex
  - Feathers-Vuex
  - Nuxt class component
  - Nuxt property decorators
  - Vuetify
  - SASS
- Server
  - Node.js
  - Feathers-plus/CLI
  - Feathers.js
  - Passport.js
  - Notifme-sdk and notification-catcher
  - Mongoose (and Mongodb)
  - Socket.IO


## Open Source Contributions
### React.js

- [Next.js auth-module](https://github.com/iaincollins/next-auth)

  I submitted the first iteration of Typescript typings for the next-auth module
### Vue.js

- [Nuxt.js](https://github.com/nuxt/nuxt.js)
  - Helped design and test the native Typescript support in Nuxt 2.4. I've also been active in the support chat to recieve help and help others.
  - Help add Typescript support to create-nuxt-app - [Pull Request](https://github.com/nuxt/create-nuxt-app/pull/328)
- nuxt.js/axios
  - Improve typescript instructions - [Pull Request](https://github.com/nuxt-community/axios-module/pull/264)

### Nest.js

- Fixes for @nestjs/graphql - [Pull Request](https://github.com/nestjs/graphql/pull/317)
- Create Accounts.js module for integration into nest.js - [Pull Request](https://github.com/accounts-js/accounts/pull/840)

### Feathers.js

- [Feathers core](https://github.com/feathersjs/feathers)

  I've submitted a few typing enhancements to the Typescript type definitions in [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped). I'm also helping convert the entire codebase to Typescript to make maintaining type definitions a thing of the past and improve multiple internal Feathers issues. I've also been active in the chat to learn and help others.
  
- [Feathers-plus/CLI](https://github.com/feathers-plus/generator-feathers-plus)

  Feathers-plus/CLI is a coding buddy. It's built on top of Yeoman and generates a ton of code for you and is safe to re-run. This is huge because it's not just a copy and paste boilerplate, it's a living breathing upgradable project. I've become one of the several goto people for Typescript in Feathers-plus/CLI and I am in communication with the core maintainer. 
   As of october 2019, this project has become stagnant. I've begun using other server frameworks (primarily nest.js)
  
- [Feathers-Vuex](https://github.com/feathers-plus/feathers-vuex)

  Feathers-Vuex makes communicating between feathers and your vue components super simple, and efficient (thanks to state management by Vuex). I've developed the typescript types and a few other fixes for Feathers-Vuex.
  - support SSR and fix serialization of models - [Pull Request](https://github.com/feathersjs-ecosystem/feathers-vuex)
  
- [Feathers-hooks-commons](https://github.com/feathers-plus/feathers-hooks-common)

  I've contributed to a few PRs on this, including [typescript definitions](https://github.com/feathersjs-ecosystem/feathers-hooks-common/pull/469) and submitted a few enhancements

### Accounts.js

- Create Accounts.js module for integration into nest.js - [Pull Request](https://github.com/accounts-js/accounts/pull/840)
- Several Misc fixes - to [typings](https://github.com/accounts-js/accounts/pull/825) - to [error handling](https://github.com/accounts-js/accounts/pull/826) - to [Impersonation API](https://github.com/accounts-js/accounts/pull/841)

### Misc

- Strapi.js

  Strapi is a CMS that aims to be completely customizable. I started using it in a project and did several PRs before hitting deal-breaker and not simple to fix issues and moved to a Feathers based solution
