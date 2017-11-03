# Publishing Process Overview

## Introduction

DataSF seeks to empower use of the City's data. Making open data available is not the only way we do this, but it is our most visible offering. Over time, we seek to increase the accessibility, discoverability, and understanding of City data.

We've designed the publishing process to balance our vision with operational realities. Specifically, there are hundreds of data systems across more than 50 departments.

We cannot apply a monolithic approach to data publishing. Instead, we apply patterns and best practices suited to our context. This involves an appropriate mix of people, technology and process within an always learning organization.

Through our processes we hope to:

1. Decrease overhead for DataSF staff and City publishers where we can
2. Ask for only what we need at the appropriate time
3. Leverage automation and work flow tools where possible
4. Maintain DataSF team transparency and collaboration on the process

## Processes

The publishing process is a set of sub-processes linked together through decision points. The sub processes are:

**[Submission and Intake](/1_submission/README.md).** The department publisher submits information to DataSF through an intake form. DataSF staff use the information provided to inform the downstream processes.

**[Inventory Update](/2_inventory/README.md).** Some reconciliation between the dataset inventory and the submission has to happen. This includes updating fields in the inventory or adding a record to the inventory if that dataset is absent.

**[Release Toolkit Review](/3_release_toolkit_review/README.md).** For protected or sensitive data, we ask departments to complete a toolkit review.

**[Manual Publishing](/4_manual_publishing/README.md).** If the dataset is more appropriate to load manually, DataSF staff provide documentation and training as needed so that the data publisher can manually load and update data.

**[ETL Specification](/5_etl_specification/README.md).** If the dataset is appropriate for automation, DataSF staff work with the data publisher to establish the best method for extraction and the desired output. This could include transformations and other automation services.

**[ETL Development](/6_etl_development/README.md).** DataSF staff implement automation for the dataset according to the specifications.

**[Review and Approval](/7_review_and_approval/README.md).** The appropriate points of contact for the dataset review and approve before publishing. This includes at least the Data Steward and may also include the Data Custodian and Data Coordinator.

### Process flow diagram

![](/assets/publishing_process.png)

### Working the process

We track these processes using a [Trello(/technology/trello.md)] board. It is composed of:

* lists for each sub-process,
* cards for each dataset moving toward publishing, 
* and labels to manage statuses (waiting on, in progress, inactive, etc.) 

This approach allows us to track our work transparently across our team and to capture data about the process so we can improve it.

![](/assets/trello_screen.png)

### The importance of unique inventory IDs

One of the principle decisions we made at the very beginning of our invententory process was to assign a unique identifier to every record. 

This ID is not tied to a particular vendor so it can float over all of our processes and systems.

We use this ID in all collateral and systems related to publishing. The ID is used:

* within the dataset inventory itself,
* as an identifier in the Trello board,
* in documents generated during the course of publishing (e.g. as part of naming conventions)

It helps us:

* loosely couple multiple systems and processes and avoid monolithic, expensive solutions,
* assure departments and DataSF staff are referring to the same thing,
* tie records together across systems and processes,
* ease in the discovery of related information about a particular dataset and it's collateral,
* ultimately, reduce overhead

While this is a relatively small, low volume system, we think leading with a data model and designing systems to be flexible is a good practice and we want to model it in our work.