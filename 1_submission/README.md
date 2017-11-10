# Submission and Intake

Publishing [begins at the publishing portal](https://datasf.org/publishing).

The intake form is an embedded [Screendoor](/technology/screendoor.md) form. Submissions are automatically forwarded to our help desk where we communicate with the publisher during the course of publishing.

![](/assets/publishing_portal.png)

## Preparing submissions

Departmental publishers will complete the form on the publishing portal. The form provides inline guidance and the portal has additional deeper guidance. DataSF staff are available to help and update the guidance based on feedback or questions.

The form asks publishers to provide:

1. **Minimal dataset metadata**. If the dataset is already inventoried, the form pre-populates with the metadata already captured. We require at this point:
   1. Title
   2. Description
   3. Data classification
   4. Category
   5. Data change frequency
   6. Geographic unit
2. **System information**. On the intake form, these are multiple choice questions to help us assess publishing approaches during intake.
3. **Data/automation services desired**. We ask if the publisher will require certain types of transformations. This gives us a sense of the complexity of the job and informs publishing approach.
4. **Supporting documentation**. We ask for field definitions and [provide a template](https://datasf.org/assets/files/FieldDefinitionTemplate.xlsx) \(xls\). Publishers can also provide additional documentation aside from field definitions. These attachments are optional, but highly encouraged to save time.
5. **Points of contact**. We require publishers to identify a data steward, a data custodian and anyone else that should be involved in the publishing.

## DataSF staff assessment and next steps

After a publisher submits the form, DataSF staff review it to generate the appropriate next steps. The main questions at this point are:

* **Is it in the inventory or has the information changed?** If yes, [we update the inventory](/2_inventory/README.md).
* **Is it classified protected or sensitive?** If yes, the dataset will have to go through the [Open Data Release Toolkit Review](/3_release_toolkit_review/README.md).
* **Is it amenable to automation?** Once ready for publishing, this assessment determines if we recommend automation or manual publishing. Automation starts with an ETL Specification.

### Assessing publishing approach

Generally if any of the following are true, we will put it through our automation process:

* Data would benefit from frequent updates
* Manual updates would be overly cumbersome
* Data system is a relational database
* Data system has an API or available connector suited to automation
* Requires transforms that will enhance the value of the data

Otherwise, we'll recommend it for manual publishing.

> **Note:** there are sometimes hybrid models where extraction from a source system cannot be automated, but other aspects of publishing can. If we think any portion of the publishing would benefit from automation and the value may outweigh the cost, we'll consider it an automation candidate.
>
> In all cases we walk through our recommendation with the department. We'll either refine the approach or make a decision that manual publishing makes more sense based on new information.



