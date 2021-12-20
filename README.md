# gha-mobile-publish

The purpose of this GitHub Action is to automate the publishing of mobile apps for
internal testing.

### Usage

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
          expo-username: ${{ secrets.EXPO_USER }}
          expo-password: ${{ secrets.EXPO_PASSWORD }}
```

### Optional Params

#### Teams Webhook

Teams Webhook URL to notify on successful build. If none is provided, no call will be made

Default: ''

```yaml
  with:
    webhook: 'https://dmsi.webhook.office.com/...'
```
