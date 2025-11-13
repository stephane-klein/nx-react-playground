```sh
$ mise install
```

## How I setup the project?

```
$ yarn dlx nx@22.0.3 init
➤ YN0000: · Yarn 4.11.0
➤ YN0000: ┌ Resolution step
➤ YN0085: │ + nx@npm:22.0.3, @emnapi/core@npm:1.7.0, @emnapi/runtime@npm:1.7.0, @emnapi/wasi-threads@npm:1.1.0, and 133 more.
➤ YN0000: └ Completed in 1s 515ms
➤ YN0000: ┌ Fetch step
➤ YN0013: │ 128 packages were added to the project (+ 48.18 MiB).
➤ YN0000: └ Completed in 1s 249ms
➤ YN0000: ┌ Link step
➤ YN0000: │ ESM support for PnP uses the experimental loader API and is therefore experimental
➤ YN0007: │ nx@npm:22.0.3 [dc3fc] must be built because it never has been before or the last one failed
➤ YN0000: └ Completed in 0s 755ms
➤ YN0000: · Done with warnings in 3s 550ms

CREATE nx.json
CREATE .gitignore
CREATE .nx/nxw.js
CREATE nx.bat
CREATE nx


 NX   🧐 Checking dependencies


 NX   📦 Installing Nx

✔ Which AI agents, if any, would you like to set up? · No items were selected

 NX   🛠️ Setting up Self-Healing CI and Remote Caching

✔ Would you like to enable AI-powered Self-Healing CI and Remote Caching? · skip

 NX   🎉 Done!

- Learn more about what to do next at https://nx.dev/getting-started/adding-to-existing
$ rm nx.bat
```
