---
title: Exchange Online Protection 的報告與訊息追蹤
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。下表將說明 EOP 系統管理員可以使用的報告和疑難排解工具。
ms.openlocfilehash: 282fd032e73ccb8217801a575f6029dbd9fadc9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598550"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a>Exchange Online Protection 的報告與訊息追蹤

Microsoft Exchange Online Protection (EOP) 提供許多不同的報告，可協助您判斷貴組織的整體狀態與健全狀況。 還有可協助您疑難排解特定事件 (例如郵件未抵達其預定收件者) 的工具，以及有助於符合規範需求的稽核報告。

## <a name="usage-reports"></a>使用情況報告

**Office 365 群組活動**： 檢視所建立和使用 Office 365 群組的數目的相關資訊。

**電子郵件活動**： 檢視傳送、 接收和讀取整個組織中與特定使用者的郵件數目的相關資訊。

**電子郵件 app 使用情況**： 檢視可用的電子郵件應用程式的相關資訊。 這包括每個應用程式的連線總數以及要連線的 Outlook 版本。

**信箱使用量**： 檢視儲存空間的相關資訊、 配額使用率、 項目計數，以及信箱的最後一個活動 （傳送或讀取的活動）。

請參閱下列資源以取得詳細資訊：

- [在系統管理中心的 Office 365 群組的 office 365 報告](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [在管理中心中的電子郵件活動的 office 365 報告](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [在管理中心中的電子郵件 app 使用情況的 office 365 報告](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [在系統管理中心的 [信箱使用量的 office 365 報告](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 系統管理中心內的安全性 & 合規性報告

這些增強型的報告可提供享有互動報告體驗若是 EOP 管理員，其中包含摘要資訊，並向下切入如需詳細資訊的能力。

**進階威脅防護 (ATP)**: 檢視安全連結和屬於 ATP 安全附件的相關資訊。

**EOP**： 檢視有關惡意程式碼偵測、 詐騙的郵件、 垃圾郵件偵測和進出組織的郵件流程的資訊。

[檢視 Office 365 進階威脅防護的報告](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自訂報告

以程式設計方式建立可用報告的 Microsoft 365 系統管理中心中使用 Microsoft Graph。 請參閱子主題的[使用中 Microsoft Graph 的 Office 365 使用情況報告](https://docs.microsoft.com/graph/api/resources/report)。

## <a name="custom-reports-using-microsoft-graph"></a>使用 Microsoft Graph 的自訂報告

以程式設計方式建立報告。 請參閱[Microsoft Graph 概觀](https://docs.microsoft.com/graph/overview)。

## <a name="message-trace"></a>郵件追蹤

在電子郵件通過 EOP 時進行追蹤。 您可以判斷服務是否接收、拒絕、延遲或傳遞電子郵件。 它也會顯示在郵件到達其最終狀態前，已對郵件執行哪些動作。

您可以使用此資訊來有效回答使用者的問題、 疑難排解郵件流程問題、 驗證原則變更，並此舉可連絡技術支援尋求協助。

請參閱[追蹤電子郵件](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)

## <a name="audit-logging"></a>稽核記錄

追蹤由系統管理員對組織所做的特定變更。 這些報告可協助您疑難排解組態問題，或找出安全性或法規遵循相關問題的原因。 請參閱[EOP 中的稽核報告](auditing-reports-in-eop.md)。

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>報告和郵件追蹤資料的可用性與延遲

下表說明可使用 EOP 報告和郵件追蹤資料的時間及時間長短。

||||
|:-----|:-----|:-----|
|**報告類型**|**資料可用時間 (回顧期間)**|**延遲**|
|郵件保護摘要報告|90 天|郵件資料彙總大部分會在 24 到 48 小時內完成。部分次要的增量彙總變更最多存在 5 天。|
|郵件保護詳細資料報告|90 天|針對 7 天內的詳細資料，資料應於 24 小時內出現，但可能要等到 48 小時後才完成。部分次要的增量變更最多存在 5 天。 <br/><br/> 若要檢視超過 7 天之郵件的詳細資料報告，結果可能需要幾個小時。|
|郵件追蹤資料|90 天|針對 7 天內的郵件執行郵件追蹤時，郵件應於 5 到 30 分鐘內出現。<br/><br/> 針對超過 7 天的郵件執行郵件追蹤時，結果可能需要幾個小時。|

> [!NOTE]
> 資料可用性和延遲是相同的是否要求透過 Microsoft 365 系統管理中心或遠端 PowerShell。
