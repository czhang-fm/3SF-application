# Formal analysis of the 3-Slot Finality based Ethereum consensus protocol
## Abstract

The current Ethereum consensus protocol is very complex with the LMD-GHOST as the availability sub-protocol and FFG-Casper as the Finality sub-protocol. The next generation candidate protocol, known as 3-Slot Finality (3SF), is less complex, which provides an opportunity for formal verification. This project aims to deliver a Dafny model that is closely correlated to the evolving executable Python specification (https://github.com/saltiniroberto/ssf), so that the desirable security properties can be established as lemmas in Dafny under reasonable assumptions for the protocol execution environment, which will greatly increase the confidance for the candidate protocol 3SF in its design stage.

## Objectives

*What are you hoping to accomplish with this grant? How do you define and measure success for this project?*

Given the 3SF currently at its design stage, we can apply the traditional formal verification to bridge the gap between the high level spec (https://arxiv.org/abs/2411.00558) and the low level spec in Python (https://github.com/saltiniroberto/ssf). Basically, we will need to produce two Dafny models corresponding to the specifications at high level and low level, with the low level Dafny model refines the high level Dafny model (i.e., the invariants established at the high level model is preserved in the low level model). Both models will need to cover the dynamic availability (DA) sub-protocol based on TOB-SVD and the finality sub-protocol based on SSF, with their corresponding security requirement proved as lemmas in both models. We specify this in the following.

### Objective 1: Dafny models for 3SF.
The high level model follows the protocol specification in the technical report (https://arxiv.org/abs/2411.00558). All possible behaviors of validators and round (time) progress are specified as predicates that transfer protocol state from one to another, guarded by the conditions specified in the protocol specification. In high level model is produced by hand. The low level model may be created by using existing tool, which may be done via a transformer (https://hackmd.io/@ericsson49/python-to-dafny-transpiler) or a fine-tuned LLM model, though human intervention is still necessary.

### Objective 2: Security properties (DA confirmation, FFG confirmation, and acountable safety)
We will need to prove security properties in both models, with some controlled efforts to be made to migrate the prove from high to low via refinement. **Optimistic DA confirmation** should be proved on the DA sub-protocol provided (1) certain length of synchrony is guaranteed and (2) honest validators get a fair chance to propose blocks within that period. **Optimistic FFG confirmation** is similar, but should proved for the FFG sub-protocol. **Accountable safety** should be proved for the FFG sub-protocol on existence limited asynchrony that in case of two conflicting blocks being finalized, there is a way to identify atleast 1⁄3 faulty validators.

The success of the project should be demonstrated via either the security properties proved at both the high level specification and the low level specification models, or the properties failed to be proved on either model. Failure of the high level model may expose design errors, and failure at the low level model may indicate issues at the executable Python implementation.

## Outcomes

*How does this project benefit the greater Ethereum ecosystem?*

This project aims to increase the trust guarantees of the Ethereum Consensus Layer specifications. Ethereum is quite a complex distributed protocol, with many moving parts and so-called “corner cases” that are easy to miss (https://notes.ethereum.org/@djrtwo/2023-fork-choice-reorg-disclosure) in the Fork Choice part of the Ethereum specification.

## Grant Scope

*What are you going to research? What is the expected output?*



## Related Work

What existing research is relevant to your project?
What is the specific gap your research is addressing within this context?

## Project Team

How many people are working on this project?

Please list their names and roles for the project as well as how many hours per month will each person work on this project?

## Background

Give us a bit of info and include relevant links, if available! Please provide other projects or research papers (ideally public and/or open source), engagements or other types of proof that your team has the necessary experience to undertake the project you are applying for.

Any links for us to review? E.g. research papers, blog posts, etc.

## Methodology

How do you plan to achieve your research objectives?

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
