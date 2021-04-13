---
title: 使用 PowerShell Cmdlet 來設定及執行 Microsoft Defender AV
description: 在 Windows 10 中，您可以使用 PowerShell Cmdlet 來執行掃描、更新安全性情報，以及變更 Microsoft Defender 防病毒中的設定。
keywords: 掃描、命令列、mpcmdrun、defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/23/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 912136a7229ec55b7f1644aebc946f63acb68040
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690166"
---
# <a name="use-powershell-cmdlets-to-configure-and-manage-microsoft-defender-antivirus"></a>使用 PowerShell Cmdlet 來設定及管理 Microsoft Defender 防毒程式

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用 PowerShell 在 Windows Defender 中執行各種功能。 類似于命令提示字元或命令列，PowerShell 是以任務為基礎的命令列命令介面及指令碼語言，特別是用來管理系統。 您可以在 [MSDN 的 PowerShell hub](/previous-versions/msdn10/mt173057(v=msdn.10))中深入瞭解。

如需 Cmdlet 及其功能和可用參數的清單，請參閱 [Defender Cmdlet](/powershell/module/defender) 主題。

PowerShell Cmdlet 在 Windows 伺服器環境中最為有用，但不依賴圖形使用者介面 (GUI) 來設定軟體。

> [!NOTE]
> PowerShell Cmdlet 不應該用作完整網路原則管理基礎結構（例如 [Microsoft 端點設定管理員](/configmgr)、 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))或 [Microsoft DEFENDER 防病毒群組原則 ADMX 範本](https://www.microsoft.com/download/101445)）的取代。

PowerShell 所做的變更會影響部署變更之端點的本機設定。 這表示使用「群組原則」、「Microsoft 端點設定管理員」或 Microsoft Intune 部署原則，可以覆寫 PowerShell 所做的變更。

您可以 [設定哪些設定可以在本機上使用本機原則覆寫](configure-local-policy-overrides-microsoft-defender-antivirus.md)。

PowerShell 一般會安裝在資料夾底下 `%SystemRoot%\system32\WindowsPowerShell` 。

## <a name="use-microsoft-defender-antivirus-powershell-cmdlets"></a>使用 Microsoft Defender 防病毒 PowerShell Cmdlet

1. 在 Windows 搜尋列中，輸入 **powershell**。
2. 從結果中選取 [ **Windows PowerShell** ]，以開啟介面。
3. 輸入 PowerShell 命令和任何參數。

> [!NOTE]
> 您可能需要以系統管理員模式開啟 PowerShell。 在 [開始] 功能表中，以滑鼠右鍵按一下專案，按一下 [以 **系統管理員身分執行** ]，然後在許可權提示中按一下 **[是]** 。

若要針對任何 Cmdlet 開啟線上說明，請輸入下列命令：

```PowerShell
Get-Help <cmdlet> -Online
```

省略此 `-online` 參數可取得本機快取説明。

## <a name="related-topics"></a>相關主題

- [管理及設定工具的參考主題](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 防病毒 Cmdlet](/powershell/module/defender/?view=win10-ps)