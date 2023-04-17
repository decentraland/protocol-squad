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
| CRDT protocol - ADR-117 | ✅ | ✅ ||
| Scene Tick - ADR-148 | ✅ | ✅ ||
| Scene Runtime ADR-133 | ✅ | ✅ ||
| Load and unload scenes | ✅ | ✅ ||
| Load static world ADR-111 | ✅ | ✅ ||
| Resolve realm base URL | ✅? | ✅ ||
| Traversal city loading | ✅ | ✅ ||
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
| Transform ADR-153 | ✅ | ✅ ||
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
