---
title: 管理可建立 Microsoft 365 群組的人員
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 瞭解如何控制可建立 Microsoft 365 群組的使用者。
ms.openlocfilehash: 49fdaa98d0b88b306b9fd3d84e52bcf52d9fdf7f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662534"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="43b18-103">管理可建立 Microsoft 365 群組的人員</span><span class="sxs-lookup"><span data-stu-id="43b18-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="43b18-104">根據預設，所有使用者都可以建立 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="43b18-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="43b18-105">這是建議的方法，因為它可讓使用者在不需要協助的情況下開始合作。</span><span class="sxs-lookup"><span data-stu-id="43b18-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="43b18-106">如果您的公司需要限制誰可以建立群組，您可以遵循本文所述的程式來執行。</span><span class="sxs-lookup"><span data-stu-id="43b18-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="43b18-107">當您限制誰可以建立群組時，它會影響依賴群組進行存取的所有服務，包括：</span><span class="sxs-lookup"><span data-stu-id="43b18-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="43b18-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="43b18-108">Outlook</span></span>
    
- <span data-ttu-id="43b18-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="43b18-109">SharePoint</span></span>
    
- <span data-ttu-id="43b18-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="43b18-110">Yammer</span></span>
    
- <span data-ttu-id="43b18-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="43b18-111">Microsoft Teams</span></span>

- <span data-ttu-id="43b18-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="43b18-112">Microsoft Stream</span></span>

- <span data-ttu-id="43b18-113">Planner</span><span class="sxs-lookup"><span data-stu-id="43b18-113">Planner</span></span>
    
- <span data-ttu-id="43b18-114">PowerBI (古典) </span><span class="sxs-lookup"><span data-stu-id="43b18-114">PowerBI (classic)</span></span>
    
- <span data-ttu-id="43b18-115">Web/藍圖的專案</span><span class="sxs-lookup"><span data-stu-id="43b18-115">Project for the web / Roadmap</span></span>
    
<span data-ttu-id="43b18-116">您可以將 Microsoft 365 群組建立限制在特定安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="43b18-116">You can restrict Microsoft 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="43b18-117">若要設定此，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="43b18-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="43b18-118">本文將引導您完成必要的步驟。</span><span class="sxs-lookup"><span data-stu-id="43b18-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="43b18-119">本文中的步驟不會防止某些角色的成員建立群組。</span><span class="sxs-lookup"><span data-stu-id="43b18-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="43b18-120">Office 365 全域系統管理員可以透過任何方式建立群組，例如 Microsoft 365 系統管理中心、Planner、小組、Exchange 及 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="43b18-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="43b18-121">其他角色可以透過有限的方式建立群組，如下所列。</span><span class="sxs-lookup"><span data-stu-id="43b18-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="43b18-122">Exchange 管理員： Exchange Admin center，Azure AD</span><span class="sxs-lookup"><span data-stu-id="43b18-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="43b18-123">合作夥伴第1層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="43b18-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="43b18-124">合作夥伴第2層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="43b18-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="43b18-125">目錄編寫者： Azure AD</span><span class="sxs-lookup"><span data-stu-id="43b18-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="43b18-126">SharePoint 管理員： SharePoint Admin center，Azure AD</span><span class="sxs-lookup"><span data-stu-id="43b18-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="43b18-127">小組服務管理員：小組系統管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="43b18-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="43b18-128">使用者管理系統管理員： Microsoft 365 Admin center、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="43b18-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="43b18-129">如果您是其中一個角色的成員，您可以為受限制的使用者建立 Microsoft 365 群組，然後將該使用者指派為群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="43b18-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="43b18-130">授權需求</span><span class="sxs-lookup"><span data-stu-id="43b18-130">Licensing requirements</span></span>

<span data-ttu-id="43b18-131">若要管理群組的建立者，下列人員必須已指派 Azure AD Premium 授權或 Azure AD 基本 EDU 授權：</span><span class="sxs-lookup"><span data-stu-id="43b18-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="43b18-132">設定這些群組建立設定的系統管理員</span><span class="sxs-lookup"><span data-stu-id="43b18-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="43b18-133">允許建立群組的安全性群組成員</span><span class="sxs-lookup"><span data-stu-id="43b18-133">The members of the security group who are allowed to create groups</span></span>
 
