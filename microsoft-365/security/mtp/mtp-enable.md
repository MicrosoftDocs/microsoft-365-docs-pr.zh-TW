---
title: 在 Microsoft 365 安全性中心中開啟 Microsoft 威脅防護
description: 了解如何啟用 Microsoft 威脅防護，並開始整合您的安全性事件和回應。
keywords: 快速入門，啟用 MTP、 Microsoft 威脅防護、 M365、 安全性、 資料位置、 必要權限、 授權資格、 設定] 頁面
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
ms.openlocfilehash: 73c4c9864713432d318b0b3cec9fbaf395deff45
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374142"
---
# <a name="turn-on-microsoft-threat-protection"></a>開啟 Microsoft 威脅防護

**適用於：**
- Microsoft 威脅防護

Microsoft 威脅防護整合了您的事件回應流程，方法是整合跨 Microsoft Defender 進階威脅防護 (ATP)、Office 365 ATP、Microsoft Cloud App Security 和 Azure ATP 的重要功能。 此整合體驗會新增您可以在 Microsoft 365 安全性中心存取的強大功能。

若要取得最佳的保護，並最佳化 Microsoft 威脅防護，我們建議部署您的網路上所有適用的支援的服務。 如需詳細資訊，[了解部署支援的服務](deploy-supported-services.md)。

## <a name="check-license-eligibility-and-required-permissions"></a>請檢查授權資格及必要的權限
Microsoft 365 E5、 E5 安全性、 A5 或 A5 安全性授權或有效的授權組合提供支援的服務和賦與您使用 Microsoft 威脅防護 Microsoft 365 安全性中心存取權。

如需詳細的授權資訊，[請閱讀授權需求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>請檢查您的角色
您必須是**全域系統管理員**或 Azure Active Directory，以開啟 [Microsoft 威脅防護中的**安全性系統管理員**。 [在 Azure AD 中檢視您的角色](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>開始使用服務
Microsoft 威脅防護彙總資料從各種的整合式服務。 它會處理程序，並儲存資料集中以識別新的深入資訊，並讓集中式的回應系統工作流程。

開啟服務之前，請在 Microsoft 365 安全性中心 ([security.microsoft.com](https://security.microsoft.com)) 當您從功能窗格中選取 [**事件**]、 [**重要訊息中心**] 或 [**狩獵**，就會顯示 Microsoft 威脅防護歡迎使用] 頁面。 這些導覽選項不會顯示是否您不可以使用 Microsoft Threat Protection。

![顯示 Microsoft 威脅防護是否尚未開啟的 Microsoft 威脅防護歡迎頁面的影像](../../media/mtp-welcome.png)
*Microsoft 威脅防護歡迎使用 Microsoft 365 安全性中心] 頁面*

若要開啟 Microsoft 威脅防護，只要完成從 [歡迎] 頁面上的程序。 您也可以開啟 Microsoft 威脅防護，功能窗格中存取**的設定**([security.microsoft.com/settings](https://security.microsoft.com/settings))，然後選取**Microsoft Threat Protection**。

>[!NOTE]
>如果您沒有看到**設定**功能窗格中，或無法存取] 頁面上，檢查您的權限和授權。

### <a name="select-data-center-location"></a>選取的資料中心位置
如果已為您的組織佈建 Microsoft Defender ATP，則資料將會儲存在為[您的 Microsoft Defender ATP 資料](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)選取的相同資料中心位置中。 如果您沒有 Microsoft Defender ATP，系統會要求您選擇專用於 Microsoft 威脅防護的新資料中心位置。 

您必須提供同意才能服務之間共用和彙總資料。

### <a name="confirm-that-the-service-is-on"></a>確認服務已開啟
服務一旦佈建，它會新增：

- [事件管理](incidents-overview.md)
- 用於管理[自動化調查和回應](mtp-autoir.md)的重要訊息中心
- [進階狩獵](advanced-hunting-overview.md)功能

![Microsoft 365 安全性中心與 Microsoft Threat Protection 功能的導覽窗格影像](../../media/mtp-on.png)
*Microsoft 365 安全性中心事件管理和其他 Microsoft 威脅防護功能*

### <a name="getting-azure-atp-data"></a>取得 Azure ATP 資料
若要使用 Microsoft 威脅防護共用 Azure ATP 資料，請確認已開啟 Microsoft Cloud App Security 和 Azure ATP 整合。 [深入了解此整合](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>關閉 Microsoft 威脅防護
若要停止使用 Microsoft 威脅防護，請移至 Microsoft 365 安全性中心的 [設定]****  >  [Microsoft 威脅防護]****  >  [選擇加入/選擇退出]****。 取消選取 [開啟 Microsoft 威脅防護]**** 並儲存變更。

對應的功能將會移除在 Microsoft 365 安全性中心。

## <a name="get-assistance"></a>取得協助

Microsoft 支援人員可以幫助佈建或 deprovision 之服務與相關的資源上您的租用戶。 如需協助，請選取 [**需要協助嗎？** Microsoft 365 安全性中心。 連絡支援時, 提及 Microsoft Threat Protection。

## <a name="related-topics"></a>相關主題

- [Microsoft 威脅防護更新概觀](microsoft-threat-protection.md)
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援的服務](deploy-supported-services.md)
- [Microsoft Defender ATP 概觀](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 概觀](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 概觀](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 概觀](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP 資料儲存](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
