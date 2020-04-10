---
title: 管理能建立 Office 365 群組的使用者
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
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
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 瞭解如何控制可建立 Office 365 群組的使用者。
ms.openlocfilehash: 9016b96821dd9d40a0fb65574ce96d7badd0c2bd
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212078"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="0869e-103">管理能建立 Office 365 群組的使用者</span><span class="sxs-lookup"><span data-stu-id="0869e-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="0869e-104">由於很容易讓使用者建立 Office 365 群組，所以您不會淹沒在要求中，您必須代表其他人員建立這些群組。</span><span class="sxs-lookup"><span data-stu-id="0869e-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="0869e-105">不過，您可能想要控制哪些人員可以建立群組，這取決於您的公司。</span><span class="sxs-lookup"><span data-stu-id="0869e-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="0869e-106">本文說明如何停用在所有使用群組的 Office 365 服務中建立群組的能力，包括：</span><span class="sxs-lookup"><span data-stu-id="0869e-106">This article explains how to disable the ability to create groups in all Office 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="0869e-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="0869e-107">Outlook</span></span>
    
- <span data-ttu-id="0869e-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="0869e-108">SharePoint</span></span>
    
- <span data-ttu-id="0869e-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="0869e-109">Yammer</span></span>
    
- <span data-ttu-id="0869e-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0869e-110">Microsoft Teams</span></span>

- <span data-ttu-id="0869e-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="0869e-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="0869e-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="0869e-112">StaffHub</span></span>
    
- <span data-ttu-id="0869e-113">Planner</span><span class="sxs-lookup"><span data-stu-id="0869e-113">Planner</span></span>
    
- <span data-ttu-id="0869e-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="0869e-114">PowerBI</span></span>

- <span data-ttu-id="0869e-115">藍圖</span><span class="sxs-lookup"><span data-stu-id="0869e-115">Roadmap</span></span>
    
<span data-ttu-id="0869e-116">您可以將 Office 365 群組建立限制在特定安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0869e-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="0869e-117">若要設定此，您可以使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0869e-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="0869e-118">本文將引導您完成必要的步驟。</span><span class="sxs-lookup"><span data-stu-id="0869e-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="0869e-119">本文中的步驟不會防止某些角色的成員建立群組。</span><span class="sxs-lookup"><span data-stu-id="0869e-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="0869e-120">Office 365 全域系統管理員可以透過任何方式建立群組，例如 Microsoft 365 系統管理中心、Planner、小組、Exchange 及 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="0869e-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="0869e-121">其他角色可以透過有限的方式建立群組，如下所列。</span><span class="sxs-lookup"><span data-stu-id="0869e-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="0869e-122">Exchange 管理員： Exchange Admin center，Azure AD</span><span class="sxs-lookup"><span data-stu-id="0869e-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="0869e-123">合作夥伴第1層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="0869e-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="0869e-124">合作夥伴第2層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="0869e-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="0869e-125">目錄編寫者： Azure AD</span><span class="sxs-lookup"><span data-stu-id="0869e-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="0869e-126">SharePoint 管理員： SharePoint Admin center，Azure AD</span><span class="sxs-lookup"><span data-stu-id="0869e-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="0869e-127">小組服務管理員：小組系統管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="0869e-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="0869e-128">使用者管理系統管理員： Microsoft 365 Admin center、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="0869e-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="0869e-129">如果您是上述角色成員，即可為受限的使用者建立 Office 365 群組，然後將指派使用者為群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="0869e-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="0869e-130">具有此角色的使用者可以在 Yammer 中建立連線的群組，不論可能禁止建立的任何 PowerShell 設定。</span><span class="sxs-lookup"><span data-stu-id="0869e-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="0869e-131">授權需求</span><span class="sxs-lookup"><span data-stu-id="0869e-131">Licensing requirements</span></span>

<span data-ttu-id="0869e-132">若要管理群組的建立者，下列人員必須已指派 Azure AD Premium 授權或 Azure AD 基本 EDU 授權：</span><span class="sxs-lookup"><span data-stu-id="0869e-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="0869e-133">設定這些群組建立設定的系統管理員</span><span class="sxs-lookup"><span data-stu-id="0869e-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="0869e-134">允許建立群組的安全性群組成員</span><span class="sxs-lookup"><span data-stu-id="0869e-134">The members of the security group who are allowed to create groups</span></span>

