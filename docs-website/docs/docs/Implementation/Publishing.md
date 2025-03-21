# Publishing WatermelonDB

### Step 1: Run all automated tests

```bash
yarn ci:check && yarn test:ios && yarn test:android && yarn ktlint
```

### Step 2: Test manually in a real app

```bash
yarn build
```

Then copy `dist/` and replace `app/node_modules/@nozbe/watermelondb` with it.

If a quick smoke test passes, proceed to publish.

### Step 3: Update CHANGELOG

Change `Unreleased` header to the new version, add new Unreleased

### Step 4: Publish

```bash
npm run release

# skips checks (only use on prerelease)
npm run release --skip-checks
```

Don't use `yarn release` (or `yarn publish`) — it won't work (yarn doesn't support NPM 2FA).
