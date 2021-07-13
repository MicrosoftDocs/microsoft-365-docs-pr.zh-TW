---
title: 判斷集中式部署的增益集是否適用于您的組織
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 判斷您的承租人和使用者是否符合需求，讓您可以使用集中式部署來部署 Office 增益集。
ms.openlocfilehash: cb1cc019cfd87ee05112ea0ac1f0f1675316c6d3
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393700"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="c0bb1-103">判斷集中式部署的增益集是否適用于您的組織</span><span class="sxs-lookup"><span data-stu-id="c0bb1-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="c0bb1-104">「集中部署」是大多數客戶將 Office 增益集部署至組織內之使用者和群組的建議和功能最豐富的方法。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="c0bb1-105">如果您是系統管理員，請使用此指導方針判斷您的組織和使用者是否符合需求，以便您可以使用集中式部署。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="c0bb1-106">[集中式部署] 提供下列優點：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-106">Centralized Deployment provides the following benefits:</span></span>

- <span data-ttu-id="c0bb1-107">全域管理員可以將增益集直接指派給使用者、透過群組將增益集指派給多個使用者，或為組織中的每個人指派增益集。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>

- <span data-ttu-id="c0bb1-108">當相關的 Office 應用程式啟動時，增益集就會自動下載。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="c0bb1-109">如果增益集支援增益集命令，增益集會自動出現在 Office 應用程式中的功能區。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>

- <span data-ttu-id="c0bb1-110">如果系統管理員關閉或刪除增益集，或從 Azure Active Directory 或將增益集指派給的群組中移除使用者，則使用者不再出現增益集。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="c0bb1-111">集中式部署支援三種桌面平臺 Windows、Mac 和線上 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="c0bb1-112">集中式部署也會支援 iOS 和 Android (Outlook 僅限行動增益集) 。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="c0bb1-113">增益集最多可能需要24小時才能顯示所有使用者的用戶端。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c0bb1-114">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="c0bb1-114">Before you begin</span></span>

