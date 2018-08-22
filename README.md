# API Product access control, based on role and Custom Attribute

This module provides Role-Based Access control to API Products for users in the Apigee
Edge Drupal-based developer portal. It examines the custom attribute "role-access" on the API Product,
and includes the product in the list displayed to a user that has  any of the roles in that list.

## Example Behavior

Given this configuration:

* Product1 has custom attribute: name:"roles-access", value:"gold-partner, silver-partner"
* Product2 has custom attribute: name:"roles-access", value:"partner100"
* Product3 has no custom attribute.
* the "default" roles configured for this module are: "administrator"
* user1 has roles: "authenticated user, gold-partner"
* user2 has role: "authenticated user"
* admin has roles: "authenticated user, administrator"

Operational results:

* When user1 logs into the devportal, he will see Product1 in the list.  He will not see Product2 or Product3.
* When user2 logs into the devportal, she will see no products in the list.
* When admin logs into the devportal, he can see Product3!



## Related modules

* devconnect API Product access control - the default access control. An alternative to this module.
* [API Product access control (Extended)](https://github.com/DinoChiesa/Edge-DevPortal-ApiProducts-Access-Extended) - an alternative module in which the Drupal admin specifies which products can be seen by which roles.
* [API Product Access by Role](https://github.com/DinoChiesa/Edge-DevPortal-Filter-ApiProducts-ByRole) - allows corse filtering based on environment, and user roles. Does not filter by API Product.
* [Filter-ApiProducts by Environment](https://github.com/DinoChiesa/Edge-DevPortal-Filter-ApiProducts) - filters products by Pantheon environment (dev, stage, live). Possibly complementary to this module.
* [ApiProducts-GroupBy-Env](https://github.com/DinoChiesa/Edge-DevPortal-ApiProducts-GroupBy-Env) - a module that groups Products by Environment in the dropdown list.  _Complementary_ to this module.

This module is different in that it infers access based on information stored on a custom attribute of the API Product.


## Installing

You should download all the files for this module into a directory named
```
sites/all/modules/custom/apiproduct_access_customattr
```
Then enable the module as normal,
in the Drupal Module administration panel.


## Notes on Configuration

To configure the access and roles, login as Administrator, and then use
Configuration > Dev Portal > API Product Role Access - Custom Attribute.
The settings are simple and the interface will be self-explanatory.

The first set of checkboxes allows you to specify a set of roles that will
have access to any API Product that does not have the custom attribute
set. This is the "default set of roles" that will apply to an API
Product unless and until you explicitly provide roles for that product,
in the custom attribute called "roles-access".

If you want API Products to _not_ be visible by any user unless the
roles-access attribute is set, then uncheck all of those boxes.


The second set of checkboxes allows you to specify a set of roles that
will have access to any API Product, regardless of the presence or value
of the custom attribute. This should probably be set to "administrator"
only.

At any point in time an administrator can modify the roles-access
attribute on any API Product. This setting will be cached by Drupal, so
in a demonstration scenario, be sure to clear the drupal cache, or turn
off caching for API products.


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
