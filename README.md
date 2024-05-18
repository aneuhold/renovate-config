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
