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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: 判斷您的 Office 365 租使用者和使用者是否符合需求，以便您可以使用集中式部署來部署 Office 增益集。
ms.openlocfilehash: a3005d02522d0a2b22b1ca337d8f49ce7fa20fb3
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209745"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="4935b-103">判斷集中式部署的增益集是否適用于您的組織</span><span class="sxs-lookup"><span data-stu-id="4935b-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="4935b-104">若要將 Office 增益集部署到 Office 365 組織中的使用者和群組，[集中式部署] 是建議大多數客戶採用且功能最豐富的方法。</span><span class="sxs-lookup"><span data-stu-id="4935b-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your Office 365 organization.</span></span> <span data-ttu-id="4935b-105">如果您是系統管理員，請使用此指導方針來判斷您的承租人和使用者是否符合需求，以便您可以使用集中式部署。</span><span class="sxs-lookup"><span data-stu-id="4935b-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="4935b-106">集中式部署支援 Windows、Mac、iOS、Android 和 Online Office 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4935b-106">Centralized Deployment supports Windows, Mac, iOS, Android and Online Office apps.</span></span>
<span data-ttu-id="4935b-107">增益集最多可能需要24小時才能顯示所有使用者的用戶端。</span><span class="sxs-lookup"><span data-stu-id="4935b-107">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4935b-108">需求</span><span class="sxs-lookup"><span data-stu-id="4935b-108">Requirements</span></span>

