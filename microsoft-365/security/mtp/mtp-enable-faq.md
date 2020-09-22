---
title: 開啟 Microsoft 威脅防護時的常見提問
description: 取得關於啟用 Microsoft 威脅防護的授權、許可權、初始設定及其他產品及服務的最常見問題的答案。
keywords: 常見問題解答、FAQ、GCC、入門、啟用 MTP、Microsoft 威脅防護、M365、安全性、資料位置、必要許可權、授權資格、設定頁面
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
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198836"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>開啟 Microsoft 威脅防護時的常見提問

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：****
- Microsoft 威脅防護

閱讀有關開啟 [Microsoft 威脅防護](microsoft-threat-protection.md)（包括要求的授權和許可權、部署支援服務及初始設定）最常見的常見問題的回應。

如需如何開啟服務的指示，請 [參閱開啟 Microsoft 威脅防護](mtp-enable.md)。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>我沒有 Microsoft 365 E5 授權。 我仍然可以使用 Microsoft 威脅防護嗎？

具有下列非 E5 授權的客戶可以使用 Microsoft 威脅防護：

- Microsoft Defender 進階威脅防護
- Azure 進階威脅防護
- Microsoft Cloud App Security
- Office 365 高級威脅防護 (方案 2) 
 
如需支援之授權的完整清單，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>我需要安裝或部署任何專案，即可開始使用 Microsoft 威脅防護？

否，Microsoft 威脅防護會合並您已部署之 Microsoft 365 安全性服務中的資料。 一旦將其開啟，事件、自動化和搜尋體驗便會開始在已部署產品的範圍內運作。 如果這些產品都未正確部署，則 Microsoft 威脅防護不會顯示任何資料，而且也無法採取任何動作。

為了優化您的 Microsoft 威脅防護體驗，建議您部署 *所有* 支援的 [microsoft 365 安全性產品和服務](deploy-supported-services.md)。

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Microsoft 威脅防護處理及儲存資料的位置為何？
Microsoft 威脅防護會自動選取資料中心的最佳位置，以進行合併資料的處理和儲存。 如果您有 Microsoft Defender ATP，它會選取 Microsoft Defender ATP 所使用的相同位置。

>[!NOTE]
>當透過 Azure Security Center 開啟時，Microsoft Defender ATP 會在歐盟 (歐盟) 資料中心。 在相同的歐盟資料中心，針對以這種方式布建 Microsoft Defender ATP 的客戶，會自動為其提供 microsoft 威脅防護。 

在 [設定] 頁面中，在 [microsoft 威脅防護] (**設定 > microsoft 威脅防護**) ] 中布建服務之前及之後都會顯示資料中心位置。 如果您想要使用另一個資料中心位置，請在 Microsoft 365 的安全性中心選取 [ **需要協助** ]，以與 Microsoft 支援人員聯繫。

## <a name="where-can-i-access-microsoft-threat-protection"></a>我可以在哪裡存取 Microsoft 威脅防護？

Microsoft 365 的安全性中心提供 microsoft 威脅防護。 若要移至 [安全性中心]，請流覽至 URL [https://security.microsoft.com](https://security.microsoft.com) 。

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>我需要哪些許可權才能存取 Microsoft 365 security center 中的 Microsoft 威脅防護？

指派下列 Azure Active Directory (AD) 角色的帳戶可存取 Microsoft 威脅防護功能和資料：

- 全域管理員
- 安全性系統管理員
- 安全性操作員
- 全域讀取者
- 安全性讀取者

>[!NOTE]
>Microsoft Defender ATP 中以角色為基礎的存取控制設定會影響資料的存取。 如需詳細資訊，請參閱 [管理 Microsoft 威脅防護的存取](mtp-permissions.md)。

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Microsoft 威脅防護預設為什麼時區？
根據預設，Microsoft 威脅防護會顯示 UTC 時區中的時間資訊。 您可以變更此設定以使用您的本機時區。 [瞭解如何設定時區](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>如何瞭解新的 Microsoft 威脅防護功能和 UI 更新？

Microsoft 定期透過各種管道提供資訊，包括：

- Microsoft 365 系統管理中心中的[郵件中心](../../admin/manage/message-center.md)
- [Microsoft 365 security & 合規性技術社區](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts

開啟 [預覽功能](preview.md)可取得最新的公開體驗。

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 威脅防護是否可用於美國政府社群雲端 (GCC) 或GCC High？
目前無法使用。

## <a name="related-topics"></a>相關主題

- [Microsoft 威脅防護更新概觀](microsoft-threat-protection.md)
- [開啟 Microsoft 威脅防護](mtp-enable.md)。
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [開啟預覽功能](preview.md)
