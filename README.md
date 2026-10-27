# golem-cache

Prebuilt pieces of [Golem](https://github.com/maxpoww/Golem), so a Golem
machine's update **downloads** them instead of compiling them (the dock,
Hyprland with Golem's patches, the nvidia and Broadcom drivers, Seam…).

- One **release per published Golem version**, tagged `g-<first 12 characters
  of the Golem commit>`. Each release is a complete Nix binary cache:
  `nix-cache-info`, one `<hash>.narinfo` per piece and its `.nar.zst`.
- Only what cache.nixos.org does not already have, and only what its licence
  lets us redistribute.
- Every piece is signed. Golem machines trust exactly this key:

  ```
  golem-cache-1:lUUA5lNDJ8EJhxXLuebT5a3bL7c0SRJKUhNooEwO1B0=
  ```

Nothing here is edited by hand: Golem's update lane (`updates/` in the Golem
repo) builds, tests, signs and uploads each release, and removes old ones.
Downloads send nothing about the machine; Golem has no telemetry.
