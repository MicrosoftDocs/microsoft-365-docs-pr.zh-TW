---
title: 部署獨立的 SharePoint Online 小組網站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 使用此逐步部署指南，在 Microsoft Office 365 中建立和設定隔離的 SharePoint Online 小組網站。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d226a545c3f8dc274f02e5d54d39739fe5d981ea
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288344"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>部署獨立的 SharePoint Online 小組網站

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

 **摘要：** 使用下列逐步指示來部署新的獨立 SharePoint Online 小組網站。

本文屬於逐步部署指南，說明如何在 Microsoft Office 365 中建立及設定獨立的 SharePoint Online 小組網站。 下列步驟假設使用三個預設 SharePoint 群組和對應的權限等級，其中每個存取層級都有一個 Azure Active Directory (AD) 型存取群組。

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>階段1：建立並填入小組網站存取群組

在這個階段中，您會針對三個預設 SharePoint 群組建立三個 Azure AD 型存取群組，並填入適當的使用者帳戶。

> [!NOTE]
> 下列步驟假設所有必要的使用者帳戶都已經存在，並已獲派適當的授權。 如果沒有，請先新增並指派授權，再繼續進行步驟1。

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>步驟1：列出網站的 SharePoint Online 系統管理員

決定與獨立小組網站的 SharePoint Online 系統管理員對應的一組使用者帳戶。

如果您是透過 Microsoft 365 管理使用者帳戶和群組，且想要使用 Windows PowerShell，請將其使用者主體名稱清單 (Upn)  (範例 UPN： belindan@contoso.com) 。

### <a name="step-2-list-the-members-for-the-site"></a>步驟2：列出網站的成員

決定與獨立小組網站成員對應的一組使用者帳戶，其會在網站中所儲存的資源上共同作業。

如果您是透過 Microsoft 365 管理使用者帳戶和群組，且想要使用 PowerShell，請建立其 Upn 的清單。 如果有大量網站成員，您可以將 UPN 清單儲存在文字檔中，並使用單一 PowerShell 命令全部新增。

### <a name="step-3-list-the-viewers-for-the-site"></a>步驟3：列出網站的檢視者

決定與獨立小組網站檢視者對應的一組使用者帳戶，其可檢視網站中儲存的資源，但不能加以修改或直接在其內容上共同作業。

如果您是透過 Microsoft 365 管理使用者帳戶和群組，且想要使用 PowerShell，請建立其 Upn 的清單。 如果有大量網站成員，您可以將 UPN 清單儲存在文字檔中，並使用單一 PowerShell 命令全部新增。

網站的檢視者可能包括管理階層、法律顧問或各部門的專案關係人。

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>步驟4：在 Azure AD 中建立網站的三個存取群組

您需要在 Azure AD 中建立下列存取群組：

- 網站管理員 (其中包含步驟 1 的清單)
- 網站成員 (其中包含步驟 2 的清單)
- 網站檢視者 (其中包含步驟 3 的清單)

1. 在您的瀏覽器中，移至 Azure 入口網站 (<https://portal.azure.com>)，並以已獲派使用者管理管理員或公司系統管理員角色的帳戶認證登入。

2. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]。

3. 在 [群組 - 所有群組] 刀鋒視窗中，按一下 [+ 新增群組]。

4. 在 [新增群組] 刀鋒視窗中：

   - 在 [群組類型] 中選取 [安全性]。

   - 在 [名稱] 中鍵入群組名稱。

   - 在 [群組描述] 中鍵入群組的描述。

   - 在 [成員資格類型] 中選取 [已指派]。

5. 按一下 [建立]，然後關閉 [群組] 刀鋒視窗。

6. 針對其他群組重複步驟 3 至 5。

> [!NOTE]
> 您需要使用 Azure 入口網站來建立群組，以便其啟用 Office 功能。 如果您後來將 SharePoint Online 獨立網站設定為高度機密網站，其使用「Azure 資訊保護」標籤來加密檔案並將權限指派給特定群組，則必須在啟用 Office 功能的情況下建立允許的群組。 建立 Azure AD 群組之後，您就無法變更其 Office 功能設定。

以下是您的最終設定，其具有三個網站存取群組。

