

What
- 
This is a fork of the Drupal 7 [OpenAM module](https://www.drupal.org/project/openam). It includes some additional functionality to support OpenAM API level 13. After patch troubles, abandoning auto roles population, and other changes, I had more changes than a few changes to warrent a patch. 

This module is meant to replace the older version, until it is updated to support API 13. 

Why 
-
ForgeRock [dropped support for legacy calls](https://forgerock.org/reply/12904/) in the OpenAM API version 12. 

How
-
- New function called [_openam_is_token_valid_13](https://github.com/rgoodie/openam_13/blob/master/openam.module#L306) and [_openam_get_informations_13](https://github.com/rgoodie/openam_13/blob/master/openam.module#L460). 
- New [menu option checkbox ](https://github.com/rgoodie/openam_13/blob/master/openam.admin.inc#L22) that sets a boolean value to use legacy or API level 13 calls. 


To Install
- 
This is basically a "drop-in replacement" for the 7.x-1.2 version. In the shell *of a TESTING system*
- remove the openam folder 
- clone this repo 




The Original README.txt file
-

The OpenAM project aims to provide a bridge between Drupal and OpenAM.

How does it work ?
If the OpenAM access is activated, the user connection block is hidden to avoid drupal user connection.
When a user wants to connect and access to the "/user" page, he is automatically redirected to the OpenAM server URL to login.

Once logged, the user automatically returned in the website and the module create the user (and define it as "external") or connect the user if exists.
User informations are update according to the mapping made on the configuration page, between the Drupal user fields and the OpenAM attributes.

Finally, the user is placed in roles, if roles have been created on the Drupal platform.

How install the module ?
  - Copy the module into the sites/[SITE]/modules/contrib directory
  - Activate the module
  - Configure access and attributes mapping on admin/config/services/openam
