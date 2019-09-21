---
title: 設定政治活動開發/測試環境的群組和使用者
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 摘要：為政治活動開發/測試環境建立具備使用者與群組的 Office 365 和 Enterprise Mobility + Security (EMS) 之試用訂閱。
ms.openlocfilehash: 6cf9fb03c66f1cf4d1f20287f5dc121474898d5b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077601"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="f20be-103">設定政治活動開發/測試環境的群組和使用者</span><span class="sxs-lookup"><span data-stu-id="f20be-103">Configure groups and users for a political campaign dev/test environment</span></span>

 <span data-ttu-id="f20be-104">**摘要：** 為政治活動開發/測試環境建立具備使用者與群組的 Office 365 和 Enterprise Mobility + Security (EMS) 之試用訂閱。</span><span class="sxs-lookup"><span data-stu-id="f20be-104">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>
  
<span data-ttu-id="f20be-105">使用本文中的指示來建立開發/測試環境，其中包括簡化使用者帳戶和群組，其適用於 [ Microsoft 安全性指導方針的政治活動、非營利組織，以及其他靈活組織](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)解決方法。</span><span class="sxs-lookup"><span data-stu-id="f20be-105">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>
  
## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="f20be-106">階段 1：建立 Office 365 開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="f20be-106">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="f20be-107">在這個階段中，您會為代表政治活動的虛構組織取得 Office 365 E5 與 Enterprise Mobility + Security (EMS) E5 試用訂閱。</span><span class="sxs-lookup"><span data-stu-id="f20be-107">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>
  
<span data-ttu-id="f20be-108">首先，請遵循 [Office 365 開發/測試環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)的**階段 2** 中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="f20be-108">First, follow the instructions in **Phase 2** of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="f20be-109">接著，註冊 EMS E5 試用訂閱，並將它新增至與 Office 365 試用訂閱相同的組織。</span><span class="sxs-lookup"><span data-stu-id="f20be-109">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your Office 365 trial subscription.</span></span>
  
