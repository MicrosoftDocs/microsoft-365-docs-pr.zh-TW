---
title: 使用 PowerShell、WMI 及 MPCmdRun.exe 管理 Microsoft Defender for Endpoint
description: 瞭解如何使用 PowerShell、WMI 及 MPCmdRun.exe 管理 Microsoft Defender for Endpoint
keywords: 遷移後、管理、作業、維護、使用狀況、PowerShell、WMI、MPCmdRun.exe、Microsoft Defender for Endpoint、edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: d2238703e3b1205287d4ab6239af20095b51df13
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841906"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>使用 PowerShell、WMI 及 MPCmdRun.exe 管理 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> 建議使用[Microsoft 端點管理員](/mem)來管理組織的威脅防護功能，以供裝置 (也稱為端點) 。 端點管理員包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)。 
> - [深入瞭解端點管理員](/mem/endpoint-manager-overview)
> - [使用 Configuration Manager 和 Intune 在 Windows 10 裝置上共同管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
> - [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md) 

您可以使用[PowerShell](#configure-microsoft-defender-for-endpoint-with-powershell)管理裝置上的某些 Microsoft Defender 防毒軟體設定， [Windows 管理工具](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) (WMI) ，以及[Microsoft 惡意程式碼防護命令列公用程式](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe) 。 例如，您可以管理一些 Microsoft Defender 防毒軟體設定。 此外，在某些情況下，您可以自訂攻擊面減少規則和 exploit protection 設定。 

> [!IMPORTANT]
> 您使用 PowerShell、WMI 或 MCPmdRun.exe 所設定的威脅防護功能，可透過使用 Intune 或 Configuration Manager 部署的設定設定覆寫。

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>設定 Microsoft Defender for Endpoint with PowerShell

您可以使用 PowerShell 來管理 Microsoft Defender 防毒軟體、exploit protection 和攻擊面降低規則。

|工作  |可深入了解的資源  |
|---------|---------|
|**管理 Microsoft Defender 防毒軟體** <br/><br/>*查看反惡意程式碼保護的狀態、設定防病毒掃描的喜好設定 & 更新，以及對您的防防毒保護進行其他變更。*    |[使用 PowerShell Cmdlet 來設定及管理 Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus)  <br/><br/>[使用 PowerShell Cmdlet 以啟用雲端提供的保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)       |
|**設定 exploit protection** ，以減輕組織裝置的威脅<br/><br/> *我們建議您先在 [稽核模式](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) 中使用 exploit protection。如此一來，您就可以看到使用方式保護會如何影響組織所使用的應用程式。*     | [自訂利用保護](/microsoft-365/security/defender-endpoint/customize-exploit-protection)<br/><br/>[PowerShell 用於 exploit protection 的 Cmdlet](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)        |
|使用 PowerShell **設定攻擊面降低規則** <br/><br/>*您可以使用 PowerShell，從攻擊面減少規則中排除檔案和資料夾。* |[自訂攻擊面降減規則：使用 PowerShell 排除檔案 & 資料夾](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders)<br/><br/>此外，請參閱 [António Vasconcelo 的圖形使用者介面工具，以使用 PowerShell 來設定攻擊面降減規則](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI)。 |
|使用 PowerShell **啟用網路保護** <br/><br/>*您可以使用 PowerShell 來啟用網路保護。* |[使用 PowerShell 開啟網路保護](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell) |
|**設定受管理的資料夾存取** 權以防護勒索軟體 <br/><br/>*「[受管理的資料夾存取](/microsoft-365/security/defender-endpoint/controlled-folders)」也稱為 antiransomware protection。* |[啟用 PowerShell 的可控資料夾存取](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell) |
|**設定 Microsoft Defender 防火牆** 以封鎖進出組織裝置的未授權網路流量 |[使用 Windows PowerShell 使用「高級安全性管理」的 Microsoft Defender 防火牆](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell) |
|**設定加密和 BitLocker** ，以保護組織執行 Windows 的裝置資訊 |[BitLockerPowerShell 參考手冊](/powershell/module/bitlocker/?view=win10-ps&preserve-view=true) |

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>設定 Microsoft Defender for Endpoint with Windows Management Instrumentation (WMI) 

WMI 是一個指令碼介面，可讓您檢索、修改和更新設定。 若要深入瞭解，請參閱 [使用 WMI](/windows/win32/wmisdk/using-wmi)。 

|工作  |可深入了解的資源  |
|---------|---------|
|在裝置上 **啟用雲端提供保護**    |[使用 Windows 管理指令 (WMI) 以啟用雲端提供的保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)       |
|**檢索、修改和更新** Microsoft Defender 防毒軟體的設定     | [使用 WMI 設定及管理 Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/use-wmi-microsoft-defender-antivirus)<br/><br/>[檢查可用 WMI 類別和範例腳本的清單](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <br/><br/>另請參閱封存的[Windows Defender WMIv2 提供者參考資訊](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)   |


## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>使用 Microsoft 惡意程式碼防護 Command-Line 公用程式 (MPCmdRun.exe 設定 Microsoft Defender for Endpoint) 

在個別裝置上，您可以執行掃描、啟動診斷追蹤、檢查安全性智慧更新，以及使用 mpcmdrun.exe 命令列工具進行更多工作。 您可以在中找到該公用程式 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。 從命令提示字元執行。

|工作  |可深入了解的資源  |
|---------|---------|
|**管理 Microsoft Defender 防毒軟體**  |[使用 mpcmdrun.exe設定及管理 Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)        |

## <a name="configure-your-microsoft-defender-security-center"></a>設定 Microsoft Defender 資訊安全中心

若尚未這麼做，請 **設定 Microsoft Defender 資訊安全中心** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。 

您也可以設定使用者是否可以在 Microsoft Defender 資訊安全中心中看到使用者的功能。

- [Microsoft Defender 資訊安全中心綜述](/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection： Microsoft Defender 資訊安全中心](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)


## <a name="next-steps"></a>後續步驟

- [深入瞭解威脅與弱點管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [流覽 Microsoft Defender 資訊安全中心的安全性運作儀表板](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
