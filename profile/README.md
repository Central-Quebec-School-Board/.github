# Repository Workflow

Each repository follows a workflow based on its type.

## Versioned repository

**Branches**:
* latest
* release/[version]
* dev

Versioned repositories have specific releases and use the following workflow:

The most recent stable release has its branch ``release/[version]`` and is also merged to ``latest``.

Previous releases can be found in the *Release* section. Up to two previous releases may also still exist in their respective ``release/[version]`` branch.  
Older release branches are removed.

Features for the next release are accumulated in ``dev``.

Each in-development feature has its own feature branch based on its requesting issue.

## Continuous development repositories

**Branches**:
* main
* staging
* dev

  Continuously developped repositories use the ``main`` branch for the currently deployed code.

  ``staging`` branch is for deployed pre-production code.

  Features for the next deployment are accumulated in ``dev``.

  Each in-development feature has its own feature branch based on its requesting issue.

# How to contribute

If you wish to contribute to open feature requests or bug requests, please consult the following guidelines.

## Pick an issue

Navigate to the *Issues* section of a repository and pick an issue.
![Picking an issue](./.github/profile/readme/picking_issue.png?raw=true)

Once you have selected an issue to work on, assign yourself and create the feature/bug branch.
![Assigning an issue](./.github/profile/readme/assigning_issue.png?raw=true)

## Checkout the branch locally

Once the branch has been created in the repository, checkout the branch locally using a git management tool.

### Git bash

Using git bash, use the following commands to clone & checkout the issue branch.
```
git clone [repository]
cd [repository_folder]
git checkout [issue-branch name]
```

if you already have the repository cloned on your local machine, use the following instead:
```
git fetch --all
git checkout [issue-branch name]
```

Once you have successfully checked out the issue branch, you may begin working on the changes requested.

## Commiting and pushing

Once you have implemented the requested changes and tested to make sure its working as intended, you may push your changes using your git management tool.

### Git bash

To commit and push using git bash, follow these steps:
![Pushing using git bash](./.github/profile/readme/pushing_using_git_bash.png?raw=true)
1. Add the file(s) using ``git add``
2. Commit the files and add a commit message using ``git commit``
3. Push the changes to the repository using ``git push``

## Creating a pull request

Once you have pushed all the necessary code using one or more commits, go to the *Pull requests* section to create a pull request.
![Pull request section](./.github/profile/readme/pull_request_section.png?raw=true)  
![Creating a new pull request](./.github/profile/readme/create_pr.png?raw=true)

Depending on the type of issue you are working on, you will have to pick the correct base branch to merge into.
Follow these guidelines to select the correct branch:
* bugfix: dev
* documentation: dev
* feature request: dev
* hotfix: latest / main

Here is an example using a bugfix
![Selecting the correct base branch](./.github/profile/readme/selecting_base_branch.png?raw=true)

Once the correct base branch has been selected, make sure to assign yourself to the pull request and reference the issue you started with. To reference an issue, prefix its issue number with `#`. Example: `#5`.  
![Example of a pull request](./.github/profile/readme/example_pr.png?raw=true)

Once the pull request has been created, a reviewer will look at the changes implemented and either accept & merge the request, or they will ask for changes to the implementation you are adding.

If changes are requested, return to your local branch and execute those requests, then pull to the issue branch again. Return to the pull request you made and add a comment referencing the commit SHA of the change by pasting the full SHA code. It will get automatically converted into a link to the commit.
![Commenting a commit SHA](./.github/profile/readme/commenting_commit_sha.png?raw=true)
![Adding a change](./.github/profile/readme/adding_change.png?raw=true)

To find the commit SHA, you can go to the issue-branch's commits and copy the SHA from there.  
![Navigate to commits](./.github/profile/readme/navigate_commits.png?raw=true)  
![Copy the SHA](./.github/profile/readme/copying_sha.png?raw=true)  
If using git bash, use the ``git rev-parse HEAD`` command and copy the output.
