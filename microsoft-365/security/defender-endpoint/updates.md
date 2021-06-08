---
title: 管理 Microsoft Defender 更新的逐步展示過程
description: 深入瞭解逐步更新程式和控制項
keywords: 更新、更新程式、控制項、版本
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f5db08e4eb98dd3fe6f7e8a84fb0c49e889fb73f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809249"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>管理 Microsoft Defender 更新的逐步展示過程

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)


務必確保用戶端元件是最新的，以提供重要的保護功能並防止受到攻擊。

功能是透過數個元件提供： 

- [& 回應的端點偵測](overview-endpoint-detection-response.md) 
- 使用[雲端傳送保護](cloud-protection-microsoft-defender-antivirus.md)的[下一代保護](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) 
- [攻擊面減少](overview-attack-surface-reduction.md)

使用逐步發行處理常式每月發行一次更新。 此程式可協助您啟用早期的失敗偵測，以在發生影響時立即取得影響，並在較大的首展之前快速處理。 

> [!NOTE]
> 如需如何控制每日定義更新的詳細資訊，請參閱[排程 Microsoft Defender 防毒軟體定義更新-Windows 安全性 |Microsoft](manage-protection-update-schedule-microsoft-defender-antivirus.md)檔。定義更新可確保下一代保護可以防禦新的威脅，即使無法使用雲端提供的保護也是一樣。

## <a name="microsoft-gradual-rollout-model"></a>Microsoft 逐步推廣模型

下列逐步展模型遵循下列專案：

1. 第一個版本會發佈到 Beta 通道訂閱者。
2. 在驗證、意見反應和修正程式之後，我們會以節流的方式開始逐步展示處理常式，並先預覽通道訂閱者。
3. 接著，我們會繼續發行更新 ato，以從10-100% 向內擴充。

我們的工程師會持續監控影響並上報任何問題，以視需要建立修正。

## <a name="how-to-customize-your-internal-deployment-process"></a>如何自訂您的內部部署程式

如果您的機器從 Windows 更新接收到 defender 更新，逐步推廣程式可能會導致某些您的電腦以較早的速度接收 defender 更新。 下一節將說明如何透過利用更新通道設定，定義允許自動更新流向不同于特定裝置群組的策略。

> [!NOTE]
> 在規劃您自己的逐步發行時，請務必確定已訂閱預覽及分段通道的裝置的選取範圍。 這將為您的組織和 Microsoft 提供機會，以防止或找出並修正您環境特有的問題。

例如，針對接收更新的電腦，Windows Server Update Services (WSUS) 或 Microsoft Endpoint Configuration Manager (MECM) ，所有 Windows 更新都會提供更多選項，包括 Microsoft Defender for Endpoint 的選項。

- 深入瞭解如何使用 WSUS （如 WSUS） MECM，以管理[管理 Microsoft Defender 防毒軟體更新及套用基準 Windows 安全性 | 的更新的發佈和應用程式。Microsoft](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)檔。

## <a name="update-channels-for-monthly-updates"></a>更新每月更新的通道

您可以將機器指派至更新通道，以定義機器接收每月引擎和平臺更新的節奏。

如需如何設定更新的詳細資訊，請參閱 [建立 Microsoft Defender 更新的自訂逐步展處理](configure-updates.md)程式。

下列更新通道可供使用：

| 通道名稱  | 描述  | 應用程式  |
|-|-|-|
| Beta 通道-預發行  | 測試其他人之前的更新  | 設定為此通道的裝置將是第一個接收新的每月更新的裝置。 選取 [Beta 通道]，以參與識別及報告 Microsoft 的問題。 預設會為此通道訂閱 Windows 有問必答方案中的裝置。 僅供測試環境使用。  |
| 目前通道 (預覽)  | 在逐步發行過程中， **早先** 取得目前的通道更新  | 設定為此通道的裝置會在逐步發行週期中儘早提供更新。 建議用於預先生產/驗證環境。  |
|  (分段) 的目前通道  | 稍後逐步發行時取得目前的頻道更新  | 在逐步發行週期中，裝置會在稍後提供更新。 建議套用至您的裝置人口的小型代表性部分 (~ 10% ) 。  |
| 目前通道 (廣泛)  | 在逐步發行結束時取得更新  | 只有在逐步發行週期完成之後，才會將更新提供給裝置。 建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。  |
|  (預設)   |   | 如果您停用或未設定此原則，裝置將會保留在目前通道中 (預設) ：在逐步發行週期內，會自動維持最新狀態。 適用于大部分裝置。  |

### <a name="update-channels-for-daily-definition-updates"></a>更新每日定義更新的通道

您可以將機器指派至更新通道，以定義機器接收每日定義更新的節奏。
  
| 通道名稱  | 描述  | 應用程式  |
|-|-|-|
|  (分段) 的目前通道  | 稍後逐步發行時取得目前的頻道更新  | 在逐步發行週期中，裝置會在稍後提供更新。 建議套用至您的裝置人口的小型代表性部分 (~ 10% ) 。  |
| 目前通道 (廣泛)  | 在逐步發行結束時取得更新  | 在逐步發行週期過後，裝置將會提供更新。 適用于僅接收有限更新的資料中心電腦。 注意：此設定會套用至所有的 Defender 更新。  |
|  (預設)   |   | 如果您停用或未設定此原則，裝置將會保留在目前通道中 (預設) ：在逐步發行週期內，會自動維持最新狀態。 適用于大部分裝置  |

> [!NOTE]
> 如果您想要強制更新為最新的簽章，而不是利用時間延遲，您必須先移除此原則。

## <a name="update-guidance"></a>更新指導

在大多數情況下，使用 Windows 更新時，建議的設定是允許端點接收並套用每月的 Defender 更新。 這可讓您在保護與可能會帶來的變更相關聯時，獲得最佳的平衡。

針對可能需要更多控制自動 Defender 更新的逐漸推廣的環境，請考慮使用部署群組的方法：

1. 參與 Windows 的內幕程式，或將裝置的群組指派給 Beta 通道。
2. 指定示範群組以預覽通道（通常是驗證環境），以及早接收新的更新。
3. 指定一組機器，以從分段通道逐步進行逐步的首次開始時接收更新。 這通常是代表大約10% 的人口。
4. 指定在逐步發行週期完成後接收更新的機器群組。 這通常是非常重要的實際執行系統。

在其他裝置中，預設設定是在 Microsoft 逐步推廣過程中收到新的更新，而且不需要進行進一步的設定。 

採用此模型：
- 可讓您在發佈至實際執行環境之前測試早期版本 
- 確定生產環境仍會收到定期更新，並確保針對重大威脅進行防護。

## <a name="management-tools"></a>管理工具
若要建立您自己的自訂逐步產生過程以進行每月更新，您可以使用下列工具：

- 群組原則
- Microsoft 端點管理員
- PowerShell

如需如何使用這些工具的詳細資訊，請參閱 [建立 Microsoft Defender 更新的自訂逐步展處理](configure-updates.md)程式。
