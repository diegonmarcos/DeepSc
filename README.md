# DeepSc___

Registry index for the DeepSc repo family (Deep-ScX) - same model as `CG___`, `Projects___` and `cloud___`. This repo is an INDEX, not a container: it holds `repos.json` (the registry, a subset of _git-repos-master/repos.json), `clone.sh` (pick which repos to have locally) and one committed relative symlink per member (`<member> -> ../<member>`); the actual clones live as siblings in `~/git/`.

## Members

- [DeepSc-X](https://github.com/diegonmarcos/DeepSc-X) - Deep-ScX / saylitics: README and deployer wiring skeleton; the matching front-labtools project c-Stk_DsX/sailytics moves here with the labtools split (#1218). #1224.

## Usage

```
./clone.sh                list what exists and what does not
./clone.sh <name>...      clone those, then link them
./clone.sh --all          clone every member
./clone.sh --link         relink whatever is already cloned
./clone.sh --relink       rewrite every link from the registry
./check-repos-sot.sh      verify repos.json against _git-repos-master
```

`repos.json` is a SUBSET of `~/git/_git-repos-master/repos.json` (the superset index of every repo this account owns): identical name/url/private/doc fields, checked by `./check-repos-sot.sh`.
