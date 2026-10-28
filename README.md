# Projects-___

Registry index for the Projects repo family — same model as `cloud-master`
(`~/git/cloud/`), narrowed to the Projects family (group b_projects). This repo is an INDEX, not a container:
it holds `repos.json` (the registry) and `clone.sh` (pick which repos to
have locally); the actual clones live as siblings in `~/git/`.

```
./clone.sh                list what exists and what does not
./clone.sh <name>...      clone those, then link them
./clone.sh --all          clone every repo of the family
./clone.sh --link         relink whatever is already cloned
./clone.sh --relink       rewrite every link from the registry
```

`repos.json` is a SUBSET of `~/git/_git-repos-master/repos.json` (the
superset index of every repo this account owns) — identical
name/url/private/doc fields, kept in sync by hand same as `cloud/repos.json`
already is.

## Hub submodule

This repo's parent hub is `_git-repos-master`, mounted as a git submodule at `0_hub/_git-repos-master` (one fixed path convention for every repo; URL https://github.com/diegonmarcos/_git-repos-master.git, pinned to the hub main). Only the upward link is a submodule; this hub keeps symlinks (not submodules) to its members, so there are no cycles. Source of truth: `repos.json` in _git-repos-master (`parent_hub` / `hub`, `_hub_submodule_doc`), guarded by `node repos-sot.js check-hubs`.
