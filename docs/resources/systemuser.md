---
subcategory: "System"
---

# Resource: systemuser

The systemuser resource is used to create users for the target ADC.


## Example usage

```hcl
resource "citrixadc_systemuser" "tf_user" {
    username = "tf_user"
    password = "tf_password"
    timeout = 200

}
```


## Argument Reference

* `username` - (Optional) Name for a user.
* `password` - (Optional) Password for the system user. Can include any ASCII character.
* `externalauth` - (Optional) Whether to use external authentication servers for the system user authentication or not. Possible values: [ ENABLED, DISABLED ]
* `promptstring` - (Optional) String to display at the command-line prompt. Can consist of letters, numbers, hyphen (-), period (.), hash (#), space ( ), at (@), equal (=), colon (:), underscore (\_), and the following variables: * %u - Will be replaced by the user name. * %h - Will be replaced by the hostname of the Citrix ADC. * %t - Will be replaced by the current time in 12-hour format. * %T - Will be replaced by the current time in 24-hour format. * %d - Will be replaced by the current date. * %s - Will be replaced by the state of the Citrix ADC. Note: The 63-character limit for the length of the string does not apply to the characters that replace the variables.
* `timeout` - (Optional) CLI session inactivity timeout, in seconds. If Restrictedtimeout argument of system parameter is enabled, Timeout can have values in the range [300-86400] seconds. If Restrictedtimeout argument of system parameter is disabled, Timeout can have values in the range [0, 10-100000000] seconds. Default value is 900 seconds.
* `logging` - (Optional) Users logging privilege. Possible values: [ ENABLED, DISABLED ]
* `maxsession` - (Optional) 
* `hashedpassword` - (Optional)


## Attribute Reference

In addition to the arguments, the following attributes are available:

* `id` - The id of the systemuser. It has the same value as the `username` attribute.


## Import

A systemuser can be imported using its name, e.g.

```shell
terraform import citrixadc_systemuser.tf_user tf_user
```
