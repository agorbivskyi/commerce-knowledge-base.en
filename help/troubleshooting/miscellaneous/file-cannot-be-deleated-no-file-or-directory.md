---
title: "The file can't be deleted. Warning! unlink: No such file or directory error from the [!DNL Admin]"
description: This article provides a solution to the issue where you see an error *The file can't be deleted. Warning!unlink No such file or directory error* from the [!DNL Admin] when you do a [!DNL Javascript/CSS] flush.
feature: Admin Workspace, Observability
role: Developer
exl-id: db265e3c-a809-4404-839a-273001e81d22
---
# *The file can't be deleted. Warning!unlink: No such file or directory error* from the [!DNL Admin]

This article provides a solution to the issue where you see an error *The file can't be deleted. Warning!unlink: No such file or directory error* from the [!DNL Commerce Admin] when you do a [!DNL JavaScript/CSS] flush.

## Affected products and versions

* Adobe Commerce 2.4.0 - 2.4.6, all deployment methods

## Issue

An error occurs when you do a [!DNL JS/CSS] flush:

*The "/app/pub/static/_cache/merged/.nfsa42d0e64799fd1000000001b" file can't be deleted. Warning!unlink(/app/pub/static/_cache/merged/.nfsa42d0e64799fd1000000001b): No such file or directory*

Or: You see the above error in the [!DNL Admin], and/or a similar error in [!DNL New Relic] or in the deployment logs.

Or: You are unable to access Advanced Reporting, and the analytics_collect_data cron job is failing with this error:

*The "/app/var/tmp/analytics/tmp/.nfsb3b6041dd44588a0000850c0" file can't be deleted. Warning!unlink(/app/var/tmp/analytics/tmp/.nfsb3b6041dd44588a0000850c0): No such file or directory*

<u>Steps to reproduce:</u>

Method 1:

1. Log in to the [!DNL Admin].
1. Go to **[!UICONTROL System]** > **[!UICONTROL Cache Management]**.
1. Click **[!UICONTROL Flush] [!DNL JavaScript/CSS] [!UICONTROL Cache]**.

Method 2:

1. Log in to the [!DNL Admin].
1. Go to **[!UICONTROL Stores]** > *[!UICONTROL Settings]* > **[!UICONTROL Configuration]**.
1. Make changes to the [!UICONTROL Base URL] or [!UICONTROL Base URL (Secure)].
1. Click on **[!UICONTROL Save Config]**.

## Solution

If you are on Adobe Commerce on Cloud infrastructure and have [!DNL magento/magento-cloud-patches] 1.0.22 installed which include the patch, you do not need to separately install ACSD-50165.

Adobe Commerce on Cloud infrastructure: Upgrade Cloud Patches for Commerce to 1.0.22 which contains this fix: [Cloud Patches for Commerce](/docs/commerce-cloud-service/user-guide/release-notes/cloud-patches.html).

Adobe Commerce on-premises: Apply ACSD-50165 using [Quality Patches Tools > Usage](/docs/commerce-operations/tools/quality-patches-tool/usage.html). The ACSD-50165 patch comes with [!DNL QPT] [v1.1.30.](/docs/commerce-operations/tools/quality-patches-tool/release-notes.html#v1-1-30)

## Related reading

* [[!DNL Quality Patches Tool] > Release Notes](/docs/commerce-operations/tools/quality-patches-tool/release-notes.html) in the Commerce Tools guide.
* [[!DNL Quality Patches Tool]: Search for patches](https://experienceleague.adobe.com/tools/commerce-quality-patches/index.html) in the Commerce Tools guide.
