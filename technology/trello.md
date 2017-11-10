# Trello

![](/assets/trello_screen.png)

## What is it

Trello is a flexible platform designed to organize collaborative work and get things done.

It uses the model of boards with different lists containing cards. This was popularized by the [Kanban approach to lean process management](https://en.wikipedia.org/wiki/Kanban) which has also made it's way into product and software development.

At it's simplest, Trello provides:

1. Workspaces called boards to organize streams of work
2. Configurable lists within those boards
3. A card system \(like digital post-its\) that can be configured and commented on to support collaboration
4. Lots of plugins and enhancements to support different syles of work and integrate with popular collaboration tools

[Learn more about Trello](https://www.trello.com/).

## How does it support our process?

Trello provides the "spine" for our entire publishing process. We can take a single dataset and move it through the entire process all on a single board.

How does this work in practice:

1. Form submissions are added automatically to the Intake list in our Publishing Queue board \(we use Zapier to integrate Screendoor submissions with Trello\)
2. We work the dataset through each list, which corresponds to [one of the sub-processes we've documented](/0_publishing_process_overview/README.md)
   1. Team members can add comments and communicate via the cards
3. As we move the card through the list, metadata is captured in a Google sheet automatically \(again using Zapier\). Metadata includes:
   1. Card ID assigned by Trello
   2. Name of the dataset
   3. Publishing department
   4. Inventory ID captured during intake or added by staff if new
   5. Status of the card \(Waiting on, In Progress, Inactive, Complete\)
   6. Created date, last updated date, completed date
4. This happens until the dataset is published
5. Data collected automatically powers a [PowerBI dashboard]() to help us monitor and improve the publishing process. The PowerBI dashboard also links back to each card if more specific questions come up when the team reviews the dashboard.

### Which processes does it support?

* [Submission and Intake](1_submission/README.md)
* [Inventory Update](2_inventory/README.md)
* [Release Toolkit Review](3_release_toolkit_review/README.md)
* [Manual Publishing](4_manual_publishing/README.md)
* [ETL Specification](5_etl_specification/README.md)
* [ETL Development](6_etl_development/README.md)
* [Review and Approval](7_review_and_approval/README.md)



