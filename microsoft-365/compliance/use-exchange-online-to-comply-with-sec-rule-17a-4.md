---
title: 使用 Exchange Online 和安全性與合規性中心以符合 SEC Rule 17a-4
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 設定 Exchange Online 和合規性中心，以協助符合 CFTC 規則1.31 (c)-(d)、FINRA 規則4511及 SEC 規則 17a-4 要求。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127300"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a>使用 Exchange Online 和安全性與合規性中心以符合 SEC Rule 17a-4

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.

However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.

為協助組織更了解如何運用安全性與合規性中心來符合其 Exchange Online 法規義務 (具體而言是與 Rule 17a-4 要求有關)，我們已與 Cohasset Associates 合作發佈評估。

Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.

## <a name="download-the-cohasset-assessment"></a>下載 Cohasset 評估

您可以[在這裡下載 Cohasset 評估](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)。

![Cohasset Associates 的可下載評估標題頁面](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a>這項評估是針對 Exchange Online

Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.

It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a>使用保留鎖定是建議設定的關鍵

Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:

- 保留一段要求的保留期間，該期間無法縮短，只能增加。
- 固定，也就是說，在要求的保留期間內，記錄無法覆寫、清除或變更。

In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.

By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:

- 原則的保留期間只能增加，無法縮短。
- 可將使用者新增到原則中，但無法移除任何使用者。
- 系統管理員無法刪除保留原則。

保留鎖定可協助您符合 SEC 17a-4 法規要求。

## <a name="how-to-set-up-preservation-lock"></a>如何設定保留鎖定

您可以使用 PowerShell 鎖定保留原則。 如需詳細資訊，請參閱[使用保留鎖定以符合法規需求](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements)。

## <a name="known-limitations"></a>已知限制

目前，Exchange Online 存在一些限制：

- 無法在 Teams 聊天和頻道訊息中使用通訊對話。
- 無法保留 Teams 聊天和頻道訊息中的讚。

> [!NOTE]
> 項目層級稽核現在可供 Microsoft 365 群組信箱使用。 如需詳細資訊，請參閱[管理信箱稽核](enable-mailbox-auditing.md)。
