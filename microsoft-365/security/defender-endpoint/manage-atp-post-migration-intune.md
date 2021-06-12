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
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: ccbcbcb71d60dadf24b6f94bab126a1f1ca1c322
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908278"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>使用 Intune 管理 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

我們建議使用[Microsoft 端點管理員](/mem)，其中包括 Microsoft Intune (Intune) ，以管理組織的威脅防護功能（裝置 (也稱為端點) ）。 [深入瞭解端點管理員](/mem/endpoint-manager-overview)。

本文說明如何在 Intune 中尋找 Microsoft Defender for Endpoint 設定，並列出您可以執行的各種工作。

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>在 Intune 中尋找 Microsoft Defender for Endpoint 設定

> [!IMPORTANT]
> 您必須是 Intune 中的全域系統管理員或服務管理員，才可設定本文所述的設定。 若要深入瞭解，請參閱 **[ (Intune) 的管理員類型](/mem/intune/fundamentals/users-add#types-of-administrators)**。

1. 請移至 Azure 入口網站 ([https://portal.azure.com](https://portal.azure.com)) 並登入。

2. 在 [ **Azure 服務**] 底下，選擇 [ **Intune**]。

3. 在左側的功能窗格中，選擇 [ **裝置** 設定]，然後在 [ **管理**] 下選擇 [ **設定檔**]。

4. 選取現有的設定檔，或建立新的設定檔。

> [!TIP]
> 需要協助？ 請參閱 **[使用 Microsoft Defender For Endpoint With Intune](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**。  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>使用 Intune 設定 Microsoft Defender for Endpoint

下表列出您可以執行的各種工作，以使用 Intune 設定 Microsoft Defender for Endpoint。 您不需要一次設定所有內容;選擇 [任務]，閱讀對應的資源，然後繼續。

|工作  |可深入了解的資源  |
|---------|---------|
|**使用 Intune 管理貴組織的裝置** ，以保護這些裝置和儲存在其上的資料     |[使用 Microsoft Intune 保護裝置](/mem/intune/protect/device-protect)         |
|**整合 Microsoft Defender For Endpoint （含 Intune** ）為行動威脅防護解決方案 <br/>*適用于執行 Windows 10 或更新版本的 Android 裝置和裝置的 ()*   |[在 Intune 中強制執行 Microsoft Defender for Endpoint 的符合條件存取](/mem/intune/protect/advanced-threat-protection)         |
|**使用條件式存取** 控制可連線到您的電子郵件及公司資源的裝置和應用程式 |[在 Microsoft Defender for Endpoint 中設定條件式存取](/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|使用 policy configuration service provider ([原則 CSP](/windows/client-management/mdm/policy-configuration-service-provider) **設定 Microsoft Defender 防毒軟體設定**)  |[裝置限制： Microsoft Defender 防毒軟體](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[原則 CSP-Microsoft Defender for Endpoint](/windows/client-management/mdm/policy-csp-defender)  | 
|**如有必要，指定 Microsoft Defender 防毒軟體的排除專案** <br/><br/>*一般來說，您不需要套用排除。Microsoft Defender 防毒軟體會根據已知的作業系統行為和一般管理檔案（例如企業管理、資料庫管理及其他企業案例中所使用的管理檔案），包含許多自動排除。* |[目前支援的 Windows 版本的 Enterprise 電腦的病毒掃描建議](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[裝置限制： Windows 10 裝置的 Microsoft Defender 防毒軟體排除專案](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[設定 Windows Server 2016 或2019上的 Microsoft Defender 防毒軟體排除](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|設定 **攻擊面減少規則**，以針對經常被攻擊者濫用的軟體行為進行目標<br/><br/>*在第一周前 (，在 [稽核模式](/microsoft-365/security/defender-endpoint/audit-windows-defender)中設定攻擊面減少規則，最多可有兩個月) 。您可以使用 Power BI 來監視狀態 ([取得範本](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)) ，然後在準備好時將這些規則設定為使用中模式。* |[Microsoft Defender for Endpoint 中的審計模式 ](/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Endpoint protection：攻擊面減少](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[深入瞭解攻擊面減少規則](/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[技術 Community 博客文章： Demystifying 攻擊面減少規則-第1部分](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**設定網路篩選** 以封鎖從任何應用程式至具有低聲譽的 IP 位址或網域的輸出連線  <br/><br/>*網路篩選也稱為 [網路保護](/microsoft-365/security/defender-endpoint/network-protection)。*<br/><br/>*請確定 Windows 10 裝置安裝了最新的 [反惡意軟體平臺更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。*|[Endpoint protection：網路篩選](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[在 Windows 事件檢視器中查看網路保護事件](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**設定受管理的資料夾存取** 權以防護勒索軟體 <br/><br/>*「[受管理的資料夾存取](/microsoft-365/security/defender-endpoint/controlled-folders)」也稱為 antiransomware protection。*  |[Endpoint protection：受控資料夾存取權](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[啟用 Intune 中的可控資料夾存取](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**設定 exploit protection** ，以保護貴組織的裝置免受惡意程式碼的攻擊，利用利用漏洞來散佈及感染其他裝置 <br/><br/> *[Exploit protection](/microsoft-365/security/defender-endpoint/exploit-protection) 也稱為「入侵防護」。* |[Endpoint protection： Microsoft Defender 惡意探索防護](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[在 Intune 中啟用 exploit protection](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**設定 Microsoft Defender SmartScreen** 以防範網際網路上的惡意網站和檔案。 <br/><br/> *Microsoft Edge 應該安裝在您組織的裝置上。針對 Google Chrome 和 FireFox 瀏覽器的保護，請設定 exploit protection。*  |[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[裝置限制： Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[在 Intune 中管理 SmartScreen 的原則設定](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**設定 Microsoft Defender 防火牆** 以封鎖進出組織裝置的未授權網路流量  |[Endpoint protection： Microsoft Defender 防火牆](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [具有高級安全性的 Microsoft Defender 防火牆](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**設定加密和 BitLocker** ，以保護組織執行 Windows 的裝置資訊 |[Endpoint protection： Windows 加密](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[Windows 10 裝置的 BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**設定 Microsoft Defender Credential Guard** 以防護認證盜竊攻擊 |如需 Windows 10、Windows Server 2016 及 Windows Server 2019，請參閱[Endpoint protection： Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>若為 Windows 7 SP1、Windows Server 2008 R2 SP1、Windows 8.1 和 Windows Server 2012 R2，請參閱[緩解傳遞-雜湊 (PtH) 攻擊和其他認證盜竊，版本1和 2](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**設定 Microsoft Defender 應用程式控制** ，以選擇是否要在組織的裝置上審核或信任應用程式 <br/><br/>*Microsoft Defender 應用程式控制也稱為 [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)。*|[使用 Microsoft Intune 部署 Microsoft Defender 應用程式控制原則](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Endpoint protection： Microsoft Defender 應用程式控制](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**設定裝置控制和 USB 週邊設備存取** ，以協助防止未經授權的外設威脅損損您的裝置 |[使用 Microsoft Defender for Endpoint 和 Intune 控制 USB 裝置和其他卸除式媒體](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>設定 Microsoft Defender 資訊安全中心

若尚未這麼做，請設定 Microsoft 365 Defender 入口網站以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。 請參閱[Microsoft Defender 資訊安全中心](microsoft-defender-security-center.md)。 您也可以設定使用者是否可以在 Microsoft 365 Defender 入口網站中看到使用者功能。

- [Microsoft Defender 資訊安全中心綜述](/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection： Microsoft Defender 資訊安全中心](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>後續步驟

- [深入瞭解威脅與弱點管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [流覽 Microsoft Defender 資訊安全中心的安全性運作儀表板](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
