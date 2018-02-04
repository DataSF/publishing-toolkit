# Review and Approval

This is the final phase where department reviewers make sure everything is ready for publishing.

While DataSF staff do internal QA, we still like to make sure the subject matter experts give a close look before publishing. 

Also, we **never** publish data without approval from a department publisher.

During [intake](/1_submission/README.md), the publisher identified the data steward, data custodian and any other reviewers. We share a private dataset with them and ask to check a handful of things:

1. Metadata completeness and accuracy including the data dictionary
2. Whether the data schema matches their expectation
3. Whether the rows represent the data according to their expectation
4. Whether there are the right number of rows

If they have any changes, we'll go through a loop to make the adjustments necessary and follow up to review.

If everything looks good, we make the dataset public and register the dataset as published in the Department's inventory.

If the job is automated, we'll [do one last bit to schedule it](/6_etl_development/README.md#scheduling).

DataSF staff finally link the published dataset to the inventory by connecting records in Airtable. A script will sync Airtable with the public inventory to reflect the publishing status and link to the dataset in the inventory by the next day. 

![Animation showing how published records are linked in the inventory](/assets/airtable_link.gif)