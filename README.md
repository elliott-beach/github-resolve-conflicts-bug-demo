This repo reproduces a problem with GitHub's "resolve conflicts" feature.
The issue occurs when merging into a non-master branch from the master branch of a fork.

The result is that a merge commit is created, but conflicts still exist.

## Steps:
1. Create a new repository, adding a dummy file `foo`.
2. Check-out a new branch `updated-upstream`.
3. Commit and push an edit on `foo` to `origin/updated-upstream`.

4. Switch to a different GitHub account and fork the repository.
5. On the fork, edit `foo` in a conflicting way on the `master` branch.
6. Create a pull request from `master` to `updated-upstream`.
7. Resolve conflicts via GitHub.
This will create a merge commit from  `updated-upstream` to `master`,  when the merge ought to be from `master` to `updated-upstream`.

See https://github.com/elliott-beach/github-resolve-conflicts-bug-demo/pull/1 for the result.
