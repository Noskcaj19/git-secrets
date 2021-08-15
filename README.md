# git secrets

## `git-absorb`

[Github](https://github.com/tummychow/git-absorb)

Automatically apply fixups to commits.

See [--fixup](#--fixup)

## `--fixup`

    git commit --fixup <commit>

If you want make a change to a past commit the `--fixup` flag will create a "fixup commit", which looks like a commit that starts with `fixup!` followed by the commit message of the commit being fixed up.

Then, git can automatically merge the fixup commit into it's corresponding commit using

    git rebase --interactive --autosquash <branch>


## `git rerere`

[Docs](https://git-scm.com/docs/git-rerere)

> Reuse recorded resolution of conflicted merge

When maintaining a fork or otherwise rebasing the same changes often, `git rerere` can help by recording previously used merge results and reusing them automatically the next time they are needed.

### Note
The command is not generally used directly, but the functionality must be enabled with the `rerere.enabled` config setting.  
To enable it in the current repo:

    git config rerere.enable true

## `git fast-export`

[Docs](https://git-scm.com/docs/git-fast-export)

    git fast-export --all
Will dump the entire git repo for inspection.  
Useful when rewriting history.  
See [git-filter-branch](https://github.com/newren/git-filter-repo).

## `git filter-branch`

[Don't.](https://git-scm.com/docs/git-filter-branch#_warning)  
Use [git-filter-repo](https://github.com/newren/git-filter-repo)

# Options

## `rerere.enabled`

See [`git rerere`](#git-rerere)

Enables the resolution recording mechanic used by `git rerere`

It works by detecting a conflict (by the "<<<<<<<" markers) and then saving the file with conflict markers in `.git/rr-cache/<hash>/preimage`, then once the conflict has been resolved, the resolved file is stored in `.git/rr-cache/<hash>/postimage`

## `rebase.autosquash`

See [`--fixup`](#--fixup)

Makes the behavior of `git rebase --autosquash` the default.


