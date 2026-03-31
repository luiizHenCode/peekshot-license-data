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

---

### Remote Config

App configuration (updates, promotions, feature flags, messages) is available at:

```
https://raw.githubusercontent.com/luiizHenCode/peekshot-license-data/main/config/remote-config.json
```

#### Schema

```json
{
  "version": 1,
  "updated_at": "<ISO 8601 timestamp>",

  "updates": {
    "latest_version": "<semver>",
    "minimum_supported_version": "<semver>",
    "download_url": "<url>",
    "force_update": false,
    "show_update_banner": true
  },

  "promotion": {
    "enabled": true,
    "title": "<string>",
    "discount_percent": 0,
    "coupon_code": "<string>",
    "valid_until": "<ISO 8601 timestamp>"
  },

  "feature_flags": {
    "qr_code_enabled": true,
    "ocr_enabled": true,
    "imgur_upload_enabled": true,
    "iphone_clipboard_capture_enabled": true,
    "local_backup_enabled": true
  },

  "messages": {
    "global_banner": "<string>",
    "paywall_note": "<string>"
  }
}
```

| Field                                          | Type      | Description                                            |
|------------------------------------------------|-----------|--------------------------------------------------------|
| `version`                                      | `number`  | Schema version                                         |
| `updated_at`                                   | `string`  | ISO 8601 timestamp of the last update                  |
| `updates.latest_version`                       | `string`  | Latest available app version                           |
| `updates.minimum_supported_version`            | `string`  | Oldest version still supported                         |
| `updates.download_url`                         | `string`  | URL to download the latest build                       |
| `updates.force_update`                         | `boolean` | Whether users must update before continuing            |
| `updates.show_update_banner`                   | `boolean` | Whether to show an update banner in the app            |
| `promotion.enabled`                            | `boolean` | Whether a promotion is currently active                |
| `promotion.title`                              | `string`  | Display title for the promotion                        |
| `promotion.discount_percent`                   | `number`  | Discount percentage                                    |
| `promotion.coupon_code`                        | `string`  | Coupon code to apply                                   |
| `promotion.valid_until`                        | `string`  | ISO 8601 expiry timestamp for the promotion            |
| `feature_flags.qr_code_enabled`               | `boolean` | Enable QR code feature                                 |
| `feature_flags.ocr_enabled`                   | `boolean` | Enable OCR feature                                     |
| `feature_flags.imgur_upload_enabled`          | `boolean` | Enable Imgur upload feature                            |
| `feature_flags.iphone_clipboard_capture_enabled` | `boolean` | Enable iPhone clipboard capture feature             |
| `feature_flags.local_backup_enabled`          | `boolean` | Enable local backup feature                            |
| `messages.global_banner`                       | `string`  | Banner message shown globally in the app               |
| `messages.paywall_note`                        | `string`  | Note shown on the paywall screen                       |
