# Description

Pubcid (Publisher Common ID) is an anonymous ID designed with performance and privacy in mind. 
It’s similar to device ID such as IDFA and AAID, but available per browser and user.
Pubcid Extender supplements Javascripts by rewriting pubcid as server side cookies to accommodate 
custom expiration time. By default it only update cookies that have been generated by other sources, 
but can also be configured to check consent and generate IDs directly.

# Working with Prebid

No configuation change needed. Prebid modules will be responsible for creating the IDs, and the 
extender will only update.

# Generating ID Directly

For extender to generate ID directly, set the Consent Function and the Generate Function in the config page.

Consent Function – This can be a custom function name, or a function provided by other modules. It should return 
true if there is user consent. If omitted, it’s treated as having consent, and that the consent is derived from 
other means such Javascript. 

Generate Function – Specify Drupal\pubcid_cookie_management\EventSubscriber\pubcid_value_generation, which 
returns a random UUID.

# Installation

1. Navigate to /admin/modules page, click "+install new module" button, input this url to the "install from a URL" field:
https://github.com/xhqiao/pubcid_cookie_management/archive/master.zip

2. Activate this module.
