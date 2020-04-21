# darknode-release
Repo for publishing darknode releases before the `darknode` repo is public

# Usage 

Say you want to publish a new release `x.y.z`. Following the steps below
1. Make sure there exists a `release/x.y.z` branch in darknode repo and its latest commit is the one we want to deploy 
2. Update the content of `version.md` file to `x.y.z`
3. Push the change to master
4. Wait for the CI to pass. 
5. Update darknode by `darknode update DARKNODE-NAME` or `darknode update --tags DARKNODE-TAG`

# Skip CI
CI will only be trigger with commits to master. If you want to update the README file or push something without triggering the CI, include `skipCI` in your commit message, CI will be ignored with your push. 
