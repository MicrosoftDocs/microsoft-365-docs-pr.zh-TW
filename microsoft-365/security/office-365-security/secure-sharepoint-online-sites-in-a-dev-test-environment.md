---
title: 在開發/測試環境中保護 SharePoint Online 網站
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 摘要：在開發/測試環境中建立公用、私用、敏感性及高度機密的 SharePoint Online 小組網站。
ms.openlocfilehash: d60d113f9b8eac453e8a516b4d5e373896ace0ec
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37078306"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a>在開發/測試環境中保護 SharePoint Online 網站

 **摘要：** 在開發/測試環境中建立公用、私用、敏感性及高度機密的 SharePoint Online 小組網站。
  
本文提供建立開發/測試環境的逐步指示，以在環境中包含[保護 SharePoint Online 網站與檔案解決方案](secure-sharepoint-online-sites-and-files.md)所提之四種不同類型的 SharePoint Online 小組網站。
  
![安全的 SharePoint Online 開發/測試環境中的所有四個小組網站。](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
您可以先使用此開發/測試環境，來試驗資訊保護行為，並針對特定需求微調設定，然後再將 SharePoint Online 小組網站部署在生產環境中。
  
## <a name="phase-1-create-your-devtest-environment"></a>階段 1：建立開發/測試環境

在這個階段中，您會為虛構組織取得 Office 365 與 Enterprise Mobility + Security (EMS) 試用訂閱。
  
首先，請遵循 [Office 365 開發/測試環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)的**階段 2** 中的指示進行。
  
接著，註冊 EMS 試用訂閱，並將它新增至與 Office 365 試用訂閱相同的組織。
  
1. 如果需要，請使用試用訂閱的全域管理員帳戶認證登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
    
2. 按一下左導覽中的 [計費] > [購買服務]****。
    
3. 在 [購買服務]**** 頁面上，尋找 **Enterprise Mobility + Security E5** 項目。將滑鼠指標停留在上面，並且按一下 [開始免費試用]****。
    
4. 在 [確認訂單]**** 頁面上，按一下 [立即試用]****。
    
5. 在 [訂單收據]**** 頁面上，按一下 [繼續]****。
    
接下來，啟用全域管理員帳戶的 Enterprise Mobility + Security E5 授權。
  
1. 在瀏覽器的 [Microsoft 365 系統管理中心]**** 索引標籤上，按一下左導覽中的 [使用者] > [作用中使用者]****。
    
2. 按一下您的全域系統管理員帳戶，然後按一下 [產品授權]**** 的 [編輯]****。
    
3. 在 [產品授權]**** 窗格中，將 [**Enterprise Mobility + Security E5**] 的產品授權設為 [開啟]****，按一下 [儲存]****，然後按兩次 [關閉]****。
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a>階段 2：建立和設定 Azure Active Directory (AD) 群組和使用者

在這個階段中，您會為虛構組織建立和設定 Azure AD 群組和使用者。
  
首先，利用 Azure 入口網站建立一組典型組織的群組。
  
1. 在瀏覽器中另外建立索引標籤，然後移至 Azure 入口網站 (網址為 [https://portal.azure.com](https://portal.azure.com))。若有需要，請使用 Office 365 E5 試用訂閱的全域管理員帳戶認證登入。
    
2. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]****。
    
3. 在 [群組 - 所有群組]**** 刀鋒視窗中，按一下 [+ 新增群組]****。
    
4. 在 [群組]**** 刀鋒視窗中：
    
  - 選取 [群組類型]**** 中的 [Office 365]****。
    
  - 在 [名稱]**** 中輸入**高階主管**。
    
  - 在 [成員資格類型]**** 中選取 [已指派]****。
      
5. 按一下 [建立]****，然後關閉 [群組]**** 刀鋒視窗。
    
6. 重複步驟 3-5，逐一設定下列群組名稱：
    
  - IT 人員
    
  - 研究人員
    
  - 一般人員
    
  - 行銷人員
    
  - 銷售人員
    
7. 瀏覽器中的 [Azure 入口網站] 索引標籤請保持開啟。
    
接下來，設定自動授權，讓群組成員自動獲指派 Office 365 和 EMS 訂閱的授權。
  
1. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [授權] > [所有產品]****。
    
2. 在清單中，選取 [Enterprise Mobility + Security E5]**** 和 [Office 365 企業版 E5]****，然後按一下 [指派]****。
    
3. 在 [指派授權]**** 刀鋒視窗中，按一下 [使用者和群組]****。
    
4. 在群組清單中，選取下列項目：
    
  - 高層主管
    
  - IT 人員
    
  - 研究人員
    
  - 一般人員
    
  - 行銷人員
    
  - 銷售人員
    
5. 按一下 [選取]****，然後按一下 [指派]****。
    
6. 關閉瀏覽器的 Azure 入口網站索引標籤。
    
接著，[與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。
  
填寫組織名稱、位置和一般密碼，然後從 PowerShell 命令提示字元或整合指令碼環境 (ISE) 執行下列命令，以建立使用者帳戶，並將帳戶新增至其群組：
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
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
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> 這裡會使用常見密碼，以便在開發/測試環境中能自動化並輕鬆進行設定。 當然，對於生產訂閱，這是非常不鼓勵的。 
  
使用下列步驟來確認群組授權運作正常。
  
1. 從瀏覽器的 [Microsoft Office 的首頁]**** 索引標籤中，按一下 [管理]**** 磚。
    
2. 從瀏覽器的新 [Microsoft 365 系統管理中心]**** 索引標籤中，按一下 [使用者]****。
    
3. 在使用者清單中，按一下 [CEO]****。
    
4. 在列出 **CEO** 使用者帳戶內容的窗格中，確認已獲指派 [Enterprise Mobility + Security E5]**** 和 [Office 365 Enterprise E5]**** 授權 (在 [Product licenses]\(產品授權)**** 中)。
    
## <a name="phase-3-create-office-365-retention-labels"></a>階段 3：Office 365 保留標籤

在這個階段中，您會為 SharePoint Online 小組網站的文件資料夾，建立不同安全性層級的保留標籤。


1. 請使用您的全域系統管理員帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com)。
    
2. 從瀏覽器的 [首頁 - Microsoft 365 合規性]**** 索引標籤，按一下 [分類] > [標籤]****。
    
3. 按一下 [保留標籤] > [建立標籤]****。
    
4. 在 [命名您的標籤]**** 窗格中，在 [命名您的標籤]**** 中輸入 **內部公用**，然後按一下 [下一步]****。

5. 在 [檔案計畫描述元]**** 窗格中，按一下 [下一步]****。
    
6. 在 [標籤設定]**** 窗格中，視需要將 [保留]**** 設定為 [開啟]****，然後按一下 [下一步]****。
    
7. 在 [檢閱您的設定]**** 窗格中，按一下 [建立標籤]****。
    
8. 針對以下名稱的標籤，重複步驟 3-7：
    
  - 私人
    
  - 敏感性
    
  - 高度機密
  
9. 從 [首頁] > [標籤]**** 窗格中，按一下 [Publish labels]\(發佈標籤)****。
    
10. 在 [選擇要發佈的標籤]**** 窗格中，按一下 [選擇要發佈的標籤]****。
    
11. 在 [Choose labels]\(選擇標籤)**** 窗格中，按一下 [新增]**** 並選取所有四個標籤。
    
12. 按一下 [完成]****。
    
13. 在 [選擇要發佈的標籤]**** 窗格上，按一下 [下一步]****。
    
14. 在 [選擇位置]**** 窗格中，按一下 [下一步]****。
    
15. 在 [命名您的原則]**** 窗格上，於 [名稱]**** 中輸入 **範例組織**，然後按一下 [下一步]****。
    
16. 在 [檢閱您的設定]**** 窗格中，按一下 [發佈標籤]****，然後按一下 [關閉]****。
    
## <a name="phase-4-create-your-sharepoint-online-team-sites"></a>階段 4：建立 SharePoint Online 小組網站

在這個階段中，您會為範例組織建立和設定四種類型的 SharePoint Online 小組網站。
  
### <a name="organization-wide-team-site"></a>整個組織的小組網站

若要建立公用的基準 SharePoint Online 小組網站，請執行下列作業：
  
1. 如果需要，請使用試用訂閱的全域管理員帳戶認證登入 [Office 365 入口網站](https://portal.office.com)。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在瀏覽器的新 [SharePoint]**** 索引標籤上，按一下 [+ 建立網站]****。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在 [網站名稱]**** 中，鍵入「整個組織」****。 
    
6. 在 [小組網站描述]**** 中輸入**整個組織的 SharePoint 網站**。
    
7. 在 [隱私權設定]**** 中，選取 [公用 - 組織中的任何人都可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [您想要新增誰?]**** 窗格上，按一下 [完成]****。
    
接下來，針對 [內部公用] 標籤設定整個組織的小組網站的文件資料夾。
  
1. 在瀏覽器的 [整個組織 - 首頁]**** 索引標籤中，按一下 [文件]****。
    
2. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
3. 在 [權限與管理]**** 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)****。
    
4. 在 [設定 - 套用標籤]**** 中，選取 [內部公用]****，然後按一下 [儲存]****。
    
### <a name="project-1-team-site"></a>專案 1 小組網站

若要為組織內部的專案建立私用的基準 SharePoint Online 小組網站，請執行下列作業：
  
1. 如果需要，請使用試用訂閱的全域管理員帳戶認證登入 [Office 365 入口網站](https://portal.office.com)。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在瀏覽器的新 [SharePoint]**** 索引標籤上，按一下 [+ 建立網站]****。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在 [網站名稱]**** 中輸入**專案 1**。 
    
6. 在 [小組網站描述]**** 中輸入**專案 1 的 SharePoint 網站**。
    
7. 在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [您想要新增誰?]**** 窗格上，按一下 [完成]****。
    
接下來，為「專案 1」小組網站的文件資料夾設定「私用」標籤。
  
1. 在瀏覽器的 [專案 1 - 首頁]**** 索引標籤中，按一下 [文件]****。
    
2. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
3. 在 [權限與管理]**** 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)****。
    
4. 在 [設定 - 套用標籤]**** 中，選取 [私用]****，然後按一下 [儲存]****。
    
### <a name="marketing-campaigns-team-site"></a>行銷活動小組網站

若要為行銷活動資源建立敏感性層級的隔離 SharePoint Online 小組網站，請執行下列作業：

 
1. 如果需要，請使用試用訂閱的全域管理員帳戶認證登入 [Office 365 入口網站](https://portal.office.com)。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在瀏覽器的新 [SharePoint]**** 索引標籤上，按一下 [+ 建立網站]****。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在 [小組網站名稱]**** 中，鍵入「行銷活動」****。
    
6. 在 [小組網站描述]**** 中，輸入**行銷活動的 SharePoint 網站 (敏感性)**。
    
7.  在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [您想要新增誰?]**** 窗格上，按一下 [完成]****。
    
9. 在瀏覽器中新的 [行銷活動]**** 索引標籤上，在工具列中按一下設定圖示，然後按一下 [網站權限]****。
    
10. 在 [網站權限]**** 窗格中，按一下 [進階權限設定]****。
    
11. 在瀏覽器的新 [權限]**** 索引標籤中，按一下 [存取要求設定]****。
    
12. 在 [存取要求設定]**** 對話方塊中，清除 [允許成員共用網站以及個別檔案和資料夾]**** 和 [允許成員邀請其他人加入網站成員群組]**** 核取方塊，在 [傳送存取的所有要求]**** 中輸入 **ITAdmin1@**\<your organization name>**.onmicrosoft.com**，然後按一下 [確定]****。
    
13. 按一下清單中的 [行銷活動成員]****。
    
14. 在 [人員與群組]**** 頁面上，按一下 [新增]****。
    
15. 在 [共用]**** 對話方塊中，輸入**行銷人員**並加以選取，然後按一下 [共用]****。
    
16. 針對 **Researcher1** 使用者帳戶，重複步驟 14 和 15。
    
17. 按一下瀏覽器上的 [上一頁] 按鈕。
    
18. 按一下清單中的 [行銷活動擁有者]****。
    
19. 在 [人員與群組]**** 頁面上，按一下 [新增]****。
    
20. 在 [共用]**** 對話方塊中，鍵入 **IT 人員**，並加以選取，然後按一下 [共用]****。
    
21. 按一下瀏覽器上的 [上一頁] 按鈕。
    
22. 關閉瀏覽器中的 [人員與群組]**** 索引標籤，按一下瀏覽器中的 [行銷活動 - 首頁]**** 索引標籤，然後關閉 [網站權限]**** 窗格。
    
以下是設定權限的結果：
  
- 「行銷活動 - 成員」**** 的 SharePoint 群組僅包含「行銷活動」**** 群組 (其中包含全域管理員使用者帳戶)、「行銷人員」**** 群組 (其中包含 Marketing1 和 Marketing2 使用者帳戶) 和 **Researcher1** 使用者帳戶。
    
- 「行銷活動 - 擁有者」**** 的 SharePoint 群組僅包含「IT 人員」**** 群組 (其中僅包含 ITAdmin1 和 ITAdmin2 使用者帳戶)。
    
- 「行銷活動 - 訪客」**** 的 SharePoint 群組未包含任何群組或使用者帳戶。
    
- 成員無法修改網站層級的權限 (這只能由**行銷活動 - 擁有者**群組成員來執行)。
    
- 其他使用者帳戶無法存取網站或其資源，但可以將電子郵件傳送至 ITAdmin1 使用者帳戶信箱，以要求存取網站。
    
接下來，為「行銷活動」小組網站的文件資料夾設定「敏感性」標籤。
  
1. 在瀏覽器的 [行銷活動 - 首頁]**** 索引標籤中，按一下 [文件]****。
    
2. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
3. 在 [權限與管理]**** 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)****。
    
4. 在 [設定 - 套用標籤]**** 中，選取 [敏感性]****，然後按一下 [儲存]****。
    
接下來，設定資料外洩防護 (DLP) 原則；當使用者在組織外部共用具「敏感性」標籤之 SharePoint Online 小組網站 (包含「行銷活動」網站) 上的文件時，即會通知使用者。

1. 請使用您的全域系統管理員帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com/)。
    
2. 在瀏覽器的新 [Microsoft 365 合規性]**** 索引標籤上，按一下 [原則] > [資料外洩防護]****。
    
3. 在 [首頁] > [資料外洩防護]**** 窗格中，按一下 [建立原則]****。
    
4. 在 [從範本開始或建立自訂原則]**** 窗格中，按一下 [自訂]****，然後按一下 [下一步]****。
    
5. 在 [命名您的原則]**** 窗格的 [名稱]**** 中，鍵入 **Sensitive label SharePoint Online team sites**，然後按一下 [下一步]****。
    
6. 在 [選擇位置]**** 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)****，然後按一下 [下一步]****。
    
7. 在位置清單中，停用 [Exchange 電子郵件]****、[OneDrive 帳戶]**** 和 [Teams 聊天與通道訊息]**** 位置，然後按 [下一步]****。
    
8. 在 [自訂您要保護的內容類型]**** 窗格中，按一下 [編輯]****。
    
9. 在 [選擇要保護的內容類型]**** 窗格中，從下拉式方塊按一下 [新增]****，然後按一下 [保留標籤]****。
    
10. 在 [保留標籤]**** 窗格中，按一下 [新增]**** 並選取 [敏感性]**** 標籤，然後依序按一下 [新增]**** 和 [完成]****。
    
11. 在 [選擇要保護的內容類型]**** 窗格中，按一下 [儲存]****。
    
12. 在 [Customize the type of content you want to protect] (自訂您要保護的內容類型)**** 窗格中，按一下 [下一步]****。

13. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)**** 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)****。
    
