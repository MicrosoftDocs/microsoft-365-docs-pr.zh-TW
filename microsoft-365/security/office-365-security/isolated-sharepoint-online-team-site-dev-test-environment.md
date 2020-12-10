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
ms.openlocfilehash: 6e056cd1d930d13e1ae20f8f8d0cdc9aa886f17e
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616485"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="afbfa-103">獨立的 SharePoint Online 小組網站開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="afbfa-103">Isolated SharePoint Online team site dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="afbfa-104">**摘要：** 設定與 Microsoft 365 開發/測試環境中組織的其他部分隔離的 SharePoint 線上小組網站。</span><span class="sxs-lookup"><span data-stu-id="afbfa-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Microsoft 365 dev/test environment.</span></span>

<span data-ttu-id="afbfa-105">Microsoft 365 中的 SharePoint 線上小組網站是使用通用文件庫、OneNote 筆記本及其他服務共同作業的位置。</span><span class="sxs-lookup"><span data-stu-id="afbfa-105">SharePoint Online team sites in Microsoft 365 are locations for collaboration using a common document library, a OneNote notebook, and other services.</span></span> <span data-ttu-id="afbfa-106">在許多情況下，您需要跨部門或組織的廣泛存取和協同作業。</span><span class="sxs-lookup"><span data-stu-id="afbfa-106">In many cases, you want wide access and collaboration across departments or organizations.</span></span> <span data-ttu-id="afbfa-107">不過，在某些情況下，您想要嚴格控制一小小組人員之間共同作業的存取權和許可權。</span><span class="sxs-lookup"><span data-stu-id="afbfa-107">However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="afbfa-108">SharePoint 線上小組網站的存取權，以及使用者可以執行的工作是由 SharePoint 群組和許可權層級來控制。</span><span class="sxs-lookup"><span data-stu-id="afbfa-108">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels.</span></span> <span data-ttu-id="afbfa-109">根據預設，SharePoint 線上網站有三種存取層級：</span><span class="sxs-lookup"><span data-stu-id="afbfa-109">By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="afbfa-110">**成員**，誰可以查看、建立及修改網站上的資源。</span><span class="sxs-lookup"><span data-stu-id="afbfa-110">**Members**, who can view, create, and modify resources on the site.</span></span>
- <span data-ttu-id="afbfa-111">**擁有者，其** 具有網站的完整控制權，包括變更許可權的功能。</span><span class="sxs-lookup"><span data-stu-id="afbfa-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>
- <span data-ttu-id="afbfa-112">**訪客**，誰只可以查看網站上的資源。</span><span class="sxs-lookup"><span data-stu-id="afbfa-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="afbfa-113">本文將引導您逐步設定隔離的 SharePoint Online 小組網站，以尋找名為 ProjectX 的機密調研專案。</span><span class="sxs-lookup"><span data-stu-id="afbfa-113">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX.</span></span> <span data-ttu-id="afbfa-114">存取需求如下：</span><span class="sxs-lookup"><span data-stu-id="afbfa-114">The access requirements are:</span></span>

- <span data-ttu-id="afbfa-115">只有專案的成員可以透過群組成員資格來存取網站及其內容 (檔、OneNote 筆記本、頁面) ，以及編輯及查看 SharePoint 許可權層級。</span><span class="sxs-lookup"><span data-stu-id="afbfa-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="afbfa-116">只有網站的建立者和網站管理員群組的成員可以執行網站管理，包含修改網站層級的許可權。</span><span class="sxs-lookup"><span data-stu-id="afbfa-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="afbfa-117">在您的 Microsoft 365 開發/測試環境中設定隔離的 SharePoint Online 小組網站有三個階段：</span><span class="sxs-lookup"><span data-stu-id="afbfa-117">There are three phases to setting up an isolated SharePoint Online team site in your Microsoft 365 dev/test environment:</span></span>

1. <span data-ttu-id="afbfa-118">建立 Microsoft 365 開發/測試環境。</span><span class="sxs-lookup"><span data-stu-id="afbfa-118">Create the Microsoft 365 dev/test environment.</span></span>

