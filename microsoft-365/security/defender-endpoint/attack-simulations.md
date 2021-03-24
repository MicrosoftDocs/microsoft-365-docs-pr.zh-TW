---
title: 透過模擬攻擊體驗 Microsoft Defender ATP
description: 執行提供的攻擊案例模擬，以體驗 Microsoft Defender ATP 如何偵測、調查和回應違規行為。
keywords: wdatp，test，案例，攻擊，模擬，模擬，diy，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 25538e1866db8f4a7bff24ac336005bf2e1ce78b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058768"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>透過模擬攻擊體驗 Microsoft Defender for Endpoint 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- 深入瞭解 Microsoft Defender ATP 中的最新增強功能： [用於端點的 Defender 新增功能？](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)。
>- 在最近的 MITRE 評估中，以試用版的端點示範業界一流的光學器件和偵測功能。 Read： [來自 MITRE ATT 的 Insights&以 CK 為基礎的評估](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。

您可能想要在將許多裝置上架到服務之前，體驗端點的 Defender。 若要這麼做，您可以在一些測試裝置上執行受控制的攻擊模擬。 在執行模擬後的攻擊之後，您可以查看 Endpoint 的 Endpoint 面對惡意活動的反應，以及如何啟用有效的回應。

## <a name="before-you-begin"></a>開始之前

若要執行提供的任何模擬，您至少需要 [一個架裝置](onboard-configure.md)。 

閱讀每個攻擊案例中提供的逐步檔。 每個檔都包括作業系統和應用程式需求，以及針對攻擊案例的詳細指示。

## <a name="run-a-simulation"></a>執行模擬

1. 在 **[** 說明  >  **模擬 & 教學** 課程] 中，選取您要模擬的哪個可用攻擊案例：

   - **案例1：檔丟掉後門** -模擬 socially 工程的引誘檔的傳遞。 檔會啟動巧盡心思的後門，可提供駭客控制權。

   - **案例2： fileless 進攻中的 PowerShell 腳本** -模擬 fileless 攻擊，其受 PowerShell、showcasing 攻擊面不足和裝置教育偵測惡意記憶體活動的偵測。
    
   - **案例3：自動化事件回應** -觸發自動調查，它會自動 hunts 及 remediates 違犯的專案，以調整您的事件回應容量。

2. 下載並閱讀您所選案例中提供的對應逐步檔。

3. 流覽以 **協助**  >  **模擬 & 教學** 課程，以下載模擬檔案或複製類比腳本。 您可以選擇在測試裝置上下載檔案或腳本，但這不是必要的。

4. 依照練習檔中的指示，在測試裝置上執行類比檔或腳本。

> [!NOTE]
> 類比檔或腳本模仿攻擊活動，但實際上卻是良性的，且不會損害或損害測試裝置。
> 
> 
> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>相關主題

- [板載裝置](onboard-configure.md)
- [板載 Windows 10 裝置](configure-endpoints.md)