14. 在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)**** 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)****。
    
15. 在文字方塊中，根據您是否實作 Azure 資訊保護來保護高度機密的檔案，以鍵入或貼上下列其中一個提示：
    
  - 若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。
    
16. 按一下 [確定]****。
    
17. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)**** 窗格中，按一下 [下一步]****。
    
18. 在 [要先開啟原則或測試內容嗎?]**** 窗格中，按一下 [是]**** 立即將它開啟，然後按一下 [下一步]****。
    
19. 在 [檢閱您的設定]**** 窗格中，按一下 [建立]****，然後按一下 [關閉]****。
  
### <a name="company-strategy-team-site"></a>公司策略小組網站

若要為組織執行長的公司策略資源，建立高度機密層級的隔離 SharePoint Online 小組網站，請執行下列作業：
  
1. 如果需要，請使用試用訂閱的全域管理員帳戶認證登入 [Office 365 入口網站](https://portal.office.com)。
    
2. 在磚清單中，按一下 [SharePoint]****。
    
3. 在瀏覽器的新 [SharePoint]**** 索引標籤上，按一下 [+ 建立網站]****。
    
4. 在 [建立網站]**** 頁面上，按一下 [小組網站]****。
    
5. 在 [小組網站名稱]**** 中，鍵入「公司策略」****。
    
6. 在 [小組網站描述]**** 中，輸入**公司策略的 SharePoint 網站 (高度機密)**。
    
7.  在 [隱私權設定]**** 中，選取 [私人 - 只有成員可以存取此網站]****，然後按一下 [下一步]****。
    
8. 在 [您想要新增誰?]**** 窗格上，按一下 [完成]****。
    
9. 在瀏覽器中新的 [活動策略]**** 索引標籤上，在工具列中按一下設定圖示，然後按一下 [網站權限]****。
    
10. 在 [網站權限]**** 窗格中，按一下 [進階權限設定]****。
    
11. 在瀏覽器的新 [權限]**** 索引標籤中，按一下 [存取要求設定]****。
    
12. 在 [存取要求設定]**** 對話方塊中，清除 [允許成員共用網站以及個別檔案和資料夾]**** 和 [允許成員邀請其他人加入網站成員群組]**** \(亦即清除所有三個核取方塊)，然後按一下 [確定]****。
    
13. 按一下清單中的 [活動策略成員]****。
    
14. 在 [人員與群組]**** 頁面上，按一下 [新增]****。
    
15. 在 [共用]**** 對話方塊中，輸入**高層主管**並加以選取，然後按一下 [共用]****。
    
16. 按一下清單中的 [活動策略擁有者]****。
    
17. 在 [人員與群組]**** 頁面上，按一下 [新增]****。
    
18. 在 [共用]**** 對話方塊中，鍵入 **IT 人員**，並加以選取，然後按一下 [共用]****。
    
19. 按一下瀏覽器上的 [上一頁] 按鈕。
    
20. 關閉瀏覽器中的 [人員與群組]**** 索引標籤，按一下瀏覽器中的 [活動策略 - 首頁]**** 索引標籤，然後關閉 [網站權限]**** 窗格。
    
以下是設定權限的結果：
  
- 「公司策略 - 成員」的 SharePoint 群組僅包含「高層主管」群組 (其中僅包含 CEO、CFO 和 CIO 使用者帳戶) 和「公司策略」群組 (其中僅包含全域管理員使用者帳戶)。
    
- **公司策略 - 擁有者** SharePoint 群組僅包含 **IT 人員**群組 (其中僅包含 ITAdmin1 和 ITAdmin2 使用者帳戶)。
    
- **公司策略 - 訪客** SharePoint 群組未包含任何群組或使用者帳戶。
    
- 成員無法修改網站層級的權限 (這只能由「公司策略 - 擁有者」群組成員來執行)。
    
- 其他使用者帳戶無法存取網站或其資源，或要求存取網站。 網站的額外權限必須由全域管理員或「公司策略 - 擁有者」群組成員來執行。
    
接下來，為「公司策略」小組網站的文件資料夾設定「高度機密」標籤。
  
1. 在瀏覽器的 [公司策略 - 首頁]**** 索引標籤中，按一下 [文件]****。
    
2. 按一下設定圖示，然後按一下 [文件庫設定]****。
    
3. 在 [權限與管理]**** 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)****。
    
