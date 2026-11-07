# How to Contribute

To be able to contribute, you will need to create a PullRequest (from a branch or a fork). A PullRequest should be created for each app manifest

Any new app manifest should follow the contribution rules described in the Official Scoop [Contributing
Guide - For Scoop buckets](https://github.com/ScoopInstaller/.github/blob/main/.github/CONTRIBUTING.md#for-scoop-buckets) and the official [App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) wiki page.

## Working on manifests

Each manifest should be in separated branch

### Creating new manifest

To help create new manifest, you can use the "snippets" available in `.vscode\json.code-snippets`.

### Before pushing the new manifest

Locally, after working on a manifest, you should execute the ps1 scripts in the bin folder ("manifest.json" is optional but highly recommended - if omitted it will run all manifests checks and it will take nearly forever :wink:):

```powershell
# replace the %%MANIFEST-NAME%% with the right name
$manifest = "%%MANIFEST-NAME%%"

.\bin\describe.ps1 $manifest
.\bin\checkurls.ps1 $manifest
.\bin\checkver.ps1 $manifest -Update
.\bin\checkhashes.ps1 $manifest -Update
.\bin\formatjson.ps1 $manifest
```

## Pull Request

For app manifests, there is a template that we recommend to use. It will guide to some validations before submitting.

The "PR Title" should follow something like :

| Action | PR Title example                           |
|--------|--------------------------------------------|
| Add    | %%manifest%% : Add version %%version%%     |
| Update | %%manifest%% : Update %%field-or-section%% |
| Remove | %%manifest%% : Remove %%Short_reason%%     |
| ...    | %%manifest%% : %%Short-explanation%%       |

For Work In Progress Pull Requests, please use the [Draft PR feature](https://github.blog/2019-02-14-introducing-draft-pull-requests/).

For a timely review/response, please avoid force-pushing additional commits if your PR already received reviews or comments.

Also we recommend that you add the team `datagone/hexagone` as reviewers.

### Actions & Bot

On a pull request creation, an Action will run that will validate some part of the content. At the end a little report will be shown.

- If it passed, you will need to wait for a reviewer's approval before completing the PR
- If failed you should see missing checkmarks that will tell you on what you should work on. When you think you has resolve the issue (or needed any other changes), you must post the comment "/verify" in the PR and it will relaunch the Action.
