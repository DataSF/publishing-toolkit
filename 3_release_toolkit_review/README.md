# Open Data Release Toolkit Review

This process is triggered if the target data is sensitive or protected in its raw form. The classification of data happens during the inventory process or on submission of the intake form if the data is not yet inventoried.

There are two editions of the toolkit:
1. To assess risk related to privacy
2. To assess risk related to security

## Privacy edition

The privacy edition of the toolkit provides a step-by-step process to assess the release of de-identified sensitive or protected datasets on the open data portal. It requires a balancing of competing factors, such as: 

* the value of publishing the data,
* an individual’s expectation of privacy,
* repercussions to an individual or the organization from re-identification, and
* the likelihood of re-identification.

The 4 main steps are:

1. Identify sensitive or protected raw data,
2. Perform a risk assessment regarding the identifiability of the data,
3. Choose and implement privacy solutions (e.g. de-identification methods), and
4. Perform a risk assessment regarding the accessibility of the de-identified data.

[This blog post](https://datasf.org/blog/4-steps-to-manage-privacy-and-de-identification-for-your-open-data-program/) summarizes the rationale of the privacy edition nicely. You can also read more about the [toolkit on the DataSF website](https://datasf.org/resources/open-data-release-toolkit/), including accessing the full guidance and related form.

## Security edition

The security edition is for datasets that pose security (versus privacy) risks. Your data may not contain any data about individuals, but it may contain data with the following kinds of risks:

* Life / safety
* Operational
* Property
* Rights / Intellectual Property
* Reputation
* Financial

The steps in the security edition are:

1. Assess the Value of Publication
2. Assess the Risk of Publication
  1. Identify risks and impact
  2. Assess the likelihood
  3. Assign a risk rating
3. Compare the Value and Risk of publication
4. Select Risk Treatment and Controls
  1. Select risk treatment
  2. Select controls

[This blog post](https://datasf.org/blog/4-steps-to-manage-security-risks-with-open-data/) summarizes the rationale of the security edition nicely. You can also read more about the [toolkit on the DataSF website](https://datasf.org/resources/open-data-release-toolkit/), including accessing the full guidance and related form.

## Next steps from the toolkit process

At a high level, going through either edition will result in:
* A decision to publish with controls (mitigations described in each toolkit)
* A decision not to publish (only in cases where the risks cannot be properly mitigated)

A department publisher, in consultation with DataSF staff, will then incorporate mitigations into the publishing approach.

Depending on the automation assessment during [intake](/1_submission/README.md), the process moves into either [ETL Specification](/5_etl_specification/README.md) (for automation) or [Manual Publishing](/4_manual_publishing/README.md).