4. 在 [設定 - 套用標籤]**** 中，選取 [高度機密]****，然後按一下 [儲存]****。
    
接下來，設定 DLP 原則；當使用者在組織外部共用具「高度機密」標籤之 SharePoint Online 小組網站 (包含「公司策略」網站) 上的文件時，即會封鎖使用者。
  
1. 請使用您的全域系統管理員帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com/)。
    
2. 在瀏覽器的新 [Microsoft 365 合規性]**** 索引標籤上，按一下 [原則] > [資料外洩防護]****。
    
3. 在 [首頁] > [資料外洩防護]**** 窗格中，按一下 [建立原則]****。
    
4. 在 [從範本開始或建立自訂原則]**** 窗格中，按一下 [自訂]****，然後按一下 [下一步]****。
    
5. 在 [命名您的原則]**** 窗格的 [名稱]**** 中，鍵入 **Highly Confidential label SharePoint Online team sites**，然後按一下 [下一步]****。
    
6. 在 [選擇位置]**** 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)****，然後按一下 [下一步]****。
    
7. 在位置清單中，停用 [Exchange 電子郵件]****、[OneDrive 帳戶]**** 和 [Teams 聊天與通道訊息]**** 位置，然後按 [下一步]****。
    
8. 在 [自訂您要保護的內容類型]**** 窗格中，按一下 [編輯]****。
    
