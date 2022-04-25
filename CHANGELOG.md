# Release Notes
Change notes summarizing adopted changes between versioning events.

----------------------------------------

## [v2.0.0 (2022-04-25)](https://github.com/conflabs/wcia-transfer-data-schema/tree/v2.0.0), [Version Diff](https://github.com/conflabs/wcia-transfer-data-schema/compare/v1.3.0...v2.0.0)
- `document_schema_version` bump to 2.0.0
- `external_id` renamed to `integrator_data`; a field for integrator-specific use.
- `serving_weight` field added to represent units per serving. This is an optional field.

## [v1.3.0 (2022-02-28)](https://github.com/conflabs/wcia-transfer-data-schema/tree/v1.3.0), [Version Diff](https://github.com/conflabs/wcia-transfer-data-schema/compare/v1.2.0...v1.3.0)  
- `document_schema_version` bump to 1.3.0
- `document_origin` field in the root object as a canonical (self) referencing URL value.

## [v1.2.0 (2022-01-21)](https://github.com/conflabs/wcia-transfer-data-schema/tree/v1.2.0), [Version Diff](https://github.com/conflabs/wcia-transfer-data-schema/compare/v1.1.0...v1.2.0)  
- `document_schema_version` bump to 1.2.0

## [v1.1.0 (2022-01-07)](https://github.com/conflabs/wcia-transfer-data-schema/tree/v1.1.0), [Version Diff](https://github.com/conflabs/wcia-transfer-data-schema/compare/v1.0.0...v1.1.0)  
- `document_schema_version` bump to 1.1.0
- `sample_type` field in the `inventory_transfer_times` array objects. With Enums.
- `line_price` field  in the `inventory_transfer_times` array objects.
- Removed deprecated field `product_price`

## [v1.0.0 (2021-12-06)](https://github.com/conflabs/wcia-transfer-data-schema/tree/v1.0.0)
- Initial schema, produced by the Technical Committee.
- Docs
- License
- Change Log
