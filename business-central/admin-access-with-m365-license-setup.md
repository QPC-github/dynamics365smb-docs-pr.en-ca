---
title: Set Up Access with Microsoft 365 Licences
description: A guide to how administrators can configure access to Business Central with Microsoft 365 licences.
author: mikebc
ms.author: mikebc
ms.reviewer: jswymer
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 11/03/2022
ms.custom: bap-template
ms.search.keywords: 'License, access, Microsoft 365, collaborate, collaboration, Teams, Microsoft Teams'
ms.search.form: 9061
---
# Set Up Business Central Access in Teams with Microsoft 365 Licences

Administrators must complete multiple activities before users can access Business Central with their Microsoft 365 licence. The steps below represent the minimum setup required to get started. To learn more about access with Microsoft 365 licences, go to [Business Central Access with Microsoft 365 Licences](admin-access-with-m365-license.md).

## Deploy the Business Central app for Teams

For Business Central licence holders to share data in Teams, and for Microsoft 365 licence holders to access that data, each must have the Business Central app for Teams installed. Although users can install the app by themselves, it's recommended that administrators use centralized deployment. Centralized deployment lets you roll out the app to a broader audience across the organization and minimize individual user effort. 

To learn how to centrally deploy the Business Central app for Teams, see [Installing the Business Central app by using Centralized Deployment](admin-teams-integration.md#installing-the-business-central-app-by-using-centralized-deployment).

> [!NOTE]
> If you have run centralized deployment before and only deployed the app to the security group of licensed Business Central users, you'll need to run it again to deploy to additional groups or the whole organization, depending on how you are configuring access.

> [!TIP]
> Looking for a quicker way to get started when trying out this feature? Test users can install the app at [aka.ms/BCgetTeamsApp](https://aka.ms/BCgetTeamsApp).

## Configure permissions

Business Central is secure by design and minimizes risk by granting no permissions to Microsoft 365 users out of the box. Administrators must configure object permissions that determine which tables, pages and reports can be accessed in Teams with only a Microsoft 365 licence. These permissions are the starting permissions assigned when a user signs in for the first time with their Microsoft 365 licence. 

To configure starting permissions:

1. In Business Central, search for **Licence Configuration**.
2. Select the Microsoft 365 licence.
3. At the top of the **Microsoft 365** licence page, select the edit icon ![Edit icon](media/edit-pencil.png), then turn on **Customize permissions**. 
4. In the **Custom Permission Sets** section, add the appropriate permission sets and choose whether they're applicable to a single company or all companies within the environment.

With this configuration, users with only a Microsoft 365 licence are added to the **Users** list when they access Business Central for the first time. For more information about users, go to [Creating Users According to Licences](ui-how-users-permissions.md).

> [!NOTE]
> When synchronizing the users list in Business Central with users in Microsoft 365, only users that have a Business Central licence are added to Business Central's users list. For more administrative control over permissions, user groups, and profiles, you can assign a security group to the environment. When environments are secured using a security group and enable access with Microsoft 365 licences, the **Update users from Microsoft 365** action in the **Users** page will also include users that only have a Microsoft 365 licence. To learn about securing environments, see [Manage access using Azure Active Directory groups](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-manage-access#manage-access-using-azure-active-directory-groups) in the developer and IT pro help.

> [!TIP]
> Looking for a quicker way to get started when trying out this feature sandbox or evaluation company? Assign the **D365 Read** permission set, which grants permission to most objects.  

When working with multiple environments, licence configuration must be applied to each environment and can be different on each environment. 

Learn more at [Assign Permissions to Users and Groups](ui-define-granular-permissions.md) and [Composing Permission Sets](/dynamics365/business-central/dev-itpro/developer/devenv-permissionset-composing).

## Turn on access with Microsoft 365 licences

Access with Microsoft 365 licences is off by default. Access must be enabled for each environment independently, giving administrators control and allowing for staged rollout across the organization. You turn on access by using the Business Central admin centre: 

1. In the upper-right corner, select **Settings** ![Settings.](media/ui-experience/settings_icon_small.png "Settings icon for role centre") > **Admin Centre**.  
2. In the admin centre, select **Environments**, then select the environment on which you want to change licence access. 
3. On the **Environment details** page, select **Modify** for the **Access with Microsoft 365 licences** setting.
4. In the **Microsoft 365 licences** pane, turn on the switch. 
5. Select **Save** when done and accept the confirmation. The change comes into effect immediately.

## Test your setup

To verify that your setup is ready for production, the following steps will help you build the confidence that everything works as it should. 

1. Create or identify two test users (A and B).

   - Test user A must have a Business Central licence and Microsoft 365 licence with access to Teams.
   - Test user B must have only a Microsoft 365 licence with access to Teams.

2. Sign in to the Business Central web client as test user A.

   1. Open a record that test user B should have access to, such as an **Item** card in the appropriate company and environment.
   2. Select **Share** ![!Share to other apps action on pages.](media/share-icon.png) > **Share to Teams** to bring up the Share to Teams window.
   3. In the **Share to** field, add test user B as the recipient. 
   4. Wait for the link to expand to a card and select Share. 

3. Sign into Microsoft Teams as test user B.

   1. Select Chat and open the conversation with test user A. 
   2. In the message sent by test user A, select the Details button on the card. If the Business Central client is displayed and is read-only, your set up was successful. 

> [!TIP]
> Something went wrong? Check out [Troubleshoot Access with Microsoft 365 Licences](admin-access-with-m365-license-troubleshooting.md).

## See also 

[Overview of Business Central Access with Microsoft 365 licences](admin-access-with-m365-license.md#minimum-requirements)  
[Troubleshoot Access with Microsoft 365 Licences](admin-access-with-m365-license-troubleshooting.md)  
[Business Central and Microsoft Teams Integration](across-teams-overview.md)  
