---
title: 建立指示器
ms.reviewer: ''
description: 建立檔案雜湊、IP 位址、URLs 或網域的指示器，以定義實體的偵測、預防和排除。
keywords: manage，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842239"
---
# <a name="create-indicators"></a>建立指示器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

 (IoCs) 相符的指示器是每個 endpoint protection 解決方案中的基本功能。 這項功能可讓 SecOps 設定標記清單以進行偵測，以及封鎖封鎖 (防護和回應) 。

建立指示器，以定義實體的偵測、預防和排除。 您可以定義要採取的動作，以及要套用動作的時間和裝置群組的範圍，以及要套用的動作。

目前支援的來源是用於 Defender for Endpoint 的雲端偵測引擎、自動調查和修正引擎，以及端點防護引擎 (Microsoft Defender 防毒軟體) 。

**雲端偵測引擎**<br>
Defender for Endpoint 的雲端偵測引擎會定期掃描收集的資料，並嘗試符合您設定的指示器。 當有相符時，會根據您為 IoC 所指定的設定採取動作。

**Endpoint 防護引擎**<br>
預防代理程式會接受相同的指示器清單。 也就是說，如果 Microsoft Defender AV 是設定的主要 AV，就會依照設定來處理相符的指示器。 例如，如果動作為 "警示和封鎖"，Microsoft Defender AV 會使檔案執行 (區塊和修正) ，且會引發對應的警示。 另一方面，如果動作設定為 "Allow"，Microsoft Defender AV 將不會偵測到或封鎖檔案執行。

**自動化調查和修正引擎**<BR>
自動調查和修正行為相同。 如果指示器設定為 "Allow"，則自動調查和修正功能將會忽略對它的「不良」判定。 如果設為 "封鎖"，自動化調查和修正會將其視為「不良」。

> [!NOTE]
> EnableFileHashComputation 設定會在檔掃描期間，計算憑證和檔案 IoC 的檔案雜湊。 它支援對散列和證書的強制執行屬於信任的應用程式。 它會同時使用 allow 或 block file 設定進行啟用與停用。 EnableFileHashComputation 是透過群組原則手動啟用，且預設為停用。


目前支援的動作如下：
- 允許
- 僅警示
- 警示和封鎖


您可以為下列專案建立指示器：
- [Files](indicator-file.md)
- [IP 位址、URLs/網域](indicator-ip-domain.md)
- [憑證](indicator-certificates.md)


> [!NOTE]
> 每個租使用者的指示器限制為15000。 檔案和憑證指示器不會封鎖[為 Microsoft Defender 防毒軟體定義的排除](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)專案。 Microsoft Defender 防毒軟體在被動模式中時，不支援指示器。 


## <a name="related-topics"></a>相關主題

- [建立上下文 IoC](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [使用 Microsoft Defender for Endpoint 指示器 API](ti-indicator.md)
- [使用夥伴整合解決方案](partner-applications.md)