![用於部署獨立 SharePoint Online 網站的三個存取群組。](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>步驟 5。 將使用者帳戶新增至存取群組

在此步驟中進行以下動作：

1. 將步驟1中的使用者清單新增至網站管理員存取群組。
2. 將步驟2中的使用者清單新增至網站成員存取群組。
3. 將步驟3的使用者清單新增至網站檢視器訪問群組。

如果您是透過 Active Directory Domain Services (AD DS) 來管理使用者帳戶和群組，請使用一般 AD DS 使用者和群組管理程式將使用者新增至適當的訪問群組，並等待與 Microsoft 365 訂閱進行同步處理。

如果您是透過 Office 365 管理使用者帳戶和群組，您可使用 Microsoft 365 系統管理中心或 PowerShell。 如果任何存取群組有重複的群組名稱，您應該使用 Microsoft 365 系統管理中心。

在 Microsoft 365 系統管理中心，使用已指派給使用者帳戶管理員或公司系統管理員角色的使用者帳戶登入，並使用群組將適當的使用者帳戶和群組新增至適當的存取群組。

在 PowerShell 中，先 [與 Azure Active Directory PowerShell for Graph 模組連線](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。

接下來，使用下列命令區塊將個別的使用者帳戶新增到存取群組：

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

如果您將任何存取群組的使用者帳戶 UPN 儲存在文字檔中，即可使用下列 PowerShell 命令區塊一次新增所有 UPN：

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

在 PowerShell 中，使用下列命令區塊將個別的群組新增至存取群組：

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

結果應該如下所述︰

- 網站管理員 Azure AD 群組包含網站管理員使用者帳戶或群組
- 網站成員 Azure AD 群組包含網站成員使用者帳戶或群組
- 網站檢視者 Azure AD 群組包含只能檢視網站內容的使用者帳戶或群組

使用 Microsoft 365 系統管理中心或下列 PowerShell 命令區塊來驗證每個存取群組的群組成員清單：

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

以下是您的最終設定，其中有三個網站存取群組填入了使用者帳戶或群組。

![三個存取群組填入了使用者帳戶。](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>第 2 階段：建立及設定獨立的小組網站

在這個階段中，您會建立獨立的 SharePoint Online 網站，並設定預設 SharePoint Online 權限等級的權限，以使用新的 Azure AD 型存取群組。 依預設，新的小組網站包含 Microsoft 365 群組和其他相關資源，但在此情況下，我們會建立沒有 Microsoft 365 群組的小組網站。 這可讓您完全透過 SharePoint 維護許可權。

首先，使用下列步驟建立 SharePoint Online 小組網站。

1. 使用也用來管理 SharePoint Online 小組網站 (SharePoint Online 管理員) 的帳戶，登入 Microsoft 365 系統管理中心。 如需說明，請參閱[在何處登入 Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。

2. 在 Microsoft 365 系統管理中心的 [系統 **管理中心**] 下，按一下 [ **SharePoint**]。

3. 在 SharePoint 系統管理中心中，展開 [ **網站** ]，然後按一下 [ **即時網頁**]。

4. 按一下 [ **建立**]，然後選擇 [ **其他選項**]。

5. 在 [ **選擇範本** ] 清單中，選擇 [ **小組網站**]。

6. 在 [網站名稱] 中，鍵入小組網站的名稱。

7. 在 [ **主要管理員**] 中，輸入您用來登入的帳戶。

8. 按一下 **[完成]**。

接下來，從新的 SharePoint Online 小組網站，設定權限。

1. 在工具列中，按一下設定圖示，然後按一下 [網站權限]。

2. 在 [ **網站共用**] 底下，按一下 [ **變更成員可以共用的方式**]。

3. 選擇 [ **唯一的網站擁有者可以共用檔案、資料夾及網站**]。

4. 將 [ **允許存取要求** 關閉] 設定為 [ **關閉**]。

5. 按一下 **[儲存]**。

6. 在 [ **許可權** ] 窗格中，按一下 [ **高級許可權設定**]。

7. 在瀏覽器的 [**許可權**] 索引標籤上，按一下清單中的 [ **\<site name> 成員**]。

8. 在 [人員與群組] 中，按一下 [新增]。

9. 在 [共用] 對話方塊中，鍵入網站成員存取群組的名稱並加以選取，然後按一下 [共用]。

10. 按一下瀏覽器上的 [上一頁] 按鈕。

11. 按一下清單中的 [ **\<site name> 擁有** 者]。

12. 在 [人員與群組] 中，按一下 [新增]。

13. 在 [共用] 對話方塊中，鍵入網站管理員存取群組的名稱並加以選取，然後按一下 [共用]。

14. 按一下瀏覽器上的 [上一頁] 按鈕。

15. 按一下清單中的 [ **\<site name> 訪客**]。

16. 在 [人員與群組] 中，按一下 [新增]。

17. 在 [共用] 對話方塊中，鍵入網站檢視者存取群組的名稱並加以選取，然後按一下 [共用]。

18. 關閉 [權限] 瀏覽器索引標籤。

這些使用權限設定的結果是：

- [ **\<site name> 擁有** 者] SharePoint 群組包含網站管理員存取群組，其中的所有成員都具有「**完全控制**」許可權層級。
- **\<site name> Members** SharePoint 群組包含網站成員存取群組，其中的所有成員都具有 [**編輯**] 許可權等級。
- [ **\<site name> 訪客** SharePoint] 群組包含「網站檢視器存取」群組，其中的所有成員都具有「**讀取**」許可權等級。
- 已停用成員邀請其他成員或非成員要求存取權的功能。

以下是您的最終設定，其中網站有三個 SharePoint 群組設定為使用三個存取群組，而這三個存取群組填入了使用者帳戶或 Azure AD 群組。

![具有存取群組與使用者帳戶的獨立 SharePoint Online 網站最終設定。](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

您和網站成員現在可以透過其中一個存取群組的群組成員資格，使用網站的資源來共同作業。

## <a name="next-step"></a>下一步

當您需要變更網站存取群組成員資格或建立具有自訂權限的文件資料夾時，請參閱[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)。

## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)

[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)

[管理獨立的 SharePoint Online 小組網站](manage-an-isolated-sharepoint-online-team-site.md)
