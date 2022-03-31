---
FGTP: "0004"
title: Content address EACs
status: Proposed
original author: redransil
created: 2022-03-31
---

## Title
Content address EACs

## Abstract
Data for EACs is currently tracked in several places, including in the 
[EAC Summary Archive](https://github.com/redransil/filecoin-renewables-purchases/tree/main/EAC_Purchase_Summary_Archive) and the Zero Labs system.

We'd like to take all of the relevant data, including certifictes, and track it with IPDL.

## Authors
redransil

## Status
Proposed

## What is the goal
Build Web3-native tools to assign CIDs to renewable energy certificates and the metadata mapping from them to SPs.

This should live, at least for now, in the [filecoin-renewables-purchases](https://github.com/redransil/filecoin-renewables-purchases) repo.

## What are the inputs
- Spreadsheet with renewable energy information
- Certificates outputted from the registry (pdfs)

Example #1: [Zero Labs REC tracker](https://docs.google.com/spreadsheets/d/1aOWOEVe9-pM666ahhSIoMdzGW_R2_JMgal0HItxFs9Y/edit?usp=sharing) for EACs already
in the system. This is a private sheet, let us know if you need access to this or a copy.
Example #2: [Order sheet](https://github.com/redransil/filecoin-renewables-purchases/blob/main/20220318_order/redemptions_ewc.csv), which we are expecting to come back with pdfs soon


## What are the outputs
IPLD data stored on [Estuary](https://estuary.tech/) which tracks pdf certificates and associated metadata.

Metadat should include, at least, all of the information returned by a transaction call to the [ZL API](https://proofs-api.zerolabs.green/api/partners/filecoin/nodes/f01234/transactions)

## Proposed Solution
- The pdf certificate should be stored on Estuary and have its own CID: [example](https://bafkreib5dmwkopgu5fb2a572o6x652shwsf45v74xfdvrnllscgunzqese.ipfs.dweb.link/)
- An object should hold a link to the pdf and metadata for each line in the EAC pdf. Each certificate will have at least one line. For example, the above I-REC has only one, 
[this certificate](https://dweb.link/ipfs/bafkreigxldrh3lo2spyg424ga4r7srss4f4umm3v7njljod7qvyjtvlg7e) has one and [this certificate](https://dweb.link/ipfs/bafkreigz5lcesy6cpfri4tgqkyk6od2yygh2t6zt3sjjh3b7eboxqugut4) has 24.
- Each transaction, mapping renewable energy to a minerID - for example an item in the array [here](https://proofs-api.zerolabs.green/api/partners/filecoin/nodes/f01234/transactions) which 
corresponds to an entry [here](https://docs.google.com/spreadsheets/d/1aOWOEVe9-pM666ahhSIoMdzGW_R2_JMgal0HItxFs9Y/edit?usp=sharing), should have its 
own CID and a bidirectional link to the corresponding line in the CID pdf. 
- There should be a tool to validate that when you follow from certificate->line->transaction and add all of the transactions, sum(transactions) <= the total on the certificate

## Implementations and Artifacts 
If you have built a version of this tool, link to it here as an implementation.
If you have given a talk, published a paper or created other artifacts about this tool, link to them here.

## Relevant Background
What publications, projects, or companies are relevant to this tool, and would provide useful information for someone working to implement it?
