# Status GetupAgency

GetupAgency Status is an error handling service to receive and log errors from your site list (including your modules).
Each error will send you an email

# Modules

We are currently developing modules for **CMS**, they are still in development so there is a risk of bug. The development of modules is very simple, to avoid overloading your site, we use **JQuery** (AJAX) and **cURL**

>**Warning** "Access Control-Allow-Origin" is a recurring error related to the security of your server.

| Target | Version | |
|--|--|--|
| Thelia | v0.5 | [download](https://status.getup.agency/Modules/thelia.zip)|
| WordPress | not available | download|
| JQuery | not available | download |


## Develop your module!

Learn to catch the errors of your site and develop your modules. A list of APIs is at your disposal.
With PHP use **cURL**, with JQuery user **Ajax**.

Further information :
  

 - http://php.net/manual/fr/class.exception.php
 - http://php.net/manual/fr/book.curl.php
 - http://api.jquery.com/jquery.ajax/
 - http://api.jquery.com/ajaxError/

# Services

The modules, the Cron tasks and the web application make use of a list of routes and methods for the smooth running of the service. A route list is made available to be called from a module or from a third party application.

> All APIS are public, protection is needed to avoid any damage...Take care of yourself!

## Online API

The PHP routes on **GET** or **POST** with their input and output parameters. They are still on status.getup.agency/ajax/**{routeName}**.php

They include ../**pdo.php** to manipulate all data in the database

|Path                     |Method                         |Parameters                   |Response |
|-------------------------|-------------------------------|-----------------------------|-------------|
|ajax/getSites.php        |GET                            |-                            |  `id@id@...`  |
|ajax/alterSite.php       |POST                           |id, stats            |-|
|ajax/addSite.php         |POST                           |url, label            |`table data`|
|ajax/rmvSite.php         |GET                            |id                           | `table data`|
|ajax/check_one.php       |GET                            |id            |`table data`|
|ajax/getGraphDatas.php   |GET                            |-             |`label@throw@cron@other@total%`|
|ajax/rmvErrors.php       |GET                            |-                            |-            |
|ajax/saveConfig.php      |POST                           |mail                         |-            |
|ajax/login.php           |POST                           |username, password           |success: 1   |


>**Except the error logging API**

|Path                     |Method                         |Parameters                   |Response     |
|-------------------------|-------------------------------|-----------------------------|-------------|
|/?api=checkAll           |GET                            |-                            |-            |
|/?api=throwError         |POST                           |content, code, origin        |-            |




## Trigger diagram

You can see how event triggers related to status.getup.agency work, with **Modules** and **Cron** :

![enter image description here](https://i.gyazo.com/ccc4ff26ad44a75bacf7772118403ae4.png)

# Credits

[GetupAgency](https://www.getup.agency/) and his team thank you for your trust!