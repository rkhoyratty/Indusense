# Identity — releves_incidents.csv

- Source: /Users/reshad.khoyratty/Documents/formation/solutionia/solutionai/indusense/datas/releves_incidents.csv
- Filesize: 134.64 Ko
- ProcessBeginAt: 08:46:21
- ProcessEndAt: 08:46:21
- Charset: UTF8
- Column types: config/column_types/releves_incidents.yaml
- Separator: virgule (,)
- Rows Number: 1245
- Cols Number: 18

## Column list

| Colname | Infered Type |
| ------- | ------------ |
| incident_id | IDENTITY |
| date | DATE |
| time | TIME |
| operator_name | CATEGORY |
| machine_id | IDENTITY |
| severity | INTEGER |
| operator_badge | IDENTITY |
| comment | TEXT |
| shift | CATEGORY |
| type_surchauffe | BOOLEAN |
| type_baisse_pression | BOOLEAN |
| type_vibration | BOOLEAN |
| type_bruit_mecanique | BOOLEAN |
| type_surconsommation | BOOLEAN |
| type_blocage_mecanique | BOOLEAN |
| type_alarme_capteur | BOOLEAN |
| type_arret_urgence | BOOLEAN |
| type_defaut_qualite | BOOLEAN |

## Numeric & date columns

### date (DATE)

- Col name: date
- Min value: 2025-06-01
- Max value: 2026-06-08

### time (TIME)

- Col name: time
- Min value: 00:06:00
- Max value: 23:55:00

### severity (INTEGER)

- Col name: severity
- Min value: 2
- Max value: 5
- Mean value: 2.925
- Median value: 3.000
