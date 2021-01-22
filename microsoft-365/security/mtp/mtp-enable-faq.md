---
title: 開啟 Microsoft 365 Defender 時常見問題
description: 取得授權、許可權、初始設定，以及其他與啟用 Microsoft 365 Defender 相關產品和服務的常見問題解答
keywords: 常見問題， 常見問題， GCC， 快速入門， 啟用 MTP， Microsoft Threat Protection， M365， 安全性， 資料位置， 必要的許可權， 授權資格， 設定頁面
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
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930183"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>開啟 Microsoft 365 Defender 時常見問題

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

閱讀有關開啟 [Microsoft 365 Defender](microsoft-threat-protection.md)的最常見問題的回復，包括必要的授權與許可權、部署支援服務，以及初始設定。

有關如何開啟服務的指示，請參閱開啟 Microsoft [365 Defender。](mtp-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>我沒有 Microsoft 365 E5 授權。 我是否仍可以使用 Microsoft 365 Defender？

擁有下列非 E5 授權的客戶可以使用 Microsoft 365 Defender：

- 適用於端點的 Microsoft Defender
- 適用於身分識別的 Microsoft Defender
- Microsoft Cloud App Security
- Office 365 方案 2 (的後) 
 
有關支援授權的完整清單， [請閱讀授權需求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>我是否需要安裝或部署任何專案，以開始使用 Microsoft 365 Defender？

否，Microsoft 365 Defender 會合並您部署之 Microsoft 365 安全性服務的資料。 開啟之後，事件、自動化和尋找體驗就會在部署的產品範圍內開始工作。 如果這些產品未正確部署，Microsoft 365 Defender 將不會顯示任何資料，且無法執行任何動作。

若要優化您的 Microsoft 365 Defender 體驗，建議您部署所有支援的[Microsoft 365 安全性產品和服務](deploy-supported-services.md)。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender 會處理和儲存我的資料在哪裡？
Microsoft 365 Defender 會自動為處理及儲存合併資料的資料中心選取最佳位置。 如果您有 Microsoft Defender for Endpoint，它會選取由 Defender for Endpoint 使用的相同位置。

>[!NOTE]
>透過 Azure Defender 開啟時，Microsoft Defender for Endpoint (歐盟) 資料中心自動提供。 Microsoft 365 Defender 將針對以這種方式提供 Microsoft Defender for Endpoint 的客戶，自動在同一個歐盟資料中心進行提供。 

在 Microsoft 365 Defender 的設定頁面提供 Microsoft 365 Defender (設定> **Microsoft 365 Defender**) 之前和之後，會顯示資料中心位置。 如果您想要使用另一個資料中心位置，請在 Microsoft  365 安全性中心中選取需要協助嗎？以與 Microsoft 支援服務聯繫。

## <a name="where-can-i-access-microsoft-365-defender"></a>我可以在哪裡存取 Microsoft 365 Defender？

Microsoft 365 資訊安全中心提供 Microsoft 365 Defender。 若要前往資訊安全中心，請流覽至 [https://security.microsoft.com](https://security.microsoft.com) URL。

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>我需要哪些許可權才能存取 Microsoft 365 資訊安全中心的 Microsoft 365 Defender？

指派有下列 Azure Active Directory 帳戶 (AD) 角色可以存取 Microsoft 365 Defender 功能和資料：

- 全域管理員
- 安全性系統管理員
- 安全性操作員
- 全域讀取者
- 安全性讀取者

>[!NOTE]
>Microsoft Defender for Endpoint 中的角色型存取控制設定會影響資料的存取。 詳細資訊請參閱管理 Microsoft [365 Defender](mtp-permissions.md)存取權。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 Defender 預設為什麼時區？
根據預設，Microsoft 365 Defender 會以 UTC 時區顯示時間資訊。 您可以將此設定變更為使用您的當地時區。 [瞭解如何設定時區](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>如何瞭解新的 Microsoft 365 Defender 功能與 UI 更新？

Microsoft 會定期透過各種通道提供資訊，包括：

- Microsoft [](../../admin/manage/message-center.md) 365 系統管理中心的訊息中心
- [Microsoft 365 安全性與&技術社群中的部落格文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

開啟預覽功能，以取得最新的 [公開體驗](preview.md)。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender 是否適用于美國政府社群雲端服務 (GCC) GCC High？
目前無法使用。

## <a name="related-topics"></a>相關主題

- [Microsoft 365 Defender 概觀](microsoft-threat-protection.md)
- [開啟 Microsoft 365 Defender。](mtp-enable.md)
- [授權需求和其他必要條件](prerequisites.md)
- [部署支援服務](deploy-supported-services.md)
- [開啟預覽功能](preview.md)
