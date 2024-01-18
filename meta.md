# Subscriber Heatmap Based Hex Boosting

- Author(s): [afisherdev](https://github.com/afisherdev), [EasyNiko](https://github.com/EasyNiko) & [meta-light](https://github.com/meta-light) 
- Start Date: 2024-01-17
- Category: Technical, Economic
- Original HIP PR: <!-- leave this empty; maintainer will fill in ID of this pull request -->
- Tracking Issue: <!-- leave this empty; maintainer will create a discussion issue -->
- Vote Requirements: veMOBILE

## Summary
This Helium Improvement Proposal (HIP) is designed to fix issues around Proof-of-Coverage gaming based on geography and use case, and introduces a new mechanism to reward Helium Mobile coverage based on subscriber density and network usage.

<!-- One paragraph explanation of the proposal. -->
<!-- Read the content requests in all sections before starting to write any section. -->

## Motivation
The Helium community has been involved in an ongoing discourse surrounding gaming of Proof-of-Coverage (PoC) rewards with HIP 101 and 103, which generally aim to disincentivize deployments that abuse the Helium Mobile subDAO PoC oracle system. Our implementation aims to solve this gaming vector through a PoC boosting system based on Helium Mobile subscriber distribution derived from Nova Labs Discovery Mapping heatmap data in order to properly incentivise deployers and operators of CBRS and WiFi hotspots to supply coverage in areas with concentrations of active subscribers. We expect this will result in higher quality coverage while disincentivisng gaming on the Mobile network.

The goal of the Helium Mobile network should be the propagation of high-quality coverage zones where they are needed (supply) in order to provide a service coverage to Helium Mobile subscribers that have indicated through Helium Mobile network usage or through sign-ups that they desire service in that geographic area or use case (demand). Any attempt to predetermine or filter 'acceptable' use cases or geographies ultimately undercuts the entire purpose of a decentralized network, with individual contributors providing coverage when and where they identify a need. Changes that call for the implementation of overly complicated third-party metrics, or changes that affect the provision of either supply or demand only introduce friction into the system and these collective frictions limit the velocity of supply and demand growth of the entire network. Supply should be served by both strategic coverage deployments (CBRS) that provide large coverage zones, as well as tactical coverage deployments (WiFi) that fill in the last-mile gaps in strategic coverage. Demand should be strategically monitored through overall subscriber counts and overall network traffic, and tactically observed by heatmaps comprised of data analysis of user movement and local network resource usage in specific geographies and use cases. 


## Stakeholders
This proposal affects 2 groups of stakeholders:
- **End Users & Subscribers** will benefit from an increase of usable coverage in high-demand areas. 
- **CBRS & WiFi Deployers** will be met with additional disincentives for attempting to game Proof-of-Coverage oracles through ineffective deployments while good-faith actors will be met with additional economic incentives. 

We hope to circulate this HIP and additional rationale within the Helium Discord server. 

## Detailed Explanation
<!-- 
- Introduce and explain new concepts.
- It should be reasonably clear how the proposal would be implemented.
- Provide representative examples that show how this proposal would be commonly used.
- Corner cases should be dissected by example.
-->

We propose a system implimentation leveraging resolution 5 [Uber H3](https://www.uber.com/blog/h3/) hexes (About 252.9 km^2) cross-referenced against publically available population data per hex, updated on a bi-monthly basis to determine the boost multuplier. Ideally this design includes a 2 month buffer for deployers to make nessicery adjustments

| Subscribers per 100k People | PoC Boost |
| ----------- | ----------- |
| 1-5 | 1.1x |
| 6-25 | 1.2x |
| 26-100 | 1.3x |
| 101-500 | 1.4x |
| 501+ | 1.5x |

## Drawbacks
We presume a moderately high level of complexity involved in accurately determining active subscriber metrics on an ongoing basis and communicating this data to rewards oracles. 

## Rationale and Alternatives
<!-- 
This is your chance to discuss your proposal in the context of the whole design space. This is
probably the most important section!
- Why is this design the best in the space of possible designs?
- What other designs have been considered and what is the rationale for not choosing them?
- What is the impact of not doing this?
-->

## Unresolved Questions
<!-- 
- What parts of the design do you expect to resolve through the HIP process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature?
- What related issues do you consider out of scope for this HIP that could be addressed in the
  future independently of the solution that comes out of this HIP?
- Are there dependencies, milestones, or dates that need to be met for this HIP to succeed?
-->
- _What will the legaility and process for Nova Labs discovery mapping data acquisition look like?_
- _Will additional measures need to be implimented to address spoofing concerns?_

## Deployment Impact
Describe how this design will be deployed and any potential impact it may have on current users of
this project.
<!-- 
- How will current users be impacted?
- How will existing documentation/knowledge base need to be supported? Any content to change at
  <http://docs.helium.com>?
- Is this backwards compatible? Can this HIP be undone?
  - If not, what is the procedure to migrate? 
-->
- Current Helium Mobile subscribers should notice a gradual increase in coverage in places where there is a demand for Helium Mobile Hotspots
- Existing PoC and Rewards documentation will need to be revised to include a detailed description of the system functionality, along with the modeled coverage explorer. (is this NOVA?)
- This HIP can easily be nullified via a future stakeholder vote if success metrics prove an ineffective implimentation. 

## Success Metrics
<!-- 
What metrics can be used to measure the success of this design? Are any new ETL reports needed to
measure the success?
- What should we measure to prove a performance increase?
- What should we measure to prove an improvement in stability?
- What should we measure to prove a reduction in complexity?
- What should we measure to prove an acceptance of this by its users?
-->
Successful implementation of this HIP will result in a greater amount of Helium Mobile cellular traffic being utilized on Helium CBRS and WiFi hotspots while reducing incentives to deploy ineffective coverage in areas with few or no current subscribers. These metrics are easily detemined by measuing the percentage of Helium Mobile cellular traffic being served by Helium radios as opposed to T-Mobile backhaul. Additionally, a successful implementation of this proposal should result in a reduction of radios providing coverage in areas with no current subscribers. 
