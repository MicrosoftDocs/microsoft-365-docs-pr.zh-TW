---
title: 使用群組原則物件管理 Microsoft Defender for Endpoint
description: 瞭解如何使用群組原則物件管理 Microsoft Defender for Endpoint
keywords: 遷移後、管理、作業、維護、使用狀況、PowerShell、Microsoft Defender for Endpoint、edr
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
ms.openlocfilehash: ce204c1a90e57a651cf9c97974a8b35d405878cc
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908289"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>使用群組原則物件管理 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> 建議使用[Microsoft 端點管理員](/mem)來管理組織的威脅防護功能，以供裝置 (也稱為端點) 。 端點管理員包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)。 **[深入瞭解端點管理員](/mem/endpoint-manager-overview)**。 

您可以在 Azure Active Directory 網域服務中使用群組原則物件，以管理 Microsoft Defender for Endpoint 中的某些設定。

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>使用群組原則物件設定 Microsoft Defender for Endpoint

下表列出您可以執行的各項工作，以使用群組原則物件設定 Microsoft Defender for Endpoint。

|工作  |可深入了解的資源  |
|---------|---------|
|**管理使用者和電腦物件的設定** <br/><br/>*自訂內建的群組原則物件，或建立自訂的群組原則物件和組織單位，以符合您的組織需求。*     |[管理 Azure Active Directory 網域服務管理網域中的群組原則](/azure/active-directory-domain-services/manage-group-policy)   |
|**設定 Microsoft Defender 防毒軟體** <br/><br/>*設定防病毒功能 & 功能，包括組織裝置上的原則設定、排除、修正及排程的掃描 (也稱為端點) 。*   |[使用群組原則設定來設定及管理 Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[使用群組原則來啟用雲端傳送保護](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**管理組織的攻擊面減少規則** <br/><br/>*從 & 資料夾中排除檔案，或將自訂文字新增至使用者裝置上顯示的通知警示，以自訂攻擊面減少規則。* |[使用群組原則物件自訂攻擊面降低規則](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**管理 exploit protection 設定**<br/><br/>*您可以自訂 exploit protection 設定、匯入設定檔，然後使用「群組原則」來部署該設定檔。*  |[自訂 exploit protection 設定](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[匯入、匯出及部署利用保護群組原則](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[使用群組原則來散佈設定](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**啟用網路保護** ，以協助防止員工在網際網路上使用惡意內容的應用程式 <br/><br/>*我們建議您先在測試環境中使用 [審計模式](/microsoft-365/security/defender-endpoint/evaluate-network-protection) ，以查看哪些應用程式會封鎖，然後再進行部署。* |[使用群組原則開啟網路保護](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**設定受管理的資料夾存取** 權以防護勒索軟體 <br/><br/>*「[受管理的資料夾存取](/microsoft-365/security/defender-endpoint/controlled-folders)」也稱為 antiransomware protection。*  |[使用群組原則啟用受控資料夾存取](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**設定 Microsoft Defender SmartScreen** 以防範網際網路上的惡意網站和檔案。  |[使用群組原則設定 Microsoft Defender SmartScreen 群組原則和行動裝置管理 (MDM) 設定](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**設定加密和 BitLocker** ，以保護組織執行 Windows 的裝置資訊 |[BitLocker群組原則設定](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**設定 Microsoft Defender Credential Guard** 以防護認證盜竊攻擊 |[使用群組原則啟用 Windows Defender Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>設定 Microsoft Defender 資訊安全中心

若尚未這麼做，請設定 Microsoft 365 Defender 入口網站以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。 請參閱[Microsoft Defender 資訊安全中心](microsoft-defender-security-center.md)。 您也可以設定使用者是否可以在 Microsoft 365 Defender 入口網站中看到使用者功能。

- [Microsoft Defender 資訊安全中心綜述](/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection： Microsoft Defender 資訊安全中心](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>後續步驟

- [深入瞭解威脅與弱點管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [流覽 Microsoft Defender 資訊安全中心的安全性運作儀表板](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
