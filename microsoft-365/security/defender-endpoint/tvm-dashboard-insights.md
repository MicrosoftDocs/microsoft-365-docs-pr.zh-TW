---
title: 儀表板深入資訊-威脅與弱點管理
description: 威脅與弱點管理儀表板可協助 SecOps 及安全性系統管理員解決 cybersecurity 威脅，並建立其組織的安全性恢復能力。
keywords: microsoft defender for endpoint tvm，microsoft defender for endpoint tvm 儀表板，威脅 & 弱點管理，威脅與弱點管理，以風險為基礎的威脅 & 弱點管理，安全性設定，Microsoft 安全評分的裝置，披露分數
search.appverid: met150
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 82b6123a99eb406918708c6bf23b870ef3bc3d79
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934138"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>儀表板深入資訊-威脅與弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅及弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

威脅和弱點管理是 Endpoint 的 Defender 元件，並提供安全性管理員和具有唯一值的安全性作業小組，包括：


- 即時端點偵測和回應（EDR）深入資訊與端點漏洞相關聯
- 事件調查期間的寶貴裝置弱點內容
- 透過 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 內建的修復程式  
  
您可以使用[Microsoft Defender 資訊安全中心](https://securitycenter.windows.com/)中的威脅與弱點管理功能來：

- 查看裝置的披露分數和 Microsoft 安全分數，以及最上層的安全性建議、軟體弱點、修復活動及公開的裝置
- 將 EDR 洞察力與端點漏洞關聯，並加以處理
- 選取修正選項，以會審及追蹤修正任務
- 選取例外狀況選項及追蹤作用中例外狀況

> [!NOTE]
> 在過去30天內非使用中的裝置，不會考慮反映組織威脅與弱點管理公開分數和裝置的 Microsoft 安全分數的資料。

觀賞這段影片，快速流覽威脅與弱點管理儀表板中的內容。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>威脅與弱點管理儀表板

 ![Microsoft Defender for Endpoint 入口網站](images/tvm-dashboard-devices.png)

區域 | 描述
:---|:---
**選取的裝置群組 ( #/# )**   | 篩選您想要在儀表板和卡片依設備群組查看的威脅與弱點管理資料。 您在篩選中選取的專案會套用到整個威脅與弱點管理頁面。
[**暴險分數**](tvm-exposure-score.md)   | 請參閱貴組織裝置對威脅及弱點的影響的目前狀態。 有許多因素會影響組織的暴露分數：在裝置中發現的弱點、裝置的可能性遭到破壞、組織中的裝置價值，以及您的裝置發現的相關警示。 目標是降低組織的暴露分數，使其更加安全。 若要降低分數，您需要修正安全性建議中所列的相關安全性設定問題。
[**裝置用 Microsoft 安全分數**](tvm-microsoft-secure-score-devices.md) | 請參閱您組織的作業系統、應用程式、網路、帳戶及安全性控制的安全性狀況。 目標是修正相關的安全性設定問題，以提升裝置的排名。 選取這些條將會帶您前往 [ **安全性建議** ] 頁面。
**裝置洩密分配** | 瞭解有多少裝置會根據其公開層級公開。 選取 [環圈圖] 中的區段，以移至 [ **裝置] 清單** 頁面，並查看受影響的裝置名稱、暴露層級、風險層級，以及其他詳細資料，例如網域、作業系統平臺、其健康狀態、最後一次看到的時間，以及其標記。
**主要安全性建議** | 請查看排序後的安全性建議，其排序及設定優先順序取決於組織的風險危險性及其所需的緊迫程度。 選取 [ **顯示更多** ]，以查看清單中的其餘安全性建議。 選取 [ **顯示例外** 狀況，列出例外狀況] 的建議。
**最常見的漏洞軟體** | 透過網路裝置上安裝的易受攻擊的軟體清單清單，即時瞭解貴組織的軟體清查，以及這些電腦對組織公開分數的影響。 選取專案以取得詳細資料，或 **顯示更多內容** ，以查看 [ **軟體清查** ] 頁面中的其他有隱患的軟體清單。
**主要修復活動** | 追蹤安全性建議所產生的修復活動。 您可以選取清單中的每個專案，以查看 **修正** 頁面中的詳細資料，或選取 [ **顯示更多** ]，以查看其餘的修復活動和作用中例外狀況。
**主要公開裝置** | 查看已公開的裝置名稱和其公開層級。 從清單中選取裝置名稱，以移至 [裝置] 頁面，您可以在此頁面上查看警示、風險、事件、安全性建議、已安裝的軟體，以及已發現的裝置相關聯的漏洞。 選取 [ **顯示更多** ]，以查看其餘的 [已公開的裝置] 清單。 在 [裝置] 清單中，您可以管理標記、啟動自動調查、啟動即時回應會話、收集調查套件、執行防病毒掃描、限制應用程式執行，以及隔離裝置。

如需整個入口網站上使用之圖示的詳細資訊，請參閱 [Microsoft Defender For Endpoint 圖示](portal-overview.md#microsoft-defender-for-endpoint-icons)。


## <a name="related-topics"></a>相關主題

- [威脅與弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [暴險分數](tvm-exposure-score.md)
- [裝置用 Microsoft 安全分數](tvm-microsoft-secure-score-devices.md)
- [安全性建議](tvm-security-recommendation.md)
- [軟體庫存](tvm-software-inventory.md)
- [活動時間表](threat-and-vuln-mgt-event-timeline.md)

