---
# generated by https://github.com/fbreckle/terraform-plugin-docs
page_title: "netbox_custom_field_choice_set Resource - terraform-provider-netbox"
subcategory: "Extras"
description: |-
  From the official documentation https://docs.netbox.dev/en/stable/models/extras/customfieldchoiceset/:
  Single- and multi-selection custom fields must define a set of valid choices from which the user may choose when defining the field value. These choices are defined as sets that may be reused among multiple custom fields.
  A choice set must define a base choice set and/or a set of arbitrary extra choices.
---

# netbox_custom_field_choice_set (Resource)

From the [official documentation](https://docs.netbox.dev/en/stable/models/extras/customfieldchoiceset/):

Single- and multi-selection custom fields must define a set of valid choices from which the user may choose when defining the field value. These choices are defined as sets that may be reused among multiple custom fields.

A choice set must define a base choice set and/or a set of arbitrary extra choices.

## Example Usage

```terraform
resource "netbox_custom_field_choice_set" "test" {
  name        = "my-custom-field-set"
  description = "Description"
  extra_choices = [
    ["choice1", "label1"], # label and choice are different
    ["choice2", "choice2"]  # label and choice are the same
  ]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String)

### Optional

- `base_choices` (String) Valid values are `IATA`, `ISO_3166` and `UN_LOCODE`. At least one of `base_choices` or `extra_choices` must be given.
- `custom_fields` (Map of String)
- `description` (String)
- `extra_choices` (List of List of String) This length of the inner lists must be exactly two, where the first value is the value of a choice and the second value is the label of the choice. At least one of `base_choices` or `extra_choices` must be given.
- `order_alphabetically` (Boolean) experimental. Defaults to `false`.

### Read-Only

- `id` (String) The ID of this resource.

