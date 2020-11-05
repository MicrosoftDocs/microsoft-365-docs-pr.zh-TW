---
title: 在 Microsoft 365 security center 中開啟 Microsoft 365 Defender
description: 瞭解如何啟用 Microsoft 365 Defender，並開始整合您的安全性事件與回應。
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
ms.openlocfilehash: c5b8cae9e4eabcb2b3c6a7eb76971784193a221d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920499"
---
# <a name="turn-on-microsoft-365-defender"></a>開啟 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) 整合您的事件回應程式，方法是在 microsoft Defender for Endpoint、microsoft Defender for Office 365、Microsoft Cloud App Security 和 microsoft Defender for Identity 中整合重要功能。 此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。

Microsoft 365 Defender 會在具備必要許可權的合格客戶造訪 Microsoft 365 的安全性中心時自動開啟。 請閱讀本文以瞭解各種必要條件，以及如何布建 Microsoft 365 Defender。

## <a name="check-license-eligibility-and-required-permissions"></a>檢查授權資格和必要許可權
Microsoft 365 安全性產品的授權一般會使您在 Microsoft 365 的安全性中心使用 Microsoft 365 Defender，而不需要額外授權成本。 我們建議您取得 Microsoft 365 E5、E5 或 A5 安全授權或有效的授權組合，以提供所有支援服務的存取權。

如需詳細的授權資訊，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>檢查您的角色
您必須是 **全域系統管理員** 或 Azure Active Directory 中的 **安全性系統管理員** ，才可開啟 Microsoft 365 Defender。 [在 Azure AD 中查看您的角色](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支援的服務
Microsoft 365 Defender 會匯總您已部署之各種支援服務的資料。 它會集中處理及儲存資料，以識別新的洞察力，並可讓集中式回應工作流程成為可能。 這樣做不會影響現有的部署、設定或與整合服務相關聯的資料。

若要取得最佳保護，並優化 Microsoft 365 Defender，我們建議在您的網路上部署所有適用的受支援服務。 如需詳細資訊，請 [參閱部署支援的服務](deploy-supported-services.md)。

## <a name="before-starting-the-service"></a>啟動服務之前
在您開啟服務之前，Microsoft 365 security center ( [security.microsoft.com](https://security.microsoft.com)) 會在您從功能窗格中選取 [ **事件** ]、[ **動作中心** ] 或 [ **搜尋** ] 時，顯示 [microsoft 365 Defender 設定] 頁面。 如果您不具備使用 Microsoft 365 Defender 的資格，就不會顯示這些流覽專案。

![Microsoft 365 Defender 尚未在 microsoft ](../../media/mtp-enable/mtp-settings.png)
 *365 security center 中開啟 Microsoft 365 defender 設定* 時所顯示之 microsoft 365 defender 設定頁面的圖像

## <a name="starting-the-service"></a>啟動服務
若要開啟 Microsoft 365 Defender，只要選取 [ **開啟 microsoft 365 defender** ] 並套用變更。 您也可以在功能窗格中選取 [ ( [security.microsoft.com/settings](https://security.microsoft.com/settings)) **設定** ]，然後選取 [ **microsoft 365 Defender** ]，即可存取此選項。

>[!NOTE]
>如果您在功能窗格中看不到 **設定** 或無法存取頁面，請檢查您的許可權和授權。

### <a name="data-center-location"></a>資料中心位置
Microsoft 365 Defender 會將資料儲存並處理于 [Microsoft Defender For Endpoint 所使用的相同位置](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。 如果您沒有 Microsoft Defender for Endpoint，會根據使用中 Microsoft 365 安全性服務的位置，自動選取新的資料中心位置。 選取的資料中心位置會顯示在螢幕上。 

在 Microsoft 365 的安全性中心中，選取 [ **需要協助** ]，以與 microsoft 支援部門聯繫，以在不同的資料中心位置布建 Microsoft 365 Defender。 

>[!NOTE]
>Microsoft Defender for Endpoint 會在歐盟 (歐盟透過 Azure Defender 開啟時) 資料中心。 Microsoft 365 Defender 會在相同的歐盟資料中心，針對以這種方式布建 Defender 的客戶自動布建。 

### <a name="confirm-that-the-service-is-on"></a>確認服務已開啟
服務一旦佈建，它會新增：

- [事件管理](incidents-overview.md)
- 用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心
- [高級搜尋](advanced-hunting-overview.md) 功能

![Microsoft 365 security center 導覽窗格與 Microsoft 365 Defender 的影像功能 ](../../media/mtp-enable/mtp-on.png)
 *microsoft 365 security center with 事件管理和其他 Microsoft 365 Defender 功能*

### <a name="getting-microsoft-defender-for-identity-data"></a>取得 Microsoft Defender 的身分識別資料
若要使用 Microsoft 365 Defender 共用 Microsoft Defender 的身分識別資料，請確定 Microsoft Cloud App Security 和 Microsoft Defender for Identity integration 已開啟。 [深入了解此整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a>關閉 Microsoft 365 Defender
若要停止使用 microsoft 365 defender，請 **Settings** 移至 microsoft  >  365 security center 中的設定 **Microsoft 365 Defender**  >  **加入宣告/自願退出** 。 取消選取 [ **開啟 Microsoft 365 Defender** ] 並套用變更。

對應的功能將會從 Microsoft 365 的安全性中心移除。

## <a name="get-assistance"></a>取得協助

若要取得有關開啟 Microsoft 365 Defender 的最常見問題的答案，請 [參閱常見問題](mtp-enable-faq.md)。

Microsoft 支援人員可協助您布建或取消設定租使用者上的服務和相關資源。 如需協助，請選取 [Microsoft 365 security center] 中的 [ **需要協助？** ]。 當您聯繫支援時，請提及 Microsoft 365 Defender。

## <a name="related-topics"></a>相關主題

- [常見問題集](mtp-enable-faq.md)
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [Microsoft 365 Defender 概述](microsoft-threat-protection.md)
- [Microsoft Defender for Endpoint 簡介](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [適用于 Office 的 Defender 365 簡介](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概觀](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender 身分識別概述](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpoint data storage](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