<span data-ttu-id="c0bb1-115">[！注意] 增益集的集中式部署需要使用者使用 Microsoft 365 企業版 SKUs： E3/E5/F3 或商務 SKUs：商務基本、商務標準、商務進階版 (並使用組織識別碼 Office 登入) ，並具有 Exchange Online 和使用中 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="c0bb1-116">您的訂閱目錄必須是 in 或同盟 to Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="c0bb1-117">您可以在下列 Office 和 Exchange 中查看特定需求，或使用[集中式部署相容性檢查](#centralized-deployment-compatibility-checker)程式。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="c0bb1-118">[集中式部署] 不支援下列項目：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-118">Centralized Deployment doesn't support the following:</span></span>

- <span data-ttu-id="c0bb1-119">目標鎖定為 Office 2013 中的 Word、Excel 或 PowerPoint 的增益集</span><span class="sxs-lookup"><span data-stu-id="c0bb1-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
- <span data-ttu-id="c0bb1-120">內部部署目錄服務</span><span class="sxs-lookup"><span data-stu-id="c0bb1-120">An on-premises directory service</span></span>
- <span data-ttu-id="c0bb1-121">增益集部署至 Exchange 部署信箱</span><span class="sxs-lookup"><span data-stu-id="c0bb1-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="c0bb1-122">將增益集部署到 SharePoint</span><span class="sxs-lookup"><span data-stu-id="c0bb1-122">Add-in deployment to SharePoint</span></span>
- <span data-ttu-id="c0bb1-123">Teams 應用程式</span><span class="sxs-lookup"><span data-stu-id="c0bb1-123">Teams apps</span></span>
- <span data-ttu-id="c0bb1-124"> (COM) 或 Visual Studio Tools for Office (VSTO) 增益集的元件物件模型部署。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="c0bb1-125">不包含 Exchange Online 的 Microsoft 365 部署，例如 SKUs： Microsoft 365 Apps for Business 及 Microsoft 365 Apps Enterprise。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="c0bb1-126">Office要求</span><span class="sxs-lookup"><span data-stu-id="c0bb1-126">Office Requirements</span></span>

- <span data-ttu-id="c0bb1-127">若為 Word、Excel 及 PowerPoint 增益集，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="c0bb1-128">在 Windows 裝置上，版本1704或更新版本的 Microsoft 365 企業版 SKUs： E3/E5/F3 或商務 SKUs：商務基本、商務標準、商務進階版。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="c0bb1-129">在 Mac 上，版本15.34 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="c0bb1-130">若為 Outlook，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-130">For Outlook, your users must be using one of the following:</span></span>
  - <span data-ttu-id="c0bb1-131">版本1701或更新版本 Microsoft 365 企業版 SKUs： E3/E5/F3 或商務 SKUs：商務基本、商務標準、商務進階版。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="c0bb1-132">版本1808或更新版本 Office 專業增強版2019或 Office 標準版2019。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="c0bb1-133">版本16.0.4494.1000 或更新版本 Office 專業增強版 2016 (msi) 或 Office 標準版 2016 (msi) \*</span><span class="sxs-lookup"><span data-stu-id="c0bb1-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="c0bb1-134">版本15.0.4937.1000 或更新版本 Office 專業增強版 2013 (msi) 或 Office 標準版 2013 (MSI) \*</span><span class="sxs-lookup"><span data-stu-id="c0bb1-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="c0bb1-135">版本16.0.9318.1000 或更新版本 Mac 版 Office 2016</span><span class="sxs-lookup"><span data-stu-id="c0bb1-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span>
- <span data-ttu-id="c0bb1-136">Outlook iOS 的行動的版本2.75.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="c0bb1-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span>
- <span data-ttu-id="c0bb1-137">2.2.145 或更新版本的 Outlook mobile for Android</span><span class="sxs-lookup"><span data-stu-id="c0bb1-137">Version 2.2.145 or later of Outlook mobile for Android</span></span>

    <span data-ttu-id="c0bb1-138">\* MSI 版本的 Outlook 會在適當的 Outlook 功能區中顯示系統管理員安裝的增益集，而不是「我的增益集」一節。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="c0bb1-139">Exchange Online 需求</span><span class="sxs-lookup"><span data-stu-id="c0bb1-139">Exchange Online requirements</span></span>

<span data-ttu-id="c0bb1-140">Microsoft Exchange 會將增益集資訊清單儲存在貴組織的租用戶中。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="c0bb1-141">部署增益集的系統管理員和接收這些增益集的使用者，必須在支援 OAuth 驗證的 Exchange Online 版本上。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>

<span data-ttu-id="c0bb1-p106">請洽詢貴組織的 Exchange 系統管理員，確認現正使用的設定。您可以使用 [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell Cmdlet，驗證每個使用者的 OAuth 連線。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span>


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="c0bb1-144">集中式部署相容性檢查程式</span><span class="sxs-lookup"><span data-stu-id="c0bb1-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="c0bb1-145">您可以使用集中式部署相容性檢查程式，確認您租使用者上的使用者是否已設定為使用 Word 的集中式部署，Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="c0bb1-146">相容性檢查程式不需要 Outlook 支援。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="c0bb1-147">下載 [相容性檢查](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)程式。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-147">Download the [compatibility checker](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>

#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="c0bb1-148">執行相容性檢查程式</span><span class="sxs-lookup"><span data-stu-id="c0bb1-148">Run the compatibility checker</span></span>

1. <span data-ttu-id="c0bb1-149">啟動提升的 PowerShell.exe 視窗。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-149">Start an elevated PowerShell.exe window.</span></span>

2. <span data-ttu-id="c0bb1-150">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. <span data-ttu-id="c0bb1-151">執行 **CompatabilityCheck** 命令：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="c0bb1-152">這個命令會提示您輸入  *_TenantDomain_* (例如， *TailspinToysIncorporated </span> 。com*) 和  *_TenantAdmin_* 認證 (使用您的全域系統管理員認證) ，然後要求同意。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0bb1-153">根據您租用戶中的使用者人數而定，檢查程式可能需要花費幾分鐘至幾小時。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span>

<span data-ttu-id="c0bb1-154">檢查程式執行完畢後，會產生一個逗號分隔 (.csv) 格式的輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="c0bb1-155">預設會將檔案儲存為 **C:\windows\system32** 。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="c0bb1-156">輸出檔案中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-156">The output file contains the following information:</span></span>

- <span data-ttu-id="c0bb1-157">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="c0bb1-157">User Name</span></span>

- <span data-ttu-id="c0bb1-158">使用者識別碼 (該使用者的電子郵件地址)</span><span class="sxs-lookup"><span data-stu-id="c0bb1-158">User ID (User's email address)</span></span>

- <span data-ttu-id="c0bb1-159">已準備好使用集中式部署 (如果其餘項目之值皆為 true)</span><span class="sxs-lookup"><span data-stu-id="c0bb1-159">Centralized Deployment ready - If the remaining items are true</span></span>

- <span data-ttu-id="c0bb1-160">Office plan-授權的 Office 計畫</span><span class="sxs-lookup"><span data-stu-id="c0bb1-160">Office plan - The plan of Office they are licensed for</span></span>

- <span data-ttu-id="c0bb1-161">Office 已啟用 (如果該使用者已啟用 Office)</span><span class="sxs-lookup"><span data-stu-id="c0bb1-161">Office Activated - If they have activated Office</span></span>

- <span data-ttu-id="c0bb1-162">支援的信箱 (如果該使用者擁有啟用 OAuth 的信箱)</span><span class="sxs-lookup"><span data-stu-id="c0bb1-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="c0bb1-163">使用集中式部署 PowerShell 模組時，不支援多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span> <span data-ttu-id="c0bb1-164">模組只適用于基本驗證。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-164">The module only works with Basic authentication.</span></span>

## <a name="user-and-group-assignments"></a><span data-ttu-id="c0bb1-165">使用者和群組指派</span><span class="sxs-lookup"><span data-stu-id="c0bb1-165">User and group assignments</span></span>

<span data-ttu-id="c0bb1-166">[集中式部署] 功能目前支援 Azure Active Directory 所支援的大部分群組，包括 Microsoft 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-166">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="c0bb1-167">目前不支援未啟用郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-167">Non-mail enabled security groups are not currently supported.</span></span>

<span data-ttu-id="c0bb1-168">集中式部署支援對承租人中個別使用者、群組和所有人的工作分派。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-168">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="c0bb1-169">[集中式部署] 支援頂層群組或無父項群組之群組中的使用者，但不支援巢狀群組或有父項群組之群組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-169">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>

<span data-ttu-id="c0bb1-p111">看看下列範例，其中晨怡、欣雯和銷售部門群組已被指派增益集。由於西岸銷售部門是巢狀群組，誠雄和又倫未被指派增益集。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>

![銷售部門圖表](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="c0bb1-173">確認群組是否包含巢狀群組</span><span class="sxs-lookup"><span data-stu-id="c0bb1-173">Find out if a group contains nested groups</span></span>

<span data-ttu-id="c0bb1-174">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-174">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="c0bb1-175">如果您在電子郵件的 [ **至** ] 欄位中輸入組名，然後在解析時選取組名，它會顯示其是否包含使用者或嵌套的群組。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-175">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="c0bb1-176">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-176">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span>

![Outlook 連絡人卡片的 [成員] 索引標籤](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

<span data-ttu-id="c0bb1-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span><span class="sxs-lookup"><span data-stu-id="c0bb1-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span>

![Outlook 連絡人卡片的 [成員資格] 索引標籤](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

<span data-ttu-id="c0bb1-p114">或者，您也可以使用 Azure Active Directory 圖形 API 來執行查詢，尋找群組中的群組清單。如需詳細資訊，請參閱[群組上的作業 | 圖形 API 參考](/previous-versions/azure/ad/graph/api/groups-operations)。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>

### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="c0bb1-183">連絡 Microsoft 以取得支援</span><span class="sxs-lookup"><span data-stu-id="c0bb1-183">Contacting Microsoft for support</span></span>

<span data-ttu-id="c0bb1-184">如果您或您的使用者在載入增益集時遇到問題，使用 Office 的 web 應用程式 (Word、Excel 等 ) （已集中部署），您可能需要與 Microsoft 支援部門聯繫 (才能[瞭解](../../business-video/get-help-support.md)) 。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-184">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="c0bb1-185">在支援票證中提供下列與 Microsoft 365 環境相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-185">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>

|<span data-ttu-id="c0bb1-186">**平台**</span><span class="sxs-lookup"><span data-stu-id="c0bb1-186">**Platform**</span></span>|<span data-ttu-id="c0bb1-187">**偵錯資訊**</span><span class="sxs-lookup"><span data-stu-id="c0bb1-187">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0bb1-188">辦公室</span><span class="sxs-lookup"><span data-stu-id="c0bb1-188">Office</span></span>  <br/> | <span data-ttu-id="c0bb1-189">Charles/Fiddler 記錄檔</span><span class="sxs-lookup"><span data-stu-id="c0bb1-189">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="c0bb1-190">租使用者識別碼 ([瞭解](/onedrive/find-your-office-365-tenant-id)) </span><span class="sxs-lookup"><span data-stu-id="c0bb1-190">Tenant ID ([learn how](/onedrive/find-your-office-365-tenant-id))</span></span>  <br/>  <span data-ttu-id="c0bb1-191">CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="c0bb1-191">CorrelationID.</span></span> <span data-ttu-id="c0bb1-192">查看其中一個 office 頁面的來源，並尋找 [相關性識別碼] 值並傳送給支援：</span><span class="sxs-lookup"><span data-stu-id="c0bb1-192">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="c0bb1-193">豐富型用戶端 (Windows、Mac)</span><span class="sxs-lookup"><span data-stu-id="c0bb1-193">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="c0bb1-194">Charles/Fiddler 記錄檔</span><span class="sxs-lookup"><span data-stu-id="c0bb1-194">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="c0bb1-195">用戶端應用程式的組建編號 (最好是檔案 **/帳戶** 的螢幕擷取畫面) </span><span class="sxs-lookup"><span data-stu-id="c0bb1-195">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="c0bb1-196">相關內容</span><span class="sxs-lookup"><span data-stu-id="c0bb1-196">Related content</span></span>

<span data-ttu-id="c0bb1-197">[在系統管理中心中部署增益集](../manage/manage-deployment-of-add-ins.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c0bb1-197">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="c0bb1-198">[在系統管理中心管理增益集](manage-addins-in-the-admin-center.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c0bb1-198">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="c0bb1-199">[集中式部署常見問題](../manage/centralized-deployment-faq.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c0bb1-199">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>\
<span data-ttu-id="c0bb1-200">[將您的商務使用者 Microsoft 365 升級至最新的 Office 用戶端](../setup/upgrade-users-to-latest-office-client.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="c0bb1-200">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 