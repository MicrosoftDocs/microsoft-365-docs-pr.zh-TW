---
title: 開啟 Microsoft 365 Defender 時的常見提問
description: 取得關於啟用 Microsoft 365 Defender 相關授權、許可權、初始設定及其他產品及服務的最常見問題的答案。
keywords: 常見問題解答、常見問題、GCC、入門、啟用 Microsoft 365 Defender、Microsoft 365 Defender、M365、安全性、資料位置、必要許可權、授權資格、設定頁面
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
ms.openlocfilehash: 1ba049e9fe608ba8bd559180c5a30060b10ee9e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285982"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>開啟 Microsoft 365 Defender 時的常見提問

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

閱讀有關開啟[Microsoft 365 Defender](microsoft-365-defender.md)的最常見問題的回應，包括所需的授權和許可權、部署支援服務，以及初始設定。

如需如何開啟服務的指示，請[參閱開啟 Microsoft 365 Defender](m365d-enable.md)。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>我沒有 Microsoft 365 E5 授權。 我仍然可以使用 Microsoft 365 Defender 嗎？

具有下列非 E5 授權的客戶可以使用 Microsoft 365 Defender：

- 適用於端點的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender
- Microsoft Cloud App Security
- 適用於 Office 365 的 Defender (方案 2)

如需支援之授權的完整清單，請 [閱讀授權要求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>若要開始使用 Microsoft 365 Defender，是否需要安裝或部署任何專案？

否，Microsoft 365 Defender 會合並您已部署 Microsoft 365 安全性服務的資料。 一旦將其開啟，事件、自動化和搜尋體驗便會開始在已部署產品的範圍內運作。 如果這些產品皆未適當部署，Microsoft 365 Defender 將不會顯示任何資料，而且也無法採取任何動作。

為了優化您的 Microsoft 365 Defender 體驗，建議您部署 *所有* 支援的 [Microsoft 365 安全產品和服務](deploy-supported-services.md)。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender 處理及儲存資料的位置為何？

Microsoft 365 Defender 會自動選取資料中心的最佳位置，以進行合併資料的處理和儲存。 如果您有 Microsoft Defender for Endpoint，它會選取用來進行終結點的 Defender 所用的相同位置。

>[!NOTE]
>Microsoft Defender for Endpoint 會在歐盟 (歐盟透過 Azure Defender 開啟時) 資料中心。 在相同的歐盟資料中心內，為以這種方式布建 Microsoft Defender for Endpoint 的客戶，Microsoft 365 Defender 會自動布建。

在 Microsoft 365 Defender (**設定 > Microsoft 365 Defender**) 的 [設定] 頁面中布建服務之前及之後都會顯示資料中心位置。 如果您想要使用另一個資料中心位置，請在 Microsoft 365 的安全性中心選取 [**需要協助**]，以聯繫 Microsoft 支援部門。

## <a name="where-can-i-access-microsoft-365-defender"></a>我可以在哪裡存取 Microsoft 365 Defender？

Microsoft 365 Defender 可用於 Microsoft 365 的安全性中心。 若要移至 [安全性中心]，請流覽至 URL <https://security.microsoft.com> 。

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>在 Microsoft 365 安全中心存取 Microsoft 365 Defender 需要哪些許可權？

指派下列 Azure Active Directory (Azure AD) 角色可以存取 Microsoft 365 Defender 功能和資料的帳戶：

- 全域管理員
- 安全性系統管理員
- 安全性操作員
- 全域讀取者
- 安全性讀取者

> [!NOTE]
> Microsoft Defender for Endpoint 中以角色為基礎的存取控制設定會影響資料的存取。 如需詳細資訊，請參閱[管理 Microsoft 365 Defender 的存取](m365d-permissions.md)。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 Defender 預設值為哪個時區？

根據預設，Microsoft 365 Defender 會在 UTC 時區內顯示時間資訊。 您可以變更此設定以使用您的本機時區。 [瞭解如何設定時區](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>如何瞭解新的 Microsoft 365 Defender 功能和 UI 更新？

Microsoft 定期透過各種管道提供資訊，包括：

- Microsoft 365 系統管理中心中的[郵件中心](../../admin/manage/message-center.md)
- [Microsoft 365 security & 規範技術社區](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的 Blogposts

開啟 [預覽功能](preview.md)可取得最新的公開體驗。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender 可供我們政府社群雲端 (GCC) 或 GCC 高？

目前無法使用。

## <a name="related-topics"></a>相關主題

- [Microsoft 365 Defender 概述](microsoft-365-defender.md)
- [開啟 Microsoft 365 Defender](m365d-enable.md)。
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [開啟預覽功能](preview.md)
