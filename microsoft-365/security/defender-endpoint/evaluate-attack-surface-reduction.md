---
title: 評估受攻擊面縮小規則
description: 請參閱攻擊面降低會如何阻擋並防止使用自訂示範工具進行攻擊。
keywords: 攻擊面減少，hips，主機入侵防護系統，保護規則，反惡意攻擊，antiexploit，exploit，感染防護，評估，測試，示範
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 07573fd92643ce5fdf3e9140031bf5f15ae8f7aa
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570336"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>評估受攻擊面縮小規則

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

攻擊面減少規則可協助防止惡意程式碼用來危害裝置或網路的動作。 設定執行下列任何版本 Windows 之裝置的攻擊面減少規則：

- Windows 10 專業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本
- Windows 10 企業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本
- Windows Server， [版本 1803 (半年通道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 或更新版本
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

瞭解如何透過稽核模式直接在組織中測試功能，以評估攻擊面減少規則。

> [!TIP]
> 您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範案例網站，確認該功能是否正常運作，並查看其運作方式。

## <a name="use-audit-mode-to-measure-impact"></a>使用稽核模式衡量影響

在稽核模式中啟用攻擊面降低規則，以查看已完全啟用該功能時，已封鎖的應用程式記錄。 測試該功能在組織中的運作方式，以確保其不會影響您的企業營運應用程式。 您也可以瞭解規則在正常使用中會觸發的頻率。

若要在稽核模式中啟用攻擊面降減規則，請使用下列 PowerShell Cmdlet：

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

其中 `<rule ID>` 是 [攻擊面降低規則的 GUID 值](attack-surface-reduction.md#attack-surface-reduction-rules)。

若要在稽核模式中啟用所有新增的攻擊面降低規則，請使用下列 PowerShell Cmdlet：

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> 如果您想要完全審核攻擊面降低規則在組織中的運作方式，您必須使用管理工具，將此設定部署至網路中的裝置 (s) 。

您也可以使用「群組原則」、「Intune」或「行動裝置管理」 (MDM) configuration service 提供者 (Csp) 來設定及部署設定。 若要深入瞭解，請參閱主要 [攻擊面減少規則](attack-surface-reduction.md) 文章。

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>在 Windows 事件檢視器中查看攻擊面減少事件

若要查看已封鎖的應用程式，請在 Microsoft-Windows Defender/運作性記錄檔中開啟事件檢視器並篩選事件識別碼1121。 下表列出所有網路保護事件。

事件識別碼 | 說明
-|-
 5007 | 設定變更時的事件
 1121 | 在封鎖模式中激發攻擊面降低規則時的事件
 1122 | 在稽核模式中引發攻擊面降低規則時的事件

## <a name="customize-attack-surface-reduction-rules"></a>自訂受攻擊面縮小規則

在評估過程中，您可能會想要個別設定每個規則，或排除某些檔案和進程，以供功能評估使用。

如需使用管理工具（包括群組原則和 MDM CSP 原則）設定該功能的詳細資訊，請參閱 [自訂攻擊面降規則](customize-attack-surface-reduction.md) 。

## <a name="see-also"></a>另請參閱

* [使用攻擊面減少規則來減少攻擊面](attack-surface-reduction.md)
* [使用稽核模式評估 Windows Defender](audit-windows-defender.md)
* [受攻擊面縮小常見問題集](attack-surface-reduction.md)
