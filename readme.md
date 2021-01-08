# pkg-fetch

## Adding patches

1. Open `alexk111/node` repo
2. Create a `vXX.XX.XX-pkg` branch from a newer version commit (tagged with `vXX.XX.XX`)
3. Merge a previous patched `vXX.XX.XX-pkg` branch into the new one and resolve conflicts
4. Commit
5. Execute `git diff --output=node.patch --unified=5 --src-prefix=node/ --dst-prefix=node/ HEAD^ HEAD`
6. Copy the `node.patch` to `patches/node.vXX.XX.XX.cpp.patch` in this repo
7. Update `patches/patches.json` with the new version

## Building & Releasing Patched Node.js

On each OS:

1. `yarn start`
2. Upload the compiled binary file to Releases

## About

Github Releases page of this project contains base binaries,
used by `pkg` to create executables. `pkg-fetch` npm package
downloads base binaries or compiles them from source.
