---
FGTP: "0010"
title: Geographical and Energy Data for a CID
status: Proposed
original author: redransil
created: 2022-09-07
---

## Title
Geographical and Energy Data for a CID

## Abstract
Build a UI and an API for getting data about where and how a CID is stored

## Authors
redransil

## Status
Proposed 

## What is the goal
To build a tool similar extending [CID.place](https://cid.place/) showing geographic, energy, and renewable energy information.


## What are the inputs
CID to minerID: CID.place (see [handbook](https://filecoin-green.gitbook.io/filecoin-green-documentation/filecoin-green-ui-tools/cid.place))
Geographic information: [synthetic locations](https://observablehq.com/@jimpick/provider-quest-synthetic-locations?collection=@jimpick/provider-quest)
Energy information: [energy consumption endpoints](https://filecoin-green.gitbook.io/filecoin-green-documentation/filecoin-green-api-docs/list-of-apis/energy-consumption-api)
Renewable energy information: [renewable energy endpoints](https://filecoin-green.gitbook.io/filecoin-green-documentation/filecoin-green-api-docs/list-of-apis/renewable-energy-certificates-api)

## What are the outputs
For each CID entered:

In aggregate:
- A map with the geographic locations where this CID is stored
- Total amount of energy used by all minerIDs storing the CID
- Total amount of renewable energy purchased by all minerIDs storing the CID
- Total amount of each type of renewable energy purchased by this minerID (ie solar, wind, hydro, biomass)

For each minerID:
- The minerID(s) currently storing it as already shown in CID.place; [example](https://cid.place/bafybeie42bt3s7ne3jcuwt2ojzlbvws7mt75dntp3exzqzqryzriyzx3xa)
- PeerID(s), and addresses as shown in CID.place
- Geographic location(s)
- Total amount of data stored
- Lower bound, upper bound, and estimate of total energy used by this minerID over its lifetime
- Total amount of renewable energy purchased by this minerID
- Amount of each type of renewable energy purchased by this minerID (ie solar, wind, hydro, biomass)

## Proposed Solution
See description and outputs. For a given CID, look up required information and aggregate data as needed.

## Implementations and Artifacts 
Extends [cid.place](https://cid.place/)
For map example, see [Filecoin energy map](https://filecoin-green.dzunic.net/)

## Relevant Background
For more information on synthetic locations, [Jim Pick's meetup presentation](https://youtu.be/PyxSRV0UlFc?t=2524)
