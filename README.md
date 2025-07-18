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

## Full Locked Dependencies

Some dependencies are completely locked at the moment. Descriptions below on why that is the case:

- `bson` to `6.2.0`: This is patched in the frontend via Yarn 4. Patched to fix a bug where bson would use top-level await for seemingly no reason. This breaks safari. Just the awaits were removed from bson.mjs. If this gets fixed, then the lock can be removed. See [this PR](https://github.com/WebKit/WebKit/pull/24122) for when this can be unlocked. Once that is merged, the dashboard can be tested with the latest version of bson.

## Major Locked Dependencies

Some dependencies are major-version locked. Mainly due to ESM. All personal libraries seem like they will need to be upgraded at the same time in order to do this.

- `node-fetch`
- `octokit`

## Schedule

The schedule is currently setup as `"schedule": ["* * * * 1,2"]` which means every Monday and Tuesday. Those seemed like good days at the time.
