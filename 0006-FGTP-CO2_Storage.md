---
FGTP: "0006"
title: CO2.Storage
status: Proposed/Active
original author: marcjohnson518, redransil, adgsm
created: 2022-05-30
---


## Title
CO2.Storage

## Abstract
The budding Refi space, and tokenized carbon credits in particular, would benefit from the development of standard data schemas for environmental assets.

A data upload utility that maps inputs to base data schemas ([IPLD](https://ipld.io/) DAGs) for off-chain data (like metadata, images, attestation documents, and other assets) would enable this standardization.

With IPLD DAGs, data is [content addressed](https://nftschool.dev/concepts/content-addressing) using IPFS, meaning the URI pointing to a piece of data (“ipfs://…”) is completely unique to that data (using a [content identifier](https://docs.ipfs.io/concepts/content-addressing/), or CID). CIDs can be used for environmental assets and metadata to ensure the asset forever actually refers to the intended data (eliminating things like double counting, and making it trustlessly verifiable what content an asset is associated with).

These standard, content addressed, data schemas would also enable more seamless cross-referencing for missing data & meta-analysis of different assets/credits, as well as help expedite the development of new forms of methodologies, supply, and marketplaces.

## Authors


- [mjohnson518](https://github.com/mjohnson518)
- [redransil](https://github.com/redransil)
- [adgsm](https://github.com/adgsm)

## Status


**Proposed/Active** 

Industry practitioners would benefit from the development of an upload utility for environmental assets based on standardized data schemas. 

[Filecoin Green](https://green.filecoin.io/) is actively pursuing the development of this concept and invites the Refi community & Solarpunk movement to join us in this endeavor.

## What is the goal

The goal is to develop a data upload utility that leverages a set of reusable templates that map inputs to base data schemas (IPLD DAGs) for the creation and verification of environmental assets. 

These templates (and underlying data schemas) could be based on various methodologies, reporting requirements, and verification processes (MRV) such as those specified by [Verra](https://verra.org/project/vcs-program/), [Gold Standard](https://www.goldstandard.org/our-story/gold-standard-global-goals), [IWA Standard](https://interwork.org/the-interwork-alliance-sustainability-initiative-to-develop-trusted-solution-for-standardizing-token-based-carbon-emission-accounting-credits-and-offsetting/), and others. 

In the longer term, these templates could expand to other methodologies and assets, such as those in the [UNFCCC CDM](https://cdm.unfccc.int/methodologies/index.html), or even more traditional ISO standards for various environmental/sustainability claims.

Furthermore, we envision that this data upload utility will be extensible, therefore essentially being a *‘templating engine’* for anyone to make their own environmental assets based on specific methodologies & variables.

## What are the inputs


The initial product flow looks something like:
- Practitioner selects a schema from available templates.
- Practitioner inputs all relevant data and uploads any accompanying documentation (such as pdfs/images of Offset/REC/EAC certifications or attestations.
- Practitioner selects if they want an independent third-party audit conducted to verify data matches the data inputs and accompanying documentation.
- Practitioner confirms submission of template to upload utility.

## What are the outputs

Initial product outputs include:
- Practitioner receives a CID representing the asset details/data.
- Data is stored on Filecoin/IPFS via [Estuary](https://estuary.tech/).
- Data Schema & relevant details are viewable on asset previewer and [IPLD Explorer](https://explore.ipld.io/#/).

Future capabilities may include:
- The ability to perform all steps with a simple API.
- Integration with the [Filecoin Virtual Machine](https://fvm.filecoin.io/) for smart contract capabilities.
- Alternative governance or oracle structures, especially as it relates to the auditing function.

## Relevant Background

[Protocol Labs](https://protocol.ai/) is building the next generation of the internet, and is committed to driving breakthroughs in computing to push humanity forward. This commitment can be attested to from our development and ongoing maintenance of decentralized data upload, storage, and retrieval solutions such as [IPFS](https://ipfs.io/), [IPLD](https://ipld.io/), [Filecoin](https://filecoin.io/), [NFT.Storage](https://nft.storage/), [Web3.Storage](https://web3.storage/), [Estuary](https://estuary.tech/), and many other projects.

 [Filecoin Green](https://green.filecoin.io/) is well positioned to lead the development of this public good for environmental assets, as can be seen from our work on the [Filecoin Network Energy Dashboard](https://filecoin.energy/), as well as [base data schema](https://github.com/protocol/0004-FGTP-Content-Address-EACs-Scraper) and [previewer](https://filecoin-green-eac-browser.dzunic.net/) for Energy Attribution Certificates (EACs).

We are excited to work with the Refi community to develop this upload utility, and we invite any existing project, team, or individual to reach out and express their interest in working with us. 

We believe teams & projects such as [Regen Network](https://www.regen.network/), [Toucan](https://toucan.earth/), [Klima](https://www.klimadao.finance/), [dClimate](https://www.dclimate.net/), [Open Forest Protocol](https://www.openforestprotocol.org/), [Nori](https://nori.com/), [GainForest](https://www.gainforest.app/), [FlowCarbon](https://www.flowcarbon.com/), [Ripple](https://ripple.com/), [Polygon](https://polygon.technology/), [Ethereum Foundation](https://ethereum.foundation/), [Verra](https://verra.org/), [Gold Standard](https://www.goldstandard.org/), [IWA Sustainability Initiative](https://interwork.org/the-interwork-alliance-sustainability-initiative-to-develop-trusted-solution-for-standardizing-token-based-carbon-emission-accounting-credits-and-offsetting/), and many others could benefit from this work, and would certainly provide invaluable insights in helping inform the development of this public good for environmental assets.

Please feel free to submit a comment to this issue, or reach out directly to [Marc Johnson](mailto:marc.johnson@protocol.ai) if this topic is of interest to you.
