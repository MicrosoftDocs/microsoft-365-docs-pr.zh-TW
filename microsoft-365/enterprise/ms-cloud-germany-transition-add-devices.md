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
description: 摘要：從 microsoft cloud 德國移至服務時，服務的其他裝置資訊 (Microsoft cloud Deutschland) 以 Office 365 新德文 datacenter 區域中的服務。
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861298"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>從 Microsoft Cloud Deutschland 遷移的其他裝置資訊

連接至 Microsoft 雲端 Deutschland 的 Azure AD 加入和註冊裝置必須在階段9和階段10之前遷移。 裝置的遷移取決於裝置類型、作業系統和 AAD 關聯。 

## <a name="frequently-asked-questions"></a>常見問題集

**如何判斷組織是否受到影響？**

管理員應該檢查 `https://portal.microsoftazure.de` 是否有任何已註冊或 AZURE AD 連接的裝置。 如果您的組織已註冊裝置，您會受到影響。

**對我的使用者有何影響？**

已註冊的裝置中的使用者將無法再登入 [遷移階段 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 已完成，且已停用 Microsoft Cloud Deutschland 的端點。  

在您的組織中斷與 Microsoft 雲端 Deutschland 的連線之前，請確定您的所有裝置都已向全球端點註冊。
  
**我的使用者何時重新註冊其裝置？**

您的成功必須先取消註冊，然後在 [階段 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) 完成之後重新登錄裝置，這一點很重要。 您必須在第10階段開始之前完成重新註冊，否則您可能會失去對裝置的存取權。

**如何在遷移後還原我的裝置狀態？**

對於向 Azure AD 註冊的公司所擁有的 Windows 裝置，管理員將能夠透過遠端觸發的工作流程（會取消註冊舊的裝置狀態）來管理這些裝置的遷移。
  
對於所有其他裝置，包括在 Azure AD 中註冊的個人 Windows 裝置，使用者必須手動執行這些步驟。 若為已加入 Azure 的裝置，使用者必須具有本機系統管理員帳戶，才可取消註冊，然後重新登錄其裝置。

如需如何成功還原下列裝置狀態的詳細指示，請參閱詳細指示。 
 
**如何知道我的所有裝置都已登錄公用雲端？**

若要檢查您的裝置是否已在公用雲端中註冊，您應該將裝置清單從 Azure AD 入口網站匯出並下載至 Excel 試算表。 然後，使用 _registeredTime_ 欄) [不同于 Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) 遷移階段之後，篩選 (所註冊的裝置。

## <a name="additional-considerations"></a>其他考量
在遷移租使用者後，裝置註冊會停用，且無法啟用或停用。 

若未使用 Intune，請登入您的訂閱，並執行此命令以重新開機此選項：

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**重要：** 在商務用遷移後，將會啟用 Intune 服務主體，這表示 Azure AD Device Registration 的啟用。 如果您在遷移之前封鎖 Azure AD 裝置註冊，您必須使用 PowerShell 停用 Intune service 主體，以使用 Azure AD 入口網站停用 Azure AD 裝置註冊。 您可以在 Graph 模組的 Azure Active Directory PowerShell 中，使用此命令來停用 Intune 服務主體。

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Azure AD 加入
這適用于 Windows 10 裝置。 

如果裝置已加入 Azure AD，必須中斷與 Azure AD 的連線，並再次連線。 

[![AZURE AD 裝置 Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


如果使用者是 Windows 10 裝置上的系統管理員，使用者可以從 Azure AD 中登出裝置，然後重新加入。 如果他沒有系統管理員許可權，則使用者需要此機器上本機系統管理員帳戶的認證。 


管理員可以在此設定路徑之後的裝置上建立本機系統管理員帳戶：

*設定 > 帳戶 > 其他帳戶 > 憑證未知 > 新增沒有 Microsoft 帳戶的使用者*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>步驟1：判斷裝置是否已加入 Azure 識別碼
1.  使用使用者電子郵件和密碼登入。
2.  移至設定 > 帳戶 > 存取單位或學校。 
3.  在清單中尋找 [ **連線至 ...] 的使用者。的 Azure AD**。 
4.  如果已連線的使用者存在，請繼續進行步驟2。 如果不是，則不需要進一步的動作。
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>步驟2：從 Azure AD 中斷裝置連線
1.  在連線的公司或學校帳戶上，按一下 [ **中斷連線]** 。 
2.  確認 [中斷連線] 兩次。 
3.  輸入本機系統管理員的使用者名稱和密碼。 裝置中斷連線。
4.  重新開機裝置。
### <a name="step-3-join-the-device-to-azure-ad"></a>步驟3：將裝置加入 Azure AD
1.  使用者使用本機系統管理員的認證登入
2.  移至 **設定** 然後 **帳戶****存取工作或學校**
3.  點擊 **連線**
4.  **重要** 事項：點擊 [**加入 Azure AD** ]
5.  輸入使用者的電子郵件地址和密碼。 裝置已連線
6.  重新開機裝置 
7.  使用您的電子郵件地址和密碼進行簽署

## <a name="azure-ad-registered-company-owned"></a>Azure AD 已登記 (公司擁有) 

若要判斷 Windows 10 裝置是否已登錄 Azure AD –已註冊，請在裝置上執行下列命令：

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

- 位置： HKLM\SOFTWARE\Policies\Microsoft\ Windows \WorkplaceJoin
- 類型： DWORD (32 位) 
- 名稱： BlockAADWorkplaceJoin
- 值資料：1

此登錄值的出現應該會封鎖 workplace join，並防止使用者看到加入裝置的提示。

## <a name="android"></a>Android

若為 Android，使用者將需要撤銷註冊並重新登錄其裝置。 這可以透過 Microsoft Authenticator 應用程式或公司入口網站應用程式來完成。 

- 在 Microsoft Authenticator 應用程式中，使用者可以前往 **設定 > 裝置註冊**。 從這裡開始，使用者可以撤銷註冊並重新登錄其裝置。
 
- 從公司入口網站中，使用者可以移至 [**裝置**] 索引標籤並移除裝置。 之後，使用公司入口網站重新註冊裝置。
 
- 使用者也可以從 [帳戶設定] 頁面移除帳戶，然後重新加入工作帳戶，以取消登錄和重新註冊。

若要使用 Microsoft Authenticator 應用程式在 Android 上撤銷登錄並重新登錄，請執行下列動作：

1.  開啟 Microsoft Authenticator 應用程式，然後移至 **設定**。
2.  選取 **Device registration**。
3.  選取 [ **登出**] 以取消登錄裝置。
4.  若為 **Device registration**，請輸入您的電子郵件地址，然後選取 [ **註冊**]，以重新註冊裝置。

若要使用 Android 設定頁面來撤銷註冊並重新登錄 Android 裝置，請執行下列動作：

1.  開啟 [**裝置設定**]，然後移至 [**帳戶**]。
2.  選取您要重新註冊的工作帳戶，然後選取 [ **移除帳戶**]。
3.  移除帳戶後，請從 [ **帳戶** ] 頁面中，選取 [ **新增帳戶 > 工作帳戶**]。
4.  在 [ **Workplace Join**] 中輸入您的電子郵件地址，然後選取 [ **加入** ] 以完成裝置的註冊。

若要從公司入口網站登出並重新登錄 Android 上的裝置：

1.  啟動公司入口網站，然後移至 [**裝置**] 索引標籤。
2.  選取裝置以查看裝置詳細資料。
3.  從省略號 (三點) 功能表中，選取 [ **移除裝置**]，並在對話方塊中確認以完成移除。
4.  您現在應該已登出公司入口網站的應用程式。 選取 [登入] 以重新 **登錄** 裝置。

如需此工作負載遷移階段所需之任何動作的詳細資訊，或對管理或使用的影響，請參閱 azure ad) 中 Azure Active Directory (Azure ad 的相關資訊，以[供從 Microsoft Cloud Deutschland 進行遷移的其他 azure ad 資訊中取得](ms-cloud-germany-transition-azure-ad.md)。

## <a name="ios"></a>iOS

在 iOS 裝置上，使用者將需要從 Microsoft Authenticator 手動移除任何快取的帳戶、登出裝置，然後登出裝置上的任何原生應用程式。

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>步驟1：若存在，請從 Microsoft Authenticator 應用程式中移除帳戶。

1. 在 Microsoft Authenticator 應用程式中點擊帳戶。
2. 按一下右上角的 **設定** 圖示。 如果您沒有看到 **設定** 圖示，則可能是您使用的是 Microsoft Authenticator 的最新版本。
3. 點擊 [ **移除帳戶** ] 按鈕。
4. 點擊 [ **此裝置上的所有應用程式**]。
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>步驟2：從 Microsoft Authenticator 應用程式中登出裝置

1. 在右上角點擊功能表圖示。
2. 按 **設定**，然後按 **裝置註冊**。
4. 如果顯示您的帳戶，請點擊 [ **登出裝置** ]，然後在對話方塊中 **繼續** 。 之後，您就不會看到任何帳戶。
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>步驟3：必要時登出個別應用程式

使用者可以移至個別應用程式，例如 Outlook、Teams 及 OneDrive，以及從這些應用程式中移除帳戶。

## <a name="more-information"></a>其他資訊

開始：

- [從 Microsoft Cloud Deutschland 遷移至新德國資料中心區域的 Office 365 服務](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 移轉協助](https://aka.ms/germanymigrateassist)
- [如何選擇加入移轉](ms-cloud-germany-migration-opt-in.md)
- [遷移期間的客戶體驗](ms-cloud-germany-transition-experience.md)

在轉換中移動：

- [移轉階段的動作與影響](ms-cloud-germany-transition-phases.md)
- [其他預備工作](ms-cloud-germany-transition-add-pre-work.md)
- [AZURE AD](ms-cloud-germany-transition-azure-ad.md)、[裝置](ms-cloud-germany-transition-add-devices.md)、[經驗](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他資訊。

雲端應用程式：

- [Dynamics 365 的移轉程式資訊](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 移轉程式資訊](/power-bi/admin/service-admin-migrate-data-germany)
- [開始升級您的 Microsoft Teams](/microsoftteams/upgrade-start-here)