```sh
$ mise install
$ yarn install
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

```
$ yarn dlx nx@22.0.3 init
➤ YN0000: · Yarn 4.11.0
➤ YN0000: ┌ Resolution step
➤ YN0085: │ + nx@npm:22.0.3, @emnapi/core@npm:1.7.0, @emnapi/runtime@npm:1.7.0, @emnapi/wasi-threads@npm:1.1.0, @jest/diff-sequences@npm:30.0.1, @jest/get-type@npm:30.1.0, and 131 more.
➤ YN0000: └ Completed in 0s 777ms
➤ YN0000: ┌ Fetch step
➤ YN0013: │ 128 packages were added to the project (+ 48.18 MiB).
➤ YN0000: └ Completed
➤ YN0000: ┌ Link step
➤ YN0000: │ ESM support for PnP uses the experimental loader API and is therefore experimental
➤ YN0007: │ nx@npm:22.0.3 [dc3fc] must be built because it never has been before or the last one failed
➤ YN0000: └ Completed in 0s 821ms
➤ YN0000: · Done with warnings in 1s 770ms

✔ Would you like a minimum or guided setup? · Guided

 NX   🐳 Nx initialization


 NX   📦 Installing dependencies


added 123 packages, and audited 124 packages in 3s

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
