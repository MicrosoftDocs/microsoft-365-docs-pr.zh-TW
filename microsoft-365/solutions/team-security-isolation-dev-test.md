---
title: 在開發/測試環境中為小組設定安全性隔離
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 設定安全性和基礎結構，讓您的員工隨時隨地都能遠端工作。
ms.openlocfilehash: 5c2de3fbb174bdf1dccc8ef8371dca1ae1bfddf0
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159392"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a>在開發/測試環境中為小組設定安全性隔離

本文提供在開發/測試環境中建立[有安全性隔離功能的小組](secure-teams-security-isolation.md)的逐步指示。

![公司策略所隔離小組的設定](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

在生產環境中部署此類型的小組之前，您可以使用此開發/測試環境來試驗和微調設定，以符合您的特定需求。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>階段 1：建置您的 Microsoft 365 企業版測試環境

如果您只想要以最小的需求，透過輕量級方式測試敏感度和高敏感度小組，請依照[輕量型基本組態](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)中的指示進行。

如果您想要在模擬的企業中測試敏感度和高敏感度小組，請依照[密碼雜湊同步處理](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)中的指示進行。

>[!Note]
>測試有安全性隔離的小組不需要模擬的企業測試環境，其中包括模擬的內部網路 (連線到網際網路) 與 Active Directory 網域服務 (AD DS) 樹系中的目錄同步處理。 其在這裡提供作為選項，讓您可以在代表典型組織的環境中測試和試驗有安全性隔離的小組。
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-group-and-users"></a>階段 2：建立和設定 Azure Active Directory (AD) 群組和使用者

在這個階段中，您會為虛構組織建立和設定 Azure AD 群組和使用者。
  
首先，請使用 Azure 入口網站建立安全性群組。
  
1. 在瀏覽器中建立個別索引標籤，然後移至 Azure 入口網站 (網址為 [https://portal.azure.com](https://portal.azure.com))。 如果需要，請使用 Microsoft 365 E5 試用或付費訂閱的全域系統管理員帳戶認證登入。
    
2. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]****。
    
3. 在 [群組 - 所有群組]**** 刀鋒視窗中，按一下 [+ 新增群組]****。
    
4. 在 [群組]**** 刀鋒視窗中：
    
  - 在 [群組類型]**** 中選取 [安全性]****。
    
  - 在 [名稱]**** 中輸入**高階主管**。
    
  - 在 [成員資格類型]**** 中選取 [已指派]****。
      
5. 按一下 [建立]****，然後關閉 [群組]**** 刀鋒視窗。
    
接下來，設定自動授權，讓新 **C-Suite** 群組的成員自動獲派 Microsoft 365 E5 授權。
  
1. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [授權] > [所有產品]****。
    
2. 在清單中，選取 [Microsoft 365 企業版 E5]****，然後按一下 [指派]****。
    
3. 在 [指派授權]**** 刀鋒視窗中，按一下 [使用者和群組]****。
    
4. 在群組清單中，選取 [C-Suite]**** 群組。
    
5. 按一下 [選取]****，然後按一下 [指派]****。
    
6. 關閉瀏覽器的 Azure 入口網站索引標籤。
    
接下來，[與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
填寫組織名稱、位置和一般密碼，然後從 PowerShell 命令提示字元或整合指令碼環境 (ISE) 執行下列命令，以建立新的使用者帳戶，並將這些帳戶新增至 C-Suite 群組：
  
```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> 這裡會使用常見密碼，以便在開發/測試環境中能自動化並輕鬆進行設定。 當然，對於生產訂閱，這是非常不鼓勵的。 
  
使用下列步驟來確認群組授權運作正常。
  
1. 登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
    
2. 從瀏覽器的新 [Microsoft 365 系統管理中心]**** 索引標籤中，按一下 [使用者]****。
    
3. 在使用者清單中，按一下 [CEO]****。
    
4. 在列出 **CEO** 使用者帳戶內容的窗格中，確認已獲指派 [Microsoft 365 企業版 E5]**** 授權 (在 [產品授權]**** 中)。
    
## <a name="phase-3-create-your-team"></a>階段 3：建立小組

在此階段中，您要為資深領導人小組的成員建立並設定有安全性隔離的小組，以便合作處理公司策略。

請先啟用敏感度標籤以保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容，然後再繼續進行[本文](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)中的步驟。

接下來，建立小組：

1. 在 Teams 中，按一下應用程式左側的 [小組]****，然後按一下小組清單底部的 [加入或建立小組]****。
2. 按一下 [建立團隊]**** (左上角的第一張卡片)。
3. 選擇 [從頭建置小組]****。
4. 在 [敏感度]**** 清單中，保留預設值。
5. 在 [隱私權]**** 底下，按一下 [私人]****。
6. 輸入**公司策略**，然後按一下 [建立]**** > [關閉]****。

接下來，您必須使用下列設定來設定敏感度標籤：

- 標籤的名稱是「公司策略」
- 已啟用加密
- 公司策略群組具有共同撰寫權限

請遵循下列步驟：

1. 開啟 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。
2. 在 [解決方案]**** 底下，按一下 [資訊保護]****。
3. 按一下 [建立標籤]****。
4. 輸入**公司策略**作為標籤名稱。
5. 輸入**資深領導人公司策略文件**作為工具提示，然後按 [下一步]****。
6. 在 [加密]**** 頁面上，於 [加密]**** 下拉式清單中選擇 [套用]****。
7. 若要新增小組權限：<br>
  a. 按一下 [指派權限]****。<br>
  b. 按一下 [新增使用者或群組]****、選取 [公司策略]****，然後按一下 [新增]****。<br>
  c. 按一下 [選擇權限]****。<br>
  d. 從下拉式清單中選擇 [共同作者]****，然後按一下 [儲存]****。<br>
8. 按 [下一步]****。
9. 在 [內容標記]**** 頁面上，按 [下一步]****。
10. 在 [網站和群組設定]**** 頁面上，將 [網站和群組設定]**** 設為 [開啟]****。
11. 在 [Office 365 群組連線小組網站的隱私權]**** 下拉式清單中，選擇 [私人 - 只有成員可以存取網站]****。
12. 在 [未受管理的裝置]**** 底下，選擇 [封鎖存取]****。
13. 按 [下一步]****。
14. 在 [Office 應用程式的自動加上標籤]**** 頁面上按 [下一步]****。
15. 按一下 [提交]****，然後按一下 [完成]****。

接下來，使用下列步驟發佈新標籤： 

1. 在 Microsoft 365 合規性中心的 [資訊保護]**** 頁面上，選擇 [標籤原則]**** 索引標籤。
2. 按一下 [發佈標籤]****。
3. 在 [選擇要發佈的敏感度標籤]**** 頁面上，按一下 [選擇要發佈的敏感度標籤]****。
4. 選取 [公司策略]****，然後按一下 [新增]****。
5. 按 [下一步]****。
6. 在 [發佈給使用者與群組]**** 頁面上，按一下 [選擇使用者和群組]****。
7. 按一下 [新增]****，然後選取 [公司策略]****。
8. 按一下 [新增]****，然後按一下 [完成]****。
9. 按 [下一步]****。
10. 在 [原則設定] 頁面上，選取 [使用者必須提供移除標籤或降低分類標籤的理由]**** 核取方塊，然後按 [下一步]****。
11. 輸入**公司策略**作為原則名稱，然後按 [下一步]****。
12. 按一下 [提交]****，然後按一下 [完成]****。

**公司策略**標籤發佈後可能需要一些時間才能使用。

接下來，將新標籤套用至**公司策略**小組，並更新預設的共用連結類型，以降低不小心將檔案和資料夾共用給更多非預期對象的風險。 

1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在 [網站]**** 底下，按一下 [使用中網站]****。
3. 按一下 [公司策略]**** 網站。
4. 在 [原則]**** 索引標籤的 [敏感度]**** 底下，按一下 [編輯]****。
5. 選取 [公司策略]**** 標籤，然後按一下 [儲存]****。
6. 在 [原則]**** 索引標籤的 [外部共用]**** 底下，按一下 [編輯]****。
5. 選擇 [只有貴組織中的人員]****。
6. 在 [預設的共用連結類型]**** 底下，清除 [與組織層級設定相同]**** 核取方塊，然後選取 [擁有現有存取權的人員]****。
7. 按一下 [儲存]****。

接下來，為**公司策略**小組設定僅限擁有者使用的網站共用功能。

1. 在 Teams 中，瀏覽至 [公司策略]**** 小組的 [一般]**** 索引標籤。
2. 在小組的工具列中，按一下 [檔案]****。
3. 按一下省略符號，然後按一下 [在 SharePoint 中開啟]****。
4. 在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]****。
5. 在 [網站權限] 窗格的 [網站共用]**** 底下，按一下 [變更成員可以使用的共用方式]****。
6. 在 [共用權限]**** 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]****，然後按一下 [儲存]****。
7. 關閉 [權限]**** 和 [設定]**** 窗格。

如果您以「公司策略」群組的成員身分登入，則會在 Word、Excel 和 PowerPoint 的 [常用] 工具列中看到 [敏感度]**** 選項中的 [公司策略]****。 從 [靈敏性]**** 選項中選取 [公司策略]**** 標籤，將標籤指派給檔案。

以下是公司策略小組產生的設定。

![公司策略所隔離小組的設定](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

小組中的檔案可以擁有公司策略群組成員所指派的公司策略敏感度標籤。 範例如下。

![套用了公司策略敏感度標籤的檔案範例](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config-example.png)
 
## <a name="next-step"></a>後續步驟

當您準備好進行生產部署時，請參閱[為小組設定安全性隔離](secure-teams-security-isolation.md)以了解詳細的設定資訊。
