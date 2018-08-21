# API Product access control, based on role and Custom Attribute

This module provides Role-Based Access control to API Products for users in the Apigee
Edge Drupal-based developer portal. It examines the custom attribute "role-access" on the API Product,
and includes the product in the list displayed to a user with any of the listed roles.

## Related modules

* API Product access control

* API Product access control (Extended)


Neither of the above modules should be used with this module. They are alternatives.
Both of the above allow the Drupal admin to explicitly configure access control in the portal itself. This module is different in that it infers access based on information in the custom attributes of the API Product.


## Installing

You should download all the files for this module into a directory named
```
sites/all/modules/custom/apiproduct_access_customattr
```
Then enable the module as normal,
in the Drupal Module administration panel.

## Configuring

To configure the access and roles, login as Administrator, and then use Configuration >
Dev Portal > API Product Role Access - Custom Attribute .  The interface should be mostly
self-explanatory from there.

The set of checkboxes allows you to specify a set of roles that will have access
to any API Product that does not have the custom attribute set. This is the "default set of roles" that will apply to an
API Product unless and until you explicitly provide roles for that product, in the custom attribute.

For example, if you want no users to be able to see any API Product until you explicitly
specify roles for the product (in the custom attribute), tick no boxes under "Default roles".

At any point in time an administrator can modify the roles that will have access to a specific existing API Product.


## Compatibility

Do not use this module with the original devconnect apiproduct access module, or the extended version.
It does not make much sense to do so. If you use this module, you should not install the others, or you should disable them.

## Disclaimer

This module is not an official Google product, nor is it part of an official Google product.


## Warranty

This software is provided "as is", without warranty of any kind, express or implied,
including but not limited to the warranties of merchantability, fitness for a particular
purpose and noninfringement. In no event shall the authors or copyright holders be
liable for any claim, damages or other liability, whether in an action of contract, tort
or otherwise, arising from, out of or in connection with the software or the use or
other dealings in the software.

## Support Status

This module is not a supported part of the Apigee Edge Drupal-based developer portal.
This module is open-source software. If you need assistance, inquire on
[The Apigee Community Site](https://community.apigee.com).  There is no service-level
guarantee for responses to inquiries regarding this module.
