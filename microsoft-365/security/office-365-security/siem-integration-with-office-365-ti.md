---
title: SIEM 與 Microsoft Defender for Office 365 的整合
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: 在 Office 365 活動管理 API 中，將組織的 SIEM 伺服器與 Microsoft Defender for Office 365 和相關威脅事件整合在一起。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86a716499a25af2a2907d9c502d31474b27ef7bc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916595"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM 與 Microsoft Defender for Office 365 的整合

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


如果您的組織使用安全性資訊和事件管理 (SIEM) server，您可以將 Microsoft Defender for Office 365 與您的 SIEM 伺服器整合。 您可以使用 [Office 365 活動管理 API](/office/office-365-management-api/office-365-management-activity-api-reference)設定這種整合方式。

SIEM 整合可讓您查看 SIEM 伺服器報告中的資訊，例如 Microsoft Defender for Office 365 偵測到的惡意程式碼或網路釣魚。

- 若要查看 SIEM 與 Microsoft Defender for Office 365 整合的範例，請參閱 [技術社區博客：使用 office 365 的 defender 和 O365 管理 API，改善 SOC 的效能](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)。

- 若要深入瞭解 Office 365 管理 APIs，請參閱 [office 365 管理 APIs 簡介](/office/office-365-management-api/office-365-management-apis-overview)。

## <a name="how-siem-integration-works"></a>SIEM 整合的運作方式

Office 365 活動管理 API 會從您組織的 Microsoft 365 和 Azure Active Directory 活動記錄檔中，檢索使用者、系統管理員、系統及原則動作和事件的相關資訊。 如果您的組織有 Microsoft Defender for Office 365 方案1或2，或 Office 365 E5，您可以使用 [Microsoft defender For office 365 架構](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)。

最近， [Microsoft Defender For office 365 方案 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) 中的自動調查和回應功能的事件已新增至 Office 365 管理活動 API。 除了包含有關核心調查詳細資料的資料（例如識別碼、名稱和狀態）之外，該 API 也包含有關調查動作和實體的高層級資訊。

SIEM server 或其他類似系統會輪詢此 **審核。一般** 工作負載來存取偵測事件。 若要深入瞭解，請參閱 [Office 365 管理 APIs 快速入門](/office/office-365-management-api/get-started-with-office-365-management-apis)。

## <a name="enum-auditlogrecordtype---type-edmint32"></a>列舉： AuditLogRecordType-類型： Edm

### <a name="auditlogrecordtype"></a>AuditLogRecordType

下表摘要說明 Microsoft Defender for Office 365 事件相關的 **AuditLogRecordType** 值：

|值|成員名稱|描述|
|---|---|---|
|日|ThreatIntelligence|Exchange Online Protection 和 Microsoft Defender for Office 365 的網路釣魚和惡意程式碼事件。|
|41|ThreatIntelligenceUrl|安全連結來自 Microsoft Defender for Office 365 的封鎖時間和封鎖覆寫事件。|
|47|ThreatIntelligenceAtpContent|Microsoft Defender for Office 365 中 SharePoint Online、商務小組 OneDrive 的檔案的網路釣魚和惡意程式碼事件。|
|64|AirInvestigation|來自 Microsoft Defender for Office 365 方案2的自動化調查和回應事件，例如調查詳細資料和相關的專案。|
|

> [!IMPORTANT]
> 您必須是全域系統管理員，或已指派安全性 & 規範中心的安全性系統管理員角色，才能設定與 Microsoft Defender for Office 365 的 SIEM 整合。
>
> 您的 Microsoft 365 環境必須開啟審核記錄。 若要取得此相關協助，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="see-also"></a>另請參閱

[Office 365 威脅調查及回應](office-365-ti.md)

[Office 365 中的自動調查和回應 (AIR) ](automated-investigation-response-office.md)