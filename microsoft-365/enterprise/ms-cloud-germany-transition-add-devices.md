---
title: 從 Microsoft Cloud Deutschland 遷移的其他裝置資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：從 Microsoft Cloud (德國移至 Microsoft cloud Deutschland 時，服務的其他裝置資訊) 新德文 datacenter 區域中的 Office 365 服務。
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688650"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 遷移的其他裝置資訊

## <a name="frequently-asked-questions"></a>常見問題集

**如何判斷組織是否受到影響？**

管理員應該檢查 `https://portal.microsoftazure.de` 是否有任何已註冊的裝置。 如果您的組織已註冊裝置，您會受到影響。

**對我的使用者有何影響？**

在您的遷移進入 [Finalize AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段後，已登錄裝置的使用者將無法再登入。  

在您的組織中斷與 Microsoft 雲端 Deutschland 的連線之前，請確定您的所有裝置都已向全球端點註冊。
  
**我的使用者何時重新註冊其裝置？**

您的成功必須先取消註冊，然後在 [不同的 Microsoft 雲端 Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段重新登錄裝置，這一點很重要。

**如何在遷移後還原我的裝置狀態？**

對於以 Azure AD 註冊的混合式 Azure AD （已加入及公司所擁有的 Windows 裝置），管理員將能夠透過遠端觸發的工作流程（會取消註冊舊的裝置狀態）來管理這些裝置的遷移。
  
對於所有其他裝置，包括在 Azure AD 中註冊的個人 Windows 裝置，使用者必須手動執行這些步驟。 若為已加入 Azure 的裝置，使用者必須具有本機系統管理員帳戶，才可取消註冊，然後重新登錄其裝置。

Microsoft 會發佈有關如何成功還原裝置狀態的指示。 
 
**如何知道我的所有裝置都已登錄公用雲端？**

若要檢查您的裝置是否已在公用雲端中註冊，您應該將裝置清單從 Azure AD 入口網站匯出並下載至 Excel 試算表。 然後，使用 _registeredTime_ 欄) [不同于 Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段之後，篩選 (所註冊的裝置。

在遷移租使用者後，裝置註冊會停用，且無法啟用或停用。 若未使用 Intune，請登入您的訂閱，並執行此命令以重新開機此選項：

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Windows 混合式 Azure AD 聯結

### <a name="windows-down-level"></a>Windows 低層級

_Windows 下層裝置_ 是目前執行舊版 Windows 的 windows 裝置 (例如 windows 8.1 或 windows 7) ，或執行2019和2016之前的 windows Server 版本。 如果這些裝置在註冊之前已註冊，您必須撤銷註冊並重新登錄這些裝置。 

若要判斷 Windows 下層裝置先前是否加入 Azure AD，請在裝置上使用下列命令：

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

如果裝置先前已加入 Azure AD，而且裝置具有與全域 Azure AD 端點的網路連線，您會看到下列輸出：

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

受影響裝置的「裝置狀態」會具有值為 "Unknown"。 若輸出為 "裝置未加入" 或 "Device state" 值為 "Ok"，請忽略下列指導方針。

僅限顯示裝置已通過 deviceId、指紋等等)  (加入，且其「裝置狀態」值為「未知」的裝置，管理員應該在此類下層裝置的網域使用者登入上下文中執行下列命令：

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

在 Windows 下層裝置上，針對每個網域使用者登入，上述命令只需執行一次。 這個命令應該在網域使用者登入的內容中執行。 

在使用者後續登入時，您必須採取足夠的護理，才可執行此命令。 當先前的命令執行時，它會為登入的使用者清除本機混合式 Azure AD –加入的電腦的已加入狀態。 而且，如果電腦仍設定為在租使用者中加入混合式 Azure AD，它會在使用者重新登入時嘗試加入。

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>脫離

若要判斷 Windows 10 裝置先前是否加入 Azure AD，請在裝置上執行下列命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果裝置為混合式 Azure AD-已加入，系統管理員會看到下列輸出：

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

如果輸出為 "AzureAdJoined：否"，請忽略下列指導方針。

僅限顯示裝置加入 Azure AD 的裝置，以系統管理員身分執行下列命令，以移除裝置的已加入狀態。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上述命令只需要在 Windows 裝置的系統管理內容中執行一次。

#### <a name="hybrid-ad-joinre-registration"></a>混合式 AD Join\Re-Registration

只要裝置具有與全域 Azure AD 端點的網路連線，裝置就會自動加入至 Azure AD （無使用者或系統管理員干預）。 


## <a name="windows-azure-ad-join"></a>Windows Azure AD 加入

**重要：** 在商務用遷移後，將會啟用 Intune 服務主體，這表示 Azure AD Device Registration 的啟用。 如果您在遷移之前封鎖 Azure AD 裝置註冊，您必須使用 PowerShell 停用 Intune service 主體，以使用 Azure AD 入口網站停用 Azure AD 裝置註冊。 您可以在 [Graph] 模組的 [Azure Active Directory PowerShell 中使用此命令來停用 Intune 服務主體。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>脫離

若要判斷 Windows 10 裝置先前是否加入 Azure AD，使用者或系統管理員可以在裝置上執行下列命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果裝置加入 Azure AD，則使用者或系統管理員會看到下列輸出：

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

如果輸出為 "AzureAdJoined：否"，請忽略下列指導方針。

使用者：如果裝置已加入 Azure AD，使用者可以從設定中脫離裝置。 在從 Azure AD unjoining 裝置之前，請確認裝置上具有本機系統管理員帳戶。 需要有本機系統管理員帳戶，才可重新登入裝置。

Admin：如果組織的系統管理員想要將已加入 Azure AD 的使用者裝置，可在每個裝置上執行下列命令，以使用群組原則等機制來執行此動作。 管理員在從 Azure AD unjoining 裝置之前，必須先確認裝置上具有本機系統管理員帳戶。 需要有本機系統管理員帳戶，才可重新登入裝置。

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

上述命令只需要在 Windows 裝置的系統管理內容中執行一次。 

### <a name="azure-ad-joinre-registration"></a>Azure AD 加入/重新註冊

使用者可以從 [Windows 設定] 將裝置加入 Azure AD： **設定 > 帳戶 > 存取工作或學校 >** 連線。
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD 已登記 (公司擁有) 

若要判斷 Windows 10 裝置是否已登錄 Azure AD，請在裝置上執行下列命令：

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

如果裝置已註冊的是 Azure AD，您會看到下列輸出：

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

若要移除裝置上現有的 Azure AD 註冊帳戶，請執行下列動作：

- 若要移除裝置上的 Azure AD 註冊帳戶，請使用 CleanupWPJ （您可以從這裡下載的工具）： [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)。

- 解壓縮 ZIP 檔，並執行 **WPJCleanup。** 此工具會根據裝置上的 Windows 版本啟動正確的可執行檔。

- 系統管理員可以使用像是「群組原則」這樣的機制，在裝置上任何登入之使用者的上下文中執行命令。

若要停用 Web 帳戶管理員在 Azure AD 中註冊裝置的提示，請新增此登錄值： 

- 位置： HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- 類型： DWORD (32 位) 
- 名稱： BlockAADWorkplaceJoin
- 值資料：1

此登錄值的出現應該會封鎖 workplace join，並防止使用者看到加入裝置的提示。

## <a name="android"></a>Android

若為 Android，使用者將需要撤銷註冊並重新登錄其裝置。 這可以透過 Microsoft 驗證器應用程式或公司入口網站應用程式來完成。 

- 使用者可以從 Microsoft 驗證器應用程式移至 [ **設定] > Device Registration**。 從這裡開始，使用者可以撤銷註冊並重新登錄其裝置。
 
- 在公司入口網站中，使用者可以移至 [ **裝置** ] 索引標籤並移除裝置。 之後，使用公司入口網站重新註冊裝置。
 
- 使用者也可以從 [帳戶設定] 頁面移除帳戶，然後重新加入工作帳戶，以取消登錄和重新註冊。

若要使用 Microsoft 驗證器應用程式，在 Android 上撤銷登錄並重新註冊裝置：

1.  開啟 Microsoft 驗證器應用程式，然後移至 [ **設定**]。
2.  選取 **Device registration**。
3.  選取 [ **登出**] 以取消登錄裝置。
4.  若為 **Device registration**，請輸入您的電子郵件地址，然後選取 [ **註冊**]，以重新註冊裝置。

若要使用 [Android 設定] 頁面撤銷註冊並重新登錄 Android 裝置，請執行下列動作：

1.  開啟 [ **裝置設定** ]，然後移至 [ **帳戶**]。
2.  選取您要重新註冊的工作帳戶，然後選取 [ **移除帳戶**]。
3.  移除帳戶後，請從 [ **帳戶** ] 頁面中，選取 [ **新增帳戶 > 工作帳戶**]。
4.  在 [ **Workplace Join**] 中輸入您的電子郵件地址，然後選取 [ **加入** ] 以完成裝置的註冊。

若要從公司入口網站上登出並重新登錄 Android 上的裝置：

1.  啟動公司入口網站，然後移至 [ **裝置** ] 索引標籤。
2.  選取裝置以查看裝置詳細資料。
3.  從省略號 (三點) 功能表中，選取 [ **移除裝置**]，並在對話方塊中確認以完成移除。
4.  您現在應該已登出公司入口網站應用程式。 選取 [登入] 以重新 **登錄** 裝置。

如需此工作負載遷移階段所需之任何動作的詳細資訊，或對管理或使用的影響，請參閱其他 Azure AD information for the Azure Active Directory (Azure AD) 中的相關資訊，以 [供從 Microsoft Cloud Deutschland 進行遷移](ms-cloud-germany-transition-azure-ad.md)。

## <a name="ios"></a>iOS

在 iOS 裝置上，使用者將需要從 Microsoft 驗證者手動移除任何快取的帳戶、登出裝置，然後登出裝置上的任何原生應用程式。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>步驟1：若存在，請從 Microsoft 驗證器應用程式中移除帳戶

1. 點擊 Microsoft 驗證應用程式中的帳戶。
2. 按一下右上角的 [ **設定** ] 圖示。 如果您看不到 [ **設定** ] 圖示，表示您可能並未使用最新版的 Microsoft 驗證者。
3. 點擊 [ **移除帳戶** ] 按鈕。
4. 點擊 [ **此裝置上的所有應用程式**]。
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>步驟2：從 Microsoft 驗證器應用程式登出裝置

1. 在右上角點擊功能表圖示。
2. 點擊 [ **設定** ]，然後按 **裝置註冊**。
4. 如果顯示您的帳戶，請點擊 [ **登出裝置** ]，然後在對話方塊中 **繼續** 。 之後，您就不會看到任何帳戶。
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>步驟3：必要時登出個別應用程式

使用者可以移至個別應用程式，例如 Outlook、小組和 OneDrive，以及從這些應用程式中移除帳戶。

## <a name="more-information"></a>其他資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德文 datacenter 區域中的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](https://aka.ms/d365ceoptin)
- [Power BI 移轉程式資訊](https://aka.ms/pbioptin)
- [開始升級您的 Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
