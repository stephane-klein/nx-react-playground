# React Nx project

This playground use *pnpm* package manager. Go to [../yarn/](../yarn/) if you prefer *yarn*.

```sh
$ mise install
$ pnpm install
$ direnv allow
```

Here are some commands (called *targets* in the Nx ecosystem) that can be run on app1:

```
$ nx lint app1
$ nx build app1
$ nx serve app1
$ nx typecheck app1
$ nx test app1
```

## How did I initially build this project?

```sh
$ cat <<'EOF' > package.json
{
  "name": "playground",
  "private": true
}
EOF
$ cat <<'EOF' > pnpm-workspace.yaml
packages:
  - packages/*
  - apps/*
EOF
```

Next:

```sh
$ pnpm dlx nx@22.0.3 init
 WARN  The "workspaces" field in package.json is not supported by pnpm. Create a "pnpm-workspace.yaml" file instead.
✔ Would you like a minimum or guided setup? · Guided

 NX   🐳 Nx initialization


 NX   📦 Installing dependencies


added 123 packages, and audited 124 packages in 4s

27 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities

 NX   🧐 Checking dependencies


 NX   📦 Installing Nx

✔ Which AI agents, if any, would you like to set up? · No items were selected

 NX   🛠️ Setting up Self-Healing CI and Remote Caching

✔ Would you like to enable AI-powered Self-Healing CI and Remote Caching? · skip

 NX   🎉 Done!

- Learn more about what to do next at https://nx.dev/getting-started/adding-to-existing
- Read a detailed guide about adding Nx to NPM/YARN/PNPM workspaces: https://nx.dev/recipes/adopting-nx/adding-to-monorepos
- Learn how Nx helps manage your TypeScript monorepo: https://nx.dev/features/maintain-ts-monorepos
```

```
$ rm package-lock.json
$ pnpm install
```

Install `@nx/react` plugin:


```
$ nx add @nx/react

✔ Installing @nx/react@22.0.3...
⠋ Initializing @nx/react...
 NX  Generating @nx/react:init

UPDATE package.json

added 2 packages, removed 2 packages, and audited 845 packages in 2s

134 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
✔ Initializing @nx/react...

 NX   Package @nx/react added successfully.
```

Create `apps/app1` React application:

