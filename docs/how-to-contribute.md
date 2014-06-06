# Overview

The general steps are:

- Create a ticket in Github Issues.
- Fork the repository on GitHub.
- Clone the repository on your local system.
- Create a branch and make your changes.
- Push the branch, create a pull request and [reference the issue in your pull request](https://github.com/blog/1506-closing-issues-via-pull-requests).

Read on for detailed steps

## Contributing to the Hardening Framework Projects

Below, replace "REPO" with the project that should be changed. Replace "USER" with your GitHub username.

0. Create a issue for the bug, feature or improvement you are contributing. 

See [Mastering Issues](https://guides.github.com/features/issues/) for details

1. Fork the repository on GitHub.

    TelekomLabs/REPO -> USER/REPO
    
    You can replace REPO in your fork with a name for the repository
    that makes it unique, if required.

2. Clone the repository locally

    ```
    git clone git@github.com:USER/REPO.git
    ```

3. Ensure the origin is your repository.

    ```
    git config remote.origin.url git@github.com:USER/REPO.git
    ```

4. Add Hardening Framework REPOs as a remote named `upstream` and track it
instead of your origin.

    ```
    git remote add upstream git://github.com/TelekomLabs/REPO.git
    git config branch.master.remote upstream
    ```

5. Make sure your master branch is updated.

    ```
    git checkout master
    git pull --rebase
    ```

6. Create a new branch for the ticket.

    ```
    git checkout -b ISSUE-####
    ```

7. Make your changes and push the branch to your origin.

    ```
    git push origin ISSUE-####
    ```

8. [Reference the ISSUE](https://github.com/blog/1506-closing-issues-via-pull-requests) in your [Github Pull Request](https://help.github.com/articles/using-pull-requests). We will review the issue and contribution as soon as possible.

### Some Tips

In order to have your contribution accepted as quickly as possible, we have some requests for you. These make it easier to merge contributions without merge conflicts, and keep the scope on topic for a specific issue.

- Please do not update the version in the metadata.rb (chef) or Modulefile/metadata.json (Puppet) files. We handle that as part of the release process.
- Please do not update the CHANGELOG.md. We handle that as part of the release process.
- Please do not mix style changes that are not related to the specific ticket. Create a new, separate ticket for style updates. For example, if a REPO has  Foodcritic findings, create a separate ticket to handle those. See the section on linting.
- Follow the current style of the code where appropriate.
- Run the provided lint, spec and integration tests

