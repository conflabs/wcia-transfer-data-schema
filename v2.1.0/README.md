# wcia-transfer-data-schema
Version control repository for the [Washington Cannabis Integrator's Alliance](https://www.cannabisintegratorsalliance.com/) Transfer Data Schema.
[https://www.cannabisintegratorsalliance.com/](https://www.cannabisintegratorsalliance.com/)

### Version 2.1.0

----------------------------------------

## Transfer Data Schema

* Transfer Data Schema Object [(WCIATransferDataSchema.json)](WCIATransferDataSchema.json)

## Table of Contents

* Legend
* Fields Guide
* Resources

## Legend

```text
Ln #  Schema
----  --------------------------------------
1.     {
2.       "document_name": "string",
3.       "document_schema_version": "string",
4.       "document_origin": "string",
5.       "from_license_number": "string",
6.       "from_license_name": "string",
7.       "to_license_number": "string",
8.       "to_license_name": "string",
9.       "to_license_type": "string",
10.      "transporter_name": "string",
11.      "transporter_license": "string",
12.      "manifest_type": "enum['delivery', 'pick-up', 'transporter']",
13.      "created_at": "string[ISO8601 datetime]",
14.      "updated_at": "string[ISO8601 datetime]",
15.      "transferred_at": "string[ISO8601 datetime]",
16.      "integrator_data": "string",
17.      "transfer_id": "string",
18.      "est_departed_at": "string[ISO8601 datetime]",
19.      "est_arrival_at": "string[ISO8601 datetime]",
20.      "route": "string",
21.      "inventory_transfer_items": [
22.        {
23.          "created_at": "string['ISO datetime']",
24.          "updated_at": "string['ISO datetime']",
25.          "external_id": "string",
26.          "is_sample": "bool['0', '1']",
27.          "sample_type": "enum['null', 'educational', 'qa', 'non-mandatory qa', 'vendor']",
28.          "product_name": "string",
29.          "qty": "numeric",
30.          "unit_weight": "float|decimal",
31.          "serving_weight": "float|decimal[OPTIONAL]",
32.          "line_price": "string['currency']",
33.          "uom": "enum['ml', 'mg', 'g', 'oz', 'lb', 'ea', 'kg']",
34.          "unit_weight_uom": "enum['ml', 'mg', 'g', 'oz', 'lb', 'ea', 'kg']",
35.          "inventory_id": "string",
36.          "sample_source_id": "string",
37.          "is_medical": "bool['0', '1']",
38.          "is_for_extraction": "bool['0', '1']",
39.          "lab_result_passed": "enum['null', 'pass', 'fail']",
40.          "lab_result_link": "string[URI]",
41.          "lab_result_data": {
42.            "lab_result_id": "",
43.            "lab_result_status": "enum['pass', 'fail']",
44.            "lab_result_detail": "string[URI]",
45.            "coa": "string[URI]",
46.            "lab_result_list": [
47.              {
48.                "coa": "string[URI]",
49.                "lab_result_id: "string",
50.                "lab_result_status: "pass" or "fail",
51.                "lab_result_link": "NULL | string[URI]",
52.                "coa_release_date": "string", //ISO8601 Date Only
53.                "coa_amended_date": "NULL | string", //ISO8601 Date Only
54.                "coa_expire_date": "NULL | string" //ISO8601 Date Only
55.              }
56.            ],
57.            "potency": [
58.              {
59.                "type":"string",
60.                "value": "float|decimal",
61.                "unit": "enum['ml', 'mg', 'g', 'oz', 'lb', 'ea', 'kg']"
62.              }
63.            ]
64.        },
65.        "inventory_category": "string",
66.        "inventory_type": "string",
67.        "strain_name": "string",
68.        "product_sku": "string"
69.        }
70.      ]
71.    }
```

# Fields Guide

----------------------------------------

## Document Name
* _Field Name:_ **document_name**
* _Type:_ **string**
* _Description:_
  * The "title" of the document, always displaying "WCIA Transfer Data Schema".
* _Legend:_ **Ln 2**

----------------------------------------

## Document Schema Version
* _Field Name:_ **document_schema_version**
* _Type:_ **string**
* _Description:_
  * The version of WCIA Transfer Data Schema used for the object.
* _Legend:_ **Ln 3**

----------------------------------------

## Document Origin
* _Field Name:_ **document_origin**
* _Type:_ **string**
* _Description:_
  * A URL referencing the document's originating source.
* _Legend:_ **Ln 4**

----------------------------------------

# From License Number

* _Field Name:_ **from_license_number**
* _Type:_ **string**
* _Description:_
  * License number of the entity submitting the transfer.
* _Legend:_ **Ln 5**

----------------------------------------

# From License Name

* _Field Name:_ **from_license_name**
* _Type:_ **string**
* _Description:_
  * Business name of the entity submitting the transfer.
* _Legend:_ **Ln 6**

----------------------------------------

# To License Number

* _Field Name:_ **to_license_number**
* _Type:_ **string**
* _Description:_
  * License number of the entity receiving the transfer.
* _Legend:_ **Ln 7**

----------------------------------------

# To License Name

* _Field Name:_ **to_license_name**
* _Type:_ **string**
* _Description:_
  * Business name of the entity receiving the transfer.
* _Legend:_ **Ln 8**

----------------------------------------

# To License Type (_optional_)

* _Field Name:_ **to_license_type**
* _Type:_ **string**
* _Description:_
  * Optional field. This could be "producer," "processor," etc.
* _Legend:_ **Ln 9**

----------------------------------------

# Transporter Name

* _Field Name:_ **transporter_name**
* _Type:_ **string**
* _Description:_
  * Name of the representative physically transporting the transfer's material contents.
* _Legend:_ **Ln 10**

----------------------------------------

# Transporter License

* _Field Name:_ **transporter_license**
* _Type:_ **string**
* _Description:_
  * State issued license number.
* _Legend:_ **Ln 11**

----------------------------------------

# Manifest Type

* _Field Name:_ **manifest_type**
* _Type:_ **enum['delivery', 'pick-up', 'transporter']**
* _Description:_
  * An enum field. The options are "delivery," "pick-up," or "transporter"
* _Legend:_ **Ln 12**

----------------------------------------

# Created At

* _Field Name:_ **created_at**
* _Type:_ **string[ISO8601 datetime]**
* _Description:_
  * An ISO8601 DateTime stamp of transfer creation.
* _Legend:_ **Ln 13**

----------------------------------------

# Updated At

* _Field Name:_ **updated_at**
* _Type:_ **string[ISO8601 datetime]**
* _Description:_
  * An ISO8601 DateTime stamp of transfer update.
* _Legend:_ **Ln 14**

----------------------------------------

# Transferred At (_optional_)

* _Field Name:_ **transferred_at**
* _Type:_ **string[ISO8601 datetime]**
* _Description:_
  * Optional field. An ISO8601 DateTime stamp of the actual transfer datetime.
* _Legend:_ **Ln 15**

----------------------------------------

# Integrator Data

* _Field Name:_ **integrator_data**
* _Type:_ **string**
* _Description:_
  * A designated string for dynamic data that is integrator specific.
* _Legend:_ **Ln 16**

----------------------------------------

# Transfer ID

* _Field Name:_ **transfer_id**
* _Type:_ **string**
* _Description:_
  * A sender-assigned identifier representing the transfer object.
* _Legend:_ **Ln 17**

----------------------------------------

# Estimated Departed At

* _Field Name:_ **est_departed_at**
* _Type:_ **string[ISO8601 datetime]**
* _Description:_
  * An ISO8601 DateTime stamp of estimated transport departure.
* _Legend:_ **Ln 18**

----------------------------------------

# Estimated Arrival At

* _Field Name:_ **est_arrival_at**
* _Type:_ **string[ISO8601 datetime]**
* _Description:_
  * An ISO8601 DateTime stamp of estimated transport arrival.
* _Legend:_ **Ln 19**

----------------------------------------

# Route (_optional_)

* _Field Name:_ **route**
* _Type:_ **string**
* _Description:_
  * Optional field. A text string providing basic transport route information between the sending and receving entities.
* _Legend:_ **Ln 20**

----------------------------------------

# Inventory Transfer Items

* _Field Name:_ **inventory_transfer_items**
* _Type:_ **array**
* _Description:_
  * An array of transfer item objects.
* _Legend:**_ **Ln 21****

----------------------------------------

## Inventory Transfer Items -> Created At

* _Field Name:_ **created_at**
* _Type:_ **string['ISO datetime']**
* _Description:_
  * An ISO8601 DateTime stamp of inventory transfer item creation.
* _Legend:_ **Ln 23**

----------------------------------------

## Inventory Transfer Items -> Updated At

* _Field Name:_ **updated_at**
* _Type:_ **string['ISO datetime']**
* _Description:_
  * An ISO8601 DateTime stamp of inventory transfer item update.
* _Legend:_ **Ln 24**

----------------------------------------

## Inventory Transfer Items -> External Id (_optional_)

* _Field Name:_ **external_id**
* _Type:_ **string**
* _Description:_
  * Optional field. A vendor system identifier.
* _Legend:_ **Ln 25**

----------------------------------------

## Inventory Transfer Items -> Is Sample

* _Field Name:_ **is_sample**
* _Type:_ **bool['0', '1']**
* _Description:_
  * A boolean string: zero for false, and one for true.
* _Legend:_ **Ln 26**

----------------------------------------

## Inventory Transfer Items -> Sample Type

* _Field Name:_ **sample_type**
* _Type:_ **enum['null', 'educational', 'qa', 'non-mandatory qa', 'vendor']**
* _Description:_
  * Designates the transfer item's types as informed by the WAC. The options are "null," "educational," "qa," "non-mandatory qa," and "vendor."
* _Legend:_ **Ln 27**

----------------------------------------

## Inventory Transfer Items -> Product Name

* _Field Name:_ **product_name**
* _Type:_ **string**
* _Description:_
  * A licensee-assigned name for the transferring item.
* _Legend:_ **Ln 28**

----------------------------------------

## Inventory Transfer Items -> Qty

* _Field Name:_ **qty**
* _Type:_ **string['float|decimal']**
* _Description:_
  * A string formatted as a float|decimal, representing the contents of a package. 
* _Legend:_ **Ln 29**

----------------------------------------

## Inventory Transfer Items -> Unit Weight

* _Field Name:_ **unit_weight**
* _Type:_ **string['float|decimal']**
* _Description:_
  * A string formatted as a float|decimal, representing the weight of a single unit.
* _Legend:_ **Ln 30**

----------------------------------------

## Inventory Transfer Items -> Unit Weight (_optional_)

* _Field Name:_ **serving_weight**
* _Type:_ **string['float|decimal']**
* _Description:_
  * A string formatted as a float|decimal, representing the units per serving.
* _Legend:_ **Ln 31**

----------------------------------------

## Inventory Transfer Items -> Line Price

* _Field Name:_ **line_price**
* _Type:_ **string['currency']**
* _Description:_
  * A string formatted as currency, representing the line total. This figure is calculated as `quantity * unit_price`
* _Legend:_ **Ln 321**

----------------------------------------

## Inventory Transfer Items -> UoM

* _Field Name:_ **uom**
* _Type:_ **enum['ml', 'mg', 'g', 'oz', 'lb', 'ea', 'kg']**
* _Description:_
  * An enum field representing one of the following possible meausre abbreviations: 'ml,' 'mg,' 'g,' 'oz,' 'lb,' 'ea,' 'kg.' 
    This value provides the standardized unit by which the item was measured.
* _Legend:_ **Ln 33**

----------------------------------------

## Inventory Transfer Items -> Unit Weight UoM

* _Field Name:_ **unit_weight_uom**
* _Type:_ **enum['ml', 'mg', 'g', 'oz', 'lb', 'ea', 'kg']**
* _Description:_
  * An enum field representing one of the following possible meausre abbreviations: 'ml,' 'mg,' 'g,' 'oz,' 'lb,' 'ea,' 'kg.'
    This value represents the "each" version of the UoM field.
* _Legend:_ **Ln 34**

----------------------------------------

## Inventory Transfer Items -> Inventory ID

* _Field Name:_ **inventory_id**
* _Type:_ **string**
* _Description:_
  * A vendor system assigned unique identifier representing the inventory from which the items were sampled.
* _Legend:_ **Ln 35**

----------------------------------------

## Inventory Transfer Items -> Sample Source ID

* _Field Name:_ **sample_source_id**
* _Type:_ **string**
* _Description:_
  * A vendor system assigned unique identifier representing the source inventory from which the items were sampled.
* _Legend:_ **Ln 36**

----------------------------------------

## Inventory Transfer Items -> Is Medical

* _Field Name:_ **is_medical**
* _Type:_ **bool['0', '1']**
* _Description:_
  * A boolean string: zero for false, and one for true. This field flags a transfer item as having medical requirements.
* _Legend:_ **Ln 37**

----------------------------------------

## Inventory Transfer Items -> Is for Extraction

* _Field Name:_ **is_for_extraction**
* _Type:_ **bool['0', '1']**
* _Description:_
  * A boolean string: zero for false, and one for true. This field flags a transfer item as designated for extraction.
* _Legend:_ **Ln 38**

----------------------------------------

## Inventory Transfer Items -> Lab Result Passed

* _Field Name:_ **lab_result_passed**
* _Type:_ **enum['null', 'pass', 'fail']**
* _Description:_
  * An enum field representing the pass/fail status of the lab result for this item. Options are null, "pass," and "fail."
* _Legend:_ **Ln 39**

----------------------------------------

## Inventory Transfer Items -> Lab Result Link

* _Field Name:_ **lab_result_link**
* _Type:_ **string[URI]**
* _Description:_
  * A link to the laboratory Certificate of Analysis.
* _Legend:_ **Ln 40**

----------------------------------------

## Inventory Transfer Items -> Lab Result Data

* _Field Name:_ **lab_result_data**
* _Type:_ **object['nullable']**
* _Description:_
  * 
* _Legend:_ **Ln 41**

### Inventory Transfer Items -> Lab Result Data -> Lab Result ID

* _Field Name:_ **Lab_result_id** 
* _Type:_ ****
* _Description:_
  * The result ID assigned by the laboratory.
* _Legend:_ **Ln 42**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result Status

* _Field Name:_ **Lab_result_status**
* _Type:_ **enum['null', 'pass', 'fail']**
* _Description:_
  * An enum field representing the pass/fail status of the lab result for this item. Options are null, "pass," and "fail."
* _Legend:_ **Ln 43**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab_result_detail

* _Field Name:_ **Lab_result_detail**
* _Type:_ **string['URI']**
* _Description:_
  * A URL to the WCIA Lab Result Link.
* _Legend:_ **Ln 44**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> CoA

* _Field Name:_ **Coa**
* _Type:_ **string['URI']**
* _Description:_
  * A URL to the Lab result Certificate of Analysis.
* _Legend:_ **Ln 45**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List

* _Field Name:_ **lab_result_list**
* _Type:_ **array['metric object']**
* _Description:_
  * An array of objects containing `coa` objects.
* _Legend:_ **Ln 46**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> CoA

* _Field Name:_ **Coa**
* _Type:_ **string['URI']**
* _Description:_
  * A URL to the Lab result Certificate of Analysis.
* _Legend:_ **Ln 48**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> Lab Result ID

* _Field Name:_ **lab_result_id**
* _Type:_ **string[URI]**
* _Description:_
  * Lab issued sample ID.
* _Legend:_ **Ln 49**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> Lab Result Status

* _Field Name:_ **lab_result_status**
* _Type:_ **string[URI]**
* _Description:_
  * A "pass" or "fail" string field provided by the Lab.
* _Legend:_ **Ln 50**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> Lab Result Detail

* _Field Name:_ **lab_result_detail**
* _Type:_ **string[URI]**
* _Description:_
  * A URL to the WCIA Lab Result Link.
* _Legend:_ **Ln 51**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> Lab Result Link

* _Field Name:_ **lab_result_link**
* _Type:_ **string[URI]**
* _Description:_
  * A link to the lab results WCIA json object.
* _Legend:_ **Ln 51**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> CoA Release Date

* _Field Name:_ **coa_release_date**
* _Type:_ **NULL | string**
* _Description:_
  * An ISO8601 Date String (e.g. 2022-01-01) representing the date the Lab released results.
* _Legend:_ **Ln 52**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> CoA Amended Date

* _Field Name:_ **coa_amended_date**
* _Type:_ **NULL | string**
* _Description:_
  * An ISO8601 Date String (e.g. 2022-01-01) representing the date the Lab released Amended results.
* _Legend:_ **Ln 53**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Lab Result List -> CoA Expire Date

* _Field Name:_ **coa_expire_date**
* _Type:_ **NULL | string**
* _Description:_
  * An ISO8601 Date String (e.g. 2022-01-01) representing the date the Lab rresults expire.
* _Legend:_ **Ln 54**

----------------------------------------

### Inventory Transfer Items -> Lab Result Data -> Potency

* _Field Name:_ **Potency**
* _Type:_ **array['metric object']**
* _Description:_
  * An array of metric objects. Specifically, cannabinoid analytes required for compliance testing in WA state.
* _Legend:_ **Ln 57**

----------------------------------------

#### Inventory Transfer Items -> Lab Result Data -> Potency -> Type

* _Field Name:_ **type**
* _Type:_ **string**
* _Description:_
  * The name of the cannabinoid analyzed. For example, "cbda," "thca," and "total-cannabinoids."
* _Legend:_ **Ln 59**

----------------------------------------

#### Inventory Transfer Items -> Lab Result Data -> Potency -> Value

* _Field Name:_ **value**
* _Type:_ **float|decimal**
* _Description:_
  * A float|decimal value representing the quantity of the analyte reported.
* _Legend:_ **Ln 60**

----------------------------------------

#### Inventory Transfer Items -> Lab Result Data -> Potency -> Unit

* _Field Name:_ **unit**
* _Type:_ **enum['ml', 'mg', 'g', 'oz', 'lb', 'ea', 'kg']**
* _Description:_
  * An enum field representing one of the following possible meausre abbreviations: 'ml,' 'mg,' 'g,' 'oz,' 'lb,' 'ea,' 'kg.'
    
* _Legend:_ **Ln 61**

----------------------------------------

## Inventory Transfer Items -> Inventory Category

* _Field Name:_ **inventory_category**
* _Type:_ **string**
* _Description:_
  * For purposes of Washington State, this is most commonly the State-assigned types such as "EndProduct."
* _Legend:_ **Ln 65**

----------------------------------------

## Inventory Transfer Items -> Inventory Type

* _Field Name:_ **inventory_type**
* _Type:_ **string**
* _Description:_
  * For purposes of Washington State, this is most commonly the State-assigned types such as "Flower Lot."
* _Legend:_ **Ln 66**

----------------------------------------

## Inventory Transfer Items -> Strain Name

* _Field Name:_ **strain_name**
* _Type:_ **string**
* _Description:_
  * The licensee-assigned name of the plant material being transferred.
* _Legend:_ **Ln 67**

----------------------------------------

## Inventory Transfer Items -> Product SKU (_optional_)

* _Field Name:_ **product_sku**
* _Type:_ **string**
* _Description:_
  * A sender-assigned product SKU code in string format.
* _Legend:_ **Ln 68**

----------------------------------------

### Resources

* [JSON Specification (RFC 8259)](https://www.ietf.org/rfc/rfc8259.txt)
* [ISO8601 Internet Dates Specification (RFC 3339)](https://www.ietf.org/rfc/rfc3339.txt)