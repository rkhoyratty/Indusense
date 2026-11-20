# Identity — machine.sql.txt

- Source: /Users/reshad.khoyratty/Documents/formation/solutionia/solutionai/indusense/datas/machine.sql.txt
- Filesize: 22.41 Ko
- ProcessBeginAt: 15:29:46
- ProcessEndAt: 15:29:46
- Charset: UTF8
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

| Colname | SQL Type | Infered Type | Constraints | Origin |
| ------- | -------- | ------------ | ----------- | ------ |
| machine_code | VARCHAR(16) | IDENTITY | PRIMARY KEY | INSERT |
| commissioning_date | DATE | DATE | NOT NULL | INSERT |
| max_daily_capacity | INT | INTEGER | NOT NULL, CHECK (max_daily_capacity > 0) | INSERT |
| max_hourly_capacity_pieces | INT | INTEGER | NOT NULL, CHECK (max_hourly_capacity_pieces > 0) | INSERT |
| model | VARCHAR(32) | CATEGORY | NOT NULL | INSERT |
| production_line | VARCHAR(16) | CATEGORY | NOT NULL | INSERT |
| location | VARCHAR(16) | CATEGORY | NOT NULL | INSERT |
| criticality | VARCHAR(8) | CATEGORY | NOT NULL, CHECK (criticality IN ('LOW', 'MEDIUM', 'HIGH')) | INSERT |
| is_active | BOOLEAN | BOOLEAN | NOT NULL, DEFAULT TRUE | DEFAULT (absente des INSERT) |
| created_at | TIMESTAMPTZ | DATETIME | NOT NULL, DEFAULT CURRENT_TIMESTAMP | DEFAULT (absente des INSERT) |
| updated_at | TIMESTAMPTZ | DATETIME | NOT NULL, DEFAULT CURRENT_TIMESTAMP | DEFAULT (absente des INSERT) |

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

| Colname | SQL Type | Infered Type | Constraints | Origin |
| ------- | -------- | ------------ | ----------- | ------ |
| maintenance_id | INT | IDENTITY | PRIMARY KEY | INSERT |
| machine_code | VARCHAR(16) | IDENTITY | NOT NULL, REFERENCES machine (machine_code) ON DELETE RESTRICT | INSERT |
| maintenance_at | TIMESTAMPTZ | DATETIME | NOT NULL | INSERT |
| maintenance_type | VARCHAR(16) | CATEGORY | NOT NULL, CHECK (maintenance_type IN ('proactive', 'reactive')) | INSERT |
| action_type | VARCHAR(32) | CATEGORY | NOT NULL | INSERT |
| component | VARCHAR(64) | CATEGORY | NOT NULL | INSERT |
| description | TEXT | TEXT | NOT NULL | INSERT |
| related_incident_id | VARCHAR(16) | IDENTITY | - | INSERT |
| duration_hours | DECIMAL(6, 2) | FLOAT | NOT NULL, CHECK (duration_hours > 0) | INSERT |
| created_at | TIMESTAMPTZ | DATETIME | NOT NULL, DEFAULT CURRENT_TIMESTAMP | DEFAULT (absente des INSERT) |
| updated_at | TIMESTAMPTZ | DATETIME | NOT NULL, DEFAULT CURRENT_TIMESTAMP | DEFAULT (absente des INSERT) |

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
