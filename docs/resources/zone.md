---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "citrix_zone Resource - citrix"
subcategory: ""
description: |-
  Manages a zone.
  For cloud DDC, Zones and Cloud Connectors are managed only by Citrix Cloud. Ensure you have a resource location manually created and connectors deployed in it. You may then apply or import the zone using the zone Id.
---

# citrix_zone (Resource)

Manages a zone.
For cloud DDC, Zones and Cloud Connectors are managed only by Citrix Cloud. Ensure you have a resource location manually created and connectors deployed in it. You may then apply or import the zone using the zone Id.

## Example Usage

```terraform
resource "citrix_zone" "example-zone" {
    name                = "example-zone"
    description         = "zone example"
    metadata            = [
        {
            name    = "key1"
            value   = "value1"
        }
    ]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Name of the zone.
For Cloud DDC, ensure this matches the name of the existing zone that needs to be used.

### Optional

- `description` (String) Description of the zone.
For Cloud DDC, ensure this matches the description of the existing zone that needs to be used.
- `metadata` (Attributes List) Metadata of the zone. Cannot be modified in DaaS cloud. (see [below for nested schema](#nestedatt--metadata))

### Read-Only

- `id` (String) GUID identifier of the zone.

<a id="nestedatt--metadata"></a>
### Nested Schema for `metadata`

Required:

- `name` (String) Metadata name.
- `value` (String) Metadata value.

## Import

Import is supported using the following syntax:

```shell
# Zone can be imported by specifying the GUID
terraform import citrix_zone.example-zone 06e5981e-dbaf-48db-b134-245fca2dc672
```