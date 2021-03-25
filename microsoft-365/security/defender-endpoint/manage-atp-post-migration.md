---
title: 管理 Microsoft Defender 進行端點後遷移
description: 現在，您已將此參數設為 Microsoft Defender for Endpoint，下一步是管理威脅防護功能
keywords: 遷移後、管理、作業、維護、使用狀況、windows defender 高級威脅防護、atp、edr
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
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: 54302f38f0fd63560ecd1c5545efa4621c6b9bbd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185858"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>管理 Microsoft Defender for Endpoint，後期遷移

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

在您從先前的 endpoint protection 和防病毒方案移至 Microsoft Defender for Endpoint 後，下一步是管理您的功能。 建議您使用 Microsoft Intune [管理員](https://docs.microsoft.com/mem/endpoint-manager-overview)（包括 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 和 [Microsoft 端點設定管理員](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)）來管理組織的裝置及安全性設定。 不過，您可以使用其他工具/方法，例如 [Azure Active Directory 網域服務中的群組原則物件](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)。 

下表列出您可以使用的各種工具/方法，以及深入瞭解的連結。 
<br/><br/>

|工具/方法  |描述  |
|---------|---------|
|Microsoft Defender Security Center 中的 **[威脅和弱點管理儀表板深入](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** ([https://securitycenter.windows.com](https://securitycenter.windows.com))  |威脅 & 弱點管理儀表板提供切實可行的資訊，讓您的安全作業小組可用來減少風險，並改善組織的安全性狀況。 <br/><br/>請參閱 [威脅 & 弱點管理](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 和 [Microsoft Defender 安全中心的概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)。  |
|**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (建議)     |Microsoft Intune (Intune) （ [Microsoft 端點管理員](https://docs.microsoft.com/mem/endpoint-manager-overview)的元件）著重于行動裝置管理 (MDM) 及行動應用程式管理 (MAM) 。 透過 Intune，您可以控制組織裝置的使用方式，包括行動電話、平板電腦和可擕式電腦。 您也可以設定特定原則來控制應用程式。 <br/><br/>請參閱 [使用 Intune 管理 Microsoft Defender For Endpoint](manage-atp-post-migration-intune.md)。         |
|**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**     |Microsoft 端點管理員 (Configuration Manager) （以前稱為 System Center Configuration Manager）是 [Microsoft 端點管理員](https://docs.microsoft.com/mem/endpoint-manager-overview)的元件。 Configuration Manager 是一種強大的工具，可用於管理使用者、裝置和軟體。<br/><br/>請參閱 [使用 Configuration Manager 管理 Microsoft Defender For Endpoint](manage-atp-post-migration-configuration-manager.md)。        |
|**[Azure Active Directory 網域服務中的群組原則物件](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory 網域服務](https://docs.microsoft.com/azure/active-directory-domain-services/overview) 包含使用者和裝置的內建群組原則物件。 您可以視環境需要自訂內建的群組原則物件，也可以建立自訂的群組原則物件和組織單位 (Ou) 。 <br/><br/>請參閱 [使用群組原則物件管理 Microsoft Defender For Endpoint](manage-atp-post-migration-group-policy-objects.md)。 |
|**[PowerShell、WMI 及 MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*建議使用 Microsoft 端點管理員 (，其中包含 Intune 及 Configuration Manager) ，以管理組織裝置上的威脅防護功能。不過，您可以設定某些設定，例如個別裝置上的 Microsoft Defender 防病毒設定 (端點) PowerShell、WMI 或 MPCmdRun.exe 工具。*<br/><br/>您可以使用 PowerShell 來管理 Microsoft Defender 防病毒、exploit protection 和攻擊面降低規則。 請參閱 [Configure a Microsoft Defender For Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)。<br/><br/>您可以使用 Windows Management Instrumentation (WMI) 來管理 Microsoft Defender 防毒程式和排除專案。 請參閱 [使用 WMI 設定 Microsoft Defender For Endpoint](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)。<br/><br/>您可以使用 Microsoft 惡意程式碼保護 Command-Line 公用程式 (MPCmdRun.exe) 管理 Microsoft Defender 防毒程式和排除專案，以及驗證網路與雲端之間的連線。 請參閱 [Configure a Microsoft Defender For Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)。 |

## <a name="see-also"></a>另請參閱

- [在 Microsoft Defender for Endpoint 中處理誤報/負片](defender-endpoint-false-positives-negatives.md)
