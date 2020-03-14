---
title: 在 Microsoft 365 安全性中心中開啟 Microsoft 威脅防護
description: 了解如何啟用 Microsoft 威脅防護，並開始整合您的安全性事件和回應。
keywords: 開始使用，啟用 MTP，Microsoft 威脅防護，M365，安全性，資料位置，必要許可權，授權資格，設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: fa970b28939ad43bf6a2717e603013277bc9130f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633901"
---
# <a name="turn-on-microsoft-threat-protection"></a>開啟 Microsoft 威脅防護

**適用於：**
- Microsoft 威脅防護

Microsoft 威脅防護整合了您的事件回應流程，方法是整合跨 Microsoft Defender 進階威脅防護 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的重要功能。 此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。

若要取得最佳保護，並優化 Microsoft 威脅防護，我們建議您在網路上部署所有適用的受支援服務。 如需詳細資訊，請[參閱部署支援的服務](deploy-supported-services.md)。

## <a name="check-license-eligibility-and-required-permissions"></a>檢查授權資格和必要許可權
Microsoft 365 E5，E5 Security，or A5 授權或有效的授權組合，可提供支援服務的存取權，並可讓您在 Microsoft 365 安全性中心使用 Microsoft 威脅防護。

如需詳細的授權資訊，請[閱讀授權要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>檢查您的角色
您必須是**全域系統管理員**或 Azure Active Directory 中的**安全性系統管理員**，才可開啟 Microsoft 威脅防護。 [在 Azure AD 中查看您的角色](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>開始使用服務
Microsoft 威脅防護會匯總各種整合服務中的資料。 它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。

在您開啟服務之前，當您從功能窗格中選取 [**事件**]、[**動作中心**] 或 [**搜尋**] 時，microsoft 365 安全中心（[security.microsoft.com](https://security.microsoft.com)）會顯示 microsoft 威脅防護歡迎頁面。 如果您不具備使用 Microsoft 威脅防護的資格，就不會顯示這些流覽選項。

![顯示 microsoft](../../media/mtp-welcome.png)
*365 security center 中*microsoft 威脅防護歡迎頁面上的 microsoft 威脅防護功能，顯示 microsoft 威脅防護歡迎頁面的圖像

若要開啟 Microsoft 威脅防護，只需從歡迎頁面完成此程式。 您也可以在功能窗格中存取**設定**（[security.microsoft.com/settings](https://security.microsoft.com/settings)），並選取 [ **microsoft 威脅防護**]，以開啟 microsoft 威脅防護。

>[!NOTE]
>如果您在功能窗格中看不到**設定**或無法存取頁面，請檢查您的許可權和授權。

### <a name="select-data-center-location"></a>選取資料中心位置
如果已為您的組織佈建 Microsoft Defender ATP，則資料將會儲存在為[您的 Microsoft Defender ATP 資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)選取的相同資料中心位置中。 如果您沒有 Microsoft Defender ATP，系統會要求您選擇專用於 Microsoft 威脅防護的新資料中心位置。 

您必須先提供同意，才可在服務和匯總間共用資料。

### <a name="confirm-that-the-service-is-on"></a>確認服務已開啟
服務一旦佈建，它會新增：

- [事件管理](incidents-overview.md)
- 用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心
- [高級搜尋](advanced-hunting-overview.md)功能

![Microsoft 365 security center 導覽窗格與 microsoft 威脅防護的影像功能](../../media/mtp-on.png)
*microsoft 365 security center with 事件管理和其他 Microsoft 威脅防護功能*

### <a name="getting-azure-atp-data"></a>取得 Azure ATP 資料
若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。 [深入了解此整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>關閉 Microsoft 威脅防護
若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]****  >  [Microsoft 威脅防護]****  >  [選擇加入/選擇退出]****。 取消選取 [開啟 Microsoft 威脅防護]**** 並儲存變更。

對應的功能將會從 Microsoft 365 的安全性中心移除。

## <a name="get-assistance"></a>取得協助

Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。 如需協助，請選取 [Microsoft 365 security center] 中的 [**需要協助？** ]。 當您聯繫支援時，請提及 Microsoft 威脅防護。

## <a name="related-topics"></a>相關主題

- [Microsoft 威脅防護更新概觀](microsoft-threat-protection.md)
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [Microsoft Defender ATP 概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概觀](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概觀](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概觀](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP 資料儲存](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
