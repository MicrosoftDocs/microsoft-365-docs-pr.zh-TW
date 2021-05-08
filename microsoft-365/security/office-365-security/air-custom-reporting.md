---
title: 使用自動調查和回應的自訂報告解決方案
keywords: SIEM，API，AIR，autoIR，Microsoft Defender for Endpoint，自動化調查，整合，自訂報告
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 瞭解如何使用自訂或協力廠商報表解決方案來整合自動調查和回應。
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275009"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 的自訂或協力廠商報表解決方案

使用[Microsoft Defender for Office 365](defender-for-office-365.md)，您可以取得[有關自動化調查的詳細資訊](air-view-investigation-results.md)。 不過，部分組織也會使用自訂或協力廠商報表解決方案。 如果您的組織想要整合利用這類方案進行的[自動調查](office-365-air.md)資訊，您可以使用 Office 365 管理活動 API。

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

使用[Microsoft Defender for Office 365](defender-for-office-365.md)，您可以取得[有關自動化調查的詳細資訊](air-view-investigation-results.md)。 不過，部分組織也會使用自訂或協力廠商報表解決方案。 如果您的組織想要整合利用這類方案進行的自動調查資訊，您可以使用 Office 365 管理活動 API。

|資源|描述|
|:---|:---|
|[Office 365 Management API 概觀](/office/office-365-management-api/office-365-management-apis-overview) (英文)|Office 365 管理活動 API 提供有關 Microsoft 365 和 Azure Active Directory 活動記錄檔中各種使用者、系統管理員、系統和原則動作和事件的資訊。|
|[開始使用 Office 365 管理 API](/office/office-365-management-api/get-started-with-office-365-management-apis) (英文)|Office 365 管理 API 使用 Azure AD 提供應用程式的驗證服務，以存取 Microsoft 365 資料。 請依照本文中的步驟進行設定。|
|[Office 365 管理活動 API 參考](/office/office-365-management-api/office-365-management-activity-api-reference) (英文)|您可以使用 Office 365 管理活動 API，從 Microsoft 365 和 Azure AD 活動記錄檔中，取得使用者、系統管理、系統及原則動作和事件的相關資訊。 請閱讀本文以深入了解其運作方式。|
|[Office 365 管理活動 API 架構](/office/office-365-management-api/office-365-management-activity-api-schema) (英文)|取得[一般架構](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)和[Office 365 和威脅調查與回應架構](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)的相關資訊，以瞭解可透過 Office 365 管理活動 API 使用的特定資料類型。|
|

## <a name="see-also"></a>另請參閱

- [適用於 Office 365 的 Microsoft Defender](defender-for-office-365.md)
- [Microsoft 365 Defender 中的自動化調查和回應](/microsoft-365/security/defender/m365d-autoir)
