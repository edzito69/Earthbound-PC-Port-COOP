# EarthBound PC Port COOP - Version 3.7

An unofficial, modified native desktop adaptation for Windows, Linux and macOS,
based on Brian Pugh and contributors' EarthBound C implementation and the
inherited Herringway/ebsrc disassembly and research.

This edition adds experimental local co-op, modern controls, save states and
expanded settings. The underlying game and code retain their original authorship.

## Download and start

1. Download the [3.7 release](https://github.com/edzito69/Earthbound-PC-Port-COOP/releases/tag/EarthboundCOOPv3.7) and extract the complete ZIP.
2. Place your own unmodified EarthBound (USA) `.sfc`/`.smc` ROM in **Put your rom here - Coloque sua rom aqui**. No ROM is included. Extract a zipped ROM first.
3. Open `Port Windows/EarthBound PC.exe`, run `Port Linux/earthbound-pc`, or open `Port Mac/EarthBound PC.app`.
4. Keep each executable's accompanying libraries and `adaptacao.ebpatch` in place.

**F1** opens options; **F2** opens saves. Enable experimental co-op in
**F1 → Gameplay**, then press Start/Options on the second controller and confirm.
See [CONTROLS.md](CONTROLS.md), the English/Portuguese READ MEs and
[CHANGELOG.md](CHANGELOG.md) for details.

## Platform status

- **Windows:** builds and automated native regression tests passed.
- **Linux:** compiled/inspected; reported audio differences remain under investigation.
- **macOS:** compiled/inspected; the reported launch problem is not confirmed resolved.

The project is experimental. A complete campaign and every physical controller
model have not been validated. The [changelog](CHANGELOG.md#testing-and-known-issues)
lists current limitations.

## Repository layout

- `Port Windows/`, `Port Linux/`, `Port Mac/`: desktop runtimes and original notices.
- `Put your rom here - Coloque sua rom aqui/`: instructions for adding your own ROM.
- `README.md`, `CHANGELOG.md`, `CONTROLS.md`, `CREDITS.md`: project documentation.

This repository distributes the packaged desktop edition and documentation;
it is not a complete source-code checkout. GitHub's automatic “Source code”
archives contain the repository files. The upstream code projects are linked below.
Personal ROMs, saves, preferences, signing keys and private build logs are excluded.

## Built on the community's work

This is a fan project made with affection for EarthBound and respect for the
people who keep it accessible. Its foundation belongs to the original authors;
this edition adds modifications to their work.

- **Brian Pugh and contributors:** the native C implementation and supporting tools in [BrianPugh/earthbound](https://github.com/BrianPugh/earthbound).
- **Cameron Ross, Herringway and the ebsrc contributors:** the inherited disassembly, documentation and research behind that foundation. See [Herringway/ebsrc](https://github.com/Herringway/ebsrc).
- The upstream revision's history also records **CJ, Sean Staggs, PhoenixBound, Cooper Harasyn, Anonymous941 and lilliththecreative**. Names follow the history; some may be aliases of the same person.
- **angelo_wf and LakeSnes contributors; Sam Lantinga and SDL2 contributors; Brian Pugh and tamp contributors; Dale Weiler and incbin contributors.**
- **Alex Foffano, Jared Morgan and the entire EarthBound Brasil translation team; FantasyAnime and its save authors; TheRunaway5; and the developers of the build tools used here.**
- Thank you to **Nintendo, Shigesato Itoi, APE, HAL Laboratory and the original EarthBound teams**, and to all community programmers, researchers, translators, testers, preservationists and players.

**AI assistance disclosure:** OpenAI Codex was used extensively to assist with
implementation, debugging, tests, builds and documentation. Edzito directed this
edition's features and integration. AI assistance does not change the authorship
of the original game, upstream code, dependencies or translations, and it does
not replace testing.

> Thank you to everyone who shared code, knowledge, tools, translations and love
> for EarthBound. This project exists because of you. It is made for the community,
> with gratitude, care and respect for the people behind the work. — Edzito

See [CREDITS.md](CREDITS.md) for expanded attribution, the upstream revision and
source-history links. Original third-party notices remain in each package's
`licenses` directory. This edition is independently maintained.
