# Ruach Studio's branch of audio.cpp

This branch is [Ruach Studio](https://github.com/igrbible/Ruach_Studio)'s derivative of [0xShug0/audio.cpp](https://github.com/0xShug0/audio.cpp). We keep it in the open: we hide nothing and are not ashamed of it.

## What the Studio ships

The Studio's Narrator builds audio.cpp from upstream commit `408935b` (Refactor Drama3 and Nemotron Transcribe with shared MoE execution, #1234) with no changes at all. That commit is tagged `ruach-pin` in this repository (HERESY 2374).

## What this branch changes

One probe, not in the Studio build: a session option `fish_drama3.cpu_expert_first` for Fish Audio Drama 3, the first layer whose expert banks go to system RAM (default 0, the lowest, as upstream). Upstream's `fish_drama3.cpu_expert_layers` takes only a count from the lowest layer; with this option the same count can sit in the middle or at the top of the stack. We used it on 09.11.2026 to measure whether the placement of the banks in RAM changes what Drama 3 reads (HERESY 2300). Four files: `include/engine/community_models/fish_drama3/backbone.h`, `src/community_models/fish_drama3/backbone.cpp`, `generator.cpp` and `loader.cpp`.

The HERESY numbers refer to `docs/HERESY.md`, Ruach Studio's numbered log of its patches.

## Licence

Upstream audio.cpp is under the Apache License 2.0 (`LICENSE`), and its files keep it. Our changes on this branch are under the GNU Affero General Public License, version 3 or any later version (AGPL-3.0-or-later), as Ruach Studio's release states for everything we wrote; Apache 2.0 code may stand inside an AGPL-3.0 work.
