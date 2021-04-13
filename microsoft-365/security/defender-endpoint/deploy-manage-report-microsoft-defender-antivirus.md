---
title: 在 Microsoft Defender 防毒軟體上部署、管理和報告
description: 您可以使用 Intune、Microsoft Endpoint Configuration Manager、群組原則、PowerShell 或 WMI 部署及管理 Microsoft Defender 防毒程式
keywords: 部署、管理、更新、保護、Microsoft Defender 防毒軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a9cd04300e67f956b50f07c02f3dc00c515f02eb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690240"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>在 Microsoft Defender 防毒軟體上部署、管理和報告

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

您可以使用多種方式，在 Microsoft Defender 防病毒上部署、管理及報告。

因為 Microsoft Defender 防病毒用戶端已安裝為 Windows 10 的核心元件，所以不會套用傳統的用戶端部署至您的端點。

不過，在大多數的情況下，您仍需要使用 Microsoft Intune、Microsoft Endpoint Configuration Manager、Azure Defender 或群組原則物件，在端點上啟用保護服務，如下表所述。

您也會看到下列的其他連結：

- 管理 Microsoft Defender 防防毒保護，包括管理產品及保護更新
- 報告 Microsoft Defender 防防毒保護

> [!IMPORTANT]
> 在大多數情況下，Windows 10 會停用 Microsoft Defender 防毒軟體（如果它找到另一個正在執行的和更新的防病毒產品）。 您必須先停用或卸載協力廠商防病毒產品，Microsoft Defender 防病毒產品才能運作。 如果您重新啟用或安裝協力廠商防病毒產品，Windows 10 會自動停用 Microsoft Defender 防病毒產品。

