# LinkedIn Job Data Analysis and Recommendation System

This project implements an end-to-end system for analyzing LinkedIn job data, providing job recommendations, and offering resume customization suggestions. The system processes job postings data from LinkedIn, transforms it through a modern data stack, and enables data-driven insights for job seekers.

## System Architecture

The project consists of several components:

1. **Data Ingestion & Storage**
   - LinkedIn job data stored in S3 as JSON files
   - Snowflake as the data warehouse
   - Airflow for orchestration

2. **Data Processing & Modeling**
   - dbt for data transformation and modeling
   - Staging models for initial data cleaning
   - Core models implementing dimensional modeling
   - Bridge tables for many-to-many relationships

3. **Data Flow**
   ```
   S3 JSON Files → Snowflake RAW → dbt Staging → dbt Core Models → BI/Visualization
   ```

4. **Key Data Models**
   - Dimension Tables:
     - Companies
     - Locations
     - Job Types
     - Experience Levels
     - Job Skills
   - Fact Tables:
     - Job Postings
   - Bridge Tables:
     - Job Skills Bridge

## Team Contributions

### Jasper's Role
- **Data Modeling & Transformation**
  - Implemented dbt models for data transformation
  - Created staging models for data cleaning and standardization
  - Developed core dimensional models for business analytics
  - Designed and implemented bridge tables for many-to-many relationships
  - Created data flow documentation using Mermaid diagrams

- **Data Quality & Testing**
  - Implemented data quality tests in dbt
  - Created test cases for data integrity
  - Developed data validation rules

- **Documentation**
  - Maintained dbt project documentation
  - Created data model documentation
  - Documented data transformation logic

## Repositories
- **Orchestration:** [samrere-Data15Group3-Orchestration](https://github.com/samrere/samrere-Data15Group3-Orchestration)
- **MWAA Airflow Web UI:** [Airflow Web UI](https://c2437eca-32dd-4ade-b665-8b1d4b4a7bb5.c0.ap-southeast-2.airflow.amazonaws.com)
- **Data Modeling:** [datagroup-dbt](https://github.com/datagroup-dbt/datagroup-dbt)
- **RAG:** [Data15Group3-RAG](https://github.com/samrere/Data15Group3-RAG)

## Development Standards

### Branching
Use the following naming convention for branches:
```
[prefix]/[ticket-number]-[task-name]
```
**Examples:**
- `feat/CP-32-add-user-login-page`
- `fix/CP-35-fix-new-user-registration-error`

### Commits
Each pull request should contain only one commit. Commit messages must follow this pattern:
```
[prefix]: [task name]

[task description]

Resolve [ticket-number]
```
**Example:**
```
feat: add user registration page

Added (static) user registration page:
- implemented registration form;
- implemented registration page as per UI;
- added unit tests for registration page and related components.

Resolve CP-32
```

