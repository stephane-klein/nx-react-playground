```sh
$ mise install
$ pnpm install
$ direnv allow
```

## How did I initially build this project?

```sh
$ cat <<'EOF' > package.json
{
  "name": "playground",
  "private": true,
  "workspaces": [
    "packages/*",
    "apps/*"
  ]
}
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
