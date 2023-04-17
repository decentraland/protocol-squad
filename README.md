# State of the Protocol Squad

Welcome to the State of the Protocol Squad document. This document is updated periodically with the status and plan of each implementation and documentation.

The team is composed of:
- @menduz
- @nicloay
- @robtfm
- @slezica

# Current objective

Render interactive scenes.

# Next objective

See eachother through comms.

# Implementation status

| Feature | Bevy | Babylon | Unity |
| - | - | - | - |
| CRDT protocol - ADR-117 | :check: | :check: ||
| Scene Tick - ADR-148 | :check: | :check: ||
| Scene Runtime ADR-133 | :check: | :check: ||
| Load and unload scenes | :check: | :check: ||
| Load static world ADR-111 | :check: | :check: ||
| Resolve realm base URL | :check:? | :check: ||
| Traversal city loading | :check: | :check: ||
| SDK Components | n of m |||
| Static entitites ||||
| Render avatars ||||
| Player Locomotion ||||
| -> Colliders ||||
| -> First Person Camera ||||
| -> ~Moving platforms~ ||||
| -> ~Third person camera~ ||||
| -> ~Jump~ ||||

| SDK Component* | Bevy | Babylon | Unity |
| - | - | - | - |
| Transform ADR-153 | :check: | :check: ||
| MeshRenderer ||||
| MeshCollider ||||
| Billboard ADR-198 ||||
| Raycast ADR-200 ||||
| PointerEvents ADR-125 ADR-200 ||||
| GltfContainer ||||
| Animator ||||
| PointerLock ||||
| CameraMode ||||
| AvatarShape ||||

* Many SDK components are left out the scope right now in pursue of the current objectives.