2. <span data-ttu-id="afbfa-119">為 ProjectX 建立使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="afbfa-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="afbfa-120">SharePoint Online 小組網站建立新的 ProjectX，並將其隔離。</span><span class="sxs-lookup"><span data-stu-id="afbfa-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="afbfa-121">按一下[這裡](https://aka.ms/catlgstack)，可查看 One Microsoft Cloud 測試實驗室指南堆疊中文件的所有視覺對應。</span><span class="sxs-lookup"><span data-stu-id="afbfa-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-microsoft-365-devtest-environment"></a><span data-ttu-id="afbfa-122">階段1：組建小型或模擬的企業 Microsoft 365 開發/測試環境</span><span class="sxs-lookup"><span data-stu-id="afbfa-122">Phase 1: Build out your lightweight or simulated enterprise Microsoft 365 dev/test environment</span></span>

<span data-ttu-id="afbfa-123">如果您只想以輕量的方式建立隔離的 SharePoint Online 小組網站，請遵循 [輕量基本](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)設定的階段2和3中的指示。</span><span class="sxs-lookup"><span data-stu-id="afbfa-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [The lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="afbfa-124">如果您想要在模擬的企業設定中建立隔離的 SharePoint Online 小組網站，請遵循 [Microsoft 365 測試環境的密碼雜湊同步](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment)處理指示。</span><span class="sxs-lookup"><span data-stu-id="afbfa-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [Password hash synchronization for your Microsoft 365 test environment](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="afbfa-125">建立隔離的 SharePoint 線上網站不需要模擬的企業開發/測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="afbfa-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="afbfa-126">這裡是以選項形式提供，可讓您測試隔離的 SharePoint Online 網站，並在代表一般組織的環境中進行嘗試。</span><span class="sxs-lookup"><span data-stu-id="afbfa-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="afbfa-127">階段2：建立使用者帳戶和存取群組</span><span class="sxs-lookup"><span data-stu-id="afbfa-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="afbfa-128">使用 [[連線至 Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) 中的指示，從您的全域系統管理員帳戶連接到您的試用訂閱：</span><span class="sxs-lookup"><span data-stu-id="afbfa-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell) to connect to your trial subscription with your global administrator account from:</span></span>

- <span data-ttu-id="afbfa-129">您的電腦 (用於羽量級 Microsoft 365 開發/測試環境) 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-129">Your computer (for the lightweight Microsoft 365 dev/test environment).</span></span>

- <span data-ttu-id="afbfa-130">模擬的企業 Microsoft 365 開發/測試環境) 的 CLIENT1 虛擬機器 (。</span><span class="sxs-lookup"><span data-stu-id="afbfa-130">The CLIENT1 virtual machine (for the simulated enterprise Microsoft 365 dev/test environment).</span></span>

<span data-ttu-id="afbfa-131">若要為 ProjectX SharePoint Online 小組網站建立新的訪問群組，請從 Windows 的 Windows Azure Active Directory 模組 PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="afbfa-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="afbfa-132">填入您的組織名稱 (範例︰contosotoycompany)，位置的兩個字元國家/地區代碼，再從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="afbfa-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="afbfa-133">從 [ **New-MsolUser** ] 命令的顯示中，記下為 Lead Designer 帳戶產生的密碼，並將其記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="afbfa-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="afbfa-134">從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="afbfa-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="afbfa-135">從 [ **New-MsolUser** ] 命令的顯示中，記下針對潛在客戶研究員帳戶產生的密碼，並將其記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="afbfa-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="afbfa-136">從適用於 Windows PowerShell 的 Windows Azure Active Directory 模組提示字元中執行下列命令︰</span><span class="sxs-lookup"><span data-stu-id="afbfa-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="afbfa-137">在 [ **New-MsolUser** ] 命令的顯示中，記下針對開發 VP 帳戶產生的密碼，並將其記錄在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="afbfa-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="afbfa-138">接下來，若要將新帳戶新增至新的訪問群組，請從 Windows 的 Windows Azure Active Directory 模組 PowerShell 提示中執行下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="afbfa-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

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

<span data-ttu-id="afbfa-139">結果：</span><span class="sxs-lookup"><span data-stu-id="afbfa-139">Results:</span></span>

- <span data-ttu-id="afbfa-140">ProjectX-Members 存取群組包含潛在客戶設計人員和潛在客戶研究員使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="afbfa-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="afbfa-141">ProjectX-Admins 存取群組包含您試用訂閱的全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="afbfa-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="afbfa-142">ProjectX-Viewers 存取群組包含開發 VP 使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="afbfa-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="afbfa-143">圖1顯示存取群組及其成員資格。</span><span class="sxs-lookup"><span data-stu-id="afbfa-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="afbfa-144">**圖 1**：</span><span class="sxs-lookup"><span data-stu-id="afbfa-144">**Figure 1**:</span></span>

![獨立 SharePoint 線上群組網站的 Microsoft 365 群組及其成員資格](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="afbfa-146">階段3： SharePoint Online 小組網站建立新的 ProjectX，並將其隔離</span><span class="sxs-lookup"><span data-stu-id="afbfa-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="afbfa-147">若要建立 ProjectX 的 SharePoint Online 小組網站，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="afbfa-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="afbfa-148">使用本機電腦上的瀏覽器 (輕量設定) 或 CLIENT1 (模擬企業設定) 上， <https://admin.microsoft.com> 使用您的全域系統管理員帳戶登入 Microsoft 365 系統管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using your global administrator account.</span></span>

2. <span data-ttu-id="afbfa-149">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="afbfa-150">在瀏覽器的 [新增 SharePoint] 索引標籤上，按一下 [ **+ 建立網站**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="afbfa-151">在 [ **小組網站名稱**] 中，輸入 **ProjectX**。</span><span class="sxs-lookup"><span data-stu-id="afbfa-151">In **Team site name**, type **ProjectX**.</span></span> <span data-ttu-id="afbfa-152">在 [ **隱私權設定**] 中，選取 [ **僅私人成員可以存取此網站**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-152">In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="afbfa-153">在 [ **小組網站描述**] 中，輸入 **ProjectX SharePoint 網站**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="afbfa-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="afbfa-154">在 [ **您想要新增誰**？]窗格中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="afbfa-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="afbfa-155">在瀏覽器的 [新增 **ProjectX-Home** ] 索引標籤上，按一下工具列上的 [設定] 圖示，然後按一下 [ **網站許可權**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="afbfa-156">在 [網站權限] 窗格中，按一下 [進階權限設定]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="afbfa-157">在瀏覽器的 [新增 **許可權：專案 X** ] 索引標籤中，按一下 [ **存取要求設定**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="afbfa-158">在 [ **存取要求設定** ] 對話方塊中，清除 [ **允許成員共用網站和個別檔案及資料夾** ]，並 **允許存取要求** (，讓所有三個核取方塊都已清除) ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="afbfa-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="afbfa-159">按一下清單中 **ProjectX 成員** 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="afbfa-160">在 [人員與群組] 頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="afbfa-161">在 [ **共用** ] 對話方塊中，輸入 **ProjectX-Members**，選取它，然後按一下 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="afbfa-162">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="afbfa-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="afbfa-163">按一下清單中的 [ **ProjectX 擁有** 者]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="afbfa-164">在 [人員與群組] 頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="afbfa-165">在 [ **共用** ] 對話方塊中，輸入 **ProjectX-Admins**，選取它，然後按一下 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="afbfa-166">按一下瀏覽器上的 [上一頁] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="afbfa-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="afbfa-167">按一下清單中的 [ **ProjectX 訪客** ]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="afbfa-168">在 [人員與群組] 頁面上，按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="afbfa-169">在 [ **共用** ] 對話方塊中，輸入 **ProjectX-Viewers**，選取它，然後按一下 [ **共用**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="afbfa-170">關閉瀏覽器中的 [ **人員與群組** ] 索引標籤，按一下瀏覽器中的 [ **ProjectX-Home** ] 索引標籤，然後關閉 [ **網站許可權** ] 窗格。</span><span class="sxs-lookup"><span data-stu-id="afbfa-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="afbfa-171">以下是設定權限的結果：</span><span class="sxs-lookup"><span data-stu-id="afbfa-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="afbfa-172">ProjectX Members SharePoint group 只包含 ProjectX-Members 訪問群組， (其中只包含潛在客戶設計工具和組長研究員使用者帳戶) 和 ProjectX 群組 (，只包含全域管理員使用者帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="afbfa-173">ProjectX 擁有人 SharePoint 群組僅包含 ProjectX-Admins 訪問群組， (只包含全域系統管理員使用者帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="afbfa-174">「ProjectX 訪客 SharePoint 群組」只包含 ProjectX-Viewers 訪問群組， (只包含開發 VP 使用者帳戶) 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="afbfa-175">成員無法修改網站層級許可權 (這只能由 ProjectX-Admins group) 的成員來執行。</span><span class="sxs-lookup"><span data-stu-id="afbfa-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="afbfa-176">其他使用者帳戶無法存取網站或其資源，或要求存取網站。</span><span class="sxs-lookup"><span data-stu-id="afbfa-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="afbfa-177">圖2顯示 SharePoint 群組及其成員資格。</span><span class="sxs-lookup"><span data-stu-id="afbfa-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="afbfa-178">**圖2**</span><span class="sxs-lookup"><span data-stu-id="afbfa-178">**Figure 2**</span></span>

![隔離 SharePoint 線上群組網站的 SharePoint 線上群組及其成員資格](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="afbfa-180">現在讓我們示範使用領導設計人員的使用者帳戶進行存取：</span><span class="sxs-lookup"><span data-stu-id="afbfa-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="afbfa-181">關閉瀏覽器中的 [ **ProjectX-Home** ] 索引標籤，然後按一下瀏覽器中的 [ **Microsoft Office 首頁** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="afbfa-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="afbfa-182">按一下您全域系統管理員的名稱，然後按一下 [ **登出**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="afbfa-183"><https://admin.microsoft.com>使用 Lead Designer 帳戶名稱及其密碼登入 Microsoft 365 系統管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-183">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="afbfa-184">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="afbfa-185">在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，于 [搜尋] 方塊中輸入 **ProjectX** ，啟動搜尋，然後按一下 [ **ProjectX** 小組網站]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-185">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="afbfa-186">您應該會在瀏覽器中看到 ProjectX 小組網站的新索引標籤。</span><span class="sxs-lookup"><span data-stu-id="afbfa-186">You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="afbfa-187">按一下 [設定] 圖示。</span><span class="sxs-lookup"><span data-stu-id="afbfa-187">Click the settings icon.</span></span> <span data-ttu-id="afbfa-188">請注意， **網站許可權** 沒有任何選項。</span><span class="sxs-lookup"><span data-stu-id="afbfa-188">Notice that there is no option for **Site Permissions**.</span></span> <span data-ttu-id="afbfa-189">這是正確的，因為只有 ProjectX-Admins 群組的成員可以修改網站的許可權。</span><span class="sxs-lookup"><span data-stu-id="afbfa-189">This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="afbfa-190">開啟 [記事本] 或您選擇的文字編輯器。</span><span class="sxs-lookup"><span data-stu-id="afbfa-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="afbfa-191">複製 ProjectX 小組網站的 URL，並將它貼到 [記事本] 或 [文字編輯器] 中的新行。</span><span class="sxs-lookup"><span data-stu-id="afbfa-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="afbfa-192">在瀏覽器的 [新增 **ProjectX-Home** ] 索引標籤上，按一下 [ **檔**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="afbfa-193">複製 ProjectX documents 資料夾的 URL，並將它貼到 [記事本] 或 [文字編輯器] 中的新行。</span><span class="sxs-lookup"><span data-stu-id="afbfa-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="afbfa-194">在瀏覽器的 [新增 **ProjectX-Documents** ] 索引標籤上，按一下 [ **新增 > Word 檔**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="afbfa-195">在頁面上輸入一些文字，等候狀態為 [ **已儲存**]，然後按一下瀏覽器上的 [上一步] 按鈕，再重新整理頁面。</span><span class="sxs-lookup"><span data-stu-id="afbfa-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="afbfa-196">您應該會在 **Documents** 資料夾中看到新的 **Document.docx** 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="afbfa-197">按一下 **Document.docx** 檔的省略號，然後按一下 [ **取得連結**]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="afbfa-198">在 [ **共用 ' Document.docx** ] 對話方塊中複製 URL，並將它貼到 [記事本] 或 [文字編輯器] 中的新行，然後關閉 [ **共用 "Document.docx** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="afbfa-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="afbfa-199">關閉瀏覽器中的 [ **ProjectX-Documents** ] 和 [ **SharePoint** ] 索引標籤，然後按一下 [ **Microsoft Office 首頁** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="afbfa-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="afbfa-200">按一下 [**潛在客戶設計** 工具名稱]，然後按一下 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="afbfa-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="afbfa-201">現在讓我們示範使用開發 VP 使用者帳戶來存取 access：</span><span class="sxs-lookup"><span data-stu-id="afbfa-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="afbfa-202"><https://admin.microsoft.com>使用開發 VP 帳戶名稱及其密碼登入 Microsoft 365 系統管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-202">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="afbfa-203">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="afbfa-204">在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，于 [搜尋] 方塊中輸入 **ProjectX** ，啟動搜尋，然後按一下 [ **ProjectX** 小組網站]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-204">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site.</span></span> <span data-ttu-id="afbfa-205">您應該會在瀏覽器中看到 ProjectX 小組網站的新索引標籤。</span><span class="sxs-lookup"><span data-stu-id="afbfa-205">You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="afbfa-206">按一下 **[檔]**，然後按一下 [ **Document.docx** 檔。</span><span class="sxs-lookup"><span data-stu-id="afbfa-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="afbfa-207">在瀏覽器的 [ **Document.docx** ] 索引標籤中，嘗試修改文字。</span><span class="sxs-lookup"><span data-stu-id="afbfa-207">In the **Document.docx** tab in your browser, try to modify the text.</span></span> <span data-ttu-id="afbfa-208">您應該會看到一則訊息 **，說明這份檔是唯讀的。**</span><span class="sxs-lookup"><span data-stu-id="afbfa-208">You should see a message stating **This document is read-only.**</span></span> <span data-ttu-id="afbfa-209">這是預期的，因為開發 VP 使用者帳戶只具有網站的「查看」許可權。</span><span class="sxs-lookup"><span data-stu-id="afbfa-209">This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="afbfa-210">關閉瀏覽器中的 [ **Document.docx**]、[ **ProjectX-Documents**] 及 [ **SharePoint** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="afbfa-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="afbfa-211">按一下 [ **Microsoft Office 首頁**] 索引標籤，按一下 [**開發 VP** ] 名稱，然後按一下 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="afbfa-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="afbfa-212">現在讓我們示範沒有許可權的使用者帳戶的 access：</span><span class="sxs-lookup"><span data-stu-id="afbfa-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="afbfa-213"><https://admin.microsoft.com>使用使用者3帳戶名稱及其密碼登入 Microsoft 365 系統管理中心 () 。</span><span class="sxs-lookup"><span data-stu-id="afbfa-213">Sign in to the Microsoft 365 admin center (<https://admin.microsoft.com>) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="afbfa-214">在磚清單中，按一下 [SharePoint]。</span><span class="sxs-lookup"><span data-stu-id="afbfa-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="afbfa-215">在瀏覽器的 [新增 **SharePoint** ] 索引標籤上，于搜尋方塊中輸入 **ProjectX** ，然後啟動搜尋。</span><span class="sxs-lookup"><span data-stu-id="afbfa-215">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search.</span></span> <span data-ttu-id="afbfa-216">您應該會在這裡看到 [郵件] 不 **符合您的搜尋。**</span><span class="sxs-lookup"><span data-stu-id="afbfa-216">You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="afbfa-217">從 [記事本] 的開啟實例或您的文字編輯器，將 ProjectX 網站的 URL 複製到瀏覽器的 [位址] 列中，然後按 **enter**。</span><span class="sxs-lookup"><span data-stu-id="afbfa-217">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="afbfa-218">您應該會看到「 **拒絕存取** 」頁面。</span><span class="sxs-lookup"><span data-stu-id="afbfa-218">You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="afbfa-219">從 [記事本] 或您的文字編輯器，將 ProjectX 檔] 資料夾的 URL 複製到瀏覽器的 [位址] 列中，然後按 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="afbfa-219">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="afbfa-220">您應該會看到「 **拒絕存取** 」頁面。</span><span class="sxs-lookup"><span data-stu-id="afbfa-220">You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="afbfa-221">從 [記事本] 或您的文字編輯器，將 Documents.docx 檔案的 URL 複製到瀏覽器的 [位址] 列中，然後按 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="afbfa-221">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**.</span></span> <span data-ttu-id="afbfa-222">您應該會看到「 **拒絕存取** 」頁面。</span><span class="sxs-lookup"><span data-stu-id="afbfa-222">You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="afbfa-223">關閉瀏覽器中的 [ **SharePoint** ] 索引標籤，按一下 [ **Microsoft Office 首頁**] 索引標籤，按一下 **使用者 3** 名稱，然後按一下 **[登出]。**</span><span class="sxs-lookup"><span data-stu-id="afbfa-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="afbfa-224">您的隔離 SharePoint 線上網站現在已準備好進行其他實驗。</span><span class="sxs-lookup"><span data-stu-id="afbfa-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="afbfa-225">下一步</span><span class="sxs-lookup"><span data-stu-id="afbfa-225">Next Step</span></span>

<span data-ttu-id="afbfa-226">當您準備好要在生產環境中部署獨立的 SharePoint Online 小組網站時，請參閱＜[設計獨立的 SharePoint Online 小組網站](design-an-isolated-sharepoint-online-team-site.md)＞中的逐步設計考量。</span><span class="sxs-lookup"><span data-stu-id="afbfa-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="afbfa-227">另請參閱</span><span class="sxs-lookup"><span data-stu-id="afbfa-227">See Also</span></span>

[<span data-ttu-id="afbfa-228">獨立的 SharePoint Online 小組網站</span><span class="sxs-lookup"><span data-stu-id="afbfa-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="afbfa-229">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="afbfa-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="afbfa-230">模擬企業基本設定</span><span class="sxs-lookup"><span data-stu-id="afbfa-230">The simulated enterprise base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/simulated-ent-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="afbfa-231">輕量型基本組態</span><span class="sxs-lookup"><span data-stu-id="afbfa-231">The lightweight base configuration</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise)

[<span data-ttu-id="afbfa-232">雲端採用和混合式解決方案</span><span class="sxs-lookup"><span data-stu-id="afbfa-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
