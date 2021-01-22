---
title: 在 Microsoft 365 資訊安全中心開啟 Microsoft 365 Defender
description: 瞭解如何啟用 Microsoft 365 Defender 並開始整合您的安全性事件和回應。
keywords: 開始使用，啟用 MTP，Microsoft Threat Protection， M365， 安全性， 資料位置， 必要的許可權， 授權資格， 設定頁面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930219"
---
# <a name="turn-on-microsoft-365-defender"></a>開啟 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) 整合了端點的 Microsoft Defender、Office 365 的 Microsoft Defender、Microsoft Cloud App 安全性及 Microsoft Defender 的身分識別等重要功能，以完成您的事件回應程式。 此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。

當具有所需許可權的合格客戶流覽 Microsoft 365 資訊安全中心時，Microsoft 365 Defender 會自動開啟。 請閱讀本文以瞭解各種先決條件，以及 Microsoft 365 Defender 的提供方式。

## <a name="check-license-eligibility-and-required-permissions"></a>檢查授權資格和必要的許可權

Microsoft 365 安全性產品授權通常可讓您在 Microsoft 365 安全性中心使用 Microsoft 365 Defender，而無需支付額外的授權成本。 建議您取得 Microsoft 365 E5、E5 安全性、A5 或 A5 安全性授權，或是提供所有支援服務存取權的有效授權組合。

有關授權的詳細資訊， [請閱讀授權需求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>檢查您的角色

您必須是 **Azure** Active Directory 中的全域系統管理員或安全性系統管理員，才能開啟 Microsoft 365 Defender。  [在 Azure AD 中查看您的角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支援服務

Microsoft 365 Defender 會匯總您部署的各種支援服務的資料。 它會集中處理和儲存資料，以識別新的深入見解，並盡可能讓集中式回應工作流程。 此功能不會影響現有的部署、設定，或與整合式服務相關聯的資料。

若要獲得最佳保護並優化 Microsoft 365 Defender，建議您在您的網路上部署所有適用的支援服務。 詳細資訊請參閱 [如何部署支援服務](deploy-supported-services.md)。

## <a name="before-starting-the-service"></a>在啟動服務之前

在您開啟服務之前，當您從功能窗格中選取了事件、控制中心或搜尋時，Microsoft 365 資訊安全中心 ([security.microsoft.com](https://security.microsoft.com)) 會顯示 Microsoft 365 **** Defender 設定頁面。  如果您不符合使用 Microsoft 365 Defender 資格，將不會顯示這些流覽專案。

![如果 Microsoft 365 資訊安全中心中未開啟 Microsoft 365 Defender 設定，則顯示的 ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender* 設定頁面圖像

## <a name="starting-the-service"></a>啟動服務

若要開啟 Microsoft 365 Defender，只要選取開啟 **Microsoft 365 Defender** 並申請變更。 您也可以選取流覽窗格中的 (security.microsoft.com/settings) 選項，[](https://security.microsoft.com/settings)然後選取 **Microsoft 365 Defender 來存取此選項**。 

> [!NOTE]
> 如果您在流覽 **窗格中看不到設定** 或無法存取頁面，請檢查您的許可權和授權。

### <a name="data-center-location"></a>資料中心位置

Microsoft 365 Defender 會儲存及處理與 Microsoft Defender for Endpoint 相同 [位置的資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。 如果您沒有 Microsoft Defender for Endpoint，就會根據使用中的 Microsoft 365 安全性服務位置自動選取新的資料中心位置。 畫面上會顯示選取的資料中心位置。

選取需要協助嗎？在 Microsoft 365 資訊安全中心中，與 Microsoft 支援服務聯繫，以在不同的資料中心位置提供 Microsoft 365 Defender。

> [!NOTE]
> 透過 Azure Defender 開啟時，Microsoft Defender for Endpoint (歐盟) 資料中心自動提供。 Microsoft 365 Defender 將針對已使用這種方式提供端點後置備的客戶，自動在同一個歐盟資料中心進行提供。

### <a name="confirm-that-the-service-is-on"></a>確認服務已開啟

服務一旦佈建，它會新增：

- [事件管理](incidents-overview.md)
- 用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心
- [進位搜尋](advanced-hunting-overview.md) 功能

![Microsoft 365 資訊安全中心流覽窗格的影像，以及具有事件管理和其他 ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender 功能的 Microsoft 365* 資訊安全中心功能

### <a name="getting-microsoft-defender-for-identity-data"></a>取得 Microsoft Defender 以取得身分識別資料

若要與 Microsoft 365 Defender 共用 Microsoft Defender 的身分識別資料，請確定已開啟 Microsoft Cloud App 安全性和身分識別整合的 Microsoft Defender。 [深入瞭解這項整合](https://docs.microsoft.com/cloud-app-security/mdi-integration)。

## <a name="get-assistance"></a>取得協助

若要取得有關開啟 Microsoft 365 Defender 的最常見問題的 [解答，請閱讀常見問題](mtp-enable-faq.md)。

Microsoft 支援人員可協助在租使用者上提供或取消提供服務及相關資源。 在 Microsoft  365 安全性中心中選取需要協助嗎？以尋求協助。 聯繫支援人員時，請提及 Microsoft 365 Defender。

## <a name="related-topics"></a>相關主題

- [常見問題集](mtp-enable-faq.md)
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [Microsoft 365 Defender 概觀](microsoft-threat-protection.md)
- [Microsoft Defender 端點概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 的 Defender 概觀](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概觀](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender 身分識別概觀](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [端點資料儲存的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
