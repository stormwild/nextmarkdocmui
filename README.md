This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.tsx`. The page auto-updates as you edit the file.

[API routes](https://nextjs.org/docs/api-routes/introduction) can be accessed on [http://localhost:3000/api/hello](http://localhost:3000/api/hello). This endpoint can be edited in `pages/api/hello.ts`.

The `pages/api` directory is mapped to `/api/*`. Files in this directory are treated as [API routes](https://nextjs.org/docs/api-routes/introduction) instead of React pages.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.

## Notes

### Setup

```
yarn create next-app  --typescript nextmarkdocmui
cd nextmarkdocmui
mkdir src && mv pages/ styles/ src
```

Add to `.gitignore`

```
# Yarn
# @see https://yarnpkg.com/getting-started/qa#which-files-should-be-gitignored
.pnp.*
.yarn/*
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions
```

When creating the next app using yarn the initial commit will contain the `.yarn/cache` files. We need to reset the initial commit so that we can apply the proper `.gitignore` to prevent storing the cache in the repo. 

[How to reset the first commit in Git?](https://candost.blog/how-to-reset-first-commit-in-git/)

```
git branch -m main old_main
git checkout --orphan main
# unstage any staged changes
# update .gitignore as above
# commit the initial files
```

Adding MUI

```sh
yarn add @mui/material @emotion/react @emotion/styled
yarn add @fontsource/roboto
yarn add @mui/icons-material
```

Then, you can import it in your entry-point. See [reference](https://mui.com/material-ui/react-typography/#roboto-font-cdn)

Add the following to `_app.tsx`

```ts
import '@fontsource/roboto/300.css';
import '@fontsource/roboto/400.css';
import '@fontsource/roboto/500.css';
import '@fontsource/roboto/700.css';
```

Additional references:

[material-ui/examples/nextjs-with-typescript at master · mui/material-ui](https://github.com/mui/material-ui/tree/master/examples/nextjs-with-typescript)

[mui/material-ui-docs](https://github.com/mui/material-ui-docs)

See docs folder for NextJs integration.

The MUI docs site uses NextJs with a custom theme.

### Errors

[Cannot find module 'next' or its corresponding type declarations](https://stackoverflow.com/questions/69238794/cannot-find-module-next-or-its-corresponding-type-declarations)

```sh
yarn dlx @yarnpkg/sdks vscode
```