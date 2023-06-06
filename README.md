# State of the Protocol Squad

Welcome to the State of the Protocol Squad document. This document is updated periodically with the status and plan of each implementation and documentation.

The current team members are:

- @leanmendoza - Godot implementation leader
- @menduz - Babylon implementation leader, technical coordination
- @robtfm - Bevy implementation leader
- @slezica - Documentation & technical writing

The Protocol Squad has two objectives:

- Publish an extensive and detailed documentation of the Decentraland protocol
- Create alternative implementations of the World Explorer

There are currently three implementations being developed, each implementation has their own different objectives and tints in development.

**Current objective**: 🔛 Render interactive scenes.  
**Next objective**: 🔜 Connect the explorers together and see eachother in-world.

The team also focuses on documenting the protocol in the shape of [Architecture Decision Records (ADR)](https://adr.decentraland.org) and as contributions to the [Official Documentation](https://docs.decentraland.org)

## Babylon.js + Typescript

**Repository**: https://github.com/decentraland/hammurabi
**Objective**: It is the educational implementation of Decentraland. Its main objective is to provide a clear standard/reference implementation that implements the Decentraland protocol in the most readable and correct way possible. Even though it contains many performance optimizations, complex optimizations are left for other explorers to optimize this one for readability. The test coverage of this implementation should be the highest and its objective is to be the "reference implementation" when implementing new explorers from scratch.  
**Current state**: ON TRACK 🟢

## Bevy + Rust

**Repository**: https://github.com/decentraland/bevy-explorer
**Objective**: Rust may be the greatest language for the coming decades, and its open source nature is very aligned with Decentraland's mission. The same happens with Bevy (the engine). Internally, Bevy is already implemented using an ECS, at the moment of writing this document, creating a Decentraland Explorer in this technology seems to be the best decision long term.  
**Current state**: ON TRACK 🟢

## Godot 4 + GDScript + Rust

**Repository**: https://github.com/decentraland/godot-explorer
**Objective**: Its objective is to be a production ready (or ready-to-fork) Decentraland Explorer. Godot (fully open source) has been gaining traction in the industry and more and more titles are being published and developed on Godot as time passes.
**Current state**: ON TRACK - Started deferred 🟠

## Unity + C#

**Current state**: ❌ CANCELLED, replaced by Godot. The Decentraland Foundation will take the lead with a [brand new Unity Explorer](https://github.com/decentraland/unity-explorer)

# Implementation, part 1. Render interactive scenes

At this stage, the implementations will focus on loading and unloading scenes, render their content in the world and oferring basic interactivity.

| Feature                    | Specification                                                                                                    | Bevy | Babylon | Godot |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------- | ---- | ------- | ----- |
| `CI Tests`                 | Continous automated testing in commits and pull requests                                                         | ✅   | ✅      | Partially |
| `Continous release`        | Continous release of testable artifacts                                                                          | ✅   | ✅      | ✅    |
| `Load and unload scenes`   | PENDING                                                                                                          | ✅   | ✅      | ✅    |
| `Scene Runtime`            | [ADR-133](https://adr.decentraland.org/adr/ADR-133) (Living)                                                     | ✅   | ✅      | ✅    |
| `CRDT protocol`            | [ADR-117](https://adr.decentraland.org/adr/ADR-117) (Living)                                                     | ✅   | ✅      | ✅    |
| `Scene Tick`               | [ADR-148](https://adr.decentraland.org/adr/ADR-148) (Living)                                                     | ✅   | ✅      |       |
| `Load static realm/world`  | [ADR-110](https://adr.decentraland.org/adr/ADR-110) [ADR-111](https://adr.decentraland.org/adr/ADR-111) (Living) | ✅   | ✅      | ✅    |
| `Resolve realm base URL`   | [ADR-144](https://adr.decentraland.org/adr/ADR-144) (Review)                                                     | ✅   | ✅      | ✅    |
| `Static entitites for SDK` | [ADR-219](https://adr.decentraland.org/adr/ADR-219) (Draft)                                                      | ✅   | ✅      |       |
| `Player Locomotion`        | PENDING                                                                                                          | ✅   | ✅      |       |
| `├── Colliders`            | `MeshCollider` & `GltfContainer`                                                                                 | ✅   | 1/2     |       |
| `└── First Person Camera`  | PENDING                                                                                                          | ✅   | ✅      |       |

| SDK Component               | Specification                                                | Bevy      | Babylon   | Godot | SDK |
| --------------------------- | ------------------------------------------------------------ | --------- | --------- | ----- | --- |
| `Transform`                 | [ADR-153](https://adr.decentraland.org/adr/ADR-153) (Living) | ✅        | ✅        | ✅     | ✅  |
| `MeshRenderer`              | PENDING                                                      | Partially | Partially | Partially | ✅  |
| `MeshCollider`              | PENDING                                                      | Partially | Partially | Partially | ✅  |
| `Billboard`                 | [ADR-198](https://adr.decentraland.org/adr/ADR-198) (Living) | ✅        | ✅        |       | ✅  |
| `Raycast`                   | [ADR-200](https://adr.decentraland.org/adr/ADR-200) (Draft)  | ✅        | ✅        |       | ✅  |
| `PointerEvents`             | [ADR-214](https://adr.decentraland.org/adr/ADR-214) (Draft)  | ✅        | ✅        |       | ✅  |
| `GltfContainer`             | [ADR-215](https://adr.decentraland.org/adr/ADR-215) (Draft)  | ✅        | ✅        | ✅    | ✅  |
| `GltfContainerLoadingState` | [ADR-215](https://adr.decentraland.org/adr/ADR-215) (Draft)  | ✅        | ✅        |       | ✅  |
| `Animator`                  | ADR-216 (PENDING)                                            | ✅        | ✅        |       | ✅  |
| `EngineInfo`                | [ADR-148](https://adr.decentraland.org/adr/ADR-148) (Living) |           | ✅        |       | ✅  |

# Implementation, part 2: Seeing other people

| Feature                              | Specification                                       | Bevy | Babylon | Godot |
| ------------------------------------ | --------------------------------------------------- | ---- | ------- | ----- |
| `Load a global scene (AvatarsScene)` | PENDING                                             | ✅   | ✅      |       |
| `Create ephemeral identity`          | PENDING                                             | ✅   | ✅      |       |
| `Connect to WebSocket transport`     | PENDING                                             | ✅   | ✅      |       |
| `├──Transport implementation`        | [ADR-105](https://adr.decentraland.org/adr/ADR-105) | ✅   | ✅      |       |
| `└──Expose transport to SDK`         | PENDING                                             |      |         |       |

| SDK Component | Specification                                           | Bevy | Babylon | Godot | SDK |
| ------------- | ------------------------------------------------------- | ---- | ------- | ----- | --- |
| `AvatarShape` | PENDING Render avatars with custom wearables and emotes | ✅   | ✅      |       | ✅  |

# Implementation, part 3: Full SDK implementation

| Feature                   | Specification | Bevy | Babylon | Godot |
| ------------------------- | ------------- | ---- | ------- | ----- |
| `Player Locomotion`       | PENDING       | ✅   | ✅      |       |
| `├── Moving platforms`    | PENDING       | ✅   |         |       |
| `├── Third person camera` | PENDING       | ✅   | ✅      |       |
| `└── Jump`                | PENDING       | ✅   | ✅      |       |
| `Traversal city loading`  | PENDING       | ✅   |         |       |

| SDK Component                   | Specification                                       | Bevy | Babylon | Godot | SDK |
| ------------------------------- | --------------------------------------------------- | ---- | ------- | ----- | --- |
| `PointerLock`                   | PENDING                                             |      |         |       |     |
| `CameraMode`                    | PENDING                                             |      |         |       | ✅  |
| `Material`                      | PENDING                                             | ✅   | ✅      |       | ✅  |
| `Cinematic`                     | PENDING                                             |      |         |       |     |
| `AvatarAttach`                  | PENDING                                             |      |         |       | ✅  |
| `AudioSource`                   | PENDING                                             |      |         |       | ✅  |
| `AudioStream`                   | PENDING                                             |      |         |       | ✅  |
| `CameraMode`                    | PENDING                                             |      |         |       | ✅  |
| `CameraModeArea`                | PENDING                                             |      |         |       |     |
| `TextShape`                     | PENDING                                             |      |         |       | ✅  |
| `PointerLock`                   | PENDING                                             |      |         |       |     |
| `VideoPlayer`                   | PENDING                                             |      |         |       |     |
| `Visibility`                    | PENDING                                             |      |         |       | ✅  |
| `UiTransform`                   | [ADR-124](https://adr.decentraland.org/adr/ADR-124) |      |         |       | ✅  |
| `UiCanvasInformation`           | [ADR-124](https://adr.decentraland.org/adr/ADR-124) |      |         |       |     |
| `UiBackground`                  | [ADR-125](https://adr.decentraland.org/adr/ADR-125) |      |         |       | ✅  |
| `UiLabel`                       | [ADR-125](https://adr.decentraland.org/adr/ADR-125) |      |         |       | ✅  |
| `UiText`                        | [ADR-125](https://adr.decentraland.org/adr/ADR-125) |      |         |       | ✅  |
| `UiInput & UiInputResult`       | [ADR-125](https://adr.decentraland.org/adr/ADR-125) |      |         |       | ✅  |
| `UiDropdown & UiDropdownResult` | [ADR-125](https://adr.decentraland.org/adr/ADR-125) |      |         |       | ✅  |

# Links

Governance proposal: https://governance.decentraland.org/proposal/?id=9303c5e0-7cbb-11ed-b135-498029192bca