```sh
$ nx generate @nx/react:app apps/app1 \
    --routing \
    --linter=eslint \
    --bundler=rspack \
    --unitTestRunner=vitest \
    --e2eTestRunner=none \
    --port=4200 \
    --style=tailwind

 NX  Generating @nx/react:application

Fetching @nx/rspack...
UPDATE nx.json
CREATE tsconfig.base.json
CREATE tsconfig.json
UPDATE package.json
CREATE apps/app1/rspack.config.js
CREATE apps/app1/src/app/app.spec.tsx
CREATE apps/app1/src/assets/.gitkeep
CREATE apps/app1/src/favicon.ico
CREATE apps/app1/src/index.html
CREATE apps/app1/src/main.tsx
CREATE apps/app1/tsconfig.app.json
CREATE apps/app1/src/app/nx-welcome.tsx
CREATE apps/app1/src/app/app.tsx
CREATE apps/app1/src/styles.css
CREATE apps/app1/tsconfig.json
CREATE apps/app1/package.json
CREATE apps/app1/postcss.config.js
CREATE apps/app1/tailwind.config.js
CREATE eslint.config.mjs
CREATE apps/app1/eslint.config.mjs
UPDATE .gitignore
CREATE apps/app1/vite.config.ts
CREATE apps/app1/tsconfig.spec.json
CREATE vitest.workspace.ts
Scope: all 2 workspace projects
 WARN  Moving tslib that was installed by a different package manager to "node_modules/.ignored"
Downloading @swc/core-linux-x64-musl@1.5.29: 20.62 MB/20.62 MB, done
Downloading @swc/core-linux-x64-gnu@1.5.29: 16.66 MB/16.66 MB, done
 WARN  8 deprecated subdependencies found: @types/minimatch@6.0.0, abab@2.0.6, domexception@4.0.0, glob@7.2.3, glob@8.1.0, inflight@1.0.6, keygrip@1.1.0, stable@0.1.8
Packages: +571 -74
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++--------------------------------------------
Progress: resolved 1445, reused 978, downloaded 331, added 571, done
node_modules/.pnpm/nx@22.0.3_@swc-node+register@1.9.2_@swc+core@1.5.29_@swc+helpers@0.5.17__@swc+types@0.1_48b358332db38ee739b6ec82ad201e1d/node_modules/nx: Running postinstall script, done in 307ms
 WARN  Issues with peer dependencies found
.
└─┬ @swc-node/register 1.9.2
  └─┬ @swc-node/core 1.14.1
    └── ✕ unmet peer @swc/core@">= 1.13.3": found 1.5.29

dependencies:
+ react-router-dom 6.29.0 (7.9.5 is available)

devDependencies:
+ @eslint/js 9.39.1
+ @nx/eslint 22.0.3
+ @nx/eslint-plugin 22.0.3
+ @nx/js 22.0.3
+ @nx/rspack 22.0.3
+ @nx/vite 22.0.3
+ @nx/web 22.0.3
+ @rspack/cli 1.6.3
+ @rspack/core 1.6.3
+ @rspack/dev-server 1.1.4
+ @rspack/plugin-react-refresh 1.5.3
+ @swc-node/register 1.9.2 (1.11.1 is available)
+ @swc/cli 0.6.0 (0.7.9 is available)
+ @swc/core 1.5.29 (1.15.1 is available)
+ @swc/helpers 0.5.17
+ @testing-library/dom 10.4.0 (10.4.1 is available)
+ @testing-library/react 16.3.0
+ @types/node 20.19.9 (24.10.1 is available)
+ @types/react 19.2.4
+ @types/react-dom 19.2.3
+ @vitejs/plugin-react 4.7.0 (5.1.1 is available)
+ @vitest/coverage-v8 3.2.4 (4.0.8 is available)
+ @vitest/ui 3.2.4 (4.0.8 is available)
+ autoprefixer 10.4.13 (10.4.22 is available)
+ eslint 9.39.1
+ eslint-config-prettier 10.1.8
+ eslint-plugin-import 2.31.0
+ eslint-plugin-jsx-a11y 6.10.1 (6.10.2 is available)
+ eslint-plugin-react 7.35.0 (7.37.5 is available)
+ eslint-plugin-react-hooks 5.0.0 (7.0.1 is available)
+ jiti 2.4.2 (2.6.1 is available)
+ jsdom 22.1.0 (27.2.0 is available)
+ postcss 8.4.38 (8.5.6 is available)
+ react-refresh 0.14.2 (0.18.0 is available)
+ tailwindcss 3.4.3 (4.1.7 is available)
+ tslib 2.8.1
+ typescript 5.9.3
+ typescript-eslint 8.46.4
+ vite 7.2.2
+ vitest 3.2.4 (4.0.8 is available)

╭ Warning ───────────────────────────────────────────────────────────────────────────────────╮
│                                                                                            │
│   Ignored build scripts: @parcel/watcher, @swc/core.                                       │
│   Run "pnpm approve-builds" to pick which dependencies should be allowed to run scripts.   │
│                                                                                            │
╰────────────────────────────────────────────────────────────────────────────────────────────╯

Done in 10.4s using pnpm v10.22.0

 NX   👀 View Details of app1

Run "nx show project app1" to view details about this project.
```

```
$ pnpm approve-builds
✔ Choose which packages to build (Press <space> to select, <a> to toggle all, <i> to invert selection) · @parcel/watcher, @swc/core
✔ The next packages will now be built: @parcel/watcher, @swc/core.
Do you approve? (y/N) · true
node_modules/.pnpm/@swc+core@1.5.29_@swc+helpers@0.5.17/node_modules/@swc/core: Running postinstall script, done in 78ms
node_modules/.pnpm/@parcel+watcher@2.5.1/node_modules/@parcel/watcher: Running install script, done in 34ms
```
