---
title: SIEM 與高級威脅防護的整合
f1.keywords:
- NOCSH
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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 將組織的 SIEM 伺服器與 office 365 的高級威脅防護和相關威脅事件，與 Office 365 活動管理 API 整合。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cfb76485fec8eca2f2b62da59fa2d18a56177bba
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203637"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM 與高級威脅防護的整合

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果您的組織使用安全性事件和事件管理 (SIEM) server，您可以將 365 Office 365 的「高級威脅防護」與 SIEM server 整合 (Office ATP) 。 您可以使用 [Office 365 活動管理 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)設定這種整合方式。 

SIEM 整合可讓您在 SIEM 伺服器報告中查看 Office 365 ATP 所偵測到的惡意程式碼或網路釣魚資訊，例如惡意程式碼或網路釣魚。 

- 若要查看與 Office 365 ATP SIEM 整合的範例，請參閱 [技術社區博客：使用 Office 365 ATP 和 O365 管理 API，提高 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

- 若要深入瞭解 Office 365 管理 APIs，請參閱 [office 365 管理 APIs 簡介](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 整合的運作方式

Office 365 活動管理 API 會從您組織的 Microsoft 365 和 Azure Active Directory 活動記錄檔中，檢索使用者、系統管理員、系統及原則動作和事件的相關資訊。 如果您的組織有 Office 365 ATP Plan 1 或2或 Office 365 E5，您可以使用 [office 365 atp 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。  

最近， [office 365 ATP 方案 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) 中的自動調查和回應功能的事件已新增至 Office 365 管理活動 API。 除了包含有關核心調查詳細資料的資料（例如識別碼、名稱和狀態）之外，該 API 也包含有關調查動作和實體的高層級資訊。

SIEM server 或其他類似系統會輪詢此 **審核。一般** 工作負載來存取偵測事件。 若要深入瞭解，請參閱 [Office 365 管理 APIs 快速入門](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>列舉： AuditLogRecordType-類型： Edm

### <a name="auditlogrecordtype"></a>AuditLogRecordType

下表摘要說明適用于 Office 365 ATP 事件的 **AuditLogRecordType** 值：

|值|成員名稱|描述|
|---|---|---|
|日|ThreatIntelligence|Exchange Online Protection 和 Office 365 ATP 中的網路釣魚和惡意程式碼事件。|
|41|ThreatIntelligenceUrl|ATP 安全連結從 Office 365 ATP 的封鎖時間與封鎖覆寫事件。|
|47|ThreatIntelligenceAtpContent|來自 Office 365 ATP 的 SharePoint Online 中的檔案、商務 OneDrive 商務和 Microsoft 小組檔案的網路釣魚和惡意程式碼事件。|
|64|AirInvestigation|自動調查和回應事件，例如從 Office 365 ATP 方案2調查詳細資料和相關的偽像。|
|

> [!IMPORTANT]
> 您必須是全域系統管理員或已指派安全性 & 規範中心的安全性系統管理員角色，才能設定與 Office 365 高級威脅防護的 SIEM 整合。<br/>您的 Microsoft 365 環境必須開啟審核記錄。 若要取得此相關協助，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>請參閱

[Office 365 威脅調查及回應](office-365-ti.md)

[Office 365 中的自動調查和回應 (AIR) ](automated-investigation-response-office.md)


