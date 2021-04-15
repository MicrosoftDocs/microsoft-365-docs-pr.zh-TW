---
title: 管理 Microsoft Defender 防病毒接收更新的方式和位置
description: 管理 Microsoft Defender 防病毒如何接收保護更新的回退順序。
keywords: 更新，安全性基準，保護，回退順序，ADL，MMPC，UNC，檔案路徑，共用，wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9b1c9bc8c86c5b348e3c4d2a51e0bfafaf3e7174
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765464"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>管理 Microsoft Defender 防病毒防護更新的來源

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

保持最新的防防毒保護是非常重要的。 管理 Microsoft Defender 防病毒的保護更新有兩個元件： 
- 下載更新的 *位置*;和 
- 下載和套用更新 *時*。 

本文說明如何指定應從何處下載更新 (這也稱為「回退訂單) 」。 請參閱 [管理 Microsoft Defender 防病毒更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md) 主題，以取得更新的運作方式，以及如何設定更新的其他方面 (例如排程更新) 。

> [!IMPORTANT]
> Microsoft Defender 防病毒安全性情報更新是透過 Windows Update 傳遞，在2019年10月21日星期一開始，所有的安全性智慧更新將 SHA-2 以獨佔方式簽署。 您的裝置必須更新為支援 SHA-2，才能更新您的安全性情報。 若要深入瞭解，請參閱 [2019 SHA-2 Windows 和 WSUS 的代碼簽署支援需求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>後備順序

一般來說，您可以根據網路設定，設定端點以個別的方式從主要來源下載更新，並依照優先順序順序從其他來源開始下載更新。 更新是以您指定的順序從來源取得。 如果來源無法使用，則會立即使用清單中的下一個來源。

發佈更新時，會套用某些邏輯來減少更新的大小。 在大多數情況下，只有最新的更新和目前安裝的更新之間的差異，也就是下載並套用裝置上的 delta) 所 (。 不過，差異大小取決於兩個主要因素：
- 裝置上最後一次更新的年齡;和 
- 用於下載及套用更新的來源。 

端點上的更新越舊，下載將會變得較大。 不過，您也必須同時考慮下載頻率。 較頻繁的更新排程可能會產生更多的網路使用量，但較低的排程可能會導致每次下載較大的檔案大小。 

有五個位置可讓您指定端點應該取得更新的位置： 

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Server Update Service](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [網路檔共用](#unc-share)
- [Microsoft Defender 防病毒和其他 microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates) (原則和登錄可能會列為 microsoft 惡意程式碼保護中心 (MMPC) 安全性情報，其為其原來的名稱。 ) 

為了確保最佳的保護層級，Microsoft 更新可讓您快速發行，這表示經常下載較小的下載。 Windows Server Update Service、Microsoft Endpoint Configuration Manager 和 Microsoft security 情報更新來源，提供的更新頻率較低。 因此，差異可能會變大，因此會產生較大的下載。 

> [!IMPORTANT]
> 如果您已將 [Microsoft Security 情報頁面](https://www.microsoft.com/security/portal/definitions/adl.aspx) 更新為 Windows Server Update Service 或 Microsoft Update 之後的回退來源，當目前的更新被視為過期時，就只會從安全智慧更新下載更新。  (預設會連續七天內，不能從 Windows Server Update Service 或 Microsoft Update services) 套用更新。
> 不過，您可以 [設定將保護報告為過期前的天數](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)。<p>
> 2019年10月21日當星期一開始，安全性智慧更新將會以獨佔方式 SHA-2。 裝置必須更新為支援 SHA-2，才能取得最新的安全性智慧更新。 若要深入瞭解，請參閱 [2019 SHA-2 Windows 和 WSUS 的代碼簽署支援需求](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。

每個來源都有一般的案例，取決於您的網路的設定方式，以及其發佈更新的頻率，如下表所述：

|位置 | 範例案例 |
|---|---|
|Windows Server Update Service | 您使用 Windows Server Update Service 來管理網路的更新。|
|Microsoft Update | 您想要讓端點直接連接至 Microsoft Update。 這對於未連接到商業網路的不規則端點很有用，否則您不會使用 Windows Server Update 服務來管理更新。|
|檔案共用 | 您有未連接網際網路的裝置 (例如 Vm) 。 您可以使用網際網路連線的 VM 主機，將更新下載至網路共用，Vm 便可以從該網路共用取得更新。 請參閱 [vdi 部署指南](deployment-vdi-microsoft-defender-antivirus.md) 瞭解如何在虛擬桌面基礎結構 (vdi) 環境中使用檔共用。|
|Microsoft 端點管理員 | 您正在使用 Microsoft 端點管理員更新您的端點。|
|Microsoft Defender 防毒軟體和其他 Microsoft 反惡意 (軟體的安全性情報更新，以前稱為 MMPC)  |[請確定您的裝置已更新，以支援 SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus)。 Microsoft Defender 防病毒安全性情報更新是透過 Windows Update 傳遞，在2019年10月21日開始，將會以獨佔方式 SHA-2 簽署安全性情報更新。 <br/>因為最近的感染，或為 [VDI 部署](deployment-vdi-microsoft-defender-antivirus.md)提供強基底影像，所以請下載最新的保護更新。 此選項一般只會用作最後的回退來源，而非主要來源。 只有在 [指定的天數](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)無法從 Windows Server update Service 或 Microsoft Update 下載更新時，才會使用此值。|

您可以管理「群組原則」、「Microsoft 端點設定管理員」、PowerShell Cmdlet 及 WMI 的更新來源的使用順序。

> [!IMPORTANT]
> 如果您將 Windows Server Update Service 設定為下載位置，則不論您用來指定位置的管理工具為何，都必須核准更新。 您可以使用 Windows Server Update 服務設定自動核准規則，這在一天內至少有一次的更新到達時可能很有用。 若要深入瞭解，請參閱 [同步處理 endpoint protection 更新中的獨立 Windows Server Update Service](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。

本文中的程式會先說明如何設定順序，以及如何設定 [檔案 **共用** ] 選項（如果已啟用的話）。

## <a name="use-group-policy-to-manage-the-update-location"></a>使用群組原則來管理更新位置

1. 在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。

2. 在 [ **群組原則管理編輯器** ] 中，移至 [ **電腦** 設定]。

3. 按一下 [ **原則** 然後是系統 **管理範本**]。

4. 將樹展開為 **windows > Windows Defender >** 簽章更新，並設定下列設定：

   1.  按兩下 [ **定義下載安全性情報更新的來源順序** ] 設定，並將此選項設定為 [ **啟用**]。

   2.  輸入來源的順序，以單一管道分隔，例如： `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` ，如下列螢幕擷取畫面所示。

   ![列出來源順序的群組原則設定的螢幕擷取畫面](images/defender/wdav-order-update-sources.png)

   3. 按一下 [確定]。 這會設定保護更新來源的順序。

   4. 按兩下 [定義檔案 **共用以下載安全性情報更新** ] 設定，並將選項設定為 [ **啟用**]。

   5. 輸入檔案共用來源。 如果您有多個來源，請依照應該使用的順序輸入每個來源，並以單一管道分隔。 使用 [標準 UNC 標記法來表示](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) 路徑，例如： `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` 。  如果您沒有輸入任何路徑，當 VM 下載更新時，將會略過此來源。

   6. 按一下 [確定]。 當您在 [ **定義來源的順序** ...] 群組原則設定中參照該來源時，這會設定共用檔共用的順序。

> [!NOTE]
> 針對 Windows 10，版本1703（含1809），原則路徑為 windows **> Microsoft Defender 防病毒 >** 簽章更新的 windows 元件，版本1903，原則路徑是 windows **元件 > Microsoft Defender 防毒程式 > 安全性情報更新**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>使用 Configuration Manager 管理更新位置

如需設定 Microsoft 端點管理員 (目前分支) 的詳細資訊，請參閱 [Configure Security 情報更新 For Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) 。


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>使用 PowerShell Cmdlet 來管理更新位置

使用下列 PowerShell Cmdlet 來設定更新順序。

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
如需詳細資訊，請參閱下列文章：
- [MpPreference-SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [MpPreference-SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [使用 PowerShell Cmdlet 來設定及執行 Microsoft Defender 防毒程式](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender Cmdlet](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>使用 Windows Management 指令 (WMI) 管理更新位置

針對下列屬性，使用 MSFT_MpPreference 類別的 [ **Set** 方法](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) ：

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

如需詳細資訊，請參閱下列文章：
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>使用行動裝置管理 (MDM) 管理更新位置

請參閱 [原則 CSP-Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) 以取得設定 MDM 的詳細資料。

## <a name="what-if-were-using-a-third-party-vendor"></a>如果我們使用協力廠商廠商，該怎麼辦？

本文說明如何設定及管理 Microsoft Defender 防病毒的更新。 不過，協力廠商廠商可用於執行這些工作。 

例如，Contoso 已聘用 Fabrikam 以管理其安全性解決方案，其中包含 Microsoft Defender 防病毒。 Fabrikam 一般使用 [Windows Management Instrumentation](./use-wmi-microsoft-defender-antivirus.md)、 [PowerShell Cmdlet](./use-powershell-cmdlets-microsoft-defender-antivirus.md)或 [windows 命令列](./command-line-arguments-microsoft-defender-antivirus.md) 來部署修補程式和更新。 

> [!NOTE]
> Microsoft 不會測試協力廠商的解決方案，以管理 Microsoft Defender 防毒軟體。

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>建立安全性智慧更新的 UNC 共用

使用排程任務，設定網路檔案共用 (UNC/已映射的磁片磁碟機) 從 MMPC 網站下載安全性智慧更新。

1. 在您想要布建共用及下載更新的系統上，建立您要儲存腳本的資料夾。
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. 建立您將簽章更新儲存至的資料夾。
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. 從 [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)下載 PowerShell 腳本。

4. 按一下 [ **手動下載**]。

5. 按一下 **[下載原始 nupkg**] 檔案。

6. 解壓縮檔。

7. 將檔案 SignatureDownloadCustomTask.ps1 複製到您先前建立的資料夾 C:\Tool\PS-Scripts\。

8. 使用命令列來設定排程的任務。
    > [!NOTE]
    > 有兩種類型的更新：完整和 delta。
   - X64 delta：

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - X64 full：

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - 針對 x86 delta：

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

   - 若為 x86 已滿：

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       “.\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1”
       ```

    > [!NOTE]
    > 建立排程的任務後，您可以在 Microsoft\Windows\Windows Defender 底下的工作排程器中找到這些工作。
9. 手動執行每項工作，並確認下列資料夾中的資料 (mpam-d.exe、mpam-fe.exe 及 nis_full.exe)  (您可能已選擇不同的位置) ：

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   如果排程的任務失敗，請執行下列命令：

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86″
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command “&\”C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\” -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86″
    ```
    > [!NOTE]
    > 問題也可能是因為執行原則。
    
10. 建立指向 C:\Temp\TempSigs (例如 server\updates) 的共用 \\ 。
    > [!NOTE]
    > 驗證的使用者至少必須具有「讀取」存取權。
11. 將原則中的共用位置設定為共用。

    > [!NOTE]
    > 請勿在路徑中新增 x64 (或 x86) 資料夾。 mpcmdrun.exe 程式會自動新增此程式。

## <a name="related-articles"></a>相關文章

- [部署 Microsoft Defender 防毒軟體](deploy-manage-report-microsoft-defender-antivirus.md)
- [管理 Microsoft Defender 防病毒更新並套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)
- [管理已過期端點的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [管理以事件為基礎的強制更新](manage-event-based-updates-microsoft-defender-antivirus.md)
- [管理行動裝置和 Vm 的更新](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)