---
title: 使用 Intune 管理 Microsoft Defender for Endpoint
description: 瞭解如何使用 Intune 管理 Microsoft Defender for Endpoint
keywords: 遷移後、管理、作業、維護、使用狀況、intune、Microsoft Defender for Endpoint、edr
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
ms.openlocfilehash: d8396c352e593f9922b11e23119f7d9718eaf752
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934222"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>使用 Intune 管理 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

建議使用 [Microsoft Intune Manager](https://docs.microsoft.com/mem)，其中包含 microsoft Intune (Intune) ，以管理組織的威脅防護功能， (也稱為端點) 。 [深入瞭解端點管理員](https://docs.microsoft.com/mem/endpoint-manager-overview)。

本文說明如何在 Intune 中尋找 Microsoft Defender for Endpoint 設定，並列出您可以執行的各種工作。

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>在 Intune 中尋找 Microsoft Defender for Endpoint 設定

> [!IMPORTANT]
> 您必須是 Intune 中的全域系統管理員或服務管理員，才可設定本文所述的設定。 若要深入瞭解，請參閱 **[ (Intune) 的管理員類型](https://docs.microsoft.com/mem/intune/fundamentals/users-add#types-of-administrators)**。

1. 請移至 Azure 入口網站 ([https://portal.azure.com](https://portal.azure.com)) 並登入。

2. 在 [ **Azure 服務**] 底下，選擇 [ **Intune**]。

3. 在左側的功能窗格中，選擇 [ **裝置** 設定]，然後在 [ **管理**] 下選擇 [ **設定檔**]。

4. 選取現有的設定檔，或建立新的設定檔。

> [!TIP]
> 需要協助？ 請參閱 **[使用 Microsoft Defender For Endpoint With Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**。  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>使用 Intune 設定 Microsoft Defender for Endpoint

下表列出您可以執行的各種工作，以使用 Intune 設定 Microsoft Defender for Endpoint。 您不需要一次設定所有內容;選擇 [任務]，閱讀對應的資源，然後繼續。

|工作  |可深入了解的資源  |
|---------|---------|
|**使用 Intune 管理貴組織的裝置** ，以保護這些裝置和儲存在其上的資料     |[使用 Microsoft Intune 保護裝置](https://docs.microsoft.com/mem/intune/protect/device-protect)         |
|**整合 Microsoft Defender For Endpoint （含 Intune** ）為行動威脅防護解決方案 <br/>*適用于執行 Windows 10 或更新版本的 Android 裝置和裝置的 ()*   |[在 Intune 中強制執行 Microsoft Defender for Endpoint 的符合條件存取](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)         |
|**使用條件式存取** 控制可連線到您的電子郵件及公司資源的裝置和應用程式 |[在 Microsoft Defender for Endpoint 中設定條件式存取](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|使用 Policy configuration service provider ([原則 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) **設定 Microsoft Defender 防病毒設定**)  |[裝置限制： Microsoft Defender 防毒程式](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[原則 CSP-Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)  | 
|**如有必要，請指定 Microsoft Defender 防病毒的排除專案** <br/><br/>*一般來說，您不需要套用排除。Microsoft Defender 防毒軟體會根據已知的作業系統行為和一般管理檔案（例如，在企業管理、資料庫管理及其他企業案例中使用的程式），包含許多自動排除。* |[目前支援 Windows 版本之企業電腦的病毒掃描建議](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[裝置限制： Windows 10 裝置的 Microsoft Defender 防病毒排除](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[設定 Windows Server 2016 或2019上的 Microsoft Defender 防病毒排除程式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|設定 **攻擊面減少規則**，以針對經常被攻擊者濫用的軟體行為進行目標<br/><br/>*在第一周前 (，在 [稽核模式](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender) 中設定攻擊面減少規則，最多可有兩個月) 。您可以使用 Power BI (來監視狀態， [取得範本](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)) ，然後在準備好時將這些規則設定為主動模式。* |[Microsoft Defender for Endpoint 中的審計模式 ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Endpoint protection：攻擊面減少](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[深入瞭解攻擊面減少規則](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[技術社區博客文章： Demystifying 攻擊面減少規則-第1部分](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**設定網路篩選** 以封鎖從任何應用程式至具有低聲譽的 IP 位址或網域的輸出連線  <br/><br/>*網路篩選也稱為 [網路保護](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/network-protection)。*<br/><br/>*請確定 Windows 10 裝置安裝了最新的 [反惡意軟體平臺更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) 。*|[Endpoint protection：網路篩選](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[在 Windows 事件檢視器中查看網路保護事件](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**設定受管理的資料夾存取** 權以防護勒索軟體 <br/><br/>*「[受管理的資料夾存取](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders)」也稱為 antiransomware protection。*  |[Endpoint protection：受控資料夾存取權](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[啟用 Intune 中的可控資料夾存取](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**設定 exploit protection** ，以保護貴組織的裝置免受惡意程式碼的攻擊，利用利用漏洞來散佈及感染其他裝置 <br/><br/> *[Exploit protection](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exploit-protection) 也稱為「入侵防護」。* |[Endpoint protection： Microsoft Defender 利用防護](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[在 Intune 中啟用 exploit protection](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**設定 Microsoft Defender SmartScreen** 以防範網際網路上的惡意網站和檔案。 <br/><br/> *Microsoft Edge 應該安裝在您組織的裝置上。針對 Google Chrome 和 FireFox 瀏覽器的保護，請設定 exploit protection。*  |[Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[裝置限制： Microsoft Defender SmartScreen](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[在 Intune 中管理 SmartScreen 的原則設定](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**設定 Microsoft Defender 防火牆** ，以封鎖進出組織裝置的未授權網路流量  |[Endpoint protection： Microsoft Defender 防火牆](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [具有高級安全性的 Microsoft Defender 防火牆](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**設定加密和 BitLocker** 以保護組織裝置執行 Windows 的資訊 |[Endpoint protection： Windows 加密](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[Windows 10 裝置的 BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**設定 Microsoft Defender Credential Guard** 以防護認證盜竊攻擊 |若為 Windows 10、Windows Server 2016 及 Windows Server 2019，請參閱 [Endpoint protection： Microsoft Defender Credential Guard](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>針對 Windows 7 SP1，Windows Server 2008 R2 SP1，Windows 8.1 及 Windows Server 2012 R2，請參閱 [緩解傳遞-雜湊 (PtH) 攻擊和其他認證盜竊，版本1和 2](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**設定 Microsoft Defender 應用程式控制** ，以選擇是否要在組織的裝置上審核或信任應用程式 <br/><br/>*Microsoft Defender 應用程式控制也稱為 [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)。*|[使用 Microsoft Intune 部署 Microsoft Defender 應用程式控制原則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Endpoint protection： Microsoft Defender 應用程式控制](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|
|**設定裝置控制和 USB 週邊設備存取** ，以協助防止未經授權的外設威脅損損您的裝置 |[使用 Microsoft Defender for Endpoint 和 Intune 控制 USB 裝置和其他卸除式媒體](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>設定您的 Microsoft Defender 安全中心

若尚未這麼做，請 **將您的 Microsoft Defender 安全中心設定** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。 

您也可以設定使用者是否可以在 Microsoft Defender Security Center 中看到哪些功能。

- [Microsoft Defender 安全中心概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection： Microsoft Defender 安全中心](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>後續步驟

- [取得威脅和弱點管理的概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [流覽 Microsoft Defender Security Center security operations 儀表板](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)
