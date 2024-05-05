# VyHub Documentation

This is the official documentation for the [VyHub](https://vyhub.net) donation and management system. VyHub helps to monetize and manage your gaming community in many aspects. 
The documentation is reachable at [https://docs.vyhub.net](https://docs.vyhub.net).

# How to deploy

1. `pip install -r requirements.txt`
2. Create a branch for each version in the format of `<major>.<minor>`.

## Deploy latest version

If we are making changes on the latest version, we want to tag it as `latest`.

`mike deploy <major>.<minor> latest -u --push`

Example: `mike deploy 0.2 latest -u --push`

## Deploy an older version

If we are making changes to an older version, we want to deploy it, without adding the `latest` label.

`mike deploy <major>.<minor> --push`

Example: `mike deploy 0.1 --push`
