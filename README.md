# driverversion

PowerShell script for returning the installed HP printer driver version as compact JSON, intended for Intune compliance or device inventory use.

## Requirements

- Windows with the PrintManagement cmdlets available
- At least one installed HP printer driver
- PowerShell 5.1 or later

## Usage

Run the script directly:

```powershell
powershell -ExecutionPolicy Bypass -File .\test.ps1
```

## Output

The script:

1. Filters installed printer drivers to HP-manufactured drivers.
2. Converts the packed driver version to `major.minor.build.revision`.
3. Returns a compact JSON object with the `HPUPDDriverVersion` field.

Example output:

```json
{"HPUPDDriverVersion":"7.1.0.25570"}
```

## Maintenance notes

- The current script only reports HP drivers.
- If multiple HP drivers are installed, the current output shape may contain more than one matching value.
- A future hardening pass should add explicit manufacturer parameterization and clearer handling when no matching driver is found.
