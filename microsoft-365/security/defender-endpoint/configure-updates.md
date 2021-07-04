---
title: 建立 Microsoft Defender 更新的自訂逐步展示過程
description: 瞭解如何使用支援的工具來建立自訂的漸進式產生過程以進行更新
keywords: 更新工具、gpo、intune、mdm、microsoft 端點管理員、原則、powershell
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
ms.openlocfilehash: a7a560cb33190105f8df5922e04aeada4d75f398
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290036"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>建立 Microsoft Defender 更新的自訂逐步展示過程

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> 這種功能需要 Microsoft Defender 防毒軟體版本4.18.2106 或更新版本。

若要建立您自己的用於 Defender 更新的自訂逐步推廣過程，您可以使用群組原則、Microsoft 端點管理員和 PowerShell。

下表列出可用來設定更新通道的群組原則設定：

| 設定標題  | 說明  | 位置  |
|:---|:---|:---|
| 選取逐步 Microsoft Defender 每月平臺更新部署通道  | 啟用此原則，以指定裝置每月逐步部署期間何時接收 Microsoft Defender 平臺更新。 Beta 通道：設定成此通道的裝置會是第一個接收新更新的裝置。 選取 [Beta 通道]，以參與識別及報告 Microsoft 的問題。 預設會為此通道訂閱 Windows 有問必答方案中的裝置。 僅供 (手動) 測試環境和有限數目的裝置使用。  <br><br>  目前通道 (預覽) ：設定成此通道的裝置會在每月逐步發佈週期中，儘早提供更新。 建議用於預先生產/驗證環境。  <br><br>  目前通道 (分段) ：在每月逐步發行週期後，將會提供裝置更新。 建議套用至實際生產環境中的小型、代表性部分 (~ 10% ) 。  <br><br>  目前通道 (多種) ：只有逐步發行週期完成之後，才會提供裝置更新。 建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。  <br><br>   如果您停用或未設定此原則，裝置會在逐步發行週期中自動維持最新狀態。 適用于大部分裝置。  | Windows元件 \ Microsoft Defender 防毒軟體  |
| 選取逐步 Microsoft Defender 每月引擎更新部署通道  | 啟用此原則，以指定裝置每月逐步部署期間何時接收 Microsoft Defender 引擎更新。  <br><br>  Beta 通道：設定成此通道的裝置會是第一個接收新更新的裝置。 選取 [Beta 通道]，以參與識別及報告 Microsoft 的問題。 預設會為此通道訂閱 Windows 有問必答方案中的裝置。 僅供 (手動) 測試環境和有限數目的裝置使用。  <br><br>  目前通道 (預覽) ：設定成此通道的裝置會在每月逐步發佈週期中，儘早提供更新。 建議用於預先生產/驗證環境。  <br><br>  目前通道 (分段) ：在每月逐步發行週期後，將會提供裝置更新。 建議套用至實際生產環境中的小型、代表性部分 (~ 10% ) 。  <br><br>  目前通道 (多種) ：只有逐步發行週期完成之後，才會提供裝置更新。 建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。  <br><br>  如果您停用或未設定此原則，裝置會在逐步發行週期中自動維持最新狀態。 適用于大部分裝置。  | Windows元件 \ Microsoft Defender 防毒軟體  |
| 選取逐步式 Microsoft Defender 每日定義更新試部署通道  | 啟用此原則，以指定裝置每日逐步部署期間何時接收 Microsoft Defender 定義更新。 <br><br> 目前通道 (分段) ：裝置會在發行週期後提供更新。 建議套用至實際生產環境 (~ 10% ) 中的小型代表性部分。 <br><br>   目前通道 (多種) ：只有逐步發行週期完成之後，才會提供裝置更新。 建議套用至實際執行填充 (~ 10-100% ) 中的一組廣泛裝置。 <br><br>   如果您停用或未設定此原則，裝置會在每日發行週期期間自動維持最新狀態。 適用于大部分裝置。  | Windows元件 \ Microsoft Defender 防毒軟體  |
| 停用 Microsoft Defender 更新逐步展入  | 啟用這個原則，以停用 Defender 更新的逐步展入。 <br><br> 目前通道 (廣泛) ：設定成此通道的裝置會在逐步發行週期中最後提供更新。 適用于僅接收有限更新的資料中心電腦。 <br><br> 注意：此設定會同時套用至每月和每日的 Defender 更新，並將覆寫先前設定平臺及引擎更新的任何先前設定的頻道選擇。 <br><br> 如果您停用或未設定此原則，裝置會維持在目前通道 (預設) ，除非另有指定的平臺及引擎更新的特定通道。 在逐步發佈週期內自動保持最新狀態。 適用于大部分裝置。  | Windows元件 \ Microsoft Defender 防毒軟體  |

## <a name="group-policy"></a>群組原則

> [!NOTE]
> 更新的 Defender ADMX 範本會一起發佈，與 Windows 10 的21H2 版本一起發行。 未當地語系化的版本可供下載 https://github.com/microsoft/defender-updatecontrols 。

您可以使用 [群組原則](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)   來設定及管理端點上的 Microsoft Defender 防毒軟體。

一般來講，您可以使用下列程式設定或變更 Microsoft Defender 防毒軟體群組原則設定：

1. 在您的群組原則管理電腦上，開啟 [ **群組原則管理主控台**]，以滑鼠右鍵按一下要設定 (GPO) 的 **群組原則物件** ，然後按一下 [ **編輯**]。

2. 使用群組原則管理編輯器移至 [ **電腦** 設定]。

3. 按一下 [系統 **管理範本**]。

4. 展開樹狀目錄，以 **Windows 元件 > Microsoft Defender 防毒軟體**。

5.  ****   在本主題中，展開包含您要設定之設定的此區段中 (參照為 Location 的位置) ，按兩下此設定以開啟它，然後進行設定變更。

6. 照常[部署更新的 GPO](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)。

## <a name="intune"></a>Intune

遵循下列連結中的指示，在 Intune 中建立自訂原則：

[Microsoft Intune Azure Microsoft 檔中的 Windows 10 裝置新增自訂設定 \|](/mem/intune/configuration/custom-settings-windows-10)

如需有關用於逐步推廣程式之 Defender Csp 的詳細資訊，請參閱 [DEFENDER csp](/windows/client-management/mdm/defender-csp)。

## <a name="powershell"></a>PowerShell

使用 `Set-MpPreference` Cmdlet 來設定逐步更新的推出。

使用下列參數：

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

範例：

用於 `Set-MpPreference -PlatformUpdatesChannel Beta` 設定平臺更新，以從 Beta 通道抵達。

如需參數及其設定方式的詳細資訊，請參閱 [MpPreference (Defender) |Microsoft](/powershell/module/defender/set-mppreference)檔。
