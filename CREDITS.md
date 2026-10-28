# Community credits and project origins

EarthBound PC Port COOP is an unofficial modified native desktop port based on
**Brian Pugh and contributors' C reimplementation**, which builds on
**Herringway/ebsrc and its contributors' disassembly and research**.
Edzito's edition adds experimental co-op, menus, controls and other adjustments,
with development assistance from Codex. Credit for the game, underlying C
implementation, disassembly, dependencies and translation belongs to their
respective authors. This edition is maintained independently of those projects.

## Original EarthBound

Thank you to Nintendo, Shigesato Itoi, APE, HAL Laboratory and the original
development teams for creating EarthBound, its characters, art, writing and music.

## Native C implementation and disassembly

- [BrianPugh/earthbound](https://github.com/BrianPugh/earthbound): Brian Pugh and all contributors to the native C implementation and its supporting tools.
- [Herringway/ebsrc](https://github.com/Herringway/ebsrc): the earlier disassembly, documentation and community research on which that project builds.
- Revision used by this edition: [`a2cf5c327d367d90440c5768713056462b0c4d9e`](https://github.com/BrianPugh/earthbound/commit/a2cf5c327d367d90440c5768713056462b0c4d9e).

The complete reachable Git history of that revision records these author names:

- Brian Pugh
- Cameron Ross
- CJ
- Sean Staggs
- PhoenixBound
- Cooper Harasyn
- Anonymous941
- Herringway
- lilliththecreative

Names are reproduced as recorded, without personal email addresses. Some names
may be aliases of the same person. This is a record of Git authorship, not a
claim that Git captures every research, testing, documentation or uncredited
contribution. It includes the inherited history, rather than crediting only
the latest fork. Upstream commits also record AI assistance in co-author
trailers; those records remain available in the original history.

- [History of the revision used](https://github.com/BrianPugh/earthbound/commits/a2cf5c327d367d90440c5768713056462b0c4d9e/)
- [BrianPugh/earthbound contributors](https://github.com/BrianPugh/earthbound/graphs/contributors)
- [Herringway/ebsrc contributors](https://github.com/Herringway/ebsrc/graphs/contributors)

## Libraries, tools and supporting projects

- **LakeSnes:** angelo_wf and all contributors; SPC700/DSP audio. [Source and history](https://github.com/angelo-wf/LakeSnes).
- **SDL2:** Sam Lantinga and all contributors; windowing, graphics, audio and controllers. [Source and history](https://github.com/libsdl-org/SDL).
- **tamp:** Brian Pugh and all contributors; compression. [Source and history](https://github.com/BrianPugh/tamp).
- **incbin:** Dale Weiler and all contributors; data embedding in private builds. [Source and history](https://github.com/graphitemaster/incbin).
- **FantasyAnime and the authors of its public save collection:** campaign checkpoints. [Original collection](https://fantasyanime.com/legacy/earthb_saves.htm).
- **TheRunaway5 / Phase Distorter 0.5:** source packages from which the bundled Linux/macOS SDL2 libraries were obtained. The Phase Distorter game executable was not reused. [Project](https://github.com/TheRunaway5/Phase-Distorter).
- **Zig, LLVM/Clang, Python, CMake, Ninja and ebtools:** their authors and contributors, for the build and extraction tools used by this edition.
- **Android NDK, Android build tools and Eclipse Temurin OpenJDK / Adoptium:** their authors and contributors, for the separate earlier Android build.

Every contributor to these dependencies is acknowledged, including those not
named individually here. Their original author lists, source histories and
copyright/license notices provide the detailed attribution for each project.
Dependency contributors are credited for their own projects, rather than
presented as maintainers of this edition. Original notices remain unchanged.

## EarthBound Brasil 1.0 — April 4, 2015

- **Project:** Alex Foffano and Jared Morgan.
- **Translation, review and graphics:** Alex Foffano.
- **Hacking, graphics and review:** Jared Morgan.
- **Translation:** Claus “Set” Martins, Flicky, Gustavo Diógenes (@TesauroRaptor), Pedro (Draco), Thiago Cianci, Vanessa and Vinicius.
- **Additional help:** H.S, JeffMan, Mr. Tenda, Mr. Accident, Tomato and ShadowOne333.
- **Original special thanks:** Ambrey, Carlos Almeida, Claus, Danilo, Hsing Hui Lee, João de Araujo, Mukuro, Porter, Rachel, Régis Sudo, Ruby, Rydel, Sadie, Thiago Schreiner, starmen.net, romhackers.org and romhacking.trd.br.

The translation's complete original credits and terms remain in
`licenses/EarthBoundBrasil-creditos.txt` in the desktop packages.

## This edition and the wider community

- **Edzito:** this edition's co-op features, menus, controls, gameplay adjustments and integration.
- **Codex:** development assistance on this edition.
- **Community developers, researchers, translators, documenters, preservationists, testers and players:** thank you for the knowledge, tools, bug reports and care that make projects like this possible.

This is a fan adaptation built on a long chain of other people's work.
“Edzito Edition” identifies these modifications; the underlying work retains
its original authorship. The project is not an official Nintendo product.
Existing third-party credits, copyright notices and license terms remain applicable.

If a credit is missing or inaccurate, please open an issue with the person's
preferred name, contribution and a source so the attribution can be corrected.
