# MISP standards

This repository is the official source of the specification and formats used in the MISP project.

The formats are described to support other implementations which reuse the format and ensuring an interoperability
with existing MISP software and other Threat Intelligence Platforms.

All the formats can be freely reused by everyone.

## MISP Formats in use and implemented in multiple software

* [misp-core-format](misp-core-format/raw.md.txt) ([markdown source](misp-core-format/raw.md)) which describes the core JSON format of MISP. Current Internet-Draft: [02](https://tools.ietf.org/html/draft-dulaunoy-misp-core-format)
* [misp-taxonomy-format](misp-taxonomy-format/raw.md.txt) ([markdown source](misp-taxonomy-format/raw.md)) which describes the taxonomy JSON format of MISP. Current Internet-Draft: [04](https://tools.ietf.org/html/draft-dulaunoy-misp-taxonomy-format)
* [misp-galaxy-format](misp-galaxy-format/raw.md.txt) which describes the [galaxy](https://github.com/MISP/misp-galaxy) template format used to expand the threat actor modelling of MISP. Current Internet-Draft: [00](https://datatracker.ietf.org/doc/draft-dulaunoy-misp-galaxy-format/)
* [misp-object-template-format](misp-object-template-format/raw.md.txt) which describes the [object](https://github.com/MISP/misp-objects) template format to add combinedand composite object to the MISP core format. Current Internet-Draft: [00](https://datatracker.ietf.org/doc/draft-dulaunoy-misp-object-template-format/)

## MISP Format in design phase and implemented in at least one software prototype

* misp-modules-protocol which describes the [misp-modules](https://github.com/MISP/misp-modules) protocol used between MISP and misp-modules.

## MISP Format in design phase

* misp-collaborative-voting-format which describes the collaborative voting and scoring format for the feeds providers.

# Contribution

If you want to contribute to the MISP specifications, feel free to [open an issue](https://github.com/MISP/misp-rfc/issues).

