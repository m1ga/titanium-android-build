# titanium-build-android

This action installs [Titanium SDK](https://titaniumsdk.com) and builds an Android debug apk.

The project root has to be a Titanium App project in order to work.

# Inputs

## `version`

By default, the `12.0.0.GA` will be used. But you can change it to a custom version too.

# Store version

You can also build a store version with your key and secret. For this you will need to add two Github Action secrets: `ANDROID_KEYSTORE` (base64 string of your keystore file) and `ANDROID_KEYSTORE_SECRET` (password):

* run `base64 my.keystore > output.txt` and copy that text into `ANDROID_KEYSTORE`.
* put your password into `ANDROID_KEYSTORE_SECRET`

If you don't set the secrets it will build a normal debug apk.

# Example

```yaml
name: Titanium Workflow
on: push
jobs:
  test:
    name: Run Tests
    runs-on: macos-latest
    steps:
      - uses: actions/checkout@v3
      - name: Build Titanium Android app
        uses:  m1ga/titanium-android-build@v2
        with:
          version: 12.0.0.GA
          keystore: ${{ secrets.ANDROID_KEYSTORE }}
          keystore_secret: "${{ secrets.ANDROID_KEYSTORE_SECRET }}"
```
