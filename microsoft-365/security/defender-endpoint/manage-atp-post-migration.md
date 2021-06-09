---
title: 管理 Microsoft Defender 進行端點後遷移
description: 現在，您已將此參數設為 Microsoft Defender for Endpoint，下一步是管理威脅防護功能
keywords: 遷移後、管理、作業、維護、利用率、Microsoft Defender for Endpoint、edr
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
ms.openlocfilehash: ea5e4cb1c4a93f5f8bd5da1c0c94b095d03ac680
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845615"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>管理 Microsoft Defender for Endpoint，後期遷移

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

在您從先前的 endpoint protection 和防病毒方案移至 Microsoft Defender for Endpoint 後，下一步是管理您的功能。 我們建議使用[Microsoft 端點管理員](/mem/endpoint-manager-overview)，其中包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)，以管理您組織的裝置及安全性設定。 不過，您可以[在 Azure Active Directory 網域服務中](/azure/active-directory-domain-services/manage-group-policy)使用其他工具/方法，例如「群組原則」物件。 

下表列出您可以使用的各種工具/方法，以及深入瞭解的連結。 
<br/><br/>

|工具/方法  |描述  |
|---------|---------|
|Microsoft Defender 資訊安全中心 (中的 **[威脅及弱點管理儀表板深入](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** 資訊 [https://securitycenter.windows.com](https://securitycenter.windows.com))  |威脅 & 弱點管理儀表板提供切實可行的資訊，讓您的安全作業小組可用來降低風險並改善組織的安全性狀況。 <br/><br/>請參閱[威脅 & 弱點管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)和[概述 Microsoft Defender 資訊安全中心](/microsoft-365/security/defender-endpoint/use)。  |
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (建議)     |Microsoft Intune (Intune) ， [Microsoft 端點管理員](/mem/endpoint-manager-overview)的元件，側重于行動裝置管理 (MDM) 和行動應用程式管理 (MAM) 。 透過 Intune，您可以控制組織裝置的使用方式，包括行動電話、平板電腦和可擕式電腦。 您也可以設定特定原則來控制應用程式。 <br/><br/>請參閱 [使用 Intune 管理 Microsoft Defender For Endpoint](manage-atp-post-migration-intune.md)。         |
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**     |Microsoft 端點管理員 (Configuration Manager) （以前稱為 System Center Configuration Manager）是[Microsoft 端點管理員](/mem/endpoint-manager-overview)的元件。 Configuration Manager 是一種強大的工具，可用於管理使用者、裝置和軟體。<br/><br/>請參閱 [使用 Configuration Manager 管理 Microsoft Defender For Endpoint](manage-atp-post-migration-configuration-manager.md)。        |
|**[Azure Active Directory 網域服務中的群組原則物件](/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory 網域服務](/azure/active-directory-domain-services/overview)包含使用者和裝置的內建群組原則物件。 您可以視環境需要自訂內建的群組原則物件，也可以建立自訂的群組原則物件和組織單位 (Ou) 。 <br/><br/>請參閱 [使用群組原則物件管理 Microsoft Defender For Endpoint](manage-atp-post-migration-group-policy-objects.md)。 |
|**[PowerShell、WMI 和 MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*我們建議使用 Microsoft 端點管理員 (，其中包含 Intune 及 Configuration Manager) ，以管理組織裝置上的威脅防護功能。不過，您可以設定某些設定，例如個別裝置上的 Microsoft Defender 防毒軟體設定 (端點) 具有 PowerShell、WMI 或 MPCmdRun.exe 工具。*<br/><br/>您可以使用 PowerShell 來管理 Microsoft Defender 防毒軟體、exploit protection 和攻擊面降低規則。 請參閱 [Configure a Microsoft Defender For Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)。<br/><br/>您可以使用 Windows Management Instrumentation (WMI) 來管理 Microsoft Defender 防毒軟體和排除。 請參閱 [使用 WMI 設定 Microsoft Defender For Endpoint](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi)。<br/><br/>您可以使用 Microsoft 惡意程式碼保護 Command-Line 公用程式 (MPCmdRun.exe) 管理 Microsoft Defender 防毒軟體和排除，以及驗證網路與雲端之間的連線。 請參閱 [Configure a Microsoft Defender For Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe)。 |

## <a name="see-also"></a>另請參閱

- [解決適用於端點的 Microsoft Defender 中的誤判/漏報](defender-endpoint-false-positives-negatives.md)
