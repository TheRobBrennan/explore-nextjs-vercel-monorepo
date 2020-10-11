This repo explores how you can use a monorepo consisting of multiple applications and successfully configure and deploy them to separate Vercel projects.

Before following along with this project, please make sure that you:

- Have created a free account on [Vercel](https://vercel.com/)
- Have installed Node.js `v12.13.1` or later on your development machine

# Getting started

For this project, we are going to be creating two Next.js apps. The first example will use `create-next-app`, and the second example will use `create-next-app` to generate a Next.js app that uses TypeScript.

We will then use Vercel integration to define two separate projects for these apps.

Once we have our two separate projects defined, we will then look at how we can improve our Vercel integration when changes to either application occur.

## Create the applications

### Create a Next.js app

We will use the latest version of `create-next-app` to generate our Next.js app:

```sh
$ npx create-next-app nextjs
```

Let's verify that our app runs by starting Next.js in development mode:

```sh
$ cd nextjs
$ npm run dev
```

### Create a Next.js app using TypeScript

We will use the latest version of `create-next-app` to generate our Next.js app with TypeScript automatically configured for us:

```sh
$ npx create-next-app nextjs-with-typescript --example with-typescript
```

Let's verify that our app runs by starting Next.js in development mode:

```sh
$ cd nextjs-with-typescript
$ npm run dev
```

## Vercel

The first step is to make sure that your have configured [Vercel for GitHub](https://vercel.com/docs/git-integrations/vercel-for-github) to work with your repository.

### Initial setup and configuration

In this example, we are going to create two separate Vercel projects for the example applications we created.

First, let's use the Vercel CLI to define a project - `envm-nextjs` - for the first application we created:

```sh
$ cd nextjs
$ npx vercel
Vercel CLI 20.1.2
? Set up and deploy “~/repos/explore-nextjs-vercel-monorepo/nextjs”? [Y/n] y
? Which scope do you want to deploy to? TheRobBrennan
? Link to existing project? [y/N] n
? What’s your project’s name? envm-nextjs
? In which directory is your code located? ./
Auto-detected Project Settings (Next.js):
- Build Command: `npm run build` or `next build`
- Output Directory: Next.js default
- Development Command: next dev --port $PORT
? Want to override the settings? [y/N] n
🔗  Linked to therobbrennan/envm-nextjs (created .vercel)
🔍  Inspect: https://vercel.com/therobbrennan/envm-nextjs/5i6myhzjk [1s]
✅  Production: https://envm-nextjs.vercel.app [copied to clipboard] [28s]
📝  Deployed to production. Run `vercel --prod` to overwrite later (https://vercel.link/2F).
💡  To change the domain or build command, go to https://vercel.com/therobbrennan/envm-nextjs/settings
```

This will create a new Vercel project named `envm-nextjs`.

You can then use the Vercel web interface to:

- Associate your repo with a `GIT INTEGRATION`
- Update the general settings of this project so that the root directory uses the `nextjs` subdirectory in this repo

Next, we will follow a similar process to use the Vercel CLI to define a project - `envm-nextjs-with-typescript` - for the second application we created:

```sh
$ cd nextjs-with-typescript
$ npx vercel
Vercel CLI 20.1.2
? Set up and deploy “~/repos/explore-nextjs-vercel-monorepo/nextjs-with-typescript”? [Y/n] y
? Which scope do you want to deploy to? TheRobBrennan
? Link to existing project? [y/N] n
? What’s your project’s name? envm-nextjs-with-typescript
? In which directory is your code located? ./
Auto-detected Project Settings (Next.js):
- Build Command: `npm run build` or `next build`
- Output Directory: Next.js default
- Development Command: next dev --port $PORT
? Want to override the settings? [y/N] n
🔗  Linked to therobbrennan/envm-nextjs-with-typescript (created .vercel)
🔍  Inspect: https://vercel.com/therobbrennan/envm-nextjs-with-typescript/hp7qdw8bo [966ms]
✅  Production: https://envm-nextjs-with-typescript.vercel.app [copied to clipboard] [35s]
📝  Deployed to production. Run `vercel --prod` to overwrite later (https://vercel.link/2F).
💡  To change the domain or build command, go to https://vercel.com/therobbrennan/envm-nextjs-with-typescript/settings
```

You can then use the Vercel web interface to:

- Associate your repo with a `GIT INTEGRATION`
- Update the general settings of this project so that the root directory uses the `nextjs-with-typescript` subdirectory in this repo
