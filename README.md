# [@next-safe/middleware](https://www.npmjs.com/package/@next-safe/middleware)

The package has been developed from a private monorepo so far, this is a first step to make it public with a proper development and release process.

There is an e2e test app that uses package bundles from source:

https://next-safe-middleware.vercel.app/

## Getting started

Jump into development:

```
yarn dev
```

It will rebuild packages on changes and start the dev server of the e2e test app.

To evaluate things around strict CSPs you need to serve a production build of the e2e test app:

```
yarn start
```

or deploy the e2e test app to Vercel:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fnibtime%2next-safe-middleware%2Ftree%2Fmain)

In your Vercel project settings:

Set `apps/e2e` as "Root Directory" and enable "Include source files outside of the Root Directory in the Build Step."

In "Build & Development Settings":

Set "Framework Preset" to `Next.js`

and override the following commands:

**Build Command:** 
```
cd ../.. && yarn build:e2e:vercel
```
**Install Command:** 
```
yarn install --immutable --immutable-cache
```
