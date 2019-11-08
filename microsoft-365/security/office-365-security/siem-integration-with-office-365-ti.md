---
title: Office 365 進階威脅防護的 SIEM 整合
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: 將貴組織的 SIEM 伺服器整合與 Office 365 進階威脅防護和 Office 365 活動管理 API 中的相關的威脅事件。
ms.openlocfilehash: a9d6c8db8ca3090bb2a10ec1bd9b6f5edb48991e
ms.sourcegitcommit: b424ea039c5915975f3efce8793bfc8dd2fdf906
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033884"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>Office 365 進階威脅防護的 SIEM 整合

如果您的組織使用的安全性事件和事件管理 (SIEM) 伺服器，您可以使用 SIEM 伺服器整合 Office 365 進階威脅防護。 SIEM 整合可讓您檢視資訊，例如惡意程式碼或在 SIEM 伺服器報表中 Office 365 進階防護，所偵測到的釣魚程式。 若要設定 SIEM 整合，您可以使用[Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)。 

Office 365 活動管理 API 從貴組織的 Office 365 和 Azure Active Directory 活動記錄檔擷取使用者、 系統、 系統及原則動作和事件的相關資訊。 [Office 365 進階威脅防護結構描述](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)搭配進階威脅防護，因此如果您的組織有 Office 365 進階威脅防護方案 1 或方案 2 或 Office 365 E5，您仍然可以使用該相同的 API 您 SIEM 伺服器整合。 

SIEM 伺服器或其他相似 system 應輪詢 access 偵測事件**audit.general**工作負載。 若要深入了解，請參閱[開始使用 Office 365 管理 Api](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 此外，下列值的**AuditLogRecordType**是相關的 Office 365 ATP 事件：

### <a name="enum-auditlogrecordtype---type-edmint32"></a>列舉： AuditLogRecordType-類型： Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|值|成員名稱|描述|
|:-----|:-----|:-----|
|28|ThreatIntelligence|從 Exchange Online Protection 和 Office 365 進階威脅防護的網路釣魚和惡意程式碼事件。|
|41|ThreatIntelligenceUrl|ATP 安全連結區塊時間] 與 [封鎖覆寫來自 Office 365 進階威脅防護的事件。|
|47|ThreatIntelligenceAtpContent|在 SharePoint Online、 OneDrive for Business 和 Microsoft Teams 從 Office 365 進階威脅防護的檔案的網路釣魚和惡意程式碼事件。|

> [!IMPORTANT]
> 您必須是 Office 365 全域管理員或具有安全性系統管理員 」 角色指派的安全性 & 合規性中心，以設定 Office 365 進階威脅防護的 SIEM 整合。<br/>稽核記錄必須開啟適用於 Office 365 環境。 若要取得此問題的協助，請參閱[開啟 Office 365 稽核記錄搜尋的開啟或關閉](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="related-topics"></a>相關主題

[Office 365 威脅調查及回應](office-365-ti.md)

[Office 365 進階威脅防護](office-365-atp.md)

[智慧型報表和深入了解 Office 365 安全性&amp;合規性中心](reports-and-insights-in-security-and-compliance.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
