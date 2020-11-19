---
title: 使用自訂報表解決方案與自動調查和回應
keywords: SIEM，API，AIR，autoIR，ATP，自動化調查，整合，自訂報告
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 瞭解如何使用自訂或協力廠商報表解決方案來整合自動調查和回應。
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 7b0b0570624b2e0dd40d40b178951a747698afe2
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357464"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>使用自訂或協力廠商報表解決方案的管理活動 API

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


使用 [Microsoft Defender For Office 365](office-365-atp.md)，您可以取得 [有關自動化調查的詳細資訊](air-view-investigation-results.md)。 不過，部分組織也會使用自訂或協力廠商報表解決方案。 如果您的組織想要整合利用這類方案進行的自動調查資訊，您可以使用 Office 365 管理活動 API。

使用下列資源進行設定：

****

|資源|描述|
|---|---|
|[Office 365 Management API 概觀](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) (英文)|Office 365 管理活動 API 提供有關 Microsoft 365 和 Azure Active Directory 活動記錄中各種使用者、系統管理員、系統及原則動作和事件的資訊。|
|[開始使用 Office 365 管理 API](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis) (英文)|Office 365 管理 API 使用 Azure AD 提供應用程式的驗證服務，以存取 Microsoft 365 資料。 請依照本文中的步驟進行設定。|
|[Office 365 管理活動 API 參考](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) (英文)|您可以使用 Office 365 管理活動 API，從 Microsoft 365 和 Azure AD 活動記錄檔中取得使用者、系統管理員、系統及原則動作和事件的相關資訊。 請閱讀本文以深入了解其運作方式。|
|[Office 365 管理活動 API 架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema) (英文)|取得 [一般架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 和 [Office 365 的 Defender （威脅調查和回應架構](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) ）的概況，以瞭解透過 OFFICE 365 管理活動 API 提供的特定資料類型。|
|

## <a name="see-also"></a>另請參閱

- [適用於 Office 365 的 Microsoft Defender](office-365-atp.md)

- [Microsoft 365 Defender 的自動化調查和回應](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
