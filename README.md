# Splunk_SA_CIM Tracking

This repo contains changes for Splunk_SA_CIM.

## Field Types

- Lookup
    - Provided to the data model via Lookup, other automatic method on the sourcetypes (assets and identities, etc)
- Calculated
    - `eval` calculation
- Passed
    - Extracted prior to the data model, and passed into the model from a previous extraction

## Version 8.5.0

- Front End Changes in `cim_setup.js`

### alert_actions.conf

- Content Removed (empty file)

### Other conf file updates

- `commands.conf`, `inputs.conf`, `restmap.conf`
    - Added `python.required` flag for Splunk 10.2+

### Python Changes

- base_modinput.py
    - added `python.required` validation exception
- cim_actions.py
    - Added new CSV Sanitized Reader Method

### Change Data Model

- Removed Constraint `NOT (object_category=file OR object_category=directory OR object_category=registry)`

| Field     | Type     | Required | Change Type | Field Type | Change                  |
|-----------|----------|----------|-------------|------------|-------------------------|
| `results` | `string` | No       | Modified    |            | Removed expected values |

### Endpoint Data Model

| Field | Type | Required | Change Type | Field Type | Change |
|-------|------|----------|-------------|------------|--------|

### Intrusion Detection Data Model

| Field     | Type     | Required | Change Type | Field Type | Change |
|-----------|----------|----------|-------------|------------|--------|
| `src_ip`  | `string` | No       | New         | Passed     |        |
| `dest_ip` | `string` | No       | New         | Passed     |        | 

### Malware Data Model

| Field     | Type     | Required | Change Type | Field Type | Change                                     |
|-----------|----------|----------|-------------|------------|--------------------------------------------|
| `src_ip`  | `string` | No       | New         | Passed     |                                            |
| `dest_ip` | `string` | No       | New         | Passed     | `Malware_Attacks` and `Malware_Operations` | 

### Network Resolution Data Model

| Field     | Type     | Required | Change Type | Field Type | Change |
|-----------|----------|----------|-------------|------------|--------|
| `src_ip`  | `string` | No       | New         | Passed     |        |
| `dest_ip` | `string` | No       | New         | Passed     |        | 

### Web Data Model

| Field     | Type     | Required | Change Type | Field Type | Change |
|-----------|----------|----------|-------------|------------|--------|
| `src_ip`  | `string` | No       | New         | Passed     |        |
| `dest_ip` | `string` | No       | New         | Passed     |        | 

## Version 6.4.0

- Front End Changes in `cim_setup.js`

### Data Access Data Model

| Field        | Type       | Required | Change Type | Field Type | Change |
|--------------|------------|----------|-------------|------------|--------|
| `dest_bunit` | `<string>` | No       | New         | Lookup     |        |
| `dvc_bunit`  | `<string>` | No       | New         | Lookup     |        |
| `src_bunit`  | `<string>` | No       | New         | Lookup     |        |
| `user_bunit` | `<string>` | No       | New         | Lookup     |        |

### Endpoint Data Model

| Field         | Type       | Required | Change Type  | Field Type | Change               |
|---------------|------------|----------|--------------|------------|----------------------|
| `parent_user` | `<string>` | No       | New          | Calculated |                      |
| `user`        |            |          | Modification |            | Description Modified |

### Network Sessions Data Model

| Field | Type       | Required | Change Type | Field Type | Change |
|-------|------------|----------|-------------|------------|--------|
| `dvc` | `<string>` | No       | New         | Calculated |        |

### Network Traffic Data Model

| Field          | Type       | Required | Change Type | Field Type | Change |
|----------------|------------|----------|-------------|------------|--------|
| `process_guid` | `<string>` | No       | New         | Passed     |        |

## Version 6.3.0

- Front End Changes in `cim_setup.js`

### Authentication Data Model

- Added `result` field, with null default.
- Updated `Failed_Authentication` model with additional OR for `result`
- Updated `Successful_Authentication` model with additional OR for `result`

### Change Data Model

- Added expected values for `object_category`

### Endpoint Data Model

- Added expected values for `process_integrity_level`

## Version 6.2.0

- Front End Changes in `cim_setup.js`

### Data Access Data Model

- Added field `dest_type`
- Moved `signature` from `required -> recommended`

### Endpoint Data Model

- Simplified eval for fields `parent_process_name`, `process_name`
- Added expected value `installed` for field `status`

### Intrusion Detection Data Model

- Added field `dest_type`

### Updates Data Model

- Changed `file_name` to multivalue

## v6.1.0

Base Install.