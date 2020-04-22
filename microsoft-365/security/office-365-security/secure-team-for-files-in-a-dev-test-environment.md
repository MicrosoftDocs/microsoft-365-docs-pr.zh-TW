---
title: 在開發/測試環境中保護 Teams 檔案
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
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
description: 摘要：針對開發/測試環境中的檔案，在 Microsoft Teams 中建立敏感性和高度機密小組。
ms.openlocfilehash: 5b3f5c74ac484eb00852d5756b3269fb7c8c6a5b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637965"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a><span data-ttu-id="2bbfa-103">在開發/測試環境中保護 Teams 檔案</span><span class="sxs-lookup"><span data-stu-id="2bbfa-103">Secure Teams for files in a dev/test environment</span></span>

<span data-ttu-id="2bbfa-104">本文提供建立開發/測試環境的逐步指示，其中包含適用於[保護 Microsoft Teams 中的檔案安全](secure-files-in-teams.md)解決方案的敏感性和高度機密小組。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-104">This article provides step-by-step instructions to create a dev/test environment that includes the sensitive and highly confidential teams for the [Secure files in Microsoft Teams](secure-files-in-teams.md) solution.</span></span>
  
![在 Microsoft Teams 中，為檔案建立敏感性和高度機密小組。](../../media/sensitive-highly-confidential-teams-dev-test.png)
  
