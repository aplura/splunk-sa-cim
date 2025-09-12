# Aplura Tracked Changes by version.

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

## Version 6.1.0

### All Data Models

- Added `cim_entity_zone` field
  - `This field is automatically provided by asset and identity correlation features of applications like Splunk Enterprise Security. Do not define extractions for this field when writing add-ons.`

### Authentication Data Model

- Added `process` field
  - `Full path and the name of the executable for the process that attempted the logon. For example, it is a "Process Name" in Windows such as 'C:\Windows\System32\svchost.exe'.`
- Added `reason_id` field
  - `The reason why logon failed. For example "0xC0000234".`

### Change Data Model

- Removed expected values from field `change_type`

### DLP Data Model

- Updated eval expression for field `category`

### Endpoint Data Model

- Added `image` field to `Registry and Filesystem` dataset.
  - `The binary file path or name that is tied to a process ID (PID) in events like process creation or termination.`

### Network Traffic Data Model

- Added `rule_id` field
  - `The vendor-specific unique identifier of the rule. Examples: 0x00011f0000011f00, 0x00011f00-syn_flood.`

### WEB Data Model

- Updated rex expression for field `url_domain`

