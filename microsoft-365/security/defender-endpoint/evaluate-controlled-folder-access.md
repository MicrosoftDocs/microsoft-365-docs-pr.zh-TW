---
title: 評估受控資料夾存取權
description: 請參閱控制的資料夾存取可如何協助保護檔案不受惡意應用程式變更。
keywords: Exploit protection，windows 10，windows defender，勒索軟體，保護，評估，測試，示範，嘗試
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e5da8ec3e4555af062aad1a4ebfa96d972bee23b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059199"
---
# <a name="evaluate-controlled-folder-access"></a>評估受控資料夾存取權

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


「[受管理的資料夾存取](controlled-folders.md)」是一項功能，可協助您保護檔和檔案，避免遭到可疑或惡意應用程式的修改。 Windows Server 2019 和 Windows 10 用戶端支援受控資料夾存取。

在協助防範 [勒索軟體](https://www.microsoft.com/wdsi/threats/ransomware) ，以嘗試加密檔案並將檔案保留在 hostage 中特別有用。

本文可協助您評估受控資料夾存取。 它說明如何啟用稽核模式，以便您可以直接在組織中測試該功能。

> [!TIP]
> 您也可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Microsoft Defender for Endpoint 示範案例網站，確認該功能是否正常運作，並查看其運作方式。

## <a name="use-audit-mode-to-measure-impact"></a>使用稽核模式衡量影響

啟用「受管理的資料夾存取」稽核模式，以查看完全啟用 *時所發生的狀況* 記錄。 測試該功能在組織中的運作方式，以確保其不會影響您的企業營運應用程式。 您也可以瞭解一般會在一段時間內發生的可疑檔案修正嘗試次數。

若要啟用稽核模式，請使用下列 PowerShell Cmdlet：

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> 如果您想要完全核查控制的資料夾存取在組織中的運作方式，您必須使用管理工具，將此設定部署至網路中的裝置 (s) 。
您也可以使用「群組原則」、「Intune」、「行動裝置管理」 (MDM) 或 Microsoft 端點管理員來設定及部署設定，如主要 [受控資料夾存取主題](controlled-folders.md)所述。

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>在 Windows 事件檢視器中檢查受控資料夾存取事件

下列的受控資料夾存取事件會出現在 Windows 事件檢視器中的 [Microsoft/Windows/Windows Defender/操作] 資料夾底下。

事件識別碼 | 描述
-|-
 5007 | 設定變更時的事件
 1124 | 已審核的受管理資料夾存取事件
 1123 | 封鎖的受管理資料夾存取事件

> [!TIP]
> 您可以設定 [Windows 事件轉移訂閱](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) 來集中收集記錄。 

## <a name="customize-protected-folders-and-apps"></a>自訂受保護的資料夾和應用程式

在評估過程中，您可能會想要新增至受保護的資料夾清單，或允許某些應用程式修改檔案。

請參閱使用「管理」工具（包括群組原則、PowerShell 及 MDM 設定服務提供者 (Csp) ）設定功能，以 [保護重要的資料夾存取權](controlled-folders.md) 。

## <a name="see-also"></a>另請參閱

* [使用受控資料夾存取權來保護重要資料夾](controlled-folders.md)
* [評估 Microsoft Defender for Endpoint](evaluate-atp.md)
* [使用稽核模式](audit-windows-defender.md)
