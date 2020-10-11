This repo explores how you can use a monorepo consisting of multiple applications and successfully configure and deploy them to separate Vercel projects.

# Getting started

For this project, we are going to be creating two Next.js apps. The first example will use `create-next-app`, and the second example will use `create-next-app` to generate a Next.js app that uses TypeScript.

We will then use Vercel integration to define two separate projects for these apps.

Once we have our two separate projects defined, we will then look at how we can improve our Vercel integration when changes to either application occur.

## Create the applications

### Create the Next.js app

We will use the latest version of `create-next-app` to generate our Next.js app:

```sh
$ npx create-next-app nextjs
```

Let's verify that our first app runs by starting Next.js in development mode:

```sh
$ cd nextjs
$ npm run dev
```
