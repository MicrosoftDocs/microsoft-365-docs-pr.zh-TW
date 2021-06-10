---
title: 在 Microsoft 365 安全中心開啟 Microsoft 365 Defender
description: 瞭解如何啟用 Microsoft 365 Defender，並開始整合您的安全性事件與回應。
keywords: 入門、啟用 Microsoft 365 defender、Microsoft 365 Defender、M365、security、data location、必要許可權、授權資格、設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 3f05cc8c9b2509f8c95b802f56905e2859221cd2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861596"
---
# <a name="turn-on-microsoft-365-defender"></a>開啟 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[Microsoft 365 defender](microsoft-365-defender.md)會整合您的事件回應程式，方法是在 microsoft defender for Endpoint、microsoft defender for Office 365、Microsoft Cloud App Security 和 Microsoft defender 身分識別上整合重要功能。 此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。

Microsoft 365當具備必要許可權的合格客戶 Microsoft 365 安全性中心時，Defender 會自動開啟。 請閱讀本文以瞭解各種必要條件，以及如何布建 Microsoft 365 Defender。

## <a name="check-license-eligibility-and-required-permissions"></a>檢查授權資格和必要許可權

Microsoft 365 安全性產品的授權，通常是您可以在 Microsoft 365 安全性中心使用 Microsoft 365 Defender，而不需要額外授權成本。 我們建議您取得 Microsoft 365 E5，E5 security，A5，或 a5 安全性授權或有效的授權組合，可提供所有支援服務的存取權。

如需詳細的授權資訊，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>檢查您的角色

您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員**，才可開啟 Microsoft 365 Defender。 [在 Azure AD 中查看您的角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支援的服務

Microsoft 365Defender 會匯總您已部署之各種支援服務的資料。 它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。 這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。

若要取得最佳保護，並優化 Microsoft 365 Defender，我們建議您在網路上部署所有適用的受支援服務。 如需詳細資訊，請 [參閱部署支援的服務](deploy-supported-services.md)。

## <a name="onboard-to-the-service"></a>服務的板載
上架至 Microsoft 365 Defender 很簡單。 從 [流覽] 功能表中，選取任何 Microsoft 365 的 Defender 專案（例如事件、搜尋、動作中心或威脅分析）以啟動上架處理常式。 

### <a name="data-center-location"></a>資料中心位置

Microsoft 365Defender 會儲存和處理[Microsoft Defender For Endpoint 所使用的相同位置](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)中的資料。 如果您沒有 Microsoft Defender for Endpoint，會根據作用中 Microsoft 365 安全性服務的位置，自動選取新的資料中心位置。 選取的資料中心位置會顯示在螢幕上。

在 [Microsoft 365 的安全性中心] 中，選取 [**需要協助**]，以與 Microsoft 支援部門聯繫，以在不同的資料中心位置布建 Microsoft 365 Defender。

> [!NOTE]
> 過去，在歐洲同盟 (歐盟) 資料中心透過 Azure Defender 開啟時，會自動布建 Microsoft Defender for Endpoint。 Microsoft 365在相同的歐盟資料中心內，為了以這種方式在過去為端點布建的客戶，Defender 會自動布建。

### <a name="confirm-that-the-service-is-on"></a>確認服務已開啟

服務一旦佈建，它會新增：

- [事件管理](incidents-overview.md)
- [警示佇列](investigate-alerts.md)
- 用於管理[自動化調查和回應](m365d-autoir.md)的重要訊息中心
- [高級搜尋](advanced-hunting-overview.md) 功能
- 威脅分析

![Microsoft 365 security center 導覽窗格的圖像，具有 Microsoft 365 Defender 功能 ](../../media/overview-incident.png)
 *Microsoft 365 安全性中心與事件管理和其他 Microsoft 365 Defender 功能*

### <a name="getting-microsoft-defender-for-identity-data"></a>取得 Microsoft Defender 的身分識別資料 
若要啟用與 Microsoft Cloud App Security 的整合，您必須至少登入 Microsoft Cloud App Security 一次。

## <a name="get-assistance"></a>取得協助

若要取得有關開啟 Microsoft 365 Defender 的最常見問題的答案，請[參閱常見問題](m365d-enable-faq.md)。

Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。 如需協助，請選取 [Microsoft 365 的安全性中心] 中的 [**需要協助**]。 當您聯繫支援時，請提及 Microsoft 365 Defender。

## <a name="related-topics"></a>相關主題

- [常見問題集](m365d-enable-faq.md)
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [Microsoft 365Defender 概述](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint 簡介](../defender-endpoint/microsoft-defender-endpoint.md)
- [Office 365 的 Defender 概述](../office-365-security/defender-for-office-365.md)
- [Microsoft 雲端 App 安全性概觀](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender 身分識別概述](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpoint data storage](../defender-endpoint/data-storage-privacy.md)
