---
title: 獨立的 SharePoint Online 小組網站開發/測試環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 摘要：設定與 Microsoft 365 開發/測試環境中組織的其他部分隔離的 SharePoint 線上小組網站。
ms.openlocfilehash: 095b0e5098d86f69c21576e72439dde48a092db3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308400"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a>獨立的 SharePoint Online 小組網站開發/測試環境

 **摘要：** 設定與 Microsoft 365 開發/測試環境中組織的其他部分隔離的 SharePoint 線上小組網站。

Microsoft 365 中的 SharePoint 線上小組網站是使用通用文件庫、OneNote 筆記本及其他服務共同作業的位置。 在許多情況下，您需要跨部門或組織的廣泛存取和協同作業。 不過，在某些情況下，您想要嚴格控制一小小組人員之間共同作業的存取權和許可權。

SharePoint 線上小組網站的存取權，以及使用者可以執行的工作是由 SharePoint 群組和許可權層級來控制。 根據預設，SharePoint 線上網站有三種存取層級：

- **成員**，誰可以查看、建立及修改網站上的資源。

- **擁有者，其**具有網站的完整控制權，包括變更許可權的功能。

- **訪客**，誰只可以查看網站上的資源。

本文將引導您逐步設定隔離的 SharePoint Online 小組網站，以尋找名為 ProjectX 的機密調研專案。 存取需求如下：

- 只有專案的成員可以透過群組成員資格來存取網站及其內容 (檔、OneNote 筆記本、頁面) ，以及編輯及查看 SharePoint 許可權層級。

- 只有網站的建立者和網站管理員群組的成員可以執行網站管理，包含修改網站層級的許可權。

在您的 Microsoft 365 開發/測試環境中設定隔離的 SharePoint Online 小組網站有三個階段：

1. 建立 Microsoft 365 開發/測試環境。

2. 為 ProjectX 建立使用者和群組。

3. SharePoint Online 小組網站建立新的 ProjectX，並將其隔離。

