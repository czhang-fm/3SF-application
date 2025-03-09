# Formal analysis of the 3-Slot Finality based Ethereum consensus protocol
## Abstract

The current Ethereum consensus protocol is very complex with the LMD-GHOST as the availability sub-protocol and FFG-Casper as the Finality sub-protocol. The next generation candidate protocol, known as 3-Slot Finality (3SF), is less complex, which provides an opportunity for formal verification. This project aims to develop a Dafny model closely aligned with the evolving executable Python specification (https://github.com/saltiniroberto/ssf), enabling the establishment of desirable security properties as lemmas in Dafny under reasonable assumptions about the protocol execution environment. Additionally, this project will investigate potential bugs and vulnerabilities in the 3SF protocol, significantly enhancing confidence in its reliability before its deployment in the Ethereum consensus layer.

## Objectives

*What are you hoping to accomplish with this grant? How do you define and measure success for this project?*

Given the 3SF currently at its design stage, we can apply the traditional formal verification to bridge the gap between the high level description (https://arxiv.org/abs/2411.00558) and the low level Python executable (https://github.com/saltiniroberto/ssf). Basically, we will need to produce two Dafny models corresponding to the specifications at both the high level and the low level. The low level Dafny model should refine the high level Dafny model, i.e., the proof results established at the high level model should be preserved in the low level model. Both models will need to cover the dynamic availability (DA) sub-protocol based on TOB-SVD and the finality sub-protocol based on SSF, with the corresponding security requirements proved as lemmas in both models. We specify the following objectives.

### Objective 1: Dafny models for 3SF.
The high level model follows the protocol specification in the technical report (https://arxiv.org/abs/2411.00558). All possible behaviors of validators and round (time) progress are specified as predicates that transfer protocol states from one to another, guarded by conditions. The high level model will be produced by hand. The low level model may be created by using existing tools, such as a automatic code transformer (https://hackmd.io/@ericsson49/python-to-dafny-transpiler) or a fine-tuned LLM model, though human intervention is still necessary.

### Objective 2: Security properties (DA confirmation, FFG confirmation, and acountable safety)
We will need to prove security properties in both models. Efforts will be made to migrate proof from the high level model to the low level model via refinement. **Optimistic DA confirmation** should be proved on the DA sub-protocol provided that (1) a certain length of synchronous period is guaranteed and (2) honest validators get a fair chance to propose blocks within that period. **Optimistic FFG confirmation** has similar assumptions, though it should be proved for the FFG sub-protocol. **Accountable safety** should be proved for the FFG sub-protocol on existence of limited asynchrony that in case of two conflicting blocks being finalized, there is a way to identify atleast 1⁄3 faulty validators.

The success of the project should be demonstrated in the established Dafny models with either the security properties verified at both the high level model and the low level model, or the properties failed to be proved in a model. Failure at the high level model may expose design errors, and failure at the low level model may indicate issues at the executable Python implementation.

## Outcomes

*How does this project benefit the greater Ethereum ecosystem?*

This project aims to increase the trust guarantees of the Ethereum Consensus Layer specifications. Given its complexity, the current Ethereum consensus protocol Gasper has been exposed of bugs or vulnerabilities in its fork choice Python specification which were fixed with great efforts (https://notes.ethereum.org/@djrtwo/2023-fork-choice-reorg-disclosure). A formally verified model at the design stage of next generation Ethereum consensus protocol, even it may adopt a certain degree of abstraction, will benefit the Ethereum ecosystem by strengthening the consensus layer. Moreover, the backend (code generation) of Dafny tool may be used to help generate executable Python implementation with minimum help from human experts.

## Grant Scope

*What are you going to research? What is the expected output?*

We check whether it is feasible to create a Dafny model for a censensus protocol instance as complex as 3SF. In the past Dafny has been used to verify protocols such as DVT (https://github.com/Consensys/distributed-validator-formal-specs-and-verification) and QBFT (https://github.com/Consensys/qbft-formal-spec-and-verification). The 3SF protocol, even at its design stage, is arguably more complex. In this project the main focus is an instance of 3SF which consists of the FFG finality sub-protocol and the TOB-SVD dynamic availability sub-protocol, which together represent an instance of Ebb-and-Flow mechanism.

The expected output is a package of Dafny models representing both a high level spec and a low level spec of the aforementioned 3SF instance protocol.

## Related Work

*What existing research is relevant to your project?
What is the specific gap your research is addressing within this context?*

## Project Team

*How many people are working on this project?*

*Please list their names and roles for the project as well as how many hours per month will each person work on this project?*

-- Chenyi Zhang (PI, senior lecturer at University of Canterbury, New Zealand, https://scholar.google.com/citations?user=0W4CUDoAAAAJ&hl=en) will guide the design, modelling the protocol as well as the proof engineering. He will contribute 37.5 hours per months (25%).

-- Thanh-Hai Tran (CoPI, Independent researcher, Australia) will guide the design, modelling the protocol as well as the proof engineering. He will contribute 75 hours per months (50%).

-- Xilong Zhuo (PhD student at the University of Canterbury, New Zealand), will participate in the Dafny modelling and formal proofs and will contribute 75 hours per month (50%).

-- Ming Li (PhD student at Jinan University, visiting student at the University of Canterbury, New Zealand), will mainly work as a research engineer for maintaining the IT environment as well as participating the modelling in Dafny and will contribute 75 hours per month (50%)

## Background

*Give us a bit of info and include relevant links, if available! Please provide other projects or research papers (ideally public and/or open source), engagements or other types of proof that your team has the necessary experience to undertake the project you are applying for.*

Chenyi Zhang (PhD in Computer Science) has contributed in defining security properties and a fast confirmation rule (https://arxiv.org/abs/2405.00549) for the current Ethereum consensus protocol (Gasper). In the past he worked on static program analysis in Java, security protocol verification, and information flow security in various semantic models.

Thanh-Hai Tran (PhD in Computer Science) has worked on formal verification of the Distributed Validator protocol in Dafny and the model checking of the Ethereum consensus protocol in TLA+. He is a co-inventor of the 3SF Ethereum consensus protocol.

Xilong Zhuo is a PhD candidate in University of Canterbury. His current research topic is formal verification of security protocols.

Ming Li is a PhD candidate in Jinan University. His current research focus is in theoretical foundation of Artificial Intelligence. He is currently a visiting student at the University of Canterbury.

*Any links for us to review? E.g. research papers, blog posts, etc.*

## Methodology

*How do you plan to achieve your research objectives?*



## Timeline

Please include a brief explanation on the milestones/roadmap, along with expected deliverables. Also outline how the funds will be used for the research project and or members of the team.

Milestone 1: title
Budget: based off hourly rate and number of hours
Number of hours (roughly)
summary of work, subtasks

## Budget

Requested grant amount and how this will be used

Please provide an requested amount and outline of how the grant will be used. A detailed budget proposal would be helpful and some items you could include are:

- Principal Researchers Costs
- Other Staff Costs
- Hardware Costs
- Software Costs
- Data Collection Costs
- Indirect Costs
