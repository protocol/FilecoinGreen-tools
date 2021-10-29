---
FGTP: "0003"
title: Filecoin Electricity Estimator
status: Active
original author: redransil
created: 2021-10-29
---

## Title
Filecoin Electricity Estimator

## Abstract
Model for estimating the electricty use of Filecoin using on-chain activity

## Authors
redransil

## Status
Active

## What is the goal
In order to reduce and mitigate the environmental impacts of Filecoin, we need to understand what the electricity use of the network is. The easiest route to do this in an open, permissionless way is to build a model that estimates electricity use based on on-chain activity.

## What are the inputs
Data scraped from the Filecoin chain showing sealing and storage over time.

## What are the outputs
Electrical power (ie in watts) and total power consumption over a given time period (ie in Wh) for (1) the network as a whole, and (2) individual minerIDs.

## Proposed Solution
See implementation below for model description.

## Implementations and Artifacts 
1. [Filecoin Energy Estimator Implementation](https://github.com/redransil/filecoin-energy-estimation/blob/main/README.md)
2. [Filecoin Green Orbit Presentation](https://www.youtube.com/watch?v=leA6cbq6ToA&list=PL_0VrY55uV18i8gXWcuVLK3J60cetDP6E&index=4)

## Relevant Background
Some relevant literature and projects:
1. [BTC Energy Consumption, Digiconomist](https://digiconomist.net/bitcoin-energy-consumption/)
2. [CBECI Methodology](https://cbeci.org/index/methodology)
3. [Energy Footprint of Blockchain Consensus Mechanisms Beyond Proof-of-Work](https://arxiv.org/abs/2109.03667)
4. [Data center growth in the United States: decoupling the demand for services from electricity use](https://iopscience.iop.org/article/10.1088/1748-9326/aaec9c/meta)
5. [Recalibrating global data center energy-use estimates](https://www.science.org/doi/10.1126/science.aba3758)
