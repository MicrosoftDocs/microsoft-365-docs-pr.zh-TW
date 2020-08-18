---
title: 在開發/測試環境中為小組設定安全性隔離
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: 設定安全性和基礎結構，讓您的員工隨時隨地都能遠端工作。
ms.openlocfilehash: 62361126ad0b843fd909b98807eeb186f13e75bb
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778333"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="1bfc2-103">在開發/測試環境中為小組設定安全性隔離</span><span class="sxs-lookup"><span data-stu-id="1bfc2-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="1bfc2-104">本文提供在開發/測試環境中建立[有安全性隔離功能的小組](secure-teams-security-isolation.md)的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![公司策略所隔離小組的設定](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="1bfc2-106">在生產環境中部署此類型的小組之前，您可以使用此開發/測試環境來試驗和微調設定，以符合您的特定需求。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1bfc2-107">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="1bfc2-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1bfc2-108">如果您只想要以最小的需求，透過輕量級方式測試敏感度和高敏感度小組，請依照[輕量型基本組態](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="1bfc2-109">如果您想要在模擬的企業中測試敏感度和高敏感度小組，請依照[密碼雜湊同步處理](../enterprise/password-hash-sync-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

>[!Note]
><span data-ttu-id="1bfc2-110">測試有安全性隔離的小組不需要模擬的企業測試環境，其中包括模擬的內部網路 (連線到網際網路) 與 Active Directory 網域服務 (AD DS) 樹系中的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-110">Testing a team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1bfc2-111">其在這裡提供作為選項，讓您可以在代表典型組織的環境中測試和試驗有安全性隔離的小組。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a><span data-ttu-id="1bfc2-112">階段 2：建立和設定 Azure Active Directory ( Azure AD) 群組和使用者</span><span class="sxs-lookup"><span data-stu-id="1bfc2-112">Phase 2: Create and configure your Azure Active Directory (Azure AD) group and users</span></span>

<span data-ttu-id="1bfc2-113">在這個階段中，您會為虛構組織建立和設定 Azure AD 群組和使用者。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>
  
<span data-ttu-id="1bfc2-114">首先，請使用 Azure 入口網站建立安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-114">First, create a security group with the Azure portal.</span></span>
  
1. <span data-ttu-id="1bfc2-115">在瀏覽器中建立個別索引標籤，然後移至 Azure 入口網站 (網址為 [https://portal.azure.com](https://portal.azure.com))。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="1bfc2-116">如果需要，請使用 Microsoft 365 E5 試用或付費訂閱的全域系統管理員帳戶認證登入。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="1bfc2-117">在 Azure 入口網站中，按一下 [Azure Active Directory] > [群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="1bfc2-118">在 [群組 - 所有群組]\*\*\*\* 刀鋒視窗中，按一下 [+ 新增群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="1bfc2-119">在 [群組]\*\*\*\* 刀鋒視窗中：</span><span class="sxs-lookup"><span data-stu-id="1bfc2-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="1bfc2-120">在 [群組類型]\*\*\*\* 中選取 [安全性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="1bfc2-121">在 [名稱]\*\*\*\* 中輸入**高階主管**。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="1bfc2-122">在 [成員資格類型]\*\*\*\* 中選取 [已指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="1bfc2-123">按一下 [建立]\*\*\*\*，然後關閉 [群組]\*\*\*\* 刀鋒視窗。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-123">Click **Create**, and then close the **Group** blade.</span></span>
    
<span data-ttu-id="1bfc2-124">接下來，設定自動授權，讓新 **C-Suite** 群組的成員自動獲派 Microsoft 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-124">Next, configure automatic licensing so that members of the new **C-Suite** group are automatically assigned a Microsoft 365 E5 license.</span></span>
  
1. <span data-ttu-id="1bfc2-125">在 Azure 入口網站中，按一下 [Azure Active Directory] > [授權] > [所有產品]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="1bfc2-126">在清單中，選取 [Microsoft 365 企業版 E5]\*\*\*\*，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="1bfc2-127">在 [指派授權]\*\*\*\* 刀鋒視窗中，按一下 [使用者和群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-127">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="1bfc2-128">在群組清單中，選取 [C-Suite]\*\*\*\* 群組。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-128">In the list of groups, select the **C-Suite** group.</span></span>
    
5. <span data-ttu-id="1bfc2-129">按一下 [選取]\*\*\*\*，然後按一下 [指派]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-129">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="1bfc2-130">關閉瀏覽器的 Azure 入口網站索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-130">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="1bfc2-131">接下來，[與 Azure Active Directory PowerShell for Graph 模組連線](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="1bfc2-132">填寫組織名稱、位置和一般密碼，然後從 PowerShell 命令提示字元或整合指令碼環境 (ISE) 執行下列命令，以建立新的使用者帳戶，並將這些帳戶新增至 C-Suite 群組：</span><span class="sxs-lookup"><span data-stu-id="1bfc2-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>
  
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
> <span data-ttu-id="1bfc2-133">這裡會使用常見密碼，以便在開發/測試環境中能自動化並輕鬆進行設定。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-133">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="1bfc2-134">當然，對於生產訂閱，這是非常不鼓勵的。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-134">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="1bfc2-135">使用下列步驟來確認群組授權運作正常。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-135">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="1bfc2-136">登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="1bfc2-137">從瀏覽器的新 [Microsoft 365 系統管理中心]\*\*\*\* 索引標籤中，按一下 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="1bfc2-138">在使用者清單中，按一下 [CEO]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-138">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="1bfc2-139">在列出 **CEO** 使用者帳戶內容的窗格中，確認已獲指派 [Microsoft 365 企業版 E5]\*\*\*\* 授權 (在 [產品授權]\*\*\*\* 中)。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>
    
## <a name="phase-3-create-your-team"></a><span data-ttu-id="1bfc2-140">階段 3：建立小組</span><span class="sxs-lookup"><span data-stu-id="1bfc2-140">Phase 3: Create your team</span></span>

<span data-ttu-id="1bfc2-141">在此階段中，您要為資深領導人小組的成員建立並設定有安全性隔離的小組，以便合作處理公司策略。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="1bfc2-142">請先啟用敏感度標籤以保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容，然後再繼續進行[本文](../compliance/sensitivity-labels-teams-groups-sites.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="1bfc2-143">接下來，建立小組：</span><span class="sxs-lookup"><span data-stu-id="1bfc2-143">Next, create the team:</span></span>

1. <span data-ttu-id="1bfc2-144">在 Teams 中，按一下應用程式左側的 [小組]\*\*\*\*，然後按一下小組清單底部的 [加入或建立小組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="1bfc2-145">按一下 [建立團隊]\*\*\*\* (左上角的第一張卡片)。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="1bfc2-146">選擇 [從頭建置小組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="1bfc2-147">在 [敏感度]\*\*\*\* 清單中，保留預設值。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="1bfc2-148">在 [隱私權]\*\*\*\* 底下，按一下 [私人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="1bfc2-149">輸入**公司策略**，然後按一下 [建立]\*\*\*\* > [關閉]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="1bfc2-150">接下來，將私人頻道的建立限制為 [公司策略] 群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-150">Next, restrict the creation of private channels to owners of the Company Strategy group.</span></span>

1. <span data-ttu-id="1bfc2-151">在該團隊中，按一下 [更多選項]\*\*\*\*，然後按一下 [管理團隊]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-151">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="1bfc2-152">在 [設定]\*\*\*\* 索引標籤上展開 [成員權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-152">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="1bfc2-153">清除 [允許成員建立私人頻道]\*\*\*\* 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-153">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="1bfc2-154">接下來，您必須使用下列設定來設定敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="1bfc2-154">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="1bfc2-155">該名稱為 [公司策略]</span><span class="sxs-lookup"><span data-stu-id="1bfc2-155">The name is Company Strategy</span></span>
- <span data-ttu-id="1bfc2-156">已啟用加密</span><span class="sxs-lookup"><span data-stu-id="1bfc2-156">Encryption is enabled</span></span>
- <span data-ttu-id="1bfc2-157">公司策略群組具有共同撰寫權限</span><span class="sxs-lookup"><span data-stu-id="1bfc2-157">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="1bfc2-158">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1bfc2-158">Follow these steps:</span></span>

1. <span data-ttu-id="1bfc2-159">開啟 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="1bfc2-160">在 [解決方案]\*\*\*\* 底下，按一下 [資訊保護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="1bfc2-161">按一下 [建立標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="1bfc2-162">輸入**公司策略**作為標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-162">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="1bfc2-163">輸入**資深領導人公司策略文件**作為工具提示，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-163">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="1bfc2-164">在 [加密]\*\*\*\* 頁面上，於 [加密]\*\*\*\* 下拉式清單中選擇 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="1bfc2-165">若要新增小組權限：</span><span class="sxs-lookup"><span data-stu-id="1bfc2-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="1bfc2-166">a.</span><span class="sxs-lookup"><span data-stu-id="1bfc2-166">a.</span></span> <span data-ttu-id="1bfc2-167">按一下 [指派權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="1bfc2-168">b.</span><span class="sxs-lookup"><span data-stu-id="1bfc2-168">b.</span></span> <span data-ttu-id="1bfc2-169">按一下 [新增使用者或群組]\*\*\*\*、選取 [公司策略]\*\*\*\*，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-169">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="1bfc2-170">c.</span><span class="sxs-lookup"><span data-stu-id="1bfc2-170">c.</span></span> <span data-ttu-id="1bfc2-171">按一下 [選擇權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="1bfc2-172">d.</span><span class="sxs-lookup"><span data-stu-id="1bfc2-172">d.</span></span> <span data-ttu-id="1bfc2-173">從下拉式清單中選擇 [共同作者]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="1bfc2-174">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-174">Click **Next**.</span></span>
9. <span data-ttu-id="1bfc2-175">在 [內容標記]\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-175">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="1bfc2-176">在 [網站和群組設定]\*\*\*\* 頁面上，將 [網站和群組設定]\*\*\*\* 設為 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-176">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="1bfc2-177">在 [Office 365 群組連線小組網站的隱私權]\*\*\*\* 下拉式清單中，選擇 [私人 - 只有成員可以存取網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-177">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="1bfc2-178">在 [未受管理的裝置]\*\*\*\* 底下，選擇 [封鎖存取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-178">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="1bfc2-179">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-179">Click **Next**.</span></span>
14. <span data-ttu-id="1bfc2-180">在 [Office 應用程式的自動加上標籤]\*\*\*\* 頁面上按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-180">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="1bfc2-181">按一下 [提交]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-181">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="1bfc2-182">接下來，使用下列步驟發佈新標籤：</span><span class="sxs-lookup"><span data-stu-id="1bfc2-182">Next, publish the new label with these steps:</span></span> 

1. <span data-ttu-id="1bfc2-183">在 Microsoft 365 合規性中心的 [資訊保護]\*\*\*\* 頁面上，選擇 [標籤原則]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-183">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="1bfc2-184">按一下 [發佈標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-184">Click **Publish labels**.</span></span>
3. <span data-ttu-id="1bfc2-185">在 [選擇要發佈的敏感度標籤]\*\*\*\* 頁面上，按一下 [選擇要發佈的敏感度標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-185">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="1bfc2-186">選取 [公司策略]\*\*\*\*，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-186">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="1bfc2-187">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-187">Click **Next**.</span></span>
6. <span data-ttu-id="1bfc2-188">在 [發佈給使用者與群組]\*\*\*\* 頁面上，按一下 [選擇使用者和群組]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-188">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="1bfc2-189">按一下 [新增]\*\*\*\*，然後選取 [公司策略]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-189">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="1bfc2-190">按一下 [新增]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-190">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="1bfc2-191">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-191">Click **Next**.</span></span>
10. <span data-ttu-id="1bfc2-192">在 [原則設定] 頁面上，選取 [使用者必須提供移除標籤或降低分類標籤的理由]\*\*\*\* 核取方塊，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-192">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="1bfc2-193">輸入**公司策略**作為原則名稱，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-193">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="1bfc2-194">按一下 [提交]\*\*\*\*，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-194">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="1bfc2-195">**公司策略**標籤發佈後可能需要一些時間才能使用。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-195">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="1bfc2-196">接下來，將新標籤套用至**公司策略**小組，並更新預設的共用連結類型，以降低不小心將檔案和資料夾共用給更多非預期對象的風險。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-196">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span> 

1. <span data-ttu-id="1bfc2-197">開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-197">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="1bfc2-198">在 [網站]\*\*\*\* 底下，按一下 [使用中網站]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-198">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="1bfc2-199">按一下 [公司策略]\*\*\*\* 網站。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-199">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="1bfc2-200">在 [原則]\*\*\*\* 索引標籤的 [敏感度]\*\*\*\* 底下，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-200">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="1bfc2-201">選取 [公司策略]\*\*\*\* 標籤，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-201">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="1bfc2-202">在 [原則]\*\*\*\* 索引標籤的 [外部共用]\*\*\*\* 底下，按一下 [編輯]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-202">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="1bfc2-203">選擇 [只有貴組織中的人員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-203">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="1bfc2-204">在 [預設的共用連結類型]\*\*\*\* 底下，清除 [與組織層級設定相同]\*\*\*\* 核取方塊，然後選取 [擁有現有存取權的人員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-204">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="1bfc2-205">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-205">Click **Save**.</span></span>

<span data-ttu-id="1bfc2-206">接下來，為**公司策略**小組設定僅限擁有者使用的網站共用功能。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-206">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="1bfc2-207">在 Teams 中，瀏覽至 [公司策略]\*\*\*\* 小組的 [一般]\*\*\*\* 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-207">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="1bfc2-208">在小組的工具列中，按一下 [檔案]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-208">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="1bfc2-209">按一下省略符號，然後按一下 [在 SharePoint 中開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-209">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="1bfc2-210">在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-210">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="1bfc2-211">在 [網站權限] 窗格的 [網站共用]\*\*\*\* 底下，按一下 [變更成員可以使用的共用方式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-211">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="1bfc2-212">在 [共用權限]\*\*\*\* 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]\*\*\*\*，然後按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-212">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="1bfc2-213">關閉 [權限]\*\*\*\* 和 [設定]\*\*\*\* 窗格。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-213">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="1bfc2-214">如果您以「公司策略」群組的成員身分登入，則會在 Word、Excel 和 PowerPoint 的 [常用] 工具列中看到 [敏感度]\*\*\*\* 選項中的 [公司策略]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-214">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="1bfc2-215">從 [靈敏性]\*\*\*\* 選項中選取 [公司策略]\*\*\*\* 標籤，將標籤指派給檔案。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-215">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="1bfc2-216">以下是公司策略小組產生的設定。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-216">Here is the resulting configuration for the Company Strategy team.</span></span>

![公司策略所隔離小組的設定](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a><span data-ttu-id="1bfc2-218">下一步</span><span class="sxs-lookup"><span data-stu-id="1bfc2-218">Next step</span></span>

<span data-ttu-id="1bfc2-219">當您準備好進行部屬時，請參閱下列 [設定指示](secure-teams-security-isolation.md)。</span><span class="sxs-lookup"><span data-stu-id="1bfc2-219">When you're ready for production deployment, see these [configuration instructions](secure-teams-security-isolation.md).</span></span>
