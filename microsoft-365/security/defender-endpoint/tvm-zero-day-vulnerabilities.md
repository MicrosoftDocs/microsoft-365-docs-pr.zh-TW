---
title: 減少零天的漏洞-威脅與弱點管理
description: 瞭解如何透過威脅與弱點管理找出並減少環境中的零天弱點。
keywords: Microsoft Defender for Endpoint tvm day 弱點，tvm，威脅 & 弱點管理，零天，0天，緩解0天的漏洞，易受攻擊的 CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538768"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a>減少零天的漏洞-威脅與弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅及弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

零一天的弱點是公開披露的弱點，尚未發行任何正式的修補程式或安全性更新。 零天的漏洞通常會有高嚴重性層級，並主動加以利用。

威脅和弱點管理只會顯示其相關資訊的零天弱點。

## <a name="find-information-about-zero-day-vulnerabilities"></a>尋找零天弱點的相關資訊

在找到零天的弱點後，就會透過 Microsoft Defender 資訊安全中心中的下列體驗來傳達相關資訊。

>[!NOTE]
> 0天功能目前不適用於非 Windows 產品 (Mac，Linux) ;不過，它會在未來新增。

### <a name="threat-and-vulnerability-management-dashboard"></a>威脅與弱點管理儀表板

在「最高安全性建議」卡片中尋找含零天標記的建議。

![使用零日標記的主要建議。](images/tvm-zero-day-top-security-recommendations.png)

在「有缺陷的軟體」卡片中尋找最主要的軟體（含零天標記）。

![具有零日標籤的常見漏洞軟體。](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a>弱點頁面

尋找名為零天的弱點，以及描述和詳細資料。

- 如果此弱點已指派 CVE 識別碼，您會在 CVE 名稱旁看到零天標籤。

- 如果此弱點未指派 CVE 識別碼，您可以在外觀為 "TVM-XXXX" 的內部暫時名稱下找到該漏洞。 在指派官方 CVE 識別碼後，就會更新此名稱，但先前的內部名稱仍可供搜尋，而且會在側面面板中找到。

![CVE-2020-17087 在弱點頁面中的零日範例。](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a>軟體庫存頁面

尋找含零天標記的軟體。 依 "zero day" 標記篩選，只查看含零天漏洞的軟體。

![在 [軟體庫存] 頁面中 Windows Server 2016 的零日範例。](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a>軟體頁面

針對每個受到零天弱點影響的軟體，尋找零天標記。

![Windows Server 2016 軟體] 頁面提供零日範例。](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a>安全性建議頁面

查看有關修復和緩解選項的明確建議，包括其存在的變通方法。 依 "zero day" 標記篩選，只請參閱解決零天弱點的安全性建議。

如果有軟體有零天弱點，還有其他弱點可解決，您就會對所有的漏洞取得一個建議。

![在 [安全性建議] 頁面中 Windows Server 2016 的零日範例。](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a>解決零天的漏洞

移至 [安全性建議] 頁面，並選取一個零一天的建議。 快顯視窗將會開啟，其中會顯示零天的資訊以及該軟體的其他弱點。

如果有可供使用的緩解選項和方法，將會有連結。 您可以在部署修補程式或安全性更新之前，避免此零天數弱點帶來的風險。

開啟修復選項，然後選擇 [注意] 類型。 因為尚未發行更新，所以建議使用「注意事項」修復選項，以取得零天的漏洞。 因為沒有要執行的特定動作，所以您無法選取到期日。 如果您想要修正此軟體舊版的漏洞，您可以覆寫「注意必要」修復選項，然後選擇「更新」。

![在 [安全性建議] 頁面中 Windows Server 2016 的零天浮出的範例。](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a>追蹤零天的修復活動

移至「威脅與弱點管理[修復](tvm-remediation.md)」頁面，以查看修正活動專案。 如果您選擇「注意必要」修復選項，則不會有任何進度列、票證狀態或到期日，因為我們沒有任何實際的動作可供監視。 您可以依修正類型進行篩選，例如「軟體更新」或「注意事項」，以查看相同類別中的所有活動專案。

## <a name="patching-zero-day-vulnerabilities"></a>修補零天弱點

當您在零天內發行修補程式時，建議會變更為「更新」，並在它旁顯示「新安全性更新天」的藍色標籤。 它將不再視為零一天，將從所有頁面移除零天標記。

![「以新的修補程式標籤更新 Microsoft Windows 10」的建議。](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a>相關文章

- [威脅與弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [儀表板](tvm-dashboard-insights.md)
- [安全性建議](tvm-security-recommendation.md)
- [軟體庫存](tvm-software-inventory.md)
- [我組織中的弱點](tvm-weaknesses.md)
