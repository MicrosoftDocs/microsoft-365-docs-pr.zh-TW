---
title: 判斷集中式部署的增益集是否適用于您的組織
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 判斷您的承租人和使用者是否符合需求，讓您可以使用集中式部署來部署 Office 增益集。
ms.openlocfilehash: fbf6ce702cfe0fa3c85b634996a38cc4857190b6
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102869"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="9ae23-103">判斷集中式部署的增益集是否適用于您的組織</span><span class="sxs-lookup"><span data-stu-id="9ae23-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="9ae23-104">若要將 Office 增益集部署至組織內的使用者和群組，集中式部署對於大多數客戶而言是建議和功能最豐富的方法。</span><span class="sxs-lookup"><span data-stu-id="9ae23-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="9ae23-105">如果您是系統管理員，請使用此指導方針判斷您的組織和使用者是否符合需求，以便您可以使用集中式部署。</span><span class="sxs-lookup"><span data-stu-id="9ae23-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="9ae23-106">[集中式部署] 提供下列優點：</span><span class="sxs-lookup"><span data-stu-id="9ae23-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="9ae23-107">全域管理員可以將增益集直接指派給使用者、透過群組將增益集指派給多個使用者，或為組織中的每個人指派增益集。</span><span class="sxs-lookup"><span data-stu-id="9ae23-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="9ae23-108">當相關的 Office 應用程式啟動時，增益集就會自動下載。</span><span class="sxs-lookup"><span data-stu-id="9ae23-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="9ae23-109">如果增益集支援增益集命令，增益集會自動出現在 Office 應用程式中的功能區。</span><span class="sxs-lookup"><span data-stu-id="9ae23-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="9ae23-110">如果系統管理員關閉或刪除增益集，或使用者已從 Azure Active Directory 或指派的群組中移除，使用者就不會再出現增益集。</span><span class="sxs-lookup"><span data-stu-id="9ae23-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="9ae23-111">集中式部署支援三種桌面平臺 Windows、Mac 和線上 Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9ae23-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="9ae23-112">集中式部署也只會支援 iOS 和 Android (Outlook Mobile 增益集) 。</span><span class="sxs-lookup"><span data-stu-id="9ae23-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="9ae23-113">增益集最多可能需要24小時才能顯示所有使用者的用戶端。</span><span class="sxs-lookup"><span data-stu-id="9ae23-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="9ae23-114">需求</span><span class="sxs-lookup"><span data-stu-id="9ae23-114">Requirements</span></span>

<span data-ttu-id="9ae23-115">[！注意] 增益集的集中式部署需要使用者使用 Microsoft 365 應用程式的 enterprise (，並使用其組織識別碼) 登入 Office，並擁有 Exchange Online 和 active Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="9ae23-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="9ae23-116">您的訂閱目錄必須是 in 或同盟至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="9ae23-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="9ae23-117">您可以在下面查看 Office 和 Exchange 的特定需求，或使用[集中式部署相容性檢查](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)程式。</span><span class="sxs-lookup"><span data-stu-id="9ae23-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="9ae23-118">[集中式部署] 不支援下列項目：</span><span class="sxs-lookup"><span data-stu-id="9ae23-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="9ae23-119">目標鎖定為 Office 2013 中的 Word、Excel 或 PowerPoint 的增益集</span><span class="sxs-lookup"><span data-stu-id="9ae23-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="9ae23-120">內部部署目錄服務</span><span class="sxs-lookup"><span data-stu-id="9ae23-120">An on-premises directory service</span></span>
- <span data-ttu-id="9ae23-121">增益集部署至部署信箱的 Exchange</span><span class="sxs-lookup"><span data-stu-id="9ae23-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="9ae23-122">將增益集部署到 SharePoint</span><span class="sxs-lookup"><span data-stu-id="9ae23-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="9ae23-123">小組應用程式</span><span class="sxs-lookup"><span data-stu-id="9ae23-123">Teams apps</span></span>
- <span data-ttu-id="9ae23-124">部署元件物件模型 (COM) 或 Visual Studio Tools for Office (VSTO) 增益集</span><span class="sxs-lookup"><span data-stu-id="9ae23-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
- <span data-ttu-id="9ae23-125">不包含 Exchange 的 Microsoft 365 部署（例如 Microsoft 365 應用程式的企業版）</span><span class="sxs-lookup"><span data-stu-id="9ae23-125">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="9ae23-126">Office 需求</span><span class="sxs-lookup"><span data-stu-id="9ae23-126">Office Requirements</span></span>

