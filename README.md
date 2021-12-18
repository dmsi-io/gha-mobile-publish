# gha-mobile-publish

The purpose of this GitHub Action is to automate the testing of mobile apps.

### Usage

```yaml
name: Publish

on:
  push:
    branches:
      - develop

jobs:
  test:
    name: Publish
    runs-on: ubuntu-latest
    steps:
      - name: Publish
        uses: dmsi-io/gha-mobile-publish@main
        with:
          expo-username: ${{ secrets.EXPO_USER }}
          expo-password: ${{ secrets.EXPO_PASSWORD }}
```

