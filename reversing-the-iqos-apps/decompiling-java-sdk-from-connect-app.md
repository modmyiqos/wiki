---
description: gathering com.pmi.iqossdk from apk
---

# Decompiling Java SDK from Connect App

#### [Requirements](https://github.com/modmyiqos/reverse-engineering#requirements)

#### Clone Reverse Engineering repository

```
git clone https://github.com/modmyiqos/reverse-engineering.git
```

{% hint style="info" %}
Repository it self does not contain decompiled code, but it has scripts/tools to make it automatically
{% endhint %}

#### [Run decompilation process](https://github.com/modmyiqos/reverse-engineering#get-compmiiqossdk)

```text
cd reverse-engineering
yarn get:iqossdk
```

If decompiling was successful you should see output like this:

```text
$ yarn get:iqossdk                                                       Fri Mar 12 00:21:45 2021
yarn run v1.22.10
$ yarn workspaces run get:iqossdk

> utils
$ ts-node get-iqos-sdk.ts
Selecting assets-v0
Downloading apk from https://github.com/modmyiqos/reverse-engineering/releases/download/assets-v0/iqos_connect.apk
Starting decompilation of /var/folders/sw/79jr8npj17s427twhdc9tg0m0000gn/T/iqos_connect.apk
✔ Unzipping APK into temporary directory
✔ Decompiling DEX file 1 of 3 (9s)
✔ Decompiling DEX file 2 of 3 (11s)
✔ Decompiling DEX file 3 of 3 (3s)
✔ Cleaning up temporary files
Copying com.pmi.iqossdk
Cleaning up
✨  Done in 32.83s.
```

Then SDK will be located in iqossdk folder at the root of the repo