1. <span data-ttu-id="f20be-110">如果需要，請使用試用訂閱的全域管理員帳戶認證登入系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="f20be-110">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="f20be-111">如需說明，請參閱[在何處登入 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="f20be-111">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="f20be-112">按一下 [管理]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="f20be-112">Click the **Admin** tile.</span></span>
    
3. <span data-ttu-id="f20be-113">在瀏覽器的 [Microsoft 365 系統管理中心]\*\*\*\* 索引標籤上，按一下左導覽中的 [計費] > [購買服務]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-113">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>
    
4. <span data-ttu-id="f20be-p102">在 [購買服務]\*\*\*\* 頁面上，尋找 **Enterprise Mobility + Security E5** 項目。將滑鼠指標停留在上面，並且按一下 [開始免費試用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
5. <span data-ttu-id="f20be-116">在 [確認訂單]\*\*\*\* 頁面上，按一下 [立即試用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-116">On the **Confirm your order** page, click **Try now**.</span></span>
    
6. <span data-ttu-id="f20be-117">在 [訂單收據]\*\*\*\* 頁面上，按一下 [繼續]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-117">On the **Order receipt** page, click **Continue**.</span></span>
    
<span data-ttu-id="f20be-118">接下來，啟用全域管理員帳戶的 EMS E5 授權。</span><span class="sxs-lookup"><span data-stu-id="f20be-118">Next, enable the EMS E5 license for your global administrator account.</span></span>
  
1. <span data-ttu-id="f20be-119">在瀏覽器的 [Microsoft 365 系統管理中心]\*\*\*\* 索引標籤上，按一下左導覽中的 [使用者] > [作用中使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-119">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
2. <span data-ttu-id="f20be-120">按一下您的全域系統管理員帳戶，然後按一下 [產品授權]\*\*\*\* 的 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
3. <span data-ttu-id="f20be-121">在 [產品授權]\*\*\*\* 窗格中，將 **Enterprise Mobility + Security E5** 的產品授權設為 [開啟]\*\*\*\*\*\*，按一下 [儲存]\*\*\*\*，然後按兩次 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="f20be-122">階段 2：建立和設定 Azure Active Directory (AD) 群組</span><span class="sxs-lookup"><span data-stu-id="f20be-122">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="f20be-123">在這個階段中，您會為活動建立和設定 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="f20be-123">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>
  
<span data-ttu-id="f20be-124">首先，利用 Azure 入口網站建立一組典型政治活動的群組。</span><span class="sxs-lookup"><span data-stu-id="f20be-124">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>
  
1. <span data-ttu-id="f20be-p103">在瀏覽器中建立個別索引標籤，然後移至 Azure 入口網站 (網址為 [https://portal.azure.com](https://portal.azure.com))。若有需要，請使用 Office 365 E5 試用訂閱的全域管理員帳戶認證登入。</span><span class="sxs-lookup"><span data-stu-id="f20be-p103">On a separate tab in your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="f20be-127">在 Azure 入口網站中，按一下 [Azure Active Directory] > [使用者和群組] > [所有群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-127">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
    
3. <span data-ttu-id="f20be-128">針對此清單中的每個群組名稱執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f20be-128">Do the following steps for each group name in this list:</span></span>
    
  - <span data-ttu-id="f20be-129">資深和策略人員</span><span class="sxs-lookup"><span data-stu-id="f20be-129">Senior and strategic staff</span></span>
    
  - <span data-ttu-id="f20be-130">IT 人員</span><span class="sxs-lookup"><span data-stu-id="f20be-130">IT staff</span></span>
    
  - <span data-ttu-id="f20be-131">分析人員</span><span class="sxs-lookup"><span data-stu-id="f20be-131">Analytics staff</span></span>
    
  - <span data-ttu-id="f20be-132">一般的核心人員</span><span class="sxs-lookup"><span data-stu-id="f20be-132">Regular core staff</span></span>
    
  - <span data-ttu-id="f20be-133">作業人員</span><span class="sxs-lookup"><span data-stu-id="f20be-133">Operations staff</span></span>
    
  - <span data-ttu-id="f20be-134">現場人員</span><span class="sxs-lookup"><span data-stu-id="f20be-134">Field staff</span></span>
    
1. <span data-ttu-id="f20be-135">在 [所有群組]\*\*\*\* 刀鋒視窗中，按一下 [+ 新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-135">On the **All groups** blade, click **+ New group**.</span></span>
    
2. <span data-ttu-id="f20be-136">從**名稱**中的清單輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f20be-136">Type the group name from the list in **Name**.</span></span>
    
3. <span data-ttu-id="f20be-137">選取在 [成員資格] \*\*\*\* 中的 [動態使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-137">Select **Dynamic user** in **Membership**.</span></span>
    
4. <span data-ttu-id="f20be-138">對 [啟用 Office 功能]\*\*\*\* 按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-138">Click **Yes** for **Enable Office features**.</span></span>
    
5. <span data-ttu-id="f20be-139">按一下 [新增動態查詢]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-139">Click **Add dynamic query**.</span></span>
    
6. <span data-ttu-id="f20be-140">在 [新增使用者位置]\*\*\*\*，請選取 [部門]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-140">In **Add users where**, select **department**.</span></span>
    
7. <span data-ttu-id="f20be-141">在下一個欄位中，選取 [等於]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-141">In the next field, select **Equals**.</span></span>
    
8. <span data-ttu-id="f20be-142">從下一個欄位中，從該清單中輸入群組名稱。</span><span class="sxs-lookup"><span data-stu-id="f20be-142">In the next field, type the group name from the list.</span></span>
    
9. <span data-ttu-id="f20be-143">按一下 [新增查詢]\*\*\*\*，然後按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-143">Click **Add query**, and then click **Create**.</span></span>
    
10. <span data-ttu-id="f20be-144">按一下 [使用者和群組 - 所有群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-144">Click **Users and groups - All groups**.</span></span>
    
<span data-ttu-id="f20be-145">接下來，設定群組，以讓系統自動為成員指派 Office 365 E5 和 EMS E5 授權。</span><span class="sxs-lookup"><span data-stu-id="f20be-145">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>
  
1. <span data-ttu-id="f20be-146">在 Azure 入口網站中，按一下 [Azure Active Directory] > [授權] > [所有產品]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-146">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="f20be-147">在清單中，選取 [Enterprise Mobility + Security E5]\*\*\*\* 和 [Office 365 企業版 E5]\*\*\*\*，然後按一下 [+ 指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-147">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>
    
3. <span data-ttu-id="f20be-148">在 [指派授權]\*\*\*\* 刀鋒視窗中，按一下 [使用者和群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-148">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="f20be-149">在群組清單中，選取下列項目：</span><span class="sxs-lookup"><span data-stu-id="f20be-149">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="f20be-150">分析人員</span><span class="sxs-lookup"><span data-stu-id="f20be-150">Analytics staff</span></span>
    
  - <span data-ttu-id="f20be-151">現場人員</span><span class="sxs-lookup"><span data-stu-id="f20be-151">Field staff</span></span>
    
  - <span data-ttu-id="f20be-152">IT 人員</span><span class="sxs-lookup"><span data-stu-id="f20be-152">IT staff</span></span>
    
  - <span data-ttu-id="f20be-153">作業人員</span><span class="sxs-lookup"><span data-stu-id="f20be-153">Operations staff</span></span>
    
  - <span data-ttu-id="f20be-154">一般的核心人員</span><span class="sxs-lookup"><span data-stu-id="f20be-154">Regular core staff</span></span>
    
  - <span data-ttu-id="f20be-155">資深和策略人員</span><span class="sxs-lookup"><span data-stu-id="f20be-155">Senior and strategic staff</span></span>
    
5. <span data-ttu-id="f20be-156">按一下 [選取]\*\*\*\*，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-156">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="f20be-157">關閉瀏覽器的 Azure 入口網站索引標籤。</span><span class="sxs-lookup"><span data-stu-id="f20be-157">Close the Azure portal tab in your browser.</span></span>
    
## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="f20be-158">階段 3：新增使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="f20be-158">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="f20be-159">在這個階段，您可以為政治活動新增範例使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f20be-159">In this phase, you add the example user accounts for your political campaign.</span></span>
  
<span data-ttu-id="f20be-160">首先，[與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="f20be-160">First, you [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="f20be-161">接下來，填寫您的組織名稱、位置及常見的密碼，並從 PowerShell 命令提示字元或整合式指令碼環境 (ISE) 執行這些命令：</span><span class="sxs-lookup"><span data-stu-id="f20be-161">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>
  
```
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
> <span data-ttu-id="f20be-p104">此處常見密碼的使用是為自動化開發/測試環境且讓您方便進行設定而提供。建議您不要將此類密碼用於產品訂閱。當您使用這些新使用者帳戶登入時，系統會提示您變更密碼。</span><span class="sxs-lookup"><span data-stu-id="f20be-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span> 
  
<span data-ttu-id="f20be-165">使用這些步驟來確認動態群組成員資格和以群組為基礎之授權是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="f20be-165">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>
  
1. <span data-ttu-id="f20be-166">從瀏覽器的 [Microsoft Office 的首頁]\*\*\*\* 索引標籤中，按一下 [管理]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="f20be-166">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="f20be-167">從瀏覽器的新 [Microsoft 365 系統管理中心]\*\*\*\* 索引標籤中，按一下 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-167">From the new **Office Admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="f20be-168">在使用者清單中，按一下 [應徵者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f20be-168">In the list of users, click **Candidate**.</span></span>
    
4. <span data-ttu-id="f20be-169">在列出 [應徵者]\*\*\*\* 使用者帳戶之內容的窗格中，請確認：</span><span class="sxs-lookup"><span data-stu-id="f20be-169">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>
    
  - <span data-ttu-id="f20be-170">它屬於**資深和策略的人員**群組 (在**群組成員資格**)。</span><span class="sxs-lookup"><span data-stu-id="f20be-170">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>
    
  - <span data-ttu-id="f20be-171">他獲派 **Enterprise Mobility + Security E5** 與 **Office 365 企業版 E5** 授權 (在**產品授權**中)。</span><span class="sxs-lookup"><span data-stu-id="f20be-171">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
5. <span data-ttu-id="f20be-172">關閉 [應徵者]\*\*\*\* 使用者帳戶窗格。</span><span class="sxs-lookup"><span data-stu-id="f20be-172">Close the **Candidate** user account pane.</span></span>
    
## <a name="record-values-for-future-reference"></a><span data-ttu-id="f20be-173">記錄值，以便日後參考</span><span class="sxs-lookup"><span data-stu-id="f20be-173">Record values for future reference</span></span>

<span data-ttu-id="f20be-174">記錄這些值以與 Office 365 和 EMS 試用訂閱在此開發/測試環境中搭配使用：</span><span class="sxs-lookup"><span data-stu-id="f20be-174">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>
  
- <span data-ttu-id="f20be-175">試用訂閱組織名稱：![](../media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="f20be-175">Your trial subscription organization name: ![](../media/Common-Images/TableLine.png)</span></span> 
    
    <span data-ttu-id="f20be-176">例如，針對 contoso.onmicrosoft.com 的試用訂閱網域名稱，組織名稱為「contoso」。</span><span class="sxs-lookup"><span data-stu-id="f20be-176">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>
    
- <span data-ttu-id="f20be-177">Office 365 全域系統管理員名稱：![](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="f20be-177">The Office 365 global administrator name: ![](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="f20be-178">在安全位置記錄此帳戶的密碼以及其他使用者帳戶的常見初始密碼。</span><span class="sxs-lookup"><span data-stu-id="f20be-178">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>
    
## <a name="next-step"></a><span data-ttu-id="f20be-179">下一步</span><span class="sxs-lookup"><span data-stu-id="f20be-179">Next step</span></span>

<span data-ttu-id="f20be-180">透過[在政治活動開發/測試環境中建立小組網站](create-team-sites-in-a-political-campaign-dev-test-environment.md)，在此開發/測試環境中建置四種不同類型的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="f20be-180">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f20be-181">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f20be-181">See also</span></span>

[<span data-ttu-id="f20be-182">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="f20be-182">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="f20be-183">在政治活動開發/測試環境中建立小組網站</span><span class="sxs-lookup"><span data-stu-id="f20be-183">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)
  
[<span data-ttu-id="f20be-184">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="f20be-184">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="f20be-185">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="f20be-185">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




