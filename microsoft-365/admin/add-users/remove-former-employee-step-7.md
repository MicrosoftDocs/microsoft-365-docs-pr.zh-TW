---
title: 步驟 7-刪除離職員工的使用者帳戶
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 請遵循下列步驟來刪除離職員工的使用者帳戶。
ms.openlocfilehash: e2e1b234eaee3818321761af8f737bad8d131b62
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286318"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>步驟 7-刪除離職員工的使用者帳戶

儲存並存取離職員工的所有使用者資料後，您可以刪除離職員工的帳戶。

> [!IMPORTANT]
> 如果您已經設定電子郵件轉寄功能或將它轉換為共用信箱的話，請不要刪除該帳戶。這兩者都需要該帳戶做為轉寄或共用信箱功能的錨點。

1. 在系統管理中心中，移至 **[使用者]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[作用中使用者]</a> 頁面。
2. 選取您要刪除的員工名稱。
3. 在使用者的名稱下，選取 [ **刪除使用者**]。 為此使用者選擇您想要的選項，然後選取 [ **刪除使用者**]。 如果您已有其他使用者存取此使用者的電子郵件和 OneDrive，您不需要在這裡重新執行。

當您刪除使用者時，帳戶會變成非作用中的狀態並持續大約 30 天。在這段期間內，您可以還原該帳戶，但 30 天一過，就會永久刪除。

## <a name="watch-delete-a-former-employees-user-account"></a>觀賞：刪除離職員工的使用者帳戶

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../../business-video/index.yml)。

## <a name="does-your-organization-use-active-directory"></a>貴組織是否使用 Active Directory？

如果您的組織同步處理使用者帳戶以從本機 active directory 環境 Microsoft 365，您必須在本機 active directory 服務中刪除及還原這些使用者帳戶。 您不能在 Office 365 刪除或還原使用者帳戶。

若要瞭解如何在 Active Directory 中刪除及還原使用者帳戶，請參閱 [刪除使用者帳戶](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。
  
如果您使用的是 Azure Active Directory，請參閱[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell Cmdlet。
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>終止員工的電子郵件工作階段所需注意的事項

以下是如何讓員工退出電子郵件 (Exchange) 的詳細資訊。

<br>

****

|您可以執行的作業|做法|
|:-----|:-----|
|終止工作階段 (例如 Outlook 網頁版、Outlook、Exchange Active Sync 等等)，並強制開啟新工作階段|重設密碼|
|終止工作階段並封鎖對日後工作階段的存取 (針對所有通訊協定)|停用帳戶。 例如，在 Exchange 系統管理中心或使用 PowerShell) 中 (： <p>  `Set-Mailbox user@contoso.com -AccountDisabled:$true`|
|終止特定通訊協定的工作階段 (例如 ActiveSync)|停用通訊協定。 例如，在 Exchange 系統管理中心或使用 PowerShell) 中 (： <p>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false`|
|

您可以在三個位置完成上述作業：
  
<br>

****

|如果您在此處終止工作階段|需要多久時間|
|---|---|
|在 Exchange 系統管理中心或使用 PowerShell|預期的延遲是 30 分鐘內|
|在 Azure Active Directory 系統管理中心|預期的延遲是 60 分鐘|
|在內部部署環境|預期的延遲是 3 小時或更多|
|

### <a name="how-to-get-fastest-response-for-account-termination"></a>如何以最快速度取得帳戶終止的回應

**最快**：使用 Exchange 系統管理中心 (使用 PowerShell) 或 Azure Active Directory 系統管理中心。 在內部部署環境中，透過 DirSync 同步處理變更可能會花費數小時。
  
使用 **內部部署和 Exchange Datacenter 中目前狀態的使用者最快**：使用 Azure Active Directory 系統管理中心或 Exchange 的系統管理中心終止會話，並在內部部署環境中也進行變更。 若不採取此做法，在 Azure Active Directory 系統管理中心或 Exchange 系統管理中心進行的變更將被 DirSync 覆寫。
  
## <a name="related-content"></a>相關內容

[還原使用者](restore-user.md) (文章) / [重設密碼](reset-passwords.md) (文章) 