<span data-ttu-id="2bbfa-106">在生產環境中部署這些類型的小組之前，您可以使用此開發/測試環境來試驗和微調設定，以符合您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying these types of teams in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2bbfa-107">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="2bbfa-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2bbfa-108">如果您只想要以最小的需求，透過輕量級方式測試敏感性和高度機密小組，請依照[輕量型基本組態](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-108">If you just want to test sensitive and highly confidential teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="2bbfa-109">如果您想要在模擬的企業中測試敏感性和高度機密小組，請依照[密碼雜湊同步處理](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-109">If you want to test sensitive and highly confidential teams in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

>[!Note]
><span data-ttu-id="2bbfa-110">測試敏感性和高度機密小組不需要模擬的企業測試環境，其中包括模擬的內部網路 (連線到網際網路) 與 Active Directory 網域服務 (AD DS) 樹系中的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-110">Testing sensitive and highly confidential teams does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2bbfa-111">它在這裡提供作為選項，讓您可以在代表典型組織的環境中測試敏感性和高度機密小組並且進行試驗。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-111">It is provided here as an option so that you can test sensitive and highly confidential teams and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="2bbfa-112">階段 2：建立和設定 Azure Active Directory (AD) 群組和使用者</span><span class="sxs-lookup"><span data-stu-id="2bbfa-112">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="2bbfa-113">在這個階段中，您會為虛構組織建立和設定 Azure AD 群組和使用者。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-113">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="2bbfa-114">首先，利用 Azure 入口網站建立兩個典型組織的群組。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-114">First, create two groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="2bbfa-115">在瀏覽器中建立個別索引標籤，然後移至 Azure 入口網站 (網址為 [https://portal.azure.com](https://portal.azure.com))。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="2bbfa-116">如果需要，請使用 Microsoft 365 E5 試用或付費訂閱的全域系統管理員帳戶認證登入。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="2bbfa-117">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="2bbfa-118">在 [群組 - 所有群組]\*\*\*\* 刀鋒視窗中，按一下 [+ 新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="2bbfa-119">在 [群組]\*\*\*\* 刀鋒視窗中：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="2bbfa-120">在 [群組類型]\*\*\*\* 中選取 [安全性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="2bbfa-121">在 [名稱]\*\*\*\* 中輸入**高階主管**。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="2bbfa-122">在 [成員資格類型]\*\*\*\* 中選取 [已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="2bbfa-123">按一下 [建立]\*\*\*\*，然後關閉 [群組]\*\*\*\* 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-123">Click **Create**, and then close the **Group** blade.</span></span>
    
6.    <span data-ttu-id="2bbfa-124">針對名為「行銷人員」\*\*\*\* 的新群組，重複步驟 3-5。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-124">Repeat steps 3-5 for a new group named **Marketing staff**.</span></span>
    
<span data-ttu-id="2bbfa-125">接下來，設定自動授權，讓群組成員自動獲指派 Microsoft 365 和 EMS 訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-125">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Microsoft 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="2bbfa-126">在 Azure 入口網站中，按一下 [Azure Active Directory] > [授權] > [所有產品]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-126">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="2bbfa-127">在清單中，選取 [Microsoft 365 企業版 E5]\*\*\*\*，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-127">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="2bbfa-128">在 [指派授權]\*\*\*\* 刀鋒視窗中，按一下 [使用者和群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-128">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="2bbfa-129">在群組清單中，選取下列項目：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-129">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="2bbfa-130">高層主管</span><span class="sxs-lookup"><span data-stu-id="2bbfa-130">C-Suite</span></span>
    
  - <span data-ttu-id="2bbfa-131">行銷人員</span><span class="sxs-lookup"><span data-stu-id="2bbfa-131">Marketing staff</span></span>
    
5. <span data-ttu-id="2bbfa-132">按一下 [選取]\*\*\*\*，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-132">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="2bbfa-133">關閉瀏覽器的 Azure 入口網站索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-133">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="2bbfa-134">接著，[與 Azure Active Directory PowerShell for Graph 模組連線](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-134">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="2bbfa-135">填寫組織名稱、位置和一般密碼，然後從 PowerShell 命令提示字元或整合指令碼環境 (ISE) 執行下列命令，以建立使用者帳戶，並將帳戶新增至其群組：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-135">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```powershell
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
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="2bbfa-136">這裡會使用常見密碼，以便在開發/測試環境中能自動化並輕鬆進行設定。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-136">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="2bbfa-137">當然，對於生產訂閱，這是非常不鼓勵的。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-137">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="2bbfa-138">使用下列步驟來確認群組授權運作正常。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-138">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="2bbfa-139">從瀏覽器的 [Microsoft Office 的首頁]\*\*\*\* 索引標籤中，按一下 [管理]\*\*\*\* 磚。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-139">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="2bbfa-140">從瀏覽器的新 [Microsoft 365 系統管理中心]\*\*\*\* 索引標籤中，按一下 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-140">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="2bbfa-141">在使用者清單中，按一下 [CEO]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-141">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="2bbfa-142">在列出 **CEO** 使用者帳戶內容的窗格中，確認已獲指派 [Microsoft 365 企業版 E5]\*\*\*\* 授權 (在 [產品授權]\*\*\*\* 中)。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-142">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-retention-labels"></a><span data-ttu-id="2bbfa-143">階段 3：建立保留標籤</span><span class="sxs-lookup"><span data-stu-id="2bbfa-143">Phase 3: Create retention labels</span></span>

<span data-ttu-id="2bbfa-144">在這個階段中，您要為基礎 SharePoint 網站文件資料夾，建立不同安全性層級的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-144">In this phase, you create the retention labels for the different levels of security for underlying SharePoint site documents folders.</span></span>

1. <span data-ttu-id="2bbfa-145">請使用您的全域系統管理員帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-145">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="2bbfa-146">從瀏覽器的 [首頁 - Microsoft 365 合規性]\*\*\*\* 索引標籤，按一下 [分類] > [標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-146">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="2bbfa-147">按一下 [保留標籤] > [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-147">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="2bbfa-148">在 [命名您的標籤]\*\*\*\* 窗格的 [命名您的標籤]\*\*\*\* 中輸入**敏感性**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-148">On the **Name your label** pane, type **Sensitive** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="2bbfa-149">在 [檔案計畫描述元]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-149">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="2bbfa-150">在 [標籤設定]\*\*\*\* 窗格中，視需要將 [保留]\*\*\*\* 設定為 [開啟]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-150">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="2bbfa-151">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-151">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="2bbfa-152">重複步驟 3-7，將其他保留標籤命名為**高度機密**。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-152">Repeat steps 3-7 for an additional retention label named **Highly Confidential**.</span></span>
    
9. <span data-ttu-id="2bbfa-153">從 [首頁] > [標籤]\*\*\*\* 窗格中，按一下 [Publish labels]\(發佈標籤)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-153">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="2bbfa-154">在 [選擇要發佈的標籤]\*\*\*\* 窗格中，按一下 [選擇要發佈的標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-154">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="2bbfa-155">在 [Choose labels]\(選擇標籤)\*\*\*\* 窗格中，按一下 [新增]\*\*\*\* 並選取所有四個標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-155">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="2bbfa-156">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-156">Click **Done**.</span></span>
    
13. <span data-ttu-id="2bbfa-157">在 [選擇要發佈的標籤]\*\*\*\* 窗格上，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-157">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="2bbfa-158">在 [選擇位置]\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-158">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="2bbfa-159">在 [命名您的原則]\*\*\*\* 窗格上，於 [名稱]\*\*\*\* 中輸入 **範例組織**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-159">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="2bbfa-160">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [發佈標籤]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-160">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-teams"></a><span data-ttu-id="2bbfa-161">階段 4：建立小組</span><span class="sxs-lookup"><span data-stu-id="2bbfa-161">Phase 4: Create your teams</span></span>

<span data-ttu-id="2bbfa-162">在此階段中，您要為您的範例組織建立並設定敏感性和高度機密小組。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-162">In this phase, you create and configure sensitive and highly confidential teams for your example organization.</span></span>

### <a name="sensitive-team-for-marketing-campaigns"></a><span data-ttu-id="2bbfa-163">行銷活動的機密性小組</span><span class="sxs-lookup"><span data-stu-id="2bbfa-163">Sensitive team for marketing campaigns</span></span>

<span data-ttu-id="2bbfa-164">若要為行銷群組成員建立敏感性層級小組，以便共同處理持續的行銷活動：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-164">To create a sensitive-level team for members of the marketing group to collaborate on ongoing marketing campaigns:</span></span>

1. <span data-ttu-id="2bbfa-165">[建立新的私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)，且名稱為**行銷活動**。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-165">[Create a new private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Marketing Campaigns**.</span></span>
2. <span data-ttu-id="2bbfa-166">開啟 [行銷活動]\*\*\*\* 小組。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-166">Open the **Marketing Campaigns** team.</span></span>
3.    <span data-ttu-id="2bbfa-167">在小組的工具列中，按一下 [檔案]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-167">In the tool bar for the team, click **Files**.</span></span>
4.    <span data-ttu-id="2bbfa-168">按一下省略符號，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-168">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.    <span data-ttu-id="2bbfa-169">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-169">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
6.    <span data-ttu-id="2bbfa-170">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-170">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.    <span data-ttu-id="2bbfa-171">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-171">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="2bbfa-172">接下來，為基礎行銷活動 SharePoint 網站的文件資料夾設定「敏感性」標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-172">Next, configure the documents folder of the underlying Marketing Campaigns SharePoint site for the Sensitive label.</span></span>

1.    <span data-ttu-id="2bbfa-173">在瀏覽器的 [行銷活動 - 首頁]\*\*\*\* 索引標籤中，按一下 [文件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-173">In the **Marketing Campaigns-Home** tab of your browser, click **Documents**.</span></span>
2.    <span data-ttu-id="2bbfa-174">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-174">Click the settings icon, and then click **Library settings**.</span></span>
3.    <span data-ttu-id="2bbfa-175">在 [權限與管理]\*\*\*\* 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-175">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.    <span data-ttu-id="2bbfa-176">在 [設定 - 套用標籤]\*\*\*\* 中，選取 [敏感性]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-176">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span> 

<span data-ttu-id="2bbfa-177">接下來，設定資料外洩防護 (DLP) 原則；當使用者在組織外部共用具「敏感性」標籤之基礎 SharePoint 網站 (包含「行銷活動」網站) 上的文件時，即會通知使用者。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-177">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on the underlying SharePoint site with the Sensitive label, which includes the Marketing Campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="2bbfa-178">請使用您的全域系統管理員帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-178">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="2bbfa-179">在瀏覽器的新 [Microsoft 365 合規性]\*\*\*\* 索引標籤上，按一下 [原則] > [資料外洩防護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-179">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="2bbfa-180">在 [首頁] > [資料外洩防護]\*\*\*\* 窗格中，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-180">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="2bbfa-181">在 [從範本開始或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-181">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="2bbfa-182">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，輸入**敏感性標籤 SharePoint 網站**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-182">In the **Name your policy** pane, type **Sensitive label SharePoint sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2bbfa-183">在 [選擇位置]\*\*\*\* 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-183">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="2bbfa-184">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\*、[OneDrive 帳戶]\*\*\*\* 和 [Teams 聊天與通道訊息]\*\*\*\* 位置，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-184">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="2bbfa-185">在 [自訂您要保護的內容類型]\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-185">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="2bbfa-186">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [保留標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-186">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="2bbfa-187">在 [保留標籤]\*\*\*\* 窗格中，按一下 [新增]\*\*\*\* 並選取 [敏感性]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-187">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="2bbfa-188">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-188">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="2bbfa-189">在 [Customize the type of content you want to protect] (自訂您要保護的內容類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-189">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="2bbfa-190">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-190">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="2bbfa-191">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-191">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="2bbfa-192">在文字方塊中，鍵入或貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-192">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="2bbfa-p104">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="2bbfa-196">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-196">Click **OK**.</span></span>
    
17. <span data-ttu-id="2bbfa-197">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-197">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="2bbfa-198">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-198">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="2bbfa-199">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-199">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="2bbfa-200">以下是行銷活動小組產生的設定。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-200">Here is the resulting configuration for the Marketing Campaigns team.</span></span>

![行銷活動小組的設定。](../../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="2bbfa-202">公司策略小組網站</span><span class="sxs-lookup"><span data-stu-id="2bbfa-202">Company strategy team site</span></span>

<span data-ttu-id="2bbfa-203">若要為資深領導小組成員建立高度機密層級小組，以共同處理公司策略：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-203">To create a highly confidential-level team for members of the senior leadership team to collaborate on company strategy:</span></span>

1. <span data-ttu-id="2bbfa-204">[建立新的私人小組](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)，且名稱為**公司策略**。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-204">[Create a new private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Company Strategy**.</span></span>
2. <span data-ttu-id="2bbfa-205">開啟 [公司策略]\*\*\*\* 小組。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-205">Open the **Company Strategy** team.</span></span>
3.    <span data-ttu-id="2bbfa-206">在小組的工具列中，按一下 [檔案]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-206">In the tool bar for the team, click **Files**.</span></span>
4.    <span data-ttu-id="2bbfa-207">按一下省略符號，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-207">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.    <span data-ttu-id="2bbfa-208">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-208">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
6.    <span data-ttu-id="2bbfa-209">在 [網站權限]\*\*\*\* 窗格的 [共用設定]\*\*\*\* 之下，按一下 [變更共用設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-209">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.    <span data-ttu-id="2bbfa-210">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-210">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
8.    <span data-ttu-id="2bbfa-211">關閉 [允許存取要求]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-211">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="2bbfa-212">接下來，為基礎公司策略 SharePoint 網站的文件資料夾設定「高度機密」標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-212">Next, configure the documents folder of the underlying Company Strategy SharePoint site for the Highly Confidential label.</span></span>

1.    <span data-ttu-id="2bbfa-213">在瀏覽器的 [公司策略 - 首頁]\*\*\*\* 索引標籤中，按一下 [文件]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-213">In the **Company Strategy-Home** tab of your browser, click **Documents**.</span></span>
2.    <span data-ttu-id="2bbfa-214">按一下設定圖示，然後按一下 [文件庫設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-214">Click the settings icon, and then click **Library settings**.</span></span>
3.    <span data-ttu-id="2bbfa-215">在 [權限與管理]\*\*\*\* 下，按一下 [Apply label to items in this library]\(將標籤套用至此文件庫中的項目)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-215">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.    <span data-ttu-id="2bbfa-216">在 [設定 - 套用標籤]\*\*\*\* 中，選取 [高度機密]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-216">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span> 

<span data-ttu-id="2bbfa-217">接下來，設定 DLP 原則；當使用者在組織外部共用具「高度機密」標籤之基礎 SharePoint Online 網站 (包含「公司策略」網站) 上的文件時，即會封鎖使用者。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-217">Next, configure a DLP policy that blocks users when they share a document on an underlying SharePoint site with the Highly Confidential label, which includes the Company Strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="2bbfa-218">請使用您的全域系統管理員帳戶登入 [Microsoft 365 合規性入口網站](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-218">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="2bbfa-219">在瀏覽器的新 [Microsoft 365 合規性]\*\*\*\* 索引標籤上，按一下 [原則] > [資料外洩防護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-219">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="2bbfa-220">在 [首頁] > [資料外洩防護]\*\*\*\* 窗格中，按一下 [建立原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-220">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="2bbfa-221">在 [從範本開始或建立自訂原則]\*\*\*\* 窗格中，按一下 [自訂]\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-221">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="2bbfa-222">在 [命名您的原則]\*\*\*\* 窗格的 [名稱]\*\*\*\* 中，輸入**高度機密標籤 SharePoint 網站**，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-222">In the **Name your policy** pane, type **Highly Confidential label SharePoint sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="2bbfa-223">在 [選擇位置]\*\*\*\* 窗格中，按一下 [Let me choose specific locations]\(讓我選擇特定位置)\*\*\*\*，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-223">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="2bbfa-224">在位置清單中，停用 [Exchange 電子郵件]\*\*\*\*、[OneDrive 帳戶]\*\*\*\* 和 [Teams 聊天與通道訊息]\*\*\*\* 位置，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-224">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="2bbfa-225">在 [自訂您要保護的內容類型]\*\*\*\* 窗格中，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-225">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="2bbfa-226">在 [選擇要保護的內容類型]\*\*\*\* 窗格中，從下拉式方塊按一下 [新增]\*\*\*\*，然後按一下 [保留標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-226">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="2bbfa-227">在 [保留標籤]\*\*\*\* 窗格中，按一下 [新增]\*\*\*\*，並選取 [高度機密性]\*\*\*\* 標籤，然後依序按一下 [新增]\*\*\*\* 和 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-227">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="2bbfa-228">在 [Choose the types of content to protect]\(選擇要保護的內容類型)\*\*\*\* 窗格中，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-228">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="2bbfa-229">在 [Customize the type of content you want to protect] (自訂您要保護的內容類型)\*\*\*\* 窗格中，按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-229">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="2bbfa-230">在 [What do you want to do if we detect sensitive info?]\(如果偵測到機密資訊要如何處理?)\*\*\*\* 窗格中，按一下 [Customize the tip and email]\(自訂提示和電子郵件)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-230">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="2bbfa-231">在 [Customize policy tips and email notifications]\(自訂原則提示和電子郵件通知)\*\*\*\* 窗格中，按一下 [Customize the policy tip text]\(自訂原則提示文字)\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-231">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="2bbfa-232">在文字方塊中，鍵入或貼上下列內容：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-232">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="2bbfa-p105">若要與組織外部的使用者共用，請下載檔案，然後將它開啟。 依序按一下 [檔案]、[保護文件] 和 [以密碼加密]，然後指定強式密碼。 以個別電子郵件或其他通訊方式傳送密碼。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-p105">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="2bbfa-236">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-236">Click **OK**.</span></span>
    
17. <span data-ttu-id="2bbfa-237">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-237">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="2bbfa-238">在 [要先開啟原則或測試內容嗎?]\*\*\*\* 窗格中，按一下 [是]\*\*\*\* 立即將它開啟，然後按一下 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-238">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="2bbfa-239">在 [檢閱您的設定]\*\*\*\* 窗格中，按一下 [建立]\*\*\*\*，然後按一下 [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-239">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="2bbfa-240">使用[下列指示](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)設定包含下列設定的敏感性標籤：</span><span class="sxs-lookup"><span data-stu-id="2bbfa-240">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="2bbfa-241">標籤的名稱是「公司策略」</span><span class="sxs-lookup"><span data-stu-id="2bbfa-241">The name of the label is Company Strategy</span></span>
- <span data-ttu-id="2bbfa-242">已啟用加密</span><span class="sxs-lookup"><span data-stu-id="2bbfa-242">Encryption is enabled</span></span>
- <span data-ttu-id="2bbfa-243">公司策略群組具有共同撰寫權限</span><span class="sxs-lookup"><span data-stu-id="2bbfa-243">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="2bbfa-244">建立之後，發佈新標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-244">After creating, publish the new label.</span></span> <span data-ttu-id="2bbfa-245">如果您以公司策略群組的成員身分登入，您會在 Word、Excel 和 PowerPoint 的 [常用] 工具列中看到 [敏感性] 選項中的新標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-245">If you sign in as a member of the Company Strategy group, you will see the new label in the Sensitivity option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="2bbfa-246">從 [靈敏性] 選項中選取 [公司策略] 標籤，將標籤指派給檔案。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-246">Select the Company Strategy label from the Sensitivity option to assign the label to a file.</span></span>

<span data-ttu-id="2bbfa-247">以下是公司策略小組產生的設定。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-247">Here is the resulting configuration for the Company Strategy team.</span></span>

![公司策略小組的設定。](../../media/highlyconfidential-team-config-dev-test.png) 

<span data-ttu-id="2bbfa-249">在基礎公司策略 SharePoint 網站文件區段中的檔案會獲指派「高度機密」保留標籤，而且受限於設定的 DLP 原則。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-249">Files in the documents section of the underlying Company Strategy SharePoint site are assigned the Highly confidential retention label and are subject to the configured DLP policy.</span></span> <span data-ttu-id="2bbfa-250">檔案也可以獲指派「公司策略敏感性」標籤。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-250">Files can also have the Company Strategy sensitivity label assigned.</span></span>    
  
## <a name="next-step"></a><span data-ttu-id="2bbfa-251">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2bbfa-251">Next step</span></span>

<span data-ttu-id="2bbfa-252">當您準備好進行生產環境部署時，請參閱[保護 Microsoft Teams 中的檔案](secure-files-in-teams.md)，以取得詳細資訊及逐步部署文章的連結。</span><span class="sxs-lookup"><span data-stu-id="2bbfa-252">When you are ready for production deployment, see [Secure files in Microsoft Teams](secure-files-in-teams.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2bbfa-253">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2bbfa-253">See Also</span></span>

[<span data-ttu-id="2bbfa-254">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="2bbfa-254">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
