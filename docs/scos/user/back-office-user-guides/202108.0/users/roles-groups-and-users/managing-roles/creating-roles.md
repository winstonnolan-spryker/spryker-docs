---
title: Creating roles
description: Learn how to create roles in the Back Office.
last_updated: Aug 2, 2021
template: back-office-user-guide-template
originalLink: https://documentation.spryker.com/2021080/docs/managing-roles
originalArticleId: 646ae8f6-32b9-440d-8cdf-c720d046de25
redirect_from:
  - /2021080/docs/managing-roles
  - /2021080/docs/en/managing-roles
  - /docs/managing-roles
  - /docs/en/managing-roles
  - /docs/scos/user/back-office-user-guides/202108.0/users/roles-groups-and-users/managing-roles.html
---

This document describes how to create roles.

## Prerequisites

To start working with roles, go to **Users** > **User Roles**.

Review the [reference information](#reference-information-creating-roles) before you start, or just look up the necessary information as you go through the process.

## Creating roles

1. On the **User Roles** page, click **Add new Role**.
2. On the **Create new Role** page, enter a **NAME** and click **Create**.
    This opens the **Edit Role** page with the success message displayed.
3. In the **Rule** pane, enter a **BUNDLE**.
4. Enter a **CONTROLLER**.
5. Enter an **ACTION**.
6. Select a **PERMISSION**
7. Click **Add Rule**.
      The page refreshes with the success message displayed and the ruled displayed in the **Assigned Rules** section.
8. Repeat steps 3-7 until you add all the needed rules.       

See [Adding rules for roles](/docs/scos/user/back-office-user-guides/{{page.version}}/users/roles-groups-and-users/managing-roles.html#adding-rules-for-roles) for information on how to create rules.



### Reference information: Creating roles

The following table describes the attributes you enter and select when creating roles:

| ATTRIBUTE | DESCRIPTION |
| --- | --- |
| NAME | Unique identifier of the role. You use this name to assign roles when managing users. |
| BUNDLE | Depending on the **PERMISSION**, allows or denies access to a part of a module. You can look up this value in a URL. For example, in `https://backoffice.de.b2b-demo-shop.local/product-attribute-gui/attribute/create`, `product-attribute-gui` is a bundle. |
| CONTROLLER | Depending on the **PERMISSION**, allows or denies access to a part of a module. You can look up this value in a URL. For example, in `https://backoffice.de.b2b-demo-shop.local/product-attribute-gui/attribute/create`, `attribute` is a controller. |
| ACTION | Depending on the **PERMISSION**, allows or denies access to a part of a module. You can look up this value in a URL. For example, in `https://backoffice.de.b2b-demo-shop.local/product-attribute-gui/attribute/create`, `create` is an action.
| PERMISSION | Denies or allows access to the **BUNDLE**, **CONTROLLER**, and **ACTION**. |


**Tips and tricks**

 To allow or deny access for all of the bundles, controllers or actions, enter `*` in the needed field.