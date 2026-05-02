# Let's go bananas!
Let’s Go Bananas is a data-driven experiment to grow a backyard “jungle” from three pseudostems. I use OLTP logging and a relational database to track growth, environment, and results over time.

---

## Concept
This project treats plant growth as a structured data problem rather than casual observations. Changes in the plants are logged over time to allow reliable analysis of what worked and what didn't. 

The system follows an OLTP-first approach, focusing on accurate operational data collection before introducing an analytical investigation once enough data has been gathered. 

---

## Data Model (ERD)
A normalized relational database is used to support time-based tracking of plant growth, care actions, experiments, and environmental conditions.

Tables:
   - plants → static plant metadata
   - size → time-series growth measurements
   - care → logged maintenance actions (watering, fertilizing, etc.)
   - care_catalogue → standardized care types
   - experiment / experiment_log → structured hypothesis tracking
   - weather → environmental conditions over time

Key Design Principles:
   - Static and dynamic data are separated to keep the schema clean and scalable.
   - A composite key (plant_id + measurement_date) ensures one measurement per plant per day and prevents duplicate entries in time-series data.
   - Event-based logging for care and experiments
   - External environmental factors tracked to later support a correlation analysis
   - The schema is normalized to reduce duplication and maintain query consistency
   - Categorical fields such as experiment status are constrained to predefined values to ensure data integrity.

--- 

## Tools
   - DBML (schema design)
   - dbdiagram.io (ERD modeling)
   - PostgreSQL (SQL-based relational database)
   - PGAdmin (database management)
   - Git and GitHub (version control)
   - (future) Tableau (data visualization)

---

## Goal
The aim is to explore how structured data tracking can be applied to real-world biological growth while running small experiments around fertilization, care routines, and environmental conditions.

By consistently logging changes over time, the system is used to observe how different variables influence banana plant growth and to identify more effective care strategies.
