# titanium-build-android

This action installs [Titanium SDK](https://titaniumsdk.com) and builds an Android debug apk.

The project root has to be a Titanium App project in order to work.

# Inputs

## `version`

By default, the `11.1.1.GA` will be used. But you can change it to a custom version too.

# Example

```yaml
name: Titanium Workflow
on: push
jobs:
  test:
    name: Run Tests
    runs-on: macos-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build Titanium Android app
        uses:  m1ga/titanium-android-build@v1
        with:
          version: 11.1.1.GA
```
