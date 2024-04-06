![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/test/badge.svg)

# Tiny Tapeout Verilog Project Template

- [Read the documentation for project](docs/info.md)

## What is Tiny Tapeout?

TinyTapeout is an educational project that aims to make it easier and cheaper than ever to get your digital designs manufactured on a real chip.

To learn more and get started, visit https://tinytapeout.com.

## Verilog Projects

1. Add your Verilog/TL-Verilog files to the `src` folder.
2. Edit the [info.yaml](info.yaml) and update information about your project, paying special attention to the `source_files` and `top_module` properties. If you are upgrading an existing Tiny Tapeout project, check out our [online info.yaml migration tool](https://tinytapeout.github.io/tt-yaml-upgrade-tool/).
3. Edit [docs/info.md](docs/info.md) and add a description of your project.
4. Optionally, add a testbench to the `test` folder. See [test/README.md](test/README.md) for more information.

The GitHub action will automatically build the ASIC files using [OpenLane](https://www.zerotoasiccourse.com/terminology/openlane/).

## Makerchip Projects

Makerchip is an online IDE for digital circuit design supporting Verilog or TL-Verilog projects.
Ctrl-click to open this [starting template](https://www.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2Ftt06-verilog-template%2Fmain%2Fsrc%2Ftt_um_template.tlv#)
or this [calculator circuit example](https://www.makerchip.com/sandbox?code_url=https:%2F%2Fraw.githubusercontent.com%2Fstevehoover%2Fmakerchip_examples%2Fmain%2Ftiny_tapeout_examples%2Ftt_um_calculator.tlv#).

![tt_template_makerchip](https://github.com/stevehoover/tt05-verilog-demo/assets/11302288/37f65ea1-6898-41ac-a5b1-c9afb7b824f1)

### Build Flow

The Verilog build flow is unchanged, but your `.v` file is no longer your source code. It is, instead, generated from a file
by the same name with a `.tlv` extension by running `make` from the `/src` directory.
Both the `.tlv` file and its generated `.v` will be committed to the repository. Continuous integration (CI) testing
triggered by pushing to GitHub treats the Verilog file as the source. It does not (currently) automatically compile
from the TL-Verilog source. So be sure to run `make` before committing changes.

### Setup

To use Makerchip for your project:

1. Create your top-level Makerchip-compatible `.tlv` (TL-Verilog or Verilog) source file as a copy of [src/tt_um_template.tlv](src/tt_um_template.tlv).
1. In this new file, specify your module name as `tt_um_<github-username>_<project-name>` using the settings at the top of the file.
1. As for Verilog projects (above), edit `info.yaml`, `docs/info.md`, `src/Makefile`, and `tb.v`.

> [!NOTE]
> In case of build errors, note that the `Makefile` uses the cocotb Makefile which messes with the Python environment and
> can break the SandPiper(TM) command that compiles the `.tlv` code. If you encounter Python environment errors, look for
> the SandPiper command in the `make` output, and run it manually. Then run `make` (as a pre-check for testing via GitHub).

## Enable GitHub actions to build the results page

- [Enabling GitHub Pages](https://tinytapeout.com/faq/#my-github-action-is-failing-on-the-pages-part)

## Resources

- [FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community](https://tinytapeout.com/discord)
- [Build your design locally](https://docs.google.com/document/d/1aUUZ1jthRpg4QURIIyzlOaPWlmQzr-jBn3wZipVUPt4)

## What next?

- [Submit your design to the next shuttle](https://app.tinytapeout.com/).
- Edit [this README](README.md) and explain your design, how it works, and how to test it.
- Share your project on your social network of choice:
  - LinkedIn [#tinytapeout](https://www.linkedin.com/search/results/content/?keywords=%23tinytapeout) [@TinyTapeout](https://www.linkedin.com/company/100708654/)
  - Mastodon [#tinytapeout](https://chaos.social/tags/tinytapeout) [@matthewvenn](https://chaos.social/@matthewvenn)
  - X (formerly Twitter) [#tinytapeout](https://twitter.com/hashtag/tinytapeout) [@matthewvenn](https://twitter.com/matthewvenn)
