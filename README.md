# darknode-release

Repo for publishing darknode releases before the `darknode` repo is public

# Usage 

1. Modify the `var.env` file with the release details you want. 
   - `ref` reference of darknode repo you want to build. It can be a tag name, a branch name or a full commit hash(40 characters)
     e.g. `ref=release/0.2.12`, `ref=cdce9c5f629e8df011f31e65386e9da6784c806e`
   - `release`  name of the release which will be published in this repo.
      Make sure the release name doesn't conflict with existing releases.     
2. Commit and push the change to master branch 
3. Wait for the CI to pass. 
4. Update darknode by `darknode update DARKNODE-NAME --version YOUR-RELEASE-NAME`

# Skip CI

CI will only be trigger with commits to master. If you want to update the README file or push something without triggering the CI, include `skipCI` in your commit message, CI will be ignored with your push. 

# Build release externally

A workflow has been set up listening for new tags in darknode repo. 
You can create a tag from the darknode repo and it will also create a new release here (release name with be same as the tag name).