- <span data-ttu-id="9ae23-127">若為 Word、Excel 及 PowerPoint 增益集，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9ae23-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="9ae23-128">在 Windows 裝置上，適用于企業的 Microsoft 365 應用程式版本1704或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9ae23-128">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="9ae23-129">在 Mac 上，版本15.34 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9ae23-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="9ae23-130">對於 Outlook，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9ae23-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="9ae23-131">適用于企業的 Microsoft 365 應用程式版本1701或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9ae23-131">Version 1701 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="9ae23-132">Office Professional Plus 2019 或 Office Standard 2019 的版本1808或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9ae23-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="9ae23-133">16.0.4494.1000 或更新版本的 Office Professional Plus 2016 (MSI) 或 Office Standard 2016 (MSI) \*</span><span class="sxs-lookup"><span data-stu-id="9ae23-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="9ae23-134">15.0.4937.1000 或更新版本的 Office Professional Plus 2013 (MSI) 或 Office Standard 2013 (MSI) \*</span><span class="sxs-lookup"><span data-stu-id="9ae23-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="9ae23-135">適用于 Mac 的 Office 2016 版本16.0.9318.1000 或更新版本</span><span class="sxs-lookup"><span data-stu-id="9ae23-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="9ae23-136">IOS 的 Outlook mobile 版本2.75.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="9ae23-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="9ae23-137">2.2.145 或更新版本的 Outlook mobile for Android</span><span class="sxs-lookup"><span data-stu-id="9ae23-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="9ae23-138">\* MSI 版本的 Outlook 會在適當的 Outlook 功能區中顯示系統管理員安裝的增益集，而不是「我的增益集」一節。</span><span class="sxs-lookup"><span data-stu-id="9ae23-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="9ae23-139">確定是否已安裝適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="9ae23-139">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="9ae23-140">若要使用 Microsoft 365 應用程式的企業版，使用者必須擁有 Microsoft 365 帳戶，且必須已獲指派授權。</span><span class="sxs-lookup"><span data-stu-id="9ae23-140">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="9ae23-141">如需詳細資訊，請參閱適用[于企業的 Microsoft 365 應用程式概述](https://go.microsoft.com/fwlink/p/?linkid=846328)。</span><span class="sxs-lookup"><span data-stu-id="9ae23-141">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="9ae23-142">偵測使用者是否已安裝 Microsoft 365 應用程式並最近使用它的最簡單方法，就是使用 microsoft Office 啟用報告，該報告可在 Microsoft 365 系統管理中心中取得。</span><span class="sxs-lookup"><span data-stu-id="9ae23-142">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9ae23-143">報告提供過去7天、30天、90天或180天內，已為企業版啟用 Microsoft 365 應用程式的所有使用者清單。</span><span class="sxs-lookup"><span data-stu-id="9ae23-143">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="9ae23-144">對於集中式部署用途而言，Windows 或 Mac 的電腦版啟用數是報告中的重要欄。</span><span class="sxs-lookup"><span data-stu-id="9ae23-144">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="9ae23-145">您可以將報告匯出到 Excel。</span><span class="sxs-lookup"><span data-stu-id="9ae23-145">You can export the report to Excel.</span></span> <span data-ttu-id="9ae23-146">如需報告的詳細資訊，請參閱系統[管理中心的 microsoft 365 報告-Microsoft Office](../activity-reports/microsoft-office-activations.md)啟用。</span><span class="sxs-lookup"><span data-stu-id="9ae23-146">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="9ae23-147">如果您不想使用啟用報告，您可以要求使用者在其電腦上開啟 Office 應用程式（如 Word），然後選擇 [**檔** \> **帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="9ae23-147">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="9ae23-148">在 [**產品資訊**] 底下，您應該會看到 [**訂閱產品**] 和 [ **Microsoft 365 for enterprise**]，如下列影像所示。</span><span class="sxs-lookup"><span data-stu-id="9ae23-148">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**, as shown in the following image.</span></span>

![Office 應用程式中的產品資訊](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="9ae23-150">如需 Microsoft 365 應用程式 enterprise 的說明，請參閱適用于[企業的 microsoft 365 應用程式疑難排解秘訣](https://go.microsoft.com/fwlink/p/?linkid=846339)。</span><span class="sxs-lookup"><span data-stu-id="9ae23-150">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="9ae23-151">Exchange Online 需求</span><span class="sxs-lookup"><span data-stu-id="9ae23-151">Exchange Online requirements</span></span>

<span data-ttu-id="9ae23-152">Microsoft Exchange 會將增益集資訊清單儲存在貴組織的租用戶中。</span><span class="sxs-lookup"><span data-stu-id="9ae23-152">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="9ae23-153">部署增益集的系統管理員和接收這些增益集的使用者，必須位於支援 OAuth 驗證的 Exchange Online 版本上。</span><span class="sxs-lookup"><span data-stu-id="9ae23-153">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="9ae23-p109">請洽詢貴組織的 Exchange 系統管理員，確認現正使用的設定。您可以使用 [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell Cmdlet，驗證每個使用者的 OAuth 連線。</span><span class="sxs-lookup"><span data-stu-id="9ae23-p109">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="9ae23-156">集中式部署相容性檢查程式</span><span class="sxs-lookup"><span data-stu-id="9ae23-156">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="9ae23-157">您可以使用集中式部署相容性檢查程式，確認您租使用者上的使用者是否已設定為使用 Word、Excel 和 PowerPoint 的集中式部署。</span><span class="sxs-lookup"><span data-stu-id="9ae23-157">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="9ae23-158">相容性檢查程式不需要 Outlook 支援。</span><span class="sxs-lookup"><span data-stu-id="9ae23-158">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="9ae23-159">請在[這裡](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) (英文) 下載相容性檢查程式。</span><span class="sxs-lookup"><span data-stu-id="9ae23-159">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="9ae23-160">執行相容性檢查程式</span><span class="sxs-lookup"><span data-stu-id="9ae23-160">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="9ae23-161">啟動提升的 PowerShell.exe 視窗。</span><span class="sxs-lookup"><span data-stu-id="9ae23-161">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="9ae23-162">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9ae23-162">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="9ae23-163">執行**CompatabilityCheck**命令：</span><span class="sxs-lookup"><span data-stu-id="9ae23-163">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="9ae23-164">這個命令會提示您輸入*_TenantDomain_* (例如， *TailspinToysIncorporated </span> 。com*) 和*_TenantAdmin_* 認證 (使用您的全域系統管理員認證) ，然後要求同意。</span><span class="sxs-lookup"><span data-stu-id="9ae23-164">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="9ae23-165">根據您租用戶中的使用者人數而定，檢查程式可能需要花費幾分鐘至幾小時。</span><span class="sxs-lookup"><span data-stu-id="9ae23-165">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="9ae23-166">檢查程式執行完畢後，會產生一個逗號分隔 (.csv) 格式的輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="9ae23-166">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="9ae23-167">預設會將檔案儲存為**C:\windows\system32** 。</span><span class="sxs-lookup"><span data-stu-id="9ae23-167">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="9ae23-168">輸出檔案中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="9ae23-168">The output file contains the following information:</span></span>
  
- <span data-ttu-id="9ae23-169">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="9ae23-169">User Name</span></span>
    
- <span data-ttu-id="9ae23-170">使用者識別碼 (該使用者的電子郵件地址)</span><span class="sxs-lookup"><span data-stu-id="9ae23-170">User ID (User's email address)</span></span>
    
- <span data-ttu-id="9ae23-171">已準備好使用集中式部署 (如果其餘項目之值皆為 true)</span><span class="sxs-lookup"><span data-stu-id="9ae23-171">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="9ae23-172">Office plan-已授權的 Office 計畫</span><span class="sxs-lookup"><span data-stu-id="9ae23-172">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="9ae23-173">Office 已啟用 (如果該使用者已啟用 Office)</span><span class="sxs-lookup"><span data-stu-id="9ae23-173">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="9ae23-174">支援的信箱 (如果該使用者擁有啟用 OAuth 的信箱)</span><span class="sxs-lookup"><span data-stu-id="9ae23-174">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="9ae23-175">使用者和群組指派</span><span class="sxs-lookup"><span data-stu-id="9ae23-175">User and group assignments</span></span>

<span data-ttu-id="9ae23-176">[集中式部署] 功能目前支援 Azure Active Directory 支援的大部分群組，包括 Microsoft 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="9ae23-176">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9ae23-177">目前不支援未啟用郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="9ae23-177">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="9ae23-178">集中式部署支援對承租人中個別使用者、群組和所有人的工作分派。</span><span class="sxs-lookup"><span data-stu-id="9ae23-178">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="9ae23-179">[集中式部署] 支援頂層群組或無父項群組之群組中的使用者，但不支援巢狀群組或有父項群組之群組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="9ae23-179">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="9ae23-p113">看看下列範例，其中晨怡、欣雯和銷售部門群組已被指派增益集。由於西岸銷售部門是巢狀群組，誠雄和又倫未被指派增益集。</span><span class="sxs-lookup"><span data-stu-id="9ae23-p113">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![銷售部門圖表](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="9ae23-183">確認群組是否包含巢狀群組</span><span class="sxs-lookup"><span data-stu-id="9ae23-183">Find out if a group contains nested groups</span></span>

<span data-ttu-id="9ae23-184">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span><span class="sxs-lookup"><span data-stu-id="9ae23-184">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="9ae23-185">如果您在電子郵件的 [**至**] 欄位中輸入組名，然後在解析時選取組名，它會顯示其是否包含使用者或嵌套的群組。</span><span class="sxs-lookup"><span data-stu-id="9ae23-185">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="9ae23-186">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span><span class="sxs-lookup"><span data-stu-id="9ae23-186">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Outlook 連絡人卡片的 [成員] 索引標籤](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="9ae23-p115">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span><span class="sxs-lookup"><span data-stu-id="9ae23-p115">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Outlook 連絡人卡片的 [成員資格] 索引標籤](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="9ae23-p116">或者，您也可以使用 Azure Active Directory 圖形 API 來執行查詢，尋找群組中的群組清單。如需詳細資訊，請參閱[群組上的作業 | 圖形 API 參考](https://go.microsoft.com/fwlink/p/?linkid=846342)。</span><span class="sxs-lookup"><span data-stu-id="9ae23-p116">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="9ae23-193">連絡 Microsoft 以取得支援</span><span class="sxs-lookup"><span data-stu-id="9ae23-193">Contacting Microsoft for support</span></span>

<span data-ttu-id="9ae23-194">如果您或您的使用者在使用 Office 應用程式來載入增益集時遇到問題 (Word、Excel 等 ) （已集中部署），您可能需要與 Microsoft 支援人員聯繫 (瞭解) 的[方式](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="9ae23-194">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="9ae23-195">在支援票證中提供下列有關您 Microsoft 365 環境的資訊。</span><span class="sxs-lookup"><span data-stu-id="9ae23-195">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="9ae23-196">**平台**</span><span class="sxs-lookup"><span data-stu-id="9ae23-196">**Platform**</span></span>|<span data-ttu-id="9ae23-197">**偵錯資訊**</span><span class="sxs-lookup"><span data-stu-id="9ae23-197">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9ae23-198">辦公室</span><span class="sxs-lookup"><span data-stu-id="9ae23-198">Office</span></span>  <br/> | <span data-ttu-id="9ae23-199">Charles/Fiddler 記錄檔</span><span class="sxs-lookup"><span data-stu-id="9ae23-199">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="9ae23-200">租用戶識別碼 ( [了解做法](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="9ae23-200">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="9ae23-201">CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="9ae23-201">CorrelationID.</span></span> <span data-ttu-id="9ae23-202">查看其中一個 office 頁面的來源，並尋找 [相關性識別碼] 值並傳送給支援：</span><span class="sxs-lookup"><span data-stu-id="9ae23-202">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="9ae23-203">豐富型用戶端 (Windows、Mac)</span><span class="sxs-lookup"><span data-stu-id="9ae23-203">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="9ae23-204">Charles/Fiddler 記錄檔</span><span class="sxs-lookup"><span data-stu-id="9ae23-204">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="9ae23-205">用戶端應用程式的組建編號 (最好是檔案 **/帳戶**的螢幕擷取畫面) </span><span class="sxs-lookup"><span data-stu-id="9ae23-205">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