9. 在 [選擇要保護的內容類型]**** 窗格中，從下拉式方塊按一下 [新增]****，然後按一下 [保留標籤]****。
    
10. 在 [保留標籤]**** 窗格中，按一下 [新增]****，並選取 [高度機密性]**** 標籤，然後依序按一下 [新增]**** 和 [完成]****。
    
11. 在 [Choose the types of content to protect]\(選擇要保護的內容類型)**** 窗格中，按一下 [儲存]****。
    
12. 在 [Customize the type of content you want to protect] (自訂您要保護的內容類型)**** 窗格中，按一下 [下一步]****。

13. 在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)**** 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)****。
    
14. 在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)**** 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)****。
    
15. 在文字方塊中，根據您是否實作 Azure 資訊保護來保護高度機密的檔案，以鍵入或貼上下列其中一個提示：
    
  - 若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。
    
16. 按一下 [確定]****。
    
17. 在 [要先開啟原則或測試內容嗎?]**** 窗格中，按一下 [是]**** 立即將它開啟，然後按一下 [下一步]****。

18. 在 [要先開啟原則或測試內容嗎?]**** 窗格中，按一下 [是]**** 立即將它開啟，然後按一下 [下一步]****。
    
19. 在 [檢閱您的設定]**** 窗格中，按一下 [建立]****，然後按一下 [關閉]****。
   
    
接下來，遵循[使用 Office 365 系統管理中心啟用 Azure RMS](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) 中的指示進行。
  
