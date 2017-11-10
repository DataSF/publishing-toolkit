# ETL Development

ETL Development is informed by the information collected during [ETL Specification](/5_etl_specification/README.md)

Every ETL Development involves:

1. Establishing a connection to the source data
2. Authoring a script or FME workspace
3. Testing the ETL and internal QA
4. Review and approval of ETL outputs
5. Scheduling the ETL

## Establishing a connection to the source data

Depending on the information captured in the ETL Spec, we'll make sure we can actually connect to the data before doing any additional work.

We do this because that's often a key dependency and it's best to get it out of the way as soon as possible.

The test will vary slightly, but generally:

1. **For data systems:** the department sets up read only credentials and we work with IT staff to create a secure connection between the system and publishing server.
2. **For SFTP drops:** we set up an account for the publisher where they can drop data. The account is tied to a single folder. We make sure they can successfully drop at least a sample extract.
3. **For APIs:** we make sure we can connect given the authentication parameters of the particular API.

## Authoring a script or FME workspace

Based on the requirements, we'll make an assessment of which automation tools to use.

Safe FME is a GUI-based ETL tool that provides a lot of functionality and excels at geographic transforms. It has a writer for Socrata.

However, FME can be over-engineered for certain types of jobs \(a simple sync or copy for example\). Here's the lightweight criteria we use to pick FME over scripting:

1. Is it simpler to connect to the source system using FME?
   1. Sometimes there aren't good open source alternatives for connectors, or they're not well supported
2. Will the job require complex geographic transforms?
   1. While we can do a lot with scripts, there are certain things that are a pain that FME does well with minimal configuration \(e.g. spatial transformations, geocoding against internal services\)

If we answer yes to either of these, then we'll often choose to use FME. Otherwise, we'll opt for a script.

As much as possible, we try to write scripts that are generalizable across multiple datasets, but some jobs do require bespoke approaches.

You can see our [ETL scripts on GitHub](https://github.com/search?q=topic%3Aetl+org%3ADataSF&type=Repositories).

## Testing the ETL

Once authored, an ETL will load a dataset to a private working copy within the open data portal \(Publica by Socrata\). The data is written either through the Safe FME writer which wraps Socrata's DataSync or via the Socrata publisher API.

Here we'll do checks to make sure that data is outputting according to our expectation. We'll compare the output with the documentation we have from the ETL Specification process. We'll check for:

1. Number of rows matches what we can see in the source system
2. Fields match the schema and valid ranges based on documentation and professional judgement

During the course of testing, we may identify specific things we want the steward and other reviewers to check. We'll pass those along to them as part of r[eview and approval](/7_review_and_approval/README.md).

## Review and approval

At this point we follow the steps documented under [review and approval](/7_review_and_approval/README.md).

Once approved we do one more bit of ETL development.

## Scheduling

During the ETL Specification, we capture the target publishing schedule.

FME jobs are run on FME server \(we have a staging and publishing environment\). FME allows you to schedule jobs through the administrative interface.

Scripts are run in a separate environment and are scheduled with crontab. Note: we are currently investigating the use of Airflow for scheduling and monitoring jobs.

