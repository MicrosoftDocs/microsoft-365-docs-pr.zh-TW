---
title: Microsoft 365 中的進階稽核
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365 中的「進階稽核」提供新的稽核功能，以協助貴組織進行鑑識與合規性調查。
ms.openlocfilehash: 49d2e2bbf7d1c19bb4c282920008a0ca9a34188d
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862383"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 中的進階稽核

Microsoft 365 中的[整合式稽核功能](search-the-audit-log-in-security-and-compliance.md)，可讓組織深入了解 Microsoft 365 中多種不同服務的多個類型的稽核活動。 現在隨著 Microsoft 365 中進階稽核的推出，我們會加入新的稽核功能，以協助貴組織進行鑑識與合規性調查。

> [!NOTE]
> 進階稽核可供具有 Office 365 或 Microsoft 365 企業版 E5 訂閱的組織使用。 此外，當「進階稽核」功能需要使用每位使用者授權時，您可以將 Microsoft 365 E5 合規性附加元件訂閱指派給使用者，針對稽核記錄和高價值稽核事件的長期保留也是如此。

本文提供這些「進階稽核」功能的概觀。

## <a name="long-term-retention-of-audit-logs"></a>長期保留稽核記錄

「進階稽核」會保留所有 Exchange、SharePoint 和 Azure Active Directory 稽核記錄一年。 這是透過預設的稽核記錄保留原則完成，它會保留包含 **Workload** 屬性 (這指出發生活動所在的服務) 的 **Exchange**、**SharePoint** 或 **AzureActiveDirectory** 的值的任何稽核記錄一年。 這可協助進行持續的鑑識或合規性調查。 如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md#default-audit-log-retention-policy)中的「預設稽核記錄保留原則」一節。

## <a name="audit-log-retention-policies"></a>稽核記錄保留原則

在其他服務中產生、未在預設稽核記錄保留原則涵蓋範圍的所有稽核記錄 (如前一節所述)，將會保留 90 天。 不過，您現在可以建立自訂的稽核記錄保留原則，以保留其他稽核記錄最多達一年。 您可以根據下列一或多項準則，建立用來保留稽核記錄的原則：

- 稽核活動發生所在的 Microsoft 365 服務

- 特定已稽核活動

- 執行已稽核活動的使用者

您也可以指定要保留符合原則的稽核記錄的時間長度和優先順序層級，以便特定原則可優先於其他原則。 另請注意，如果您需要為組織中的部分或所有使用者保留 Exchange、SharePoint 或 Azure Active Directory 稽核記錄少於一年，任何自訂稽核記錄保留原則都會優先於預設的稽核保留原則。 如需詳細資訊，請參閱[管理稽核記錄保留原則](audit-log-retention-policies.md)。

## <a name="high-value-audit-events"></a>高價值稽核活動

高價值安全性與合規性相關的稽核事件，可協助您調查可能的外洩或其他與鑑識相關的調查。 我們要發佈的第一個這類高價值事件是 *MailItemsAccessed* 信箱稽核事件。 當郵件資料由郵件通訊協定和用戶端存取時，即會觸發此事件。 MailItemsAccessed 事件可協助調查人員識別資料外洩，並判斷可能已遭入侵的郵件範圍。 如果攻擊者取得電子郵件訊息，即使沒有明確訊號指出已實際讀取 (也就是說，在稽核記錄中記錄了透過繫結或同步處理之類的存取類型)，也會觸發 MailItemsAccessed 事件。

新的 MailItemsAccessed 信箱動作會取代 Exchange Online 中信箱稽核記錄的 MessageBind，並提供下列改善：

- MessageBind 僅可針對 AuditAdmin 使用者登入類型設定；不適用於代理人或擁有者動作。 MailItemsAccessed 適用於所有登入類型。

- MessageBind 僅涵蓋透過郵件用戶端的存取。 並不適用同步處理活動。 MailItemsAccessed 事件會由繫結和同步處理存取類型觸發。

- 當存取相同的電子郵件訊息時，MessageBind 動作會觸發多個稽核記錄，這會導致稽核的「雜訊」。 相反地，MailItemsAccessed 事件會彙總在較少的稽核記錄中。

如需有關信箱稽核記錄的詳細資訊，請參閱[管理信箱稽核](enable-mailbox-auditing.md)。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 管理活動 API 的高頻寬存取權

透過 Office 365 管理活動 API 存取稽核記錄的組織，其節流限制會處於發行者層級。 這表示，針對代表多個客戶提取資料的發行者，此限制會由所有客戶所共用。

隨著進階稽核的推出，我們會將發行者層級限制移至租用戶層級限制。 結果是每個組織都會獲得自己完整配置的頻寬配額，以存取其稽核資料。 頻寬不是靜態、預先定義的限制，但是會以一些要素的組合模組化，其中包括組織中的基座數量，以及 E5 組織可獲得較非 E5 組織更多的頻寬。

所有組織一開始都會配置每分鐘 2,000 個要求的基準。 視組織的基座數和授權訂閱而定，此限制將會動態增加。 E5 組織可獲得的頻寬大約可達到非 E5 組織的兩倍。 最大頻寬也會有上限，以保護服務的健康情況。

如需詳細資訊，請參閱 [Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)中的「API 節流」一節。
