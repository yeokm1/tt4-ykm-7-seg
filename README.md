![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg) ![](../../workflows/wokwi_test/badge.svg)

# tt4-ykm-7-seg

A Wokwi project for Tiny Tapout to show the string "ykM_1St_CHIP" character by character.

Wokwi page: https://wokwi.com/projects/372184284115580929

## How it works?

The string is shown by individual characters to the 7-segment LCD. 

By default with all pins except Clock being Low, the chip will cycle through all the characters depending on clock speed.

To display individual characters manually, set HIGH to counter pin and BCD. Then select the bits 0-3 manually.

## Directory structure

* generate-wokwi: Files used to produce the truthtable using the [wokwi-lookup-table-generator](https://github.com/maehw/wokwi-lookup-table-generator)
* wokwi-docs: Design files downloaded from Wokwi website

## Generating LUT

After setting up the [wokwi-lookup-table-generator](https://github.com/maehw/wokwi-lookup-table-generator), 

```bash
python3 generate.py -f ykm_text.json -o ykm_text.diagram.json --tinytapeout3 -v
```

## References
* https://github.com/r4d10n/tinytapeout-HELLo-3orLd-7seg/

------

# What is Tiny Tapeout?

TinyTapeout is an educational project that aims to make it easier and cheaper than ever to get your digital designs manufactured on a real chip!

Go to https://tinytapeout.com for instructions!

## How to change the Wokwi project

Edit the [info.yaml](info.yaml) and change the wokwi_id to match your project.

## How to enable the GitHub actions to build the ASIC files

Please see the instructions for:

- [Enabling GitHub Actions](https://tinytapeout.com/faq/#when-i-commit-my-change-the-gds-action-isnt-running)
- [Enabling GitHub Pages](https://tinytapeout.com/faq/#my-github-action-is-failing-on-the-pages-part)

## How does it work?

When you edit the info.yaml to choose a different ID, the [GitHub Action](.github/workflows/gds.yaml) will fetch the digital netlist of your design from Wokwi.

After that, the action uses the open source ASIC tool called [OpenLane](https://www.zerotoasiccourse.com/terminology/openlane/) to build the files needed to fabricate an ASIC.

## Resources

- [FAQ](https://tinytapeout.com/faq/)
- [Digital design lessons](https://tinytapeout.com/digital_design/)
- [Learn how semiconductors work](https://tinytapeout.com/siliwiz/)
- [Join the community](https://discord.gg/rPK2nSjxy8)

## What next?

- Submit your design to the next shuttle [on the website](https://tinytapeout.com/#submit-your-design), the closing date is 8th September.
- Share your GDS on Twitter, tag it [#tinytapeout](https://twitter.com/hashtag/tinytapeout?src=hashtag_click) and [link me](https://twitter.com/matthewvenn)!
