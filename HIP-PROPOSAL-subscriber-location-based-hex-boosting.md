# HIP Template (Give it a title here but do not allocate a number, maintainer will allocate a number)

- Author(s): [Andrew Fisher](https://github.com/afisherdev) & [Niko LeMieux](https://github.com/EasyNiko) & [Russell From](https://github.com/) & [Nick Carpinito](https://github.com/meta-light)
- Contributor: [Josh Heller](https://github.com/jhella)
- Start Date: 2024-01-17
- Category: technical, economic
- Original HIP PR: <!-- leave this empty; maintainer will fill in ID of this pull request -->
- Tracking Issue: <!-- leave this empty; maintainer will create a discussion issue -->
- Vote Requirements: veMOBILE

## Summary

One paragraph explanation of the proposal.

<!-- Read the content requests in all sections before starting to write any section. -->

## Motivation
The Helium community has been involved in an ongoing discourse surrounding HIP 101 and 103, which generally aim to disincentivize deployments that aim to abuse the Helium Mobile subDAO Proof-of-Coverage oracle system. Our implementation aims to solve this gaming vector through a PoC boosting system based on Helium Mobile subscriber distribution derived from Nova Labs Discovery Mapping heatmap data in order to properly incentivise deployers and operators of CBRS and WiFi hotspots to supply coverage in areas with concentrations of active subscribers. We expect this will result in higher quality coverage while disincentivisng gaming on the Mobile network. 

The goal of the Helium Mobile network should be the propagation of high-quality coverage zones where they are needed (supply) in order to provide a service coverage to subscribers that have indicated through usage or through sign-ups that they desire service in that area (demand). Changes that call for the implementation over laborious metrics to make even a basic action for the provision of either supply or demand only introduce friction into the system and these collective frictions limit the velocity of supply and demand growth of the entire network. Supply should be served by both strategic coverage deployments (CBRS) that provide large coverage zones, as well as tactical coverage deployments (WiFi) that fill in the last-mile gaps in strategic coverage. Demand should be strategically observed through subscriber counts and overall network traffic, and tactically observed by heatmaps comprised of data analysis of user movement and local network resource usage. 


## Stakeholders

- Who is affected by this HIP? A stakeholder is any individual, group, or party such as network
  users, Hotspot hosts, or token holders.
- How are we soliciting feedback on this HIP from these stakeholders? Note that they may not be
  watching the HIP repository or even directly active in the Helium Community chat channels.

## Detailed Explanation

- Introduce and explain new concepts.
- It should be reasonably clear how the proposal would be implemented.
- Provide representative examples that show how this proposal would be commonly used.
- Corner cases should be dissected by example.

## Drawbacks

- Why should we _not_ do this?
- What problems could occur if we do this?

## Rationale and Alternatives

This is your chance to discuss your proposal in the context of the whole design space. This is
probably the most important section!

- Why is this design the best in the space of possible designs?
- What other designs have been considered and what is the rationale for not choosing them?
- What is the impact of not doing this?

## Unresolved Questions

- What parts of the design do you expect to resolve through the HIP process before this gets merged?
- What parts of the design do you expect to resolve through the implementation of this feature?
- What related issues do you consider out of scope for this HIP that could be addressed in the
  future independently of the solution that comes out of this HIP?
- Are there dependencies, milestones, or dates that need to be met for this HIP to succeed?

## Deployment Impact

Describe how this design will be deployed and any potential impact it may have on current users of
this project.

- How will current users be impacted?
- How will existing documentation/knowledge base need to be supported? Any content to change at
  <http://docs.helium.com>?
- Is this backwards compatible? Can this HIP be undone?
  - If not, what is the procedure to migrate?

## Success Metrics

What metrics can be used to measure the success of this design? Are any new ETL reports needed to
measure the success?

- What should we measure to prove a performance increase?
- What should we measure to prove an improvement in stability?
- What should we measure to prove a reduction in complexity?
- What should we measure to prove an acceptance of this by its users?