工具|部署選項 (<a href="#fn2" id="ref2">2</a>) |網路範圍設定和原則或基準部署)  ([3](#fn3)) 的管理選項 (|報告選項  
---|---|---|---  
Microsoft Intune|[在 Intune 中新增 endpoint protection 設定](/intune/endpoint-protection-configure)|[在 Intune 中設定裝置限制設定](/intune/device-restrictions-configure)| [使用 Intune 主控台管理裝置](/intune/device-management)  
Microsoft 端點管理員 ([1](#fn1)) |使用 [Endpoint protection point site system role][] 並 [啟用具有自訂用戶端設定的 endpoint protection][]|使用 [預設和自訂的反惡意程式碼原則][] 及 [用戶端管理][]|使用預設 [Configuration Manager 監控工作區][] 和 [電子郵件警示][]  
群組原則和 Active Directory (已加入網域的) |使用群組原則物件部署設定變更，並確定已啟用 Microsoft Defender 防病毒。|使用群組原則物件 (Gpo) [設定 Microsoft Defender 防毒軟體的更新選項][] 及 [設定 Windows Defender 功能][]|「群組原則」無法使用端點報告。 您可以產生 [群組原則的清單，以判斷是否未套用任何設定或原則][]
PowerShell|使用群組原則、Microsoft 端點設定管理員或在個別端點上手動部署。|使用在 Defender 模組中可用的 [MpPreference] 和 [MpSignature] Cmdlet。|使用 [在 Defender 模組中可用的適當 Get Cmdlet][]
Windows Management Instrumentation|使用群組原則、Microsoft 端點設定管理員或在個別端點上手動部署。|使用 [MSFT_MpPreference 類別的 Set 方法][] 和 [MSFT_MpSignature 類別的 Update 方法][]|使用[Windows Defender WMIv2 提供者][]中關聯類別的[MSFT_MpComputerStatus][]類別和 get 方法
Microsoft Azure|[使用 Visual Studio virtual machine configuration 或使用 Azure PowerShell Cmdlet，在 azure 入口網站](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)中部署 Azure 的 Microsoft 反惡意軟體。 您也可以 [在 Azure Defender 中安裝 Endpoint protection *](/azure/security-center/security-center-install-endpoint-protection)|[使用 Azure PowerShell Cmdlet 為虛擬機器和雲端服務設定 Microsoft 反惡意軟體，](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)或[使用程式碼範例](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|使用 [Microsoft 反惡意軟體（搭配 Azure PowerShell Cmdlet）進行虛擬機器和雲端服務](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) ，以啟用監視。 您也可以在 Azure Active Directory 中查看使用狀況報告，以判斷可疑的活動（包括 [可能受感染的裝置][] 報告），並設定 SIEM 工具，以報告 [Microsoft Defender 防病毒事件][] ，並將該工具新增為 AAD 中的應用程式。

1. <span id="fn1" />Microsoft 端點管理員 (目前的分支) 與 System Center 2012 Configuration Manager 不同，因此某些功能及功能（特別是與雲端提供的保護）的可用性有所不同。 在此文件庫中，我們已專注于 Windows 10、Windows Server 2016 和 Microsoft 端點管理員 (目前的分支) 。 請參閱 [使用 microsoft 雲端在 Microsoft Defender 防毒軟體中提供的保護](cloud-protection-microsoft-defender-antivirus.md) ，以取得主要差異的表格。 [ (回到 table) ](#ref2)
  
2.  <span id="fn2" />在 Windows 10 中，Microsoft Defender 防病毒是可用的元件，未安裝或部署其他用戶端或服務。 在未安裝協力廠商防病毒產品時，會自動啟用此功能 ([但 Windows Server 2016) 除外](microsoft-defender-antivirus-on-windows-server.md) 。 因此不需要傳統部署。 此處的部署是指確定 Microsoft Defender 防病毒元件可在端點或伺服器上使用並啟用。 [ (回到 table) ](#ref2)

3. <span id="fn3" />功能和保護的設定，包括設定產品及保護更新，會在此程式庫的 [ [設定 Microsoft Defender 防病毒功能](configure-notifications-microsoft-defender-antivirus.md) ] 區段中進一步說明。 [ (回到 table) ](#ref2)

[Endpoint Protection point site system role]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[預設及自訂的反惡意程式碼原則]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[用戶端管理]:  /configmgr/core/clients/manage/manage-clients
[啟用具有自訂用戶端設定的 Endpoint Protection]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Configuration Manager 監控工作區]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[電子郵件警示]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[MSFT_MpPreference 類別的 Set 方法]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpSignature 類別的 Update 方法]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2 提供者]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[更新-MpSignature]: /powershell/module/defender/update-mpsignature
[在 Defender 模組中使用的取得 Cmdlet]: /powershell/module/defender/
[設定 Microsoft Defender 防病毒的更新選項]: manage-updates-baselines-microsoft-defender-antivirus.md
[設定 Windows Defender 功能]: configure-microsoft-defender-antivirus-features.md
[決定未套用任何設定或原則的群組原則]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[可能受感染的裝置]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender 防病毒事件]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>本節內容

主題 | 描述
---|---
[部署並啟用 Microsoft Defender 防防毒保護](deploy-microsoft-defender-antivirus.md) | 當用戶端安裝為 Windows 10 的核心元件時，如果不會套用傳統部署，則您仍然需要使用 Microsoft 端點 Configuration Manager、Microsoft Intune 或群組原則物件，在端點上啟用用戶端。 
[管理 Microsoft Defender 防病毒更新並套用基準](manage-updates-baselines-microsoft-defender-antivirus.md) | 更新 Microsoft Defender 防病毒有兩個部分：在端點上更新用戶端 (產品更新) ，以及更新安全性智慧 (保護更新) 。 您可以使用 Microsoft 端點設定管理員、群組原則、PowerShell 及 WMI，以許多方式更新安全性情報。
[監視和報告 Microsoft Defender 防防毒保護](report-monitor-microsoft-defender-antivirus.md) | 您可以使用 microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite 的更新合規性增益集，或是協力廠商的 SIEM 產品 (，方法是使用 Windows 事件記錄檔) 監視保護狀態，並建立有關 Endpoint protection 的報告。