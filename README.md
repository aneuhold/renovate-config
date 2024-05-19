# renovate-config

A personal renovate config preset

## Setup

For a new repo, add the following to a new file in the root of the repo `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>aneuhold/renovate-config"]
}
```

Then go to [GitHub settings here](https://github.com/settings/installations/50400353) and add the new repository to the list at the bottom of the page.

## Locked Dependencies

Some dependencies are completely locked at the moment. Descriptions below on why that is the case:

- `bson` to `6.2.0`: This is patched in the frontend via Yarn 4. Patched to fix a bug where bson would use top-level await for seemingly no reason. This breaks safari. Just the awaits were removed from bson.mjs. If this gets fixed, then the lock can be removed.