<span data-ttu-id="0869e-135">下列人員不需要有指派給它們的 Azure AD Premium 或 Azure AD 基本 EDU 授權：</span><span class="sxs-lookup"><span data-stu-id="0869e-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="0869e-136">屬於 Office 365 群組成員的人員，以及沒有建立其他群組的能力。</span><span class="sxs-lookup"><span data-stu-id="0869e-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="0869e-137">步驟 1：為需要建立 Office 365 群組的使用者建立安全性群組</span><span class="sxs-lookup"><span data-stu-id="0869e-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="0869e-138">您組織中只有一個安全性群組可用於控制誰可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="0869e-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="0869e-139">不過，您可以以巢狀方式內嵌其他安全性群組，做為此群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0869e-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="0869e-140">例如，名為「Allow Group Creation」的群組即為指定的安全性群組，而名為「Microsoft Planner Users and Exchange Online Users」的群組則屬於該群組成員。</span><span class="sxs-lookup"><span data-stu-id="0869e-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="0869e-141">以上所列角色中的系統管理員不需要是此群組的成員：他們保留其建立群組的能力。</span><span class="sxs-lookup"><span data-stu-id="0869e-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0869e-142">請務必使用**安全性群組**來限制誰可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="0869e-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="0869e-143">如果您嘗試使用 Office 365 群組，成員將無法從 SharePoint 建立群組，因為它會檢查安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0869e-143">If you try to use an Office 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="0869e-144">在系統管理中心中，移至 [**群組** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">群組</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="0869e-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="0869e-145">按一下 [**新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="0869e-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="0869e-146">選擇 [**安全性**] 做為「群組類型」。</span><span class="sxs-lookup"><span data-stu-id="0869e-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="0869e-147">請記下群組名稱！</span><span class="sxs-lookup"><span data-stu-id="0869e-147">Remember the name of the group!</span></span> <span data-ttu-id="0869e-148">以便後續步驟使用。</span><span class="sxs-lookup"><span data-stu-id="0869e-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="0869e-149">完成設定安全性群組，新增您想要在您的組織中建立群組的人員或其他安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0869e-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="0869e-150">如需詳細指示，請參閱[建立、編輯或刪除 Microsoft 365 admin center 中的安全性群組](../email/create-edit-or-delete-a-security-group.md)。</span><span class="sxs-lookup"><span data-stu-id="0869e-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="0869e-151">步驟 2：執行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="0869e-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="0869e-152">您必須使用預覽版本的 [ [Azure Active Directory PowerShell For Graph （AzureAD）](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （模組名稱**AzureADPreview**）以變更群組層級來賓存取設定：</span><span class="sxs-lookup"><span data-stu-id="0869e-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="0869e-153">如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)，並遵循指示來安裝公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="0869e-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="0869e-154">如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。</span><span class="sxs-lookup"><span data-stu-id="0869e-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="0869e-155">如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。</span><span class="sxs-lookup"><span data-stu-id="0869e-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="0869e-156">將下列腳本複製到文字編輯器（例如記事本）或[Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)。</span><span class="sxs-lookup"><span data-stu-id="0869e-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="0869e-157">以您建立的安全性群組名稱取代\* \<SecurityGroupName\> \* 。</span><span class="sxs-lookup"><span data-stu-id="0869e-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="0869e-158">例如：</span><span class="sxs-lookup"><span data-stu-id="0869e-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="0869e-159">將檔案儲存為 GroupCreators。</span><span class="sxs-lookup"><span data-stu-id="0869e-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="0869e-160">在 [PowerShell] 視窗中，流覽至您儲存檔案的位置（輸入 " <FileLocation>CD"）。</span><span class="sxs-lookup"><span data-stu-id="0869e-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="0869e-161">輸入下列命令以執行腳本：</span><span class="sxs-lookup"><span data-stu-id="0869e-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="0869e-162">系統提示時，請[使用系統管理員帳戶登入](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)。</span><span class="sxs-lookup"><span data-stu-id="0869e-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="0869e-163">腳本的最後一行會顯示更新的設定：</span><span class="sxs-lookup"><span data-stu-id="0869e-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="0869e-165">如果您想要變更使用的安全性群組，您可以使用新安全性群組的名稱重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="0869e-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="0869e-166">如果您想關閉群組建立限制，並再次允許所有使用者建立群組，請將 $GroupName 設定為 ""，並 $AllowGroupCreation 為 "True"，然後重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="0869e-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="0869e-167">步驟4：確認其運作正常</span><span class="sxs-lookup"><span data-stu-id="0869e-167">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="0869e-168">請使用不具備群組建立能力的使用者帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0869e-168">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="0869e-169">也就是說，它們不是您所建立之安全性群組的成員，或是管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="0869e-169">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="0869e-170">選取 [ **Planner** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="0869e-170">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="0869e-171">在 Planner 中，選取左側導覽中的 [**新增方案**]，以建立計畫。</span><span class="sxs-lookup"><span data-stu-id="0869e-171">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="0869e-172">您應該會收到一則停用計畫和群組建立的訊息。</span><span class="sxs-lookup"><span data-stu-id="0869e-172">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="0869e-173">請使用安全性群組的成員嘗試相同的程式。</span><span class="sxs-lookup"><span data-stu-id="0869e-173">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="0869e-174">如果安全性群組的成員無法建立群組，請檢查他們未透過[OWA 信箱原則](https://go.microsoft.com/fwlink/?linkid=852135)封鎖。</span><span class="sxs-lookup"><span data-stu-id="0869e-174">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="0869e-175">相關文章</span><span class="sxs-lookup"><span data-stu-id="0869e-175">Related articles</span></span>

[<span data-ttu-id="0869e-176">開始使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="0869e-176">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="0869e-177">在 Azure Active Directory 中設定自助群組管理</span><span class="sxs-lookup"><span data-stu-id="0869e-177">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="0869e-178">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="0869e-178">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="0869e-179">用於設定群組設定的 Azure Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0869e-179">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
