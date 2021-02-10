---
title: 設定群組和使用者 - 政治活動開發/測試環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 摘要：為政治活動開發/測試環境建立具備使用者與群組的 Office 365 和 Enterprise Mobility + Security (EMS) 之試用訂閱。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d23539951e4d51fcd29417ab71ce599853d7537
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165700"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>設定政治活動開發/測試環境的群組和使用者

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 2](https://go.microsoft.com/fwlink/?linkid=2148715)

 **摘要：** 為政治活動開發/測試環境建立具備使用者與群組的 Office 365 和 Enterprise Mobility + Security (EMS) 之試用訂閱。

使用本文中的指示來建立開發/測試環境，其中包括簡化使用者帳戶和群組，其適用於 [ Microsoft 安全性指導方針的政治活動、非營利組織，以及其他靈活組織](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)解決方法。

## <a name="phase-1-create-your-office-365-devtest-environment"></a>階段 1：建立 Office 365 開發/測試環境

在這個階段中，您會為代表政治活動的虛構組織取得 Office 365 E5 與 Enterprise Mobility + Security (EMS) E5 試用訂閱。

首先，請依照[輕量型基本組態](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)中「第 2 階段」的指示進行。

接著，註冊 EMS E5 試用訂閱，並將它新增至與試用訂閱相同的組織。

1. 如果需要，請使用試用訂閱的全域管理員帳戶認證登入系統管理中心。 如需說明，請參閱[在何處登入](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。

2. 按一下 [管理] 磚。

3. 在瀏覽器的 [Microsoft 365 系統管理中心] 索引標籤上，按一下左導覽中的 [計費] > [購買服務]。

4. 在 [購買服務] 頁面上，尋找 **Enterprise Mobility + Security E5** 項目。將滑鼠指標停留在上面，並且按一下 [開始免費試用]。

5. 在 [確認訂單] 頁面上，按一下 [立即試用]。

6. 在 [訂單收據] 頁面上，按一下 [繼續]。

接下來，啟用全域管理員帳戶的 EMS E5 授權。

1. 在瀏覽器的 [Microsoft 365 系統管理中心] 索引標籤上，按一下左導覽中的 [使用者] > [作用中使用者]。

2. 按一下您的全域系統管理員帳戶，然後按一下 [產品授權] 的 [編輯]。

3. 在 [產品授權] 窗格中，將 Enterprise Mobility + Security E5 的產品授權設為 [開啟]**，按一下 [儲存]，然後按兩次 [關閉]。

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>階段 2：建立和設定 Azure Active Directory (AD) 群組

在這個階段中，您會為活動建立和設定 Azure AD 群組。

首先，利用 Azure 入口網站建立一組典型政治活動的群組。

1. 在瀏覽器的個別索引標籤中，移至 Azure 入口網站 (網址為 <https://portal.azure.com>)。 如果需要，請使用 Office 365 E5 試用訂閱的全域管理員帳戶認證登入。

2. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [使用者和群組] > [所有群組]。

3. 針對此清單中的每個群組名稱執行下列步驟：

   - 資深和策略人員

   - IT 人員

   - 分析人員

   - 一般的核心人員

   - 作業人員

   - 現場人員

1. 在 [所有群組] 刀鋒視窗中，按一下 [+ 新增群組]。

2. 從 **名稱** 中的清單輸入群組名稱。

3. 選取在 [成員資格] 中的 [動態使用者]。

4. 對 [啟用 Office 功能] 按一下 [是]。

5. 按一下 [新增動態查詢]。

6. 在 [新增使用者位置]，請選取 [部門]。

7. 在下一個欄位中，選取 [等於]。

8. 從下一個欄位中，從該清單中輸入群組名稱。

9. 按一下 [新增查詢]，然後按一下 [建立]。

10. 按一下 [使用者和群組 - 所有群組]。

接下來，設定群組，以讓系統自動為成員指派 Office 365 E5 和 EMS E5 授權。

1. 在 Azure 入口網站中，按一下 [Azure Active Directory] > [授權] > [所有產品]。

2. 在清單中，選取 [Enterprise Mobility + Security E5] 和 [Office 365 企業版 E5]，然後按一下 [+ 指派]。

3. 在 [指派授權] 刀鋒視窗中，按一下 [使用者和群組]。

4. 在群組清單中，選取下列項目：

   - 分析人員

   - 現場人員

   - IT 人員

   - 作業人員

   - 一般的核心人員

   - 資深和策略人員

5. 按一下 [選取]，然後按一下 [指派]。

6. 關閉瀏覽器的 Azure 入口網站索引標籤。

## <a name="phase-3-add-your-user-accounts"></a>階段 3：新增使用者帳戶

在這個階段，您可以為政治活動新增範例使用者帳戶。

首先，[與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell)。

接下來，填寫您的組織名稱、位置及常見的密碼，並從 PowerShell 命令提示字元或整合式指令碼環境 (ISE) 執行這些命令：

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> 此處常見密碼的使用是為自動化開發/測試環境且讓您方便進行設定而提供。建議您不要將此類密碼用於產品訂閱。當您使用這些新使用者帳戶登入時，系統會提示您變更密碼。

使用這些步驟來確認動態群組成員資格和以群組為基礎之授權是否運作正常。

1. 從瀏覽器的 [Microsoft Office 的首頁] 索引標籤中，按一下 [管理] 磚。

2. 從瀏覽器的新 [Microsoft 365 系統管理中心] 索引標籤中，按一下 [使用者]。

3. 在使用者清單中，按一下 [應徵者]。

4. 在列出 [應徵者] 使用者帳戶之內容的窗格中，請確認：

   - 它屬於 **資深和策略的人員** 群組 (在 **群組成員資格**)。

   - 他獲派 **Enterprise Mobility + Security E5** 與 **Office 365 企業版 E5** 授權 (在 **產品授權** 中)。

5. 關閉 [應徵者] 使用者帳戶窗格。

## <a name="record-values-for-future-reference"></a>記錄值，以便日後參考

記錄這些值以與 Office 365 和 EMS 試用訂閱在此開發/測試環境中搭配使用：

- 您的試用訂閱組織名稱： ![底線](../../media/Common-Images/TableLine.png)

  例如，針對 contoso.onmicrosoft.com 的試用訂閱網域名稱，組織名稱為「contoso」。

- 全域系統管理員名稱： ![底線](../../media/Common-Images/TableLine.png).onmicrosoft.com

  在安全位置記錄此帳戶的密碼以及其他使用者帳戶的常見初始密碼。

## <a name="next-step"></a>下一步

透過[在政治活動開發/測試環境中建立小組網站](create-team-sites-in-a-political-campaign-dev-test-environment.md)，在此開發/測試環境中建置四種不同類型的 SharePoint Online 小組網站。

## <a name="see-also"></a>另請參閱

[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[在政治活動開發/測試環境中建立小組網站](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[雲端採用測試實驗室指南 (TLG)](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[雲端採用和混合式解決方案](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
