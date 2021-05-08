---
title: 在 Microsoft Defender 防毒軟體中執行及自訂隨選掃描
description: 在具有 Windows 安全性應用程式的端點上，使用 PowerShell、Windows 管理工具或個別的方式執行及設定隨選掃描
keywords: 掃描、隨選、dos、intune、立即掃描
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 8b6889a2eabcfb777983be79d78060165497de72
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246341"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>設定和執行隨選 Microsoft Defender 防毒軟體掃描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以在個別端點上執行隨選掃描。 這些掃描會立即開始，您可以定義掃描的參數，例如位置或類型。

## <a name="quick-scan-versus-full-scan"></a>快速掃描與完整掃描

快速掃描查看可能已註冊惡意程式碼的所有位置，例如登錄機碼和已知 Windows 開機檔案夾。

> [!IMPORTANT]
> 執行本機掃描時，Microsoft Defender 防毒軟體會在[LocalSystem](/windows/win32/services/localsystem-account)帳戶的上下文中執行。 若為網路掃描，它會使用裝置帳戶的內容。 如果網域裝置帳戶沒有存取共用的適當許可權，則掃描將無法運作。 確定裝置具有存取網路共用的許可權。

與 [always on 即時保護功能](configure-real-time-protection-microsoft-defender-antivirus.md)組合在一起，可在開啟和關閉檔時檢查檔案，以及每當使用者流覽至資料夾時，都可以為以系統和內核層級惡意程式碼開頭的惡意程式碼提供強大的覆蓋。  

在大多數的情況下，快速掃描足以找到即時保護未挑選的惡意程式碼。

完整掃描可用於已經報告惡意程式碼威脅的端點。 掃描可識別是否有任何非使用中的元件需要更徹底的清理。 如果您的組織執行的是手動掃描，則這是理想的功能。

> [!NOTE]
> 根據預設，在裝載的可拆卸裝置（例如 USB 磁片磁碟機）上執行快速掃描。

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>使用 Microsoft 端點管理員執行掃描

1. 請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。
2. 選擇 [ **Endpoint security**  >  **防病毒**]。
3. 在索引標籤清單中，選取 [ **Windows 10 不健全的端點**]。
4. 從提供的動作清單中，選取 [ **快速掃描** ] 或 [ **完全掃描**]。

[![影像 ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> 如需使用 Microsoft 端點管理員執行掃描的詳細資訊，請參閱[反惡意軟體和防火牆工作：如何執行隨選掃描](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>使用 mpcmdrun.exe 命令列公用程式執行掃描

使用下列 `-scan` 參數：

```console
mpcmdrun.exe -scan -scantype 1
```

如需如何使用工具及其他參數（包括開始完整掃描或定義路徑）的詳細資訊，請參閱[use the mpcmdrun.exe 命令列工具來設定及管理 Microsoft Defender 防毒軟體](command-line-arguments-microsoft-defender-antivirus.md)。

## <a name="use-microsoft-intune-to-run-a-scan"></a>使用 Microsoft Intune 執行掃描

1. 請移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。
2. 從側邊選取 [ **裝置 > 所有裝置** ]，然後選擇您要掃描的裝置。
3. 選取 **.。。其他**。 從選項中，選取 [ **快速掃描** ] 或 [ **完全掃描**]。

## <a name="use-the-windows-security-app-to-run-a-scan"></a>使用 Windows 安全性應用程式執行掃描

請參閱[在 Windows 安全性應用程式中執行掃描](microsoft-defender-security-center-antivirus.md)，以取得在個別端點上執行掃描的指示。

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>使用 PowerShell Cmdlet 執行掃描

請使用下列 Cmdlet：

```PowerShell
Start-MpScan
```

如需如何搭配 Microsoft Defender 防毒軟體使用 PowerShell 的詳細資訊，請參閱[use PowerShell Cmdlet 以設定及執行 Microsoft Defender 防毒軟體](use-powershell-cmdlets-microsoft-defender-antivirus.md)和[Defender Cmdlet](/powershell/module/defender/)。

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>使用 Windows 管理指令 (WMI) 執行掃描

使用 **MSFT_MpScan** 類別的 [ **Start** 方法](/previous-versions/windows/desktop/defender/start-msft-mpscan)。

如需允許哪些參數的詳細資訊，請參閱[Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>相關文章

- [設定 Microsoft Defender 防毒軟體掃描選項](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [設定排定的 Microsoft Defender 防毒軟體掃描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-in-windows-10.md)