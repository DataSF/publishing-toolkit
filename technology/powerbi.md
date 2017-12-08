# Power BI

![Screenshot of our PowerBI report used to monitor the publishing process](/assets/powerbi_screen.png)
PowerBI let's us quickly see where we are in the publishing process and helps us identify opportunities for process improvements.

## What is it

A business intelligence platform from Microsoft. Connects to a variety of sources and provides tools for quickly generating dashboards, visuals and reports.

[Learn more about Power BI](https://powerbi.microsoft.com).

## How does it support our process?

We use a Power BI report to monitor our publishing process at a high level. Typically, our team logs into the dashboard at our weekly meeting to review and discuss our publishing queue, which is a standing agenda item. The dashboard links to our Trello board so if we have questions about a specific dataset we can pull up the Trello card easily.

We continue to iterate on the report and related dashboards, but it helps us answer questions like:

1. How many datasets did we publish in the last quarter?
2. What datasets are aging \(have been in the queue for a long time\)?
3. Which publishers/departments are we waiting on?
4. Where in the process do we have the most activity right now \(e.g. waiting on versus in ETL development\)?
5. On average, how long does it take for a job to complete?

The data that feeds the dashboard includes:

1. [Trello](/technology/trello.md) data \(captured in a google sheet\)
2. [The dataset inventory](https://data.sfgov.org/City-Management-and-Ethics/Dataset-inventory/y8fp-fbf5)
3. [The published data catalog](https://data.sfgov.org/City-Management-and-Ethics/Published-data-and-views/g9d8-sczp)
4. [Desk](/technology/desk.md) case logs

Data is joined together through the inventory IDs, publishing IDs and Trello card IDs.

### Which processes does it support?

It helps us measure and monitor all processes and is a complement to Trello. While Trello lets us see where things are now quickly and in detail. Power BI lets us roll up stats about the process.

* [Submission and Intake](1_submission/README.md)
* [Release Toolkit Review](3_release_toolkit_review/README.md)
* [Manual Publishing](4_manual_publishing/README.md)
* [ETL Specification](5_etl_specification/README.md)
* [Review and Approval](7_review_and_approval/README.md)



