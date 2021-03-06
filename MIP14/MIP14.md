# MIP14: Protocol DAI Transfer

## Preamble
```
MIP#: 14
Title: Protocol DAI Transfer
Author(s): @LongForWisdom
Contributors: N/A
Type: Process
Status: Formal Submission (FS)
Date Proposed: 2020-05-12
Date Ratified: <yyyy-mm-dd>
Dependencies: MIP0
Replaces: N/A
```
## References
**[MIP14c2-Subproposal-Template.md](MIP14c2-Subproposal-Template.md)**

## Sentence Summary

MIP14 defines a generic process for transfering DAI from the Maker Protocol to a target ethereum address.

## Paragraph Summary

MIP14 defines a generic process for transfering DAI from the Maker Protocol to a target ethereum address. This process is a fallback method of transferring value from the protocol in the event that a more specific process does not exist to do so. 

## Component Summary

**MIP14c1: Considerations Regarding Protocol DAI Transfers**  
A component which outlines the various considerations that should be made before transferring DAI out of the protocol using MIP14c2.

**MIP14c2: Protocol DAI Transfer Process**  
A process component that allows Maker Governance to transfer DAI from the Maker Protocol to a target ethereum address.

**MIP14c3: Protocol DAI Transfer List**  
A list component that lists the previous direct DAI transfers that have been made by the protocol in the past.


## Motivation

Giving governance the ability to use the value generated by the Maker Protocol is beneficial for two main reasons:
- It allows Maker Governance to incentivise actions taken to improve the protocol.
- It reduces Maker Governance's reliance on the Maker Foundation.

Less reliance on the Foundation moves the protocol towards decentralization. Creating a process to allow Maker Governance to spend the value accrued by the protocol empowers Maker Governance to build and improve the protocol in the future.

## Specification / Proposal Details

**MIP14c1: Considerations Regarding Protocol DAI Transfers**  
There are several important considerations to take into account before transferring value out of the Maker Protocol.
- Transfer of DAI from the protocol to an external address that is not controlled by Maker Governance is a one-way operation.
- Transfer of DAI from the protocol will take DAI from the surplus buffer if available.
- If there is insufficient DAI available in the surplus buffer unbacked DAI will be created and FLOP auctions will be able to be triggered immediately.
- If there is a more specific process MIP that allows DAI transfers that is more appropriate to the use case, use that process instead.

---

**MIP14c2: Protocol DAI Transfer Process**  
MIP14c2 is a Process MIP component that allows Maker Governance to transfer DAI from the Maker Protocol to a target ethereum address. Note that MIP14c2 subproposals are technical subproposals, they define executive code that transfers DAI from the Maker Protocol to one or more target addresses.

If a MIP14c2 subproposal is Accepted, The DAI Transfer is appended to the list in MIP14c3 by a MIP Editor.

MIP14c2 subproposals have parameters that depend on the total amount of DAI to be transferred (even if split among multipe target addresses) according to the following logic:

**< 10,000 DAI Transfer**
- **Feedback Period:** 0 full weeks
- **Frozen period:** 0 full weeks

**10,000 - 100,000 DAI Transfer**
- **Feedback Period:** 4 full weeks
- **Frozen period:** 1 full week

**> 100,000 DAI Transfer**
- **Feedback Period:** 12 full weeks
- **Frozen period:** 4 full weeks

MIP14c2 subproposals must use the template located at **[MIP14c2-Subproposal-Template.md](MIP14c2-Subproposal-Template.md)**. This template is considered ratified once this MIP moves to Accepted status.

---

**MIP14c3: Protocol DAI Transfer List**  
This list can be amended through subproposals created under MIP14c2.

**List Entry Template**
Entries into this list should follow the following template:

```
Reason:
Sub-proposal Number: #
Date Ratified: (yyyy-mm-dd)
Amount Transferred:
Recipient Address:
```

**Historical Transfer List**
There are currently no historical transfers. Below is an example transfer which should be removed (as should this paragraph) when the first ratified transfer is added to this list .

```
Reason: Funding Chocolate for Governance Facilitators
Sub-proposal Number: MIP14c1-SP0
Date Ratified: 2020-02-30
Amount Transferred: 1,000,000 DAI
Recipient Address: 0x0000000000000000000000000000000000000000
```

---
