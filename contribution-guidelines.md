# Contribution guidelines

### Development and Production branches

Our `development` and `production` branches are the two main branches through which codes are tested and pushed through live `environment`. Any contribution needs to follow a proper `git-flow` to integrate your codes to these branches for testing and deployments.

### Feature branch

Any **feature-branch** needs to be created from **production**. Once stable codes are ready, create a pull request to test your codes in our `development` branch where we manage our testing servers. **feature-branchs** needs to be prefixed with `feat`. Example: `feat/test-editor`, `feat/email-templating` etc.

```sh
> git checkout production
> git checkout -b feat/email-templating
```

If your codes work and pass the **tests**, you also need to push your codes to `production` at the same time through a pull request for final checks and deployment preparations.

> CAUTION: Never pull any code in your **feature-branch** from `development`. You can only pull codes from **production** `environment` or `brnach` we should say. Whenever new stable codes are published here, keep your branches in sync with **production**. Bear in mind **development** is almost like a replica of **production**. Only stable codes from different **feature** branches are lying there to test the integration.

After all testing are done features will be merged into `release` and the `feature` branch will be deleted.

### HotFix branch

A **hotfix-branch** is always created to provide resolutions on **P1 Incidents** or **Bug reports**. Checkout a new branch from `production` with a prefix `hot-fix`. Fix your code in isolation here. 

```sh
> git checkout production
> git checkout -b hot-fix/validation-rules
```

For testing provide your codes through **PR**:

1. Send your codes to `development`.
2. If step `1` passes send your code to `production`.

Your branch will be merged to `release` after ensuring proper `QA`.

After your `hot-fix` branch is merged into `release`, the `hot-fix` will be deleted from repository.

> CAUTION: Never pull any code in your **hotfix-branch** from branchs other than `production`.

### Release branch

Release branches are created to send stable codes to `live-servers` and these are prefixed with `release`. We create them for `tagging`, `minor bug fixing` and `deployment` preparations and
`documentation` purposes.

> CAUTION: Never pull any code in a **release-branch** from branchs other than `production`.

### Important Notes

> Any **pull-request** in this repository requires atleast one person to `review` manually before they can be merged to the **target branch**.