接著，遵循下列步驟，設定新的 Azure 資訊保護原則和子標籤，為高階主管群組提供保護及權限：
  
1. 若需要，使用您的全域系統管理員帳戶登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。
    
2. 在您瀏覽器的個別索引標籤中，移至 Azure 入口網站 ([https://portal.azure.com](https://portal.azure.com))。
    
3. 如果這是您第一次設定 Azure 資訊保護，請參閱這些[指示](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time)。
    
4. 在清單窗格中，按一下 [所有服務]****，輸入**資訊**，然後按一下 [Azure 資訊保護]****。

5. 按一下 [標籤]****。
    
6. 以滑鼠右鍵按一下 [高度機密]**** 標籤，然後再按一下 [新增子標籤]****。
    
7. 在 [名稱]**** 與 [描述]**** 中輸入 **高階主管成員**。
    
8. 在 [為包含此標籤的文件與電子郵件設定權限]**** 中，按一下 [保護]****。
    
9. 在 [保護]**** 區段中，按一下 [Azure (雲端金鑰)]****。
    
10. 在 [保護]**** 刀鋒視窗中，按一下 [保護設定]**** 下的 [+ 新增權限]****。
    
11. 在 [新增權限]**** 刀鋒視窗中，按一下 [指定使用者與群組]**** 下的 [+ 瀏覽目錄]****。
    
12. 在 [AAD 使用者與群組]**** 窗格中，選取 [高階主管]****，然後按一下 [選取]****。
    
13. 在 [選擇預設的權限，或設定自訂]**** 下，按一下 [自訂]****，然後選取 [檢視權限]****、[編輯內容]****、[儲存]****、[回覆]****、[全部回覆]**** 核取方塊。
    
14. 按兩次 [確定]****。
    
15. 在 [子標籤]**** 刀鋒視窗中，按一下 [儲存]****，然後按一下 [確定]****。

16. 在 [Azure 資訊保護]**** 刀鋒視窗中，按一下 [原則] > [+ 新增原則]****。
    
17. 在 [原則名稱]**** 中輸入 **公司策略**，並在 [描述]**** 中輸入**公司策略小組網站中的文件**。
    
18. 按一下 [選取取得此原則的使用者或群組] > [使用者/群組]****，然後選取 [高階主管]****。
    
19. 按一下 [選取] > [確定]****。

20. 按一下 [新增或移除標籤]****。在 [原則: 新增或移除標籤]**** 窗格中，按一下 [高階主管]****，然後按一下 [確定]****。   

21. 按一下 [儲存]****，然後按一下 [確定]****。
    
若要使用 Azure 資訊保護和這個新標籤來保護文件，您必須在測試電腦上[安裝 Azure 資訊保護用戶端](https://docs.microsoft.com/information-protection/rms-client/install-client-app)，並從系統管理中心安裝 Office，然後從 Microsoft Word 使用試用訂閱的**高階主管**群組中的帳戶登入。
  
您現在準備好建立這四個網站中的文件，以及使用您試用訂用帳戶中的不同使用者帳戶來測試與其的存取。
  
以下是所有四種 SharePoint Online 小組網站的整體設定。
  
![安全的 SharePoint Online 開發/測試環境中的所有四個小組網站。](../media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
## <a name="next-step"></a>下一步

當您準備好進行安全的 SharePoint Online 網站的生產環境部署時，請參閱[保護 SharePoint Online 網站與檔案](secure-sharepoint-online-sites-and-files.md)，以取得詳細資訊及逐步部署文章的連結。
  
## <a name="see-also"></a>另請參閱

[保護 SharePoint Online 網站與檔案](secure-sharepoint-online-sites-and-files.md)
  
[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




