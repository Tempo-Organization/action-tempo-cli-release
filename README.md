# setup-tempo-cli

example usage yml
```
name: generate_mod_releases

permissions:
  contents: write
  discussions: write

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  generate_mod_releases:
    name: generate_mod_releases
    runs-on: [self-hosted, windows, x64]

    steps:
      - name: Checkout
        uses: actions/checkout@v6

      - name: Generate mod releases using action-tempo-cli-release
        uses: Tempo-Organization/action-tempo-cli-release@main
```
Note, you need a github token to upload releases as a secret of your repo with perms to upload.  
I reccomend creating one only for the specific repo you plan to use it for.  
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens?search-overlay-open=true  
https://github.com/softprops/action-gh-release?tab=readme-ov-file
