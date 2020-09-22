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
ms.openlocfilehash: 65e3a2609bc41ddeda95134874e5873e184a2a54
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201156"
---
# <a name="turn-on-microsoft-threat-protection"></a>開啟 Microsoft 威脅防護

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 威脅防護

[Microsoft 威脅防護](microsoft-threat-protection.md) 會整合您的事件回應程式，方法是在 Microsoft Defender 高級威脅防護 (ATP) 、OFFICE 365 ATP、Microsoft Cloud App Security 和 Azure ATP 間整合重要功能。 此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。

當具有必要許可權的合格客戶具備必要365許可權時，microsoft 威脅防護即會自動開啟。 請閱讀本文以瞭解各種必要條件，以及如何布建 Microsoft 威脅防護。

## <a name="check-license-eligibility-and-required-permissions"></a>檢查授權資格和必要許可權
Microsoft 365 安全性產品的授權一般會使您在 Microsoft 365 的安全性中心使用 Microsoft 威脅防護，而不需要額外授權成本。 我們建議您取得 Microsoft 365 E5、E5 或 A5 安全授權或有效的授權組合，以提供所有支援服務的存取權。

如需詳細的授權資訊，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>檢查您的角色
您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員** ，才可開啟 Microsoft 威脅防護。 [在 Azure AD 中查看您的角色](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支援的服務
Microsoft 威脅防護會匯總您已部署之各種支援服務的資料。 它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。 這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。

若要取得最佳保護，並優化 Microsoft 威脅防護，我們建議您在網路上部署所有適用的受支援服務。 如需詳細資訊，請 [參閱部署支援的服務](deploy-supported-services.md)。

## <a name="before-starting-the-service"></a>啟動服務之前
在您開啟服務之前，Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)) 會顯示 [Microsoft 威脅防護設定] 頁面，當您從功能窗格中選取 [ **事件**]、[ **動作中心**] 或 [ **搜尋** ]。 如果您不具備使用 Microsoft 威脅防護的資格，就不會顯示這些流覽專案。

![Microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 security center 中*未開啟 microsoft 威脅防護設定時所顯示之 microsoft 威脅防護設定頁面的圖像

## <a name="starting-the-service"></a>啟動服務
若要開啟 Microsoft 威脅防護，只要選取 [ **開啟 Microsoft 威脅防護** ] 並套用變更。 您也可以在功能窗格中選取 [ ([security.microsoft.com/settings](https://security.microsoft.com/settings)) **設定**]，然後選取 [ **microsoft 威脅防護**]，即可存取此選項。

>[!NOTE]
>如果您在功能窗格中看不到 **設定** 或無法存取頁面，請檢查您的許可權和授權。

### <a name="data-center-location"></a>資料中心位置
Microsoft 威脅防護會儲存和處理 [Microsoft DEFENDER ATP 使用的相同位置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)的資料。 如果您沒有 Microsoft Defender ATP，會根據使用中 Microsoft 365 安全性服務的位置，自動選取新的資料中心位置。 選取的資料中心位置會顯示在螢幕上。 

在 Microsoft 365 的安全性中心中，選取 [ **需要協助** ]，以與 microsoft 支援人員聯繫，以在不同的資料中心位置提供 Microsoft 威脅防護。 

>[!NOTE]
>當透過 Azure Security Center 開啟時，Microsoft Defender ATP 會在歐盟 (歐盟) 資料中心。 在相同的歐盟資料中心，針對以這種方式布建 Microsoft Defender ATP 的客戶，會自動為其提供 microsoft 威脅防護。 

### <a name="confirm-that-the-service-is-on"></a>確認服務已開啟
服務一旦佈建，它會新增：

- [事件管理](incidents-overview.md)
- 用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心
- [高級搜尋](advanced-hunting-overview.md) 功能

![Microsoft 365 security center 導覽窗格與 Microsoft 威脅防護的影像功能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 威脅防護功能*

### <a name="getting-azure-atp-data"></a>取得 Azure ATP 資料
若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。 [深入了解此整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>關閉 Microsoft 威脅防護
若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]****  >  [Microsoft 威脅防護]****  >  [選擇加入/選擇退出]****。 取消選取 [ **開啟 Microsoft 威脅防護** ]，然後套用變更。

對應的功能將會從 Microsoft 365 的安全性中心移除。

## <a name="get-assistance"></a>取得協助

若要取得有關開啟 Microsoft 威脅防護最常見的常見問題的答案，請 [參閱常見問題](mtp-enable-faq.md)。

Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。 如需協助，請選取 [Microsoft 365 security center] 中的 [ **需要協助？** ]。 當您聯繫支援時，請提及 Microsoft 威脅防護。

## <a name="related-topics"></a>相關主題

- [常見問題集](mtp-enable-faq.md)
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [Microsoft 威脅防護更新概觀](microsoft-threat-protection.md)
- [Microsoft Defender ATP 概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概觀](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概觀](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概觀](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP 資料儲存](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