> [!TIP]
> 按一下[這裡](https://aka.ms/catlgstack)，可查看 One Microsoft Cloud 測試實驗室指南堆疊中文件的所有視覺對應。

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a>階段1：組建小型或模擬的企業 Microsoft 365 開發/測試環境

如果您只想以輕量的方式建立隔離的 SharePoint Online 小組網站，請遵循 [輕量基本](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)設定的階段2和3中的指示。

如果您想要在模擬的企業設定中建立隔離的 SharePoint Online 小組網站，請遵循 [Microsoft 365 測試環境的密碼雜湊同步](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)處理指示。

> [!NOTE]
> 建立隔離的 SharePoint 線上網站不需要模擬的企業開發/測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。 這裡是以選項形式提供，可讓您測試隔離的 SharePoint Online 網站，並在代表一般組織的環境中進行嘗試。

## <a name="phase-2-create-user-accounts-and-access-groups"></a>階段2：建立使用者帳戶和存取群組

使用 [[連線至 Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) 中的指示，從您的全域系統管理員帳戶連接到您的試用訂閱：

- 您的電腦 (用於羽量級 Microsoft 365 開發/測試環境) 。

- 模擬的企業 Microsoft 365 開發/測試環境) 的 CLIENT1 虛擬機器 (。

若要為 ProjectX SharePoint Online 小組網站建立新的訪問群組，請從 Windows 的 Windows Azure Active Directory 模組 PowerShell 提示中執行下列命令：

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

填入您的組織名稱 (範例︰contosotoycompany)，位置的兩個字元國家/地區代碼，再從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

從 [ **New-MsolUser** ] 命令的顯示中，記下為 Lead Designer 帳戶產生的密碼，並將其記錄在安全的位置。

從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

從 [ **New-MsolUser** ] 命令的顯示中，記下針對潛在客戶研究員帳戶產生的密碼，並將其記錄在安全的位置。

從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

在 [ **New-MsolUser** ] 命令的顯示中，記下針對開發 VP 帳戶產生的密碼，並將其記錄在安全的位置。

接下來，若要將新帳戶新增至新的訪問群組，請從 Windows 的 Windows Azure Active Directory 模組 PowerShell 提示中執行下列 PowerShell 命令：

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

結果：

- ProjectX-Members 存取群組包含潛在客戶設計人員和潛在客戶研究員使用者帳戶

- ProjectX-Admins 存取群組包含您試用訂閱的全域系統管理員帳戶

- ProjectX-Viewers 存取群組包含開發 VP 使用者帳戶

圖1顯示存取群組及其成員資格。

**圖1**

![獨立 SharePoint 線上群組網站的 Microsoft 365 群組及其成員資格](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a>階段3： SharePoint Online 小組網站建立新的 ProjectX，並將其隔離

若要建立 ProjectX 的 SharePoint Online 小組網站，請執行下列操作：

1. 使用本機電腦上的瀏覽器 (輕量設定) 或 CLIENT1 (模擬企業設定) 上， [https://admin.microsoft.com](https://admin.microsoft.com) 使用您的全域系統管理員帳戶登入 Microsoft 365 系統管理中心 () 。

2. 在磚清單中，按一下 [SharePoint]****。

3. 在瀏覽器的 [新增 SharePoint] 索引標籤上，按一下 [ **+ 建立網站**]。

4. 在 [ **小組網站名稱**] 中，輸入 **ProjectX**。 在 [ **隱私權設定**] 中，選取 [ **僅私人成員可以存取此網站**]。

5. 在 [ **小組網站描述**] 中，輸入 **ProjectX SharePoint 網站**，然後按 **[下一步]**。

6. 在 [ **您想要新增誰**？]窗格中，按一下 **[完成]**。

7. 在瀏覽器的 [新增 **ProjectX-Home** ] 索引標籤上，按一下工具列上的 [設定] 圖示，然後按一下 [ **網站許可權**]。

8. 在 [網站權限]**** 窗格中，按一下 [進階權限設定]****。

9. 在瀏覽器的 [新增 **許可權：專案 X** ] 索引標籤中，按一下 [ **存取要求設定**]。

10. 在 [ **存取要求設定** ] 對話方塊中，清除 [ **允許成員共用網站和個別檔案及資料夾** ]，並 **允許存取要求** (，讓所有三個核取方塊都已清除) ，然後按一下 **[確定]**。

11. 按一下清單中 **ProjectX 成員** 。

12. 在 [人員與群組]**** 頁面上，按一下 [新增]****。

13. 在 [ **共用** ] 對話方塊中，輸入 **ProjectX-Members**，選取它，然後按一下 [ **共用**]。

14. 按一下瀏覽器上的 [上一頁] 按鈕。

15. 按一下清單中的 [ **ProjectX 擁有** 者]。

16. 在 [人員與群組]**** 頁面上，按一下 [新增]****。

17. 在 [ **共用** ] 對話方塊中，輸入 **ProjectX-Admins**，選取它，然後按一下 [ **共用**]。

18. 按一下瀏覽器上的 [上一頁] 按鈕。

19. 按一下清單中的 [ **ProjectX 訪客** ]。

20. 在 [人員與群組]**** 頁面上，按一下 [新增]****。

21. 在 [ **共用** ] 對話方塊中，輸入 **ProjectX-Viewers**，選取它，然後按一下 [ **共用**]。

22. 關閉瀏覽器中的 [ **人員與群組** ] 索引標籤，按一下瀏覽器中的 [ **ProjectX-Home** ] 索引標籤，然後關閉 [ **網站許可權** ] 窗格。

以下是設定權限的結果：

- ProjectX Members SharePoint group 只包含 ProjectX-Members 訪問群組， (其中只包含潛在客戶設計工具和組長研究員使用者帳戶) 和 ProjectX 群組 (，只包含全域管理員使用者帳戶) 。

- ProjectX 擁有人 SharePoint 群組僅包含 ProjectX-Admins 訪問群組， (只包含全域系統管理員使用者帳戶) 。

- 「ProjectX 訪客 SharePoint 群組」只包含 ProjectX-Viewers 訪問群組， (只包含開發 VP 使用者帳戶) 。

- 成員無法修改網站層級許可權 (這只能由 ProjectX-Admins group) 的成員來執行。

- 其他使用者帳戶無法存取網站或其資源，或要求存取網站。

圖2顯示 SharePoint 群組及其成員資格。

**圖2**

![隔離 SharePoint 線上群組網站的 SharePoint 線上群組及其成員資格](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

現在讓我們示範使用領導設計人員的使用者帳戶進行存取：

1. 關閉瀏覽器中的 [ **ProjectX-Home** ] 索引標籤，然後按一下瀏覽器中的 [ **Microsoft Office 首頁** ] 索引標籤。

2. 按一下您全域系統管理員的名稱，然後按一下 [ **登出**]。

3. [https://admin.microsoft.com](https://admin.microsoft.com)使用 Lead Designer 帳戶名稱及其密碼登入 Microsoft 365 系統管理中心 () 。

4. 在磚清單中，按一下 [SharePoint]****。

5. 在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，于 [搜尋] 方塊中輸入 **ProjectX** ，啟動搜尋，然後按一下 [ **ProjectX** 小組網站]。 您應該會在瀏覽器中看到 ProjectX 小組網站的新索引標籤。

6. 按一下 [設定] 圖示。 請注意， **網站許可權**沒有任何選項。 這是正確的，因為只有 ProjectX-Admins 群組的成員可以修改網站的許可權。

7. 開啟 [記事本] 或您選擇的文字編輯器。

8. 複製 ProjectX 小組網站的 URL，並將它貼到 [記事本] 或 [文字編輯器] 中的新行。

9. 在瀏覽器的 [新增 **ProjectX-Home** ] 索引標籤上，按一下 [ **檔**]。

10. 複製 ProjectX documents 資料夾的 URL，並將它貼到 [記事本] 或 [文字編輯器] 中的新行。

11. 在瀏覽器的 [新增 **ProjectX-Documents** ] 索引標籤上，按一下 [ **新增 > Word 檔**]。

12. 在頁面上輸入一些文字，等候狀態為 [ **已儲存**]，然後按一下瀏覽器上的 [上一步] 按鈕，再重新整理頁面。 您應該會在**Documents**資料夾中看到新的**Document.docx** 。

13. 按一下 **Document.docx** 檔的省略號，然後按一下 [ **取得連結**]。

14. 在 [ **共用 ' Document.docx** ] 對話方塊中複製 URL，並將它貼到 [記事本] 或 [文字編輯器] 中的新行，然後關閉 [ **共用 "Document.docx** ] 對話方塊。

15. 關閉瀏覽器中的 [ **ProjectX-Documents** ] 和 [ **SharePoint** ] 索引標籤，然後按一下 [ **Microsoft Office 首頁** ] 索引標籤。

16. 按一下 [**潛在客戶設計**工具名稱]，然後按一下 **[登出]。**

現在讓我們示範使用開發 VP 使用者帳戶來存取 access：

1. [https://admin.microsoft.com](https://admin.microsoft.com)使用開發 VP 帳戶名稱及其密碼登入 Microsoft 365 系統管理中心 () 。

2. 在磚清單中，按一下 [SharePoint]****。

3. 在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，于 [搜尋] 方塊中輸入 **ProjectX** ，啟動搜尋，然後按一下 [ **ProjectX** 小組網站]。 您應該會在瀏覽器中看到 ProjectX 小組網站的新索引標籤。

4. 按一下 **[檔]**，然後按一下 [ **Document.docx** 檔。

5. 在瀏覽器的 [ **Document.docx** ] 索引標籤中，嘗試修改文字。 您應該會看到一則訊息 **，說明這份檔是唯讀的。** 這是預期的，因為開發 VP 使用者帳戶只具有網站的「查看」許可權。

6. 關閉瀏覽器中的 [ **Document.docx**]、[ **ProjectX-Documents**] 及 [ **SharePoint** ] 索引標籤。

7. 按一下 [ **Microsoft Office 首頁**] 索引標籤，按一下 [**開發 VP** ] 名稱，然後按一下 **[登出]。**

現在讓我們示範沒有許可權的使用者帳戶的 access：

1. [https://admin.microsoft.com](https://admin.microsoft.com)使用使用者3帳戶名稱及其密碼登入 Microsoft 365 系統管理中心 () 。

2. 在磚清單中，按一下 [SharePoint]****。

3. 在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，于搜尋方塊中輸入 **ProjectX** ，然後啟動搜尋。 您應該會在這裡看到 [郵件] 不 **符合您的搜尋。**

4. 從 [記事本] 的開啟實例或您的文字編輯器，將 ProjectX 網站的 URL 複製到瀏覽器的 [位址] 列中，然後按 **enter**。 您應該會看到「 **拒絕存取** 」頁面。

5. 從 [記事本] 或您的文字編輯器，將 ProjectX 檔] 資料夾的 URL 複製到瀏覽器的 [位址] 列中，然後按 **enter**鍵。 您應該會看到「 **拒絕存取** 」頁面。

6. 從 [記事本] 或您的文字編輯器，將 Documents.docx 檔案的 URL 複製到瀏覽器的 [位址] 列中，然後按 **enter**鍵。 您應該會看到「 **拒絕存取** 」頁面。

7. 關閉瀏覽器中的 [ **SharePoint** ] 索引標籤，按一下 [ **Microsoft Office 首頁**] 索引標籤，按一下**使用者 3**名稱，然後按一下 **[登出]。**

您的隔離 SharePoint 線上網站現在已準備好進行其他實驗。

## <a name="next-step"></a>下一步

當您準備好要在生產環境中部署獨立的 SharePoint Online 小組網站時，請參閱＜[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)＞中的逐步設計考量。

## <a name="see-also"></a>另請參閱

[獨立的 SharePoint Online 小組網站](isolated-sharepoint-online-team-sites.md)

[雲端採用測試實驗室指南 (TLG)](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[模擬企業基本設定](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[輕量型基本組態](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
