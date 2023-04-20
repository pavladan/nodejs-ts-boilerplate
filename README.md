## 🆕 Release

To release a new version after merging features into the master branch, follow these steps:

1. Move to main branch and pull updates from origin:
   ```bash
    git pull
   ```
2. Create and checkout a new `release` branch:
   ```bash
   git checkout -b release
   ```
3. Create release tag and update CHANGELOG.md with the command:
   ```bash
   yarn release
   ```
4. Push updates with follow tags:
   ```bash
   git push --follow-tags origin release
   ```
5. Create Merge Request from the `release` branch to the `main` branch and merge it

Now a new versioned tag has been created. To update the version on the prod servers, you need to change the version tag in the artifacts:

Go to [this line](https://git.exness.io/internal_anti_fraud/artifacts/-/blob/prod.env/helm-charts/iaf_collector/values.yaml#L11), set the new version and push it.
