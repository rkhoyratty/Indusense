# Identity — machine.sql.txt

- Source: /Users/reshad.khoyratty/Documents/formation/solutionia/solutionai/indusense/datas/machine.sql.txt
- Filesize: 22.41 Ko
- ProcessBeginAt: 08:46:21
- ProcessEndAt: 08:46:21
- Charset: UTF8
- Column types: config/column_types/machine.yaml
- Format: SQL (postgres)
- Statements Number: 10
- Tables Number: 2
- Rows Number: 130

| Table | Rows Number | Cols Number |
| ----- | ----------- | ----------- |
| machine | 15 | 11 |
| maintenance | 115 | 11 |

## Table `machine`

- Rows Number: 15
- Cols Number: 11
- Primary key: machine_code
- Indexes: idx_machine_line (production_line); idx_machine_location (location)

### Column list

| Colname | Infered Type |
| ------- | ------------ |
| machine_code | IDENTITY |
| commissioning_date | DATE |
| max_daily_capacity | INTEGER |
| max_hourly_capacity_pieces | INTEGER |
| model | CATEGORY |
| production_line | CATEGORY |
| location | CATEGORY |
| criticality | CATEGORY |
| is_active | BOOLEAN |
| created_at | DATETIME |
| updated_at | DATETIME |

### Numeric & date columns

#### commissioning_date (DATE)

- Col name: commissioning_date
- Min value: 2019-07-23
- Max value: 2025-05-25

#### max_daily_capacity (INTEGER)

- Col name: max_daily_capacity
- Min value: 750
- Max value: 1428
- Mean value: 1054.867
- Median value: 1027.000

#### max_hourly_capacity_pieces (INTEGER)

- Col name: max_hourly_capacity_pieces
- Min value: 47
- Max value: 89
- Mean value: 65.867
- Median value: 64.000

## Table `maintenance`

- Rows Number: 115
- Cols Number: 11
- Primary key: maintenance_id
- Indexes: idx_maintenance_machine_time (machine_code, maintenance_at); idx_maintenance_type (maintenance_type)

### Column list

| Colname | Infered Type |
| ------- | ------------ |
| maintenance_id | IDENTITY |
| machine_code | IDENTITY |
| maintenance_at | DATETIME |
| maintenance_type | CATEGORY |
| action_type | CATEGORY |
| component | CATEGORY |
| description | TEXT |
| related_incident_id | IDENTITY |
| duration_hours | FLOAT |
| created_at | DATETIME |
| updated_at | DATETIME |

### Numeric & date columns

#### maintenance_at (DATETIME)

- Col name: maintenance_at
- Min value: 2025-06-15 06:00:00
- Max value: 2026-05-30 22:00:00

#### duration_hours (FLOAT)

- Col name: duration_hours
- Min value: 1.000
- Max value: 8.000
- Mean value: 2.943
- Median value: 2.640
