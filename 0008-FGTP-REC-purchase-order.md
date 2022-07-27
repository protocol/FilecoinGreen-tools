---
FGTP: "0008"
title: REC Purchase Order
status: Proposed
original author: redransil
created: 2022-07-26
---

## Title
REC Purchase Order

## Abstract
Tool for determining how many new RECs to purchase in aggregate

## Authors
redransil

## Status
Proposed

## What is the goal
In order to buy RECs in aggregate from brokers, we need to determine how many to buy by geography and time period.

## What are the inputs
* Filecoin dashboard [energy use API](https://filecoin-green.gitbook.io/filecoin-green-documentation/filecoin-green-api-docs/list-of-apis/energy-consumption-api)
* [Renewables purchases repo](https://github.com/redransil/filecoin-renewables-purchases) to track RECs already under contract
* Synthetic location data from provider.quest ([examples](https://github.com/redransil/filecoin-renewables-purchases/tree/main/20220501_ACT_PL_transaction_1/_assets))

## What are the outputs
A csv order form with:

*columns* corresponding to quarters (ie. 2021-Q1)
*rows* corresponding to regions. Generally these are [country codes](https://github.com/redransil/filecoin-renewables-purchases/blob/main/country_codes_irec.json) (ie. CN), for the US they are NERC regions (ie. US-MISO)
*values* corresponding to amount of RECs to purchase, in MWh, rounded up to the nearest integer.

## Proposed Solution
1) Using the location file, find all the regions (ie countries and NERC regions) represented
2) For every completed quarter in time since the network launched in Q2 2000:
* Step through regions
* For each region, step through all of the corresponding minerIDs 
* For each minerID, find the upper bound of the energy used during this time period from the API.
  * API with one-day resolution should be sufficient
  * Multiply by 1.5 so that we over-buy RECs
  * If the minerID has multiple locations, multiply by the fraction of those locations in this region. Example: if a minerID lists {CN, CN, JP} and we are calculating RECs for China, multiply by 2/3.
* Sum over all minerIDs for this region and quarter. Round up to the nearest integer. This result is the number of RECs to buy for the corresesponding region and quarter.
3) For the current quarter, calculate REC purchases for each region as the following:
* Find the energy use (MWh) for a given minerID in the region so far this quarter
* Determine the average power use (MW) over the quarter to date (ie. the 90 days ending at the current date). Multiply by the time remaining in the quarter (ie. if we are 2 months into the quarter, multiply by 1 additional month)
* Add the two numbers above; ie the sum of actual power use so far plus extrapolated power use
* Multiply by 1.5 and the fraction of minerID locations in this region, as above.
* Sum over all minerIDs in the region and round up
4) Extrapolate for the upcoming quarter
* Calculate power (MW) as above, and multiply by the length of the upcoming quarter (approximately 90 days)

## Implementations and Artifacts 


## Relevant Background