> [!NOTE]
> <span data-ttu-id="43b18-134">如需如何指派 Azure 授權的詳細資訊，請參閱 [在 Azure Active Directory 入口網站中指派或移除授權](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 。</span><span class="sxs-lookup"><span data-stu-id="43b18-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="43b18-135">下列人員不需要有指派給它們的 Azure AD Premium 或 Azure AD 基本 EDU 授權：</span><span class="sxs-lookup"><span data-stu-id="43b18-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="43b18-136">屬於 Microsoft 365 群組成員的人員，以及沒有建立其他群組的能力。</span><span class="sxs-lookup"><span data-stu-id="43b18-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="43b18-137">步驟1：為需要建立 Microsoft 365 群組的使用者建立安全性群組</span><span class="sxs-lookup"><span data-stu-id="43b18-137">Step 1: Create a security group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="43b18-138">您組織中只有一個安全性群組可用於控制誰可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="43b18-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="43b18-139">不過，您可以以巢狀方式內嵌其他安全性群組，做為此群組的成員。</span><span class="sxs-lookup"><span data-stu-id="43b18-139">But, you can nest other security groups as members of this group.</span></span>

<span data-ttu-id="43b18-140">以上所列角色中的系統管理員不需要是此群組的成員：他們保留其建立群組的能力。</span><span class="sxs-lookup"><span data-stu-id="43b18-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43b18-141">請務必使用 **安全性群組** 來限制誰可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="43b18-141">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="43b18-142">不支援使用 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="43b18-142">Using a Microsoft 365 group is not supported.</span></span> 
    
1. <span data-ttu-id="43b18-143">在系統管理中心中，移至 [ [群組] 頁面](https://admin.microsoft.com/adminportal/home#/groups)。</span><span class="sxs-lookup"><span data-stu-id="43b18-143">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="43b18-144">按一下 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="43b18-144">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="43b18-145">選擇 [ **安全性** ] 做為「群組類型」。</span><span class="sxs-lookup"><span data-stu-id="43b18-145">Choose **Security** as the group type.</span></span> <span data-ttu-id="43b18-146">請記下群組名稱！</span><span class="sxs-lookup"><span data-stu-id="43b18-146">Remember the name of the group!</span></span> <span data-ttu-id="43b18-147">以便後續步驟使用。</span><span class="sxs-lookup"><span data-stu-id="43b18-147">You'll need it later.</span></span>
  
4. <span data-ttu-id="43b18-148">完成設定安全性群組，新增您想要在您的組織中建立群組的人員或其他安全性群組。</span><span class="sxs-lookup"><span data-stu-id="43b18-148">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="43b18-149">如需詳細指示，請參閱 [建立、編輯或刪除 Microsoft 365 admin center 中的安全性群組](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)。</span><span class="sxs-lookup"><span data-stu-id="43b18-149">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="43b18-150">步驟 2：執行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="43b18-150">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="43b18-151">您必須使用預覽版本的 [ [Azure Active Directory PowerShell For Graph (AzureAD) ](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (模組名稱 **AzureADPreview**) ，以變更群組層級來賓存取設定：</span><span class="sxs-lookup"><span data-stu-id="43b18-151">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="43b18-152">如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)，並遵循指示來安裝公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="43b18-152">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="43b18-153">如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。</span><span class="sxs-lookup"><span data-stu-id="43b18-153">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="43b18-154">如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。</span><span class="sxs-lookup"><span data-stu-id="43b18-154">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="43b18-155">將下列腳本複製到文字編輯器（例如記事本）或 [Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)。</span><span class="sxs-lookup"><span data-stu-id="43b18-155">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="43b18-156">取代 *\<SecurityGroupName\>* 為您建立的安全性群組名稱。</span><span class="sxs-lookup"><span data-stu-id="43b18-156">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="43b18-157">例如：</span><span class="sxs-lookup"><span data-stu-id="43b18-157">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="43b18-158">將檔案儲存為 GroupCreators.ps1。</span><span class="sxs-lookup"><span data-stu-id="43b18-158">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="43b18-159">在 [PowerShell] 視窗中，流覽至您儲存檔案的位置， (輸入 "CD <FileLocation> " ) 。</span><span class="sxs-lookup"><span data-stu-id="43b18-159">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="43b18-160">輸入下列命令以執行腳本：</span><span class="sxs-lookup"><span data-stu-id="43b18-160">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="43b18-161">系統提示時，請 [使用系統管理員帳戶登入](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) 。</span><span class="sxs-lookup"><span data-stu-id="43b18-161">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="43b18-162">腳本的最後一行會顯示更新的設定：</span><span class="sxs-lookup"><span data-stu-id="43b18-162">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="43b18-164">如果您想要變更使用的安全性群組，您可以使用新安全性群組的名稱重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="43b18-164">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="43b18-165">如果您想關閉群組建立限制，並再次允許所有使用者建立群組，請將 $GroupName 設定為 ""，並 $AllowGroupCreation 為 "True"，然後重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="43b18-165">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="43b18-166">步驟4：確認其運作正常</span><span class="sxs-lookup"><span data-stu-id="43b18-166">Step 4: Verify that it works</span></span>

<span data-ttu-id="43b18-167">變更可能需要30分鐘以上的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="43b18-167">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="43b18-168">您可以執行下列動作來驗證新的設定：</span><span class="sxs-lookup"><span data-stu-id="43b18-168">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="43b18-169">使用不具備建立群組功能之人員的使用者帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="43b18-169">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="43b18-170">也就是說，它們不是您所建立之安全性群組的成員，或是管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="43b18-170">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="43b18-171">選取 [ **Planner** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="43b18-171">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="43b18-172">在 Planner 中，選取左側導覽中的 [ **新增方案** ]，以建立計畫。</span><span class="sxs-lookup"><span data-stu-id="43b18-172">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="43b18-173">您應該會收到一則停用計畫和群組建立的訊息。</span><span class="sxs-lookup"><span data-stu-id="43b18-173">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="43b18-174">請使用安全性群組的成員嘗試相同的程式。</span><span class="sxs-lookup"><span data-stu-id="43b18-174">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="43b18-175">如果安全性群組的成員無法建立群組，請檢查他們未透過 [OWA 信箱原則](https://go.microsoft.com/fwlink/?linkid=852135)封鎖。</span><span class="sxs-lookup"><span data-stu-id="43b18-175">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="43b18-176">相關文章</span><span class="sxs-lookup"><span data-stu-id="43b18-176">Related articles</span></span>

[<span data-ttu-id="43b18-177">開始使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="43b18-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="43b18-178">在 Azure Active Directory 中設定自助群組管理</span><span class="sxs-lookup"><span data-stu-id="43b18-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="43b18-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="43b18-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="43b18-180">用於設定群組設定的 Azure Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="43b18-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
