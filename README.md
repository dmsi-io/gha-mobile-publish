# gha-mobile-publish

The purpose of this GitHub Action is to automate the publishing of mobile apps for
internal testing.

## Inputs

| NAME         | DESCRIPTION                                          | TYPE      | REQUIRED | DEFAULT                     |
|:-------------|:-----------------------------------------------------|:----------|:---------|:----------------------------|
| `branch`     | What Expo branch to push to                          | `string`  | `false`  | The current git branch name |
| `expo-token` | The token for the expo account being released from   | `string`  | `true`   |                             |
| `message`    | What message to include on the update                | `string`  | `false`  | The last git commit message |
| `suffix`     | A version suffix to append to the end of the version | `string`  | `false`  |                             |

## Usage

```yaml
name: Publish

on:
  push:
    branches:
      - develop

jobs:
  publish:
    name: Publish
    runs-on: ubuntu-latest
    steps:
      - name: Publish
        uses: dmsi-io/gha-mobile-publish@main
        with:
          expo-token: ${{ secrets.EXPO_TOKEN }}
```
