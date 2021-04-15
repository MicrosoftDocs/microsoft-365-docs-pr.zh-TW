---
title: Windows 10 中的 Microsoft Defender 離線功能
description: 您可以從 Windows Defender 防病毒應用程式直接使用 Microsoft Defender Offline。 您也可以管理在網路中部署的方式。
keywords: 掃描、defender、離線
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1e7e70c6ca217d3ad8859c1493598d71054f84
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765332"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>執行並審閱 Microsoft Defender 離線掃描的結果

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline 是一種惡意程式碼掃描工具，可讓您從信任的環境引導及執行掃描。 掃描會從一般 Windows 內核以外的地方執行，因此它可以針對企圖略過 Windows 命令介面的惡意程式碼，例如感染或覆寫主開機記錄 (MBR) 的病毒和 rootkit。

如果您懷疑惡意程式碼受到感染，您可以使用 Microsoft Defender Offline，或是在惡意程式碼爆發後確認完全清除的端點。

在 Windows 10 中，您可以直接按一下 [ [Windows 安全性] 應用程式](microsoft-defender-security-center-antivirus.md)來執行 Microsoft Defender Offline。 在舊版 Windows 中，使用者必須將 Microsoft Defender Offline 安裝至可啟動的媒體、重新開機端點，然後載入可啟動的媒體。

## <a name="prerequisites-and-requirements"></a>必要條件和需求

Windows 10 中的 Microsoft Defender Offline 與 Windows 10 具有相同的硬體需求。 

如需有關 Windows 10 需求的詳細資訊，請參閱下列主題：

- [基本硬體需求](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [硬體元件指導方針](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> 在具有 ARM 處理器的電腦上，或在 Windows Server Stock 保留單位上，不支援 Microsoft Defender Offline。

若要從端點執行 Microsoft Defender Offline，使用者必須以系統管理員許可權登入。
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender 離線更新

Microsoft Defender 離線使用端點上最新的保護更新;每當更新 Windows Defender 防病毒時，它就會更新。 

> [!NOTE]
> 在執行離線掃描之前，您應該嘗試更新 Microsoft Defender AV 保護。 您可以使用群組原則強制執行更新，也可以一般將更新部署至端點，也可以從 [Microsoft 惡意程式碼保護中心](https://www.microsoft.com/security/portal/definitions/adl.aspx)手動下載及安裝最新的保護更新。

如需詳細資訊，請參閱 [管理 Microsoft Defender 防病毒安全性情報更新](manage-protection-updates-microsoft-defender-antivirus.md) 主題。

## <a name="usage-scenarios"></a>使用情況

在 Windows 10 版本1607中，您可以手動強制進行離線掃描。 或者，如果 Windows Defender 決定要執行 Microsoft Defender Offline，它會在端點上提示使用者。 

如果您要使用它來管理端點，也會在 Microsoft 端點管理員中顯示執行離線掃描的需求。

提示會透過通知進行，類似如下所示：

![顯示要求以執行 Microsoft Defender 離線狀態的 Windows 通知](images/defender/notification.png)

Windows Defender 用戶端中也會通知使用者。

在 [設定管理員] 中，您可以透過流覽 **監視 > 概述 > 安全性 > Endpoint Protection 狀態 > System Center Endpoint Protection 狀態**，識別端點的狀態。 

Microsoft Defender 離線掃描會在 **惡意程式碼修復狀態** 下指出為 **需要離線掃描**。

![Microsoft 端點管理員指出需要 Microsoft Defender 離線掃描](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>設定通知

Microsoft Defender 離線通知是以與其他 Microsoft Defender AV 通知相同的原則設定進行設定。

如需 Windows Defender 中通知的詳細資訊，請參閱 [設定出現在端點上的通知](configure-notifications-microsoft-defender-antivirus.md) 主題。

## <a name="run-a-scan"></a>執行掃描 

> [!IMPORTANT]
> 在離線使用 Microsoft Defender 之前，請確定您已儲存任何檔案並關閉執行中的程式。 Microsoft Defender 離線掃描大約需要15分鐘才能執行。 掃描完成後，它會重新開機端點。 掃描是在一般 Windows 作業環境外執行。 使用者介面會與 Windows Defender 執行的一般掃描有所不同。 掃描完成後，將會重新開機端點，Windows 將會正常載入。

您可以執行 Microsoft Defender 離線掃描，其方式如下：

- PowerShell
- Windows Management Instrumentation (WMI)
- Windows 安全性應用程式



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>使用 PowerShell Cmdlet 執行離線掃描

使用下列 Cmdlet：

```PowerShell
Start-MpWDOScan
```

如需如何使用 Microsoft Defender 防病毒 PowerShell 的詳細資訊，請參閱 [Use PowerShell Cmdlet 來設定及執行 Microsoft Defender 防病毒](use-powershell-cmdlets-microsoft-defender-antivirus.md) 程式和 [Defender Cmdlet](/powershell/module/defender/) 。

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>使用 Windows Management 指令 (WMI) 以執行離線掃描

使用 [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 類別執行離線掃描。

下列 WMI 腳本程式碼片段會立即執行 Microsoft Defender 離線掃描，這會導致端點重新開機、執行離線掃描，然後重新開機並引導到 Windows。

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

如需詳細資訊，請參閱下列各項：
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>使用 Windows Defender 安全性應用程式執行離線掃描

1. 按一下工作列上的盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 [Windows 安全性] 應用程式。

2. 在左功能表列上，按一下 [ **病毒 & 威脅防護** 磚] (或盾牌圖示) ，然後按一下 [ **高級掃描** ] 標籤：
    
3. 選取 [ **Microsoft Defender 離線掃描** ]，然後按一下 [ **立即掃描**]。

    > [!NOTE]
    > 在 windows 10 版本1607中，離線掃描可從 **windows 設定**  >  **更新 & security**  >  **Windows Defender** 或從 Windows defender 用戶端執行。


## <a name="review-scan-results"></a>查看掃描結果

Microsoft Defender 離線掃描結果會列在 [Windows 安全性應用程式的 [掃描記錄] 區段](microsoft-defender-security-center-antivirus.md)中。 


## <a name="related-articles"></a>相關文章

- [自訂、啟動和審查掃描和修正的結果](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)