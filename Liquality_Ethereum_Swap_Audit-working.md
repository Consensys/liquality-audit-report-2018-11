# Liquality Ethereum Swap Audit

<img height="100px" Hspace="30" Vspace="10" align="right" src="static-content/diligence.png"/>

<!-- Don't remove this -->
<!--59bcc3ad6775562f845953cf01624225-->
<!-- Don't remove this -->

## 1 Summary

ConsenSys Diligence conducted a security audit on Liquality's "Ethereum Swap" contract. The scope of the audit was just the output of the Ethereum provider's `createSwapScript` function, which is a hashed timelock that is used in the context of cross-chain atomic swaps.

The audit covered the file `EthereumSwapProvider.js` with the MD5 hash `395c95e0449cd60b14202c383ea858a2`.

### 1.1 Audit Dashboard

________________

<img height="120px" Hspace="30" Vspace="10" align="right" src="static-content/dashboard.png"/>

#### Audit Details
* **Project Name:** Liquality Ethereum Swap
* **Client Name:** Liquality
* **Client Contact:** Matthew Black
* **Auditors:** Steve Marx, Gonçalo Sá
* **GitHub:** https://github.com/liquality/chainabstractionlayer/blob/4a1e55e31e20206165dabbf4bd22c44ac785a34a/src/providers/ethereum/EthereumSwapProvider.js
* **Languages:** EVM bytecode
* **Date:** 2018-11-02

#### Number of issues per severity

<%= issue_overview %>

________________

### 1.2 Audit Goals

The focus of the audit was to verify that the smart contract system is secure, resilient and working according to its specifications. The audit activities can be grouped in the following three categories:  

**Security:** Identifying security related issues within each contract and within the system of contracts.

**Sound Architecture:** Evaluation of the architecture of this system through the lens of established smart contract best practices and general software best practices.

**Code Correctness and Quality:** A full review of the contract source code. The primary areas of focus include:

* Correctness
* Readability
* Sections of code with high complexity
* Improving scalability
* Quantity and quality of test coverage

### 1.3 System Overview

#### Scope

The scope of the audit was purely on the output of the Ethereum provider's `createSwapScript` function. However, other code was skimmed to understand the context in which this code is used.

#### Design

The contract is used as part of an atomic swap. It stores ether and transfers it to one of two addresses depending on whether a correct hash preimage is provided and whether an expiration time has been reached.

### 1.4 Key Observations/Recommendations

* The bytecode is well optimized for gas consumption.
* The bytecode is easy to follow (as compared to other hand-written bytecode).
* There's poor test coverage of the contract.
* Hand-written bytecode is difficult to audit and for end users to review as compared to Solidity.

## 2 Issue Overview  

The following table contains all the issues discovered during the audit. The issues are ordered based on their severity. More detailed description on the levels of severity can be found in Appendix 1. The table also contains the GitHub status of any discovered issue.

<%= issue_list %>


## 3 Issue Detail  

<%= issues_markdown %>

## Appendix 1 - Severity


### A.1.1 - Minor

Minor issues are generally subjective in nature, or potentially deal with topics like "best practices" or "readability".  Minor issues in general will not indicate an actual problem or bug in code.

The maintainers should use their own judgment as to whether addressing these issues improves the codebase.

### A.1.2 - Medium

Medium issues are generally objective in nature but do not represent actual bugs or security problems.

These issues should be addressed unless there is a clear reason not to.

### A.1.3 - Major

Major issues will be things like bugs or security vulnerabilities.  These issues may not be directly exploitable, or may require a certain condition to arise in order to be exploited.

Left unaddressed these issues are highly likely to cause problems with the operation of the contract or lead to a situation which allows the system to be exploited in some way.

### A.1.4 - Critical

Critical issues are directly exploitable bugs or security vulnerabilities.

Left unaddressed these issues are highly likely or guaranteed to cause major problems or potentially a full failure in the operations of the contract.

## Appendix 2 - Disclosure

ConsenSys Diligence (“CD”) typically receives compensation from one or more clients (the “Clients”) for performing the analysis contained in these reports (the “Reports”). The Reports may be distributed through other means, including via ConsenSys publications and other distributions.

The Reports are not an endorsement or indictment of any particular project or team, and the Reports do not guarantee the security of any particular project. This Report does not consider, and should not be interpreted as considering or having any bearing on, the potential economics of a token, token sale or any other product, service or other asset. Cryptographic tokens are emergent technologies and carry with them high levels of technical risk and uncertainty. No Report provides any warranty or representation to any Third-Party in any respect, including regarding the bugfree nature of code, the business model or proprietors of any such business model, and the legal compliance of any such business. No third party should rely on the Reports in any way, including for the purpose of making any decisions to buy or sell any token, product, service or other asset. Specifically, for the avoidance of doubt, this Report does not constitute investment advice, is not intended to be relied upon as investment advice, is not an endorsement of this project or team, and it is not a guarantee as to the absolute security of the project. CD owes no duty to any Third-Party by virtue of publishing these Reports.

PURPOSE OF REPORTS The Reports and the analysis described therein are created solely for Clients and published with their consent. The scope of our review is limited to a review of Solidity code and only the Solidity code we note as being within the scope of our review within this report. The Solidity language itself remains under development and is subject to unknown risks and flaws. The review does not extend to the compiler layer, or any other areas beyond Solidity that could present security risks. Cryptographic tokens are emergent technologies and carry with them high levels of technical risk and uncertainty.

CD makes the Reports available to parties other than the Clients (i.e., “third parties”) -- on its GitHub account (https://github.com/ConsenSys). CD hopes that by making these analyses publicly available, it can help the blockchain ecosystem develop technical best practices in this rapidly evolving area of innovation.

LINKS TO OTHER WEB SITES FROM THIS WEB SITE You may, through hypertext or other computer links, gain access to web sites operated by persons other than ConsenSys and CD. Such hyperlinks are provided for your reference and convenience only, and are the exclusive responsibility of such web sites' owners. You agree that ConsenSys and CD are not responsible for the content or operation of such Web sites, and that ConsenSys and CD shall have no liability to you or any other person or entity for the use of third party Web sites. Except as described below, a hyperlink from this web Site to another web site does not imply or mean that ConsenSys and CD endorses the content on that Web site or the operator or operations of that site. You are solely responsible for determining the extent to which you may use any content at any other web sites to which you link from the Reports. ConsenSys and CD assumes no responsibility for the use of third party software on the Web Site and shall have no liability whatsoever to any person or entity for the accuracy or completeness of any outcome generated by such software.

TIMELINESS OF CONTENT The content contained in the Reports is current as of the date appearing on the Report and is subject to change without notice. Unless indicated otherwise, by ConsenSys and CD.

