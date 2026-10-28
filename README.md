# DeepSc-___

Registry index for the DeepSc repo family (Deep-ScX) - same model as `CG-___`, `Projects-___` and `cloud-___`. This repo is an INDEX, not a container: it holds `repos.json` (the registry, a subset of _git-repos-master/repos.json), `clone.sh` (pick which repos to have locally) and one committed relative symlink per member (`<member> -> ../<member>`); the actual clones live as siblings in `~/git/`.

## Members

- [DeepSc-X](https://github.com/diegonmarcos/DeepSc-X) - Deep-ScX / saylitics: README and deployer wiring skeleton; the matching front-labtools project c-Stk_DsX/sailytics moves here with the labtools split (#1218). #1224.
- CAD-Simulators (public, renamed from DeepSc-Tools) - CAD and simulators: first tool is CAD with MCP servers for agentic 3D modelling (FreeCAD, Blender, AutoCAD/DXF as pinned upstream submodules under tools/cad). #1255.

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

## Hub submodule

This repo's parent hub is `Projects-___`, mounted as a git submodule at `0_hub/Projects-___` (one fixed path convention for every repo; URL https://github.com/diegonmarcos/Projects-___.git, pinned to the hub main). Only the upward link is a submodule; this hub keeps symlinks (not submodules) to its members, so there are no cycles. Source of truth: `repos.json` in _git-repos-master (`parent_hub` / `hub`, `_hub_submodule_doc`), guarded by `node repos-sot.js check-hubs`.