<span data-ttu-id="4935b-109">[！注意] 增益集的集中式部署需要使用者使用 Office 365 ProPlus （並使用其組織識別碼登入 Office），且具有 Exchange Online 和 active Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="4935b-109">Centralized deployment of add-ins requires that the users are using Office 365 ProPlus (and are signed into Office using their Organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="4935b-110">您的訂閱 [目錄] 必須是 in 或同盟至 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="4935b-110">Your subscription'd directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="4935b-111">您可以在下面查看 Office 和 Exchange 的特定需求，或使用[office 365 集中式部署相容性檢查](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)程式。</span><span class="sxs-lookup"><span data-stu-id="4935b-111">You can view specific requirements for Office and Exchange below, or use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="4935b-112">[集中式部署] 不支援下列項目：</span><span class="sxs-lookup"><span data-stu-id="4935b-112">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="4935b-113">目標鎖定為 Office 2013 中的 Word、Excel 或 PowerPoint 的增益集</span><span class="sxs-lookup"><span data-stu-id="4935b-113">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="4935b-114">內部部署目錄服務</span><span class="sxs-lookup"><span data-stu-id="4935b-114">An on-premises directory service</span></span>
    
- <span data-ttu-id="4935b-115">將增益集部署到 SharePoint</span><span class="sxs-lookup"><span data-stu-id="4935b-115">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="4935b-116">小組應用程式</span><span class="sxs-lookup"><span data-stu-id="4935b-116">Teams apps</span></span>
   
- <span data-ttu-id="4935b-117">部署元件物件模型 (COM) 或 Visual Studio Tools for Office (VSTO) 增益集</span><span class="sxs-lookup"><span data-stu-id="4935b-117">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="4935b-118">不包含 Exchange 的 Office 365 部署，例如 Office 365 商務版</span><span class="sxs-lookup"><span data-stu-id="4935b-118">Deployments of Office 365 that do not include Exchange such as Office 365 Business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="4935b-119">Office 需求</span><span class="sxs-lookup"><span data-stu-id="4935b-119">Office Requirements</span></span>

- <span data-ttu-id="4935b-120">若為 Word、Excel 及 PowerPoint 增益集，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4935b-120">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="4935b-121">在 Windows 裝置上，版本1704或更新版本的 Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="4935b-121">On a Windows device, Version 1704 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="4935b-122">在 Mac 上，版本15.34 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4935b-122">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="4935b-123">對於 Outlook，您的使用者必須使用下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4935b-123">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="4935b-124">版本1701或更新版本的 Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="4935b-124">Version 1701 or later of Office 365 ProPlus.</span></span>
  - <span data-ttu-id="4935b-125">Office Professional Plus 2019 或 Office Standard 2019 的版本1808或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4935b-125">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="4935b-126">16.0.4494.1000 或更新版本的 Office Professional Plus 2016 （MSI）或 Office Standard 2016 （MSI）\*</span><span class="sxs-lookup"><span data-stu-id="4935b-126">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="4935b-127">15.0.4937.1000 或更新版本的 Office Professional Plus 2013 （MSI）或 Office Standard 2013 （MSI）\*</span><span class="sxs-lookup"><span data-stu-id="4935b-127">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="4935b-128">適用于 Mac 的 Office 2016 版本16.0.9318.1000 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4935b-128">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="4935b-129">IOS 的 Outlook mobile 版本2.75.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4935b-129">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="4935b-130">2.2.145 或更新版本的 Outlook mobile for Android</span><span class="sxs-lookup"><span data-stu-id="4935b-130">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="4935b-131">\* MSI 版本的 Outlook 會在適當的 Outlook 功能區中顯示系統管理員安裝的增益集，而不是「我的增益集」一節。</span><span class="sxs-lookup"><span data-stu-id="4935b-131">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a><span data-ttu-id="4935b-132">確認是否已安裝 Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="4935b-132">Find out if Office 365 ProPlus is installed</span></span>

<span data-ttu-id="4935b-133">若要使用 Office 365 ProPlus，使用者必須擁有 Office 365 帳戶，且必須已獲指派授權。</span><span class="sxs-lookup"><span data-stu-id="4935b-133">To use Office 365 ProPlus, a user must have an Office 365 account and must have been assigned a license.</span></span> <span data-ttu-id="4935b-134">如需詳細資訊，請參閱 [Office 365 專業增強版概觀](https://go.microsoft.com/fwlink/p/?linkid=846328)。</span><span class="sxs-lookup"><span data-stu-id="4935b-134">For more information, see [Overview of Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="4935b-135">偵測使用者是否已安裝 Office 365 ProPlus 且最近使用它的最簡單方法，就是使用 microsoft Office 啟用報告，該報告可在 Microsoft 365 系統管理中心中取得。</span><span class="sxs-lookup"><span data-stu-id="4935b-135">The simplest way to detect if a user has Office 365 ProPlus installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4935b-136">報告提供已在最近 7 天、30 天、90 天或 180 天內啟用 Office 365 專業增強版之所有使用者的清單。</span><span class="sxs-lookup"><span data-stu-id="4935b-136">The report provides a list of all users who have activated Office 365 ProPlus within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="4935b-137">對於集中式部署用途而言，Windows 或 Mac 的電腦版啟用數是報告中的重要欄。</span><span class="sxs-lookup"><span data-stu-id="4935b-137">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="4935b-138">您可以將報告匯出到 Excel。</span><span class="sxs-lookup"><span data-stu-id="4935b-138">You can export the report to Excel.</span></span> <span data-ttu-id="4935b-139">如需有關報告的詳細資訊，請參閱[系統管理中心的 Office 365 報告 - Microsoft Office 啟用](../activity-reports/microsoft-office-activations.md)。</span><span class="sxs-lookup"><span data-stu-id="4935b-139">For more information about the report, see [Office 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="4935b-140">如果您不想使用啟用報告，您可以要求使用者在其電腦上開啟 Office 應用程式（如 Word），然後選擇 [**檔** \> **帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="4935b-140">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="4935b-141">Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.</span><span class="sxs-lookup"><span data-stu-id="4935b-141">Under **Product Information**, you should see **Subscription Product** and **Microsoft Office 365 ProPlus**, as shown in the following image.</span></span>

![Office 應用程式中的產品資訊](../../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
<span data-ttu-id="4935b-143">如需 Office 365 專業增強版的相關說明，請參閱 [Office 365 專業增強版的疑難排解提示](https://go.microsoft.com/fwlink/p/?linkid=846339)。</span><span class="sxs-lookup"><span data-stu-id="4935b-143">For help with Office 365 ProPlus, see [Troubleshooting tips for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="4935b-144">Exchange Online 需求</span><span class="sxs-lookup"><span data-stu-id="4935b-144">Exchange Online requirements</span></span>

<span data-ttu-id="4935b-145">Microsoft Exchange 會將增益集資訊清單儲存在貴組織的租用戶中。</span><span class="sxs-lookup"><span data-stu-id="4935b-145">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="4935b-146">部署增益集的系統管理員和接收這些增益集的使用者，必須位於支援 OAuth 驗證的 Exchange Online 版本上。</span><span class="sxs-lookup"><span data-stu-id="4935b-146">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="4935b-p107">請洽詢貴組織的 Exchange 系統管理員，確認現正使用的設定。您可以使用 [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell Cmdlet，驗證每個使用者的 OAuth 連線。</span><span class="sxs-lookup"><span data-stu-id="4935b-p107">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="office-365-centralized-deployment-compatibility-checker"></a><span data-ttu-id="4935b-149">Office 365 集中式部署相容性檢查程式</span><span class="sxs-lookup"><span data-stu-id="4935b-149">Office 365 Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="4935b-p108">使用 Office 365 集中式部署相容性檢查程式，即可確認您租用戶中的使用者是否已設定完畢，可使用適用於 Word、Excel 和 PowerPoint 的集中式部署。相容性檢查程式不需要 Outlook 支援。請在[這裡](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) (英文) 下載相容性檢查程式。</span><span class="sxs-lookup"><span data-stu-id="4935b-p108">Using the Office 365 Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint. The Compatibility Checker is not required for Outlook support. Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="4935b-153">執行相容性檢查程式</span><span class="sxs-lookup"><span data-stu-id="4935b-153">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="4935b-154">啟動提升的 PowerShell.exe 視窗。</span><span class="sxs-lookup"><span data-stu-id="4935b-154">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="4935b-155">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4935b-155">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="4935b-156">執行**CompatabilityCheck**命令：</span><span class="sxs-lookup"><span data-stu-id="4935b-156">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="4935b-157">這會提示您*_TenantDomain_* （例如， *TailspinToysIncorporated）。</span>com*）和*_TenantAdmin_* 認證（使用您的全域系統管理員認證），然後要求同意。</span><span class="sxs-lookup"><span data-stu-id="4935b-157">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4935b-158">根據您租用戶中的使用者人數而定，檢查程式可能需要花費幾分鐘至幾小時。</span><span class="sxs-lookup"><span data-stu-id="4935b-158">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="4935b-159">檢查程式執行完畢後，會產生一個逗號分隔 (.csv) 格式的輸出檔案。</span><span class="sxs-lookup"><span data-stu-id="4935b-159">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="4935b-160">預設會將檔案儲存為**C:\windows\system32** 。</span><span class="sxs-lookup"><span data-stu-id="4935b-160">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="4935b-161">輸出檔案中包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="4935b-161">The output file contains the following information:</span></span>
  
- <span data-ttu-id="4935b-162">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="4935b-162">User Name</span></span>
    
- <span data-ttu-id="4935b-163">使用者識別碼 (該使用者的電子郵件地址)</span><span class="sxs-lookup"><span data-stu-id="4935b-163">User ID (User's email address)</span></span>
    
- <span data-ttu-id="4935b-164">已準備好使用集中式部署 (如果其餘項目之值皆為 true)</span><span class="sxs-lookup"><span data-stu-id="4935b-164">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="4935b-165">Office plan-已授權的 Office 計畫</span><span class="sxs-lookup"><span data-stu-id="4935b-165">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="4935b-166">Office 已啟用 (如果該使用者已啟用 Office)</span><span class="sxs-lookup"><span data-stu-id="4935b-166">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="4935b-167">支援的信箱 (如果該使用者擁有啟用 OAuth 的信箱)</span><span class="sxs-lookup"><span data-stu-id="4935b-167">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="4935b-168">使用者和群組指派</span><span class="sxs-lookup"><span data-stu-id="4935b-168">User and group assignments</span></span>

<span data-ttu-id="4935b-169">[集中式部署] 功能目前支援 Azure Active Directory 支援的大多數群組，包括 Office 365 群組、通訊群組清單和安全性群組。</span><span class="sxs-lookup"><span data-stu-id="4935b-169">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Office 365 Groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4935b-170">目前不支援未啟用郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="4935b-170">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="4935b-171">集中式部署支援對承租人中個別使用者、群組和所有人的工作分派。</span><span class="sxs-lookup"><span data-stu-id="4935b-171">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="4935b-172">[集中式部署] 支援頂層群組或無父項群組之群組中的使用者，但不支援巢狀群組或有父項群組之群組中的使用者。</span><span class="sxs-lookup"><span data-stu-id="4935b-172">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="4935b-p111">看看下列範例，其中晨怡、欣雯和銷售部門群組已被指派增益集。由於西岸銷售部門是巢狀群組，誠雄和又倫未被指派增益集。</span><span class="sxs-lookup"><span data-stu-id="4935b-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![銷售部門圖表](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="4935b-176">確認群組是否包含巢狀群組</span><span class="sxs-lookup"><span data-stu-id="4935b-176">Find out if a group contains nested groups</span></span>

<span data-ttu-id="4935b-177">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span><span class="sxs-lookup"><span data-stu-id="4935b-177">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="4935b-178">如果您在電子郵件的 [**至**] 欄位中輸入組名，然後在解析時選取組名，它會顯示其是否包含使用者或嵌套的群組。</span><span class="sxs-lookup"><span data-stu-id="4935b-178">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="4935b-179">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span><span class="sxs-lookup"><span data-stu-id="4935b-179">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Outlook 連絡人卡片的 [成員] 索引標籤](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="4935b-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span><span class="sxs-lookup"><span data-stu-id="4935b-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Outlook 連絡人卡片的 [成員資格] 索引標籤](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="4935b-p114">或者，您也可以使用 Azure Active Directory 圖形 API 來執行查詢，尋找群組中的群組清單。如需詳細資訊，請參閱[群組上的作業 | 圖形 API 參考](https://go.microsoft.com/fwlink/p/?linkid=846342)。</span><span class="sxs-lookup"><span data-stu-id="4935b-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="4935b-186">連絡 Microsoft 以取得支援</span><span class="sxs-lookup"><span data-stu-id="4935b-186">Contacting Microsoft for support</span></span>

<span data-ttu-id="4935b-187">如果您或您的使用者在使用 Office 應用程式（Word、Excel 等）時載入增益集時遇到問題，則您可能需要與 Microsoft 支援人員取得聯繫（[瞭解如何](../contact-support-for-business-products.md)）。</span><span class="sxs-lookup"><span data-stu-id="4935b-187">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="4935b-188">並且在支援票證中提供有關您 Office 365 環境的以下資訊。</span><span class="sxs-lookup"><span data-stu-id="4935b-188">Provide the following information about your Office 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="4935b-189">**平台**</span><span class="sxs-lookup"><span data-stu-id="4935b-189">**Platform**</span></span>|<span data-ttu-id="4935b-190">**偵錯資訊**</span><span class="sxs-lookup"><span data-stu-id="4935b-190">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4935b-191">辦公室</span><span class="sxs-lookup"><span data-stu-id="4935b-191">Office</span></span>  <br/> | <span data-ttu-id="4935b-192">Charles/Fiddler 記錄檔</span><span class="sxs-lookup"><span data-stu-id="4935b-192">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="4935b-193">租用戶識別碼 ( [了解做法](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span><span class="sxs-lookup"><span data-stu-id="4935b-193">Tenant ID ( [learn how](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))</span></span>  <br/>  <span data-ttu-id="4935b-194">CorrelationID。</span><span class="sxs-lookup"><span data-stu-id="4935b-194">CorrelationID.</span></span> <span data-ttu-id="4935b-195">查看其中一個 office 頁面的來源，並尋找 [相關性識別碼] 值並傳送給支援：</span><span class="sxs-lookup"><span data-stu-id="4935b-195">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="4935b-196">豐富型用戶端 (Windows、Mac)</span><span class="sxs-lookup"><span data-stu-id="4935b-196">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="4935b-197">Charles/Fiddler 記錄檔</span><span class="sxs-lookup"><span data-stu-id="4935b-197">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="4935b-198">用戶端應用程式的組建編號（最好是檔案 **/帳戶**的螢幕擷取畫面）</span><span class="sxs-lookup"><span data-stu-id="4935b-198">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

