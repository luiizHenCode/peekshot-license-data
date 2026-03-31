# peekshot-license-data

Public repository for Peekshot license data, served directly via raw GitHub URLs.

## Data

### Revoked Licenses

A list of revoked license keys is available at:

```
https://raw.githubusercontent.com/luiizHenCode/peekshot-license-data/main/data/v1/revoked.json
```

#### Schema

```json
{
  "version": 1,
  "updated_at": "<ISO 8601 timestamp>",
  "revoked": [
    "<license-key-1>",
    "<license-key-2>"
  ]
}
```

| Field        | Type            | Description                                      |
|--------------|-----------------|--------------------------------------------------|
| `version`    | `number`        | Schema version                                   |
| `updated_at` | `string`        | ISO 8601 timestamp of the last update            |
| `revoked`    | `string[]`      | Array of revoked license key strings             |
