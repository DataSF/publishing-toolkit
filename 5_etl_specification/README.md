# ETL Specification

The ETL specification is a document collecting necessary information for developing ETL scripts ([see the template](https://docs.google.com/document/d/1Xa7enW8aOejhCTnjjRy77rb2GifmOw8zRl4WrLKTuWM/edit#heading=h.1f4qdu4un4pj)). Portions will get pre-filled based on the [intake](/1_submission/README.md).

The requirements we collect in the spec fall into two groups:

* **Data extraction requirements (Extraction).** To understand what we need to connect to and how.
* **Data output requirements (Transform and Load).** To understand what data processing needs to happen and how before it goes to the portal.

DataSF staff use [the template specification document](https://docs.google.com/document/d/1Xa7enW8aOejhCTnjjRy77rb2GifmOw8zRl4WrLKTuWM/edit#heading=h.1f4qdu4un4pj) to collect the information outlined below.

## Data extraction requirements

To implement data extraction, we need to know a couple of things:

* **Extraction method.** There are several patterns we use to accommodate different data systems. Those patterns are outlined below.
* **Publishing schedule.** We need to know a target for when the jobs should run.

### Extraction methods

Below are several patterns that are common within the City. We maintain operational flexibility (hence "Other"), but most cases can be met with one of the pre-defined patterns.

#### Connect to a read only DB view

<table>
  <tbody>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What is it</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <p>A method for connecting securely to a read only table or view generated using SQL in the database</p>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>Best suited for</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <p>Relational databases where a read only view or table can be exposed to a named user account. Examples:</p>
        <ul>
          <li>MS SQL Server</li>
          <li>MySQL</li>
          <li>Oracle</li>
          <li>Postgres</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What&rsquo;s required</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <ul>
          <li>Department data custodian works with DataSF and Department of Technology to open appropriate ports within the City&rsquo;s network</li>
          <li>Department data custodian sets up user and credentials for DataSF extraction, shares those securely with DataSF.</li>
          <li>Department data custodian and data steward work together to develop views that expose only the fields necessary for publishing to the DataSF extraction user</li>
          <li>The DataSF extraction user <strong>must have read only access</strong> to the appropriate views or tables</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### API Connection
<table>
  <tbody>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What is it</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <p>A method for connecting to any application programming interface (API) offered by a system vendor to extract data</p>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>Best suited for</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <ul>
          <li>A data system that has an available Application Programming Interface (API)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What&rsquo;s required</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <ul>
          <li>If API access requires authentication, data custodian coordinates access to the API with DataSF</li>
          <li>Data steward or custodian provide documentation about the API methods</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### Esri feature service connection
<table>
  <tbody>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What is it</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <p>A method for replicating data directly from a feature service to the open data</p>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>Best suited for</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <ul>
          <li>Geographic data available via an Esri feature service</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What&rsquo;s required</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <ul>
          <li>Department custodian shares feature service endpoint(s)</li>
          <li>If feature services are private, data custodian coordinates with DataSF to provide read only access to the necessary endpoint(s)</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### Secure FTP Drop

> **Note:** Secure FTP drops have more points of failure and can cause more disruption of service than other methods. For example, if a script fails to output data to SFTP, we have to involve department IT staff to fix the issue. In practice, if something goes wrong with the other methods, we can often resume service with minimal to zero disruption of department staff. This method should be used only in the case where all other methods are impractical or technically infeasible.

<table>
  <tbody>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What is it</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <p>A method for dropping a data extract (csv, tsv, pipe delimited file, shapefile) to a folder on the City’s secure FTP server</p>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>Best suited for</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <ul>
          <li>Legacy systems without robust access control</li>
          <li>Highly constrained data systems</li>
          <li>Geographic data stored as shapefiles, where feature services or other programmatic access is not possible</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td colspan="1" rowspan="1">
        <p><strong>What&rsquo;s required</strong></p>
      </td>
      <td colspan="1" rowspan="1">
        <ul>
          <li>DataSF sets up department folder and user account on the Department of Technology Secure FTP</li>
          <li>DataSF shares user credentials securely, access will be Read/Write and constrained to a folder. Custodian will have the ability to update the password.</li>
          <li>Department custodian writes a script to extract appropriate fields from the data system and upload them to SFTP</li>
          <li>Department custodian schedules that script to run on a schedule based on the needs of the data steward and target publishing frequency</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

#### Other

Rarely used, but if there's a special case, we'll capture it here. If we see enough of a certain pattern, we may create new options.

### Scheduling

We ask departments to give us a time to run the automated job based on when there will be minimal impact on the system.

## Data output requirements

The required data transformations and nature of the data help us in the design of automation scripts. We ask for the following:

* **Fields and definitions.** We need to know the field names and types to develop the ETL and we need to have definitions to comply with the [metadata standard](https://datasf.org/resources/metadata-standard/).
* **Transformations (if applicable).** Optionally, we need to know if there are any transformations that will be needed as this factors into the scope of the ETL development.
* **Data characteristics.** We need to understand the volume and veracity of data so we can design robust ETLs.
* **Who to notice on job success/failure.**

### Fields and definitions

We allow publishers to submit fields and definitions during intake. 
* If we don't have those by now, we collect them during the automation spec. 
* If we do have them, we just review them with the publisher to make sure nothing has changed.

We have a [standard template for collecting this information](https://datasf.org/assets/files/FieldDefinitionTemplate.xlsx) (xlsx).

### Transformations and Data Enrichment

There are a number of transformations or data enrichment options that can be applied in the process of publishing.

We provide examples on our [automation services guidance](https://datasf.org/publishing/services#toc5) for publishers and in the automation spec itself.

These include, but are not limited to:

* Convert the input field from a string to a timestamp
* Convert the input field from a string to a boolean (Y=true; N=false)
* Generate a coordinate from address field(s)
* Generate a supervisor district number based on which district boundary (or other boundaries) an address falls within
* Match a code to a predefined list of lookup definitions

We ask publishers to specify the outcome of the transformation and DataSF staff will assess feasability and approach.

We use the standard field definitions template referenced in the previous section as a starting point for producing a field definition spec. This document is used to make sure we're applying the appropriate business rules on the source data.

### Data characteristics

We ask just a handful of multiple choice questions to understand:

* The relative size of the data
* The frequency that the underlying data changes (as distinct from the targeted publishing frequency)
* How the underlying records change (do updates happen on existing records, can records be deleted, can records be created)
* Whether there's a unique identifier
* Whether the data publishing needs to lag by some time period

### Noticing

All of our jobs are designed to push notices to distribution lists on success and failure. We ask department publishers who should receive the notice. DataSF staff monitor these notices as well.

## Next steps

Once the specification is agreed upon, DataSF staff move on to [ETL Development](/6_etl_development/README.md).