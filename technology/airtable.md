# Airtable

## What is it?

A cloud collaboration app to "organize anything." Provides the ability to create separate tables grouped into "bases." Essentially a cloud database with a very user-friendly, highly configurable set of features.

[Learn more about Airtable](https://airtable.com).

## How does it support our process?

Airtable is where we keep a set of related tables for managing aspects of our program. These tables include:

1. **Systems Inventory.** We collect systems information from departments at least annually and update records here.
2. **Dataset Inventory.** We collect dataset information from departments at least annually and update records here.
3. **Data Catalog.** We sync information about all published and unpublished datasets on the open data portal. This is used to connect records to the inventory when publishing is complete. [Syncing script we use is available in github](https://github.com/DataSF/sync-socrata-airtable).
3. **ETL Inventory.** We log all of our scripts including information about schedules, environments and dependencies.
4. **Public Issue Log.** For known issues, we log updates and resolutions so our data users are aware of them. This table syncs to the portal as well using the syncing script linked above.

A template of the Airtable base we developed [is available through Airtable Universe](https://airtable.com/universe/expdzCcK4CSOfLuhD/open-data-management)

![This image shows the dataset inventory table in DataSF's airtable base](/assets/airtable_inventory.png)

Several automations link Airtable to our process:

1. A [Zapier](https://zapier.com) task updates inventory records from publishing intake submissions and emails staff to review
2. A [script](https://github.com/DataSF/sync-socrata-airtable) syncs data from Socrata using the [Metadata API](https://github.com/DataSF/sync-socrata-airtable), [Discovery API](https://socratadiscovery.docs.apiary.io/#) and other datasets
3. The same script syncs both the inventory and issue log to the open data portal

### Which processes does it support?

Airtable is the primary system of record. It gets updated several times during our process to reflect changes in the inventory.

* [Inventory Update](2_inventory/README.md)
* [ETL Development](6_etl_development/README.md)
* [Review and Approval](7_review_and_approval/README.md)