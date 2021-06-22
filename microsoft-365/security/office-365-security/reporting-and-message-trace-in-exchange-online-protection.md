---
title: 報告和郵件追蹤
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解可用來 Microsoft Exchange Online Protection (EOP) 系統管理員的報告和疑難排解工具。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cc49a92d5fb1fb0368b14eef7524638542f38deb
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054382"
---
# <a name="reporting-and-message-trace-in-eop"></a>EOP 中的報告和郵件追蹤

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，EOP 提供許多不同的報告，可協助您判斷組織的整體狀態與健康情況。 還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。

## <a name="usage-reports"></a>使用情況報告

- **Microsoft 365 群組活動**：查看已建立及使用之 Microsoft 365 群組數目的相關資訊。 如需詳細資訊，請參閱系統[管理中心的 Microsoft 365 報告-Microsoft 365 群組](../../admin/activity-reports/office-365-groups.md)。
- **電子郵件活動**：查看有關您整個組織中傳送、接收和讀取的郵件數目，以及特定使用者的資訊。 如需詳細資訊，請參閱[admin center 中的 Microsoft 365 報告-電子郵件活動](../../admin/activity-reports/email-activity.md)。
- **電子郵件應用程式使用狀況**：查看使用的電子郵件應用程式的相關資訊。 這包括每個應用程式的連線總數，以及所連接之 Outlook 的版本。 如需詳細資訊，請參閱系統[管理中心的 Microsoft 365 報告-電子郵件應用程式使用](../../admin/activity-reports/email-apps-usage.md)。
- **信箱使用狀況**：查看信箱的「傳送或讀取活動」) 使用的儲存空間、配額消耗、專案計數及最後一項活動的相關資訊 (。 如需詳細資訊，請參閱[在系統管理中心中 Microsoft 365 報告-信箱使用量](../../admin/activity-reports/mailbox-usage.md)。

## <a name="security-reports-in-the-microsoft-365-defender-portal"></a>Microsoft 365 defender 入口網站中的安全性報告

這些增強型報告提供 EOP 系統管理員的互動式報告經驗（包括摘要資訊），以及深入查看詳細資訊的功能。

- **Office 365 的 Defender**：查看有關保管庫連結的資訊，以及保管庫屬於 Microsoft Defender Office 365 的附件。 如需詳細資訊，請參閱[在 Microsoft 365 Defender 入口網站中查看 Office 365 報表的 Defender](view-reports-for-mdo.md)。
- **EOP**：查看組織中惡意程式碼偵測、欺騙性郵件、垃圾郵件偵測和郵件流程的相關資訊。 如需詳細資訊，請參閱[在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告](view-email-security-reports.md)。

## <a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自訂報告

使用 Microsoft Graph，以程式設計方式建立可以在系統管理中心中使用的報告。 如需詳細資訊，請參閱[microsoft Graph](/graph/overview)和[使用 microsoft Graph 中的 Office 365 使用方式報告](/graph/api/resources/report)。

## <a name="message-trace"></a>郵件追蹤

在電子郵件通過 EOP 時進行追蹤。 您可以判斷服務是否接收、拒絕、延遲或傳遞電子郵件。 它也會顯示在郵件到達其最終狀態前，已對郵件執行哪些動作。

您可以使用此資訊來有效地回答使用者的問題、疑難排解郵件流程問題、驗證原則變更，以及緩解聯繫技術支援以尋求協助的需求。

請參閱[Microsoft 365 Defender 入口網站中的郵件追蹤](message-trace-scc.md)。

## <a name="audit-logging"></a>稽核記錄

追蹤由系統管理員對組織所做的特定變更。 這些報告可協助您疑難排解組態問題，或找出安全性或法規遵循相關問題的原因。 請參閱[Exchange Online 中的審計報告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>報告和郵件追蹤資料的可用性與延遲

下表說明可使用 EOP 報告和郵件追蹤資料的時間及時間長短。

<br>

****

|報告類型|資料可用時間 (回顧期間)|延遲|
|---|---|---|
|郵件保護摘要報告|90 天|郵件資料彙總大部分會在 24 到 48 小時內完成。部分次要的增量彙總變更最多存在 5 天。|
|郵件保護詳細資料包告|90 天|針對 7 天內的詳細資料，資料應於 24 小時內出現，但可能要等到 48 小時後才完成。部分次要的增量變更最多存在 5 天。 <p> 若要檢視超過 7 天之郵件的詳細資料報告，結果可能需要幾個小時。|
|郵件追蹤資料|90 天|針對 7 天內的郵件執行郵件追蹤時，郵件應於 5 到 30 分鐘內出現。<p> 針對超過 7 天的郵件執行郵件追蹤時，結果可能需要幾個小時。|
|

> [!NOTE]
> 不論是透過系統管理中心或遠端 PowerShell 所要求的資料可用性和延遲，都是相同的。
