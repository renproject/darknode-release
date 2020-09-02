# darknode-release

Repo for publishing darknode releases before the `darknode` repo is public. 

# Usage 

1. Modify the `var.env` file with the release details you want. 
   - `ref` reference of darknode repo you want to build. It can be a tag name, a branch name or a full commit hash(40 characters)
     e.g. `ref=release/0.2.12`, `ref=cdce9c5f629e8df011f31e65386e9da6784c806e`
   - `release`  name of the release which will be published in this repo.
      Make sure the release has a proper name and doesn't conflict with existing releases.
   - `prerelease` whether the release will be a pre-release or not, should be either `true` or `false` 
2. Commit and push the change to master branch 
3. Wait for the CI to pass. 
4. Make sure your CLI has version >= 3.0.10. Update darknode by running `darknode update DARKNODE-NAME --version YOUR-RELEASE-NAME` 

# Build release externally

A workflow has been set up listening for tag creation events in darknode repo. 
You can create a tag from the darknode repo and it will also create a new release here (with the same name of the tag).
The tag can be commit from any branch. 
```shell
git tag TAG_NAME
git push origin TAG_NAME
```

# Skip CI

CI will only be trigger with commits to master. If you want to update the README file or push something without triggering the CI, include `skipCI` in your commit message, CI will be ignored. 

# Known issue

- If you make a release by giving a commit hash. The binary will not contain the correct branch name. (e.g. 1.0.11-HEAD-a355b0b)
- If you fill the var.env file with invalid values, it might not work.
- If you try to create a release which already exists, it won't override the old one. 
