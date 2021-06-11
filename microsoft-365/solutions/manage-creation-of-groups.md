---
title: 管理能建立 Microsoft 365 群組的使用者
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
recommendations: false
description: 瞭解如何控制哪些使用者可以建立 Microsoft 365 群組。
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539176"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="deb2a-103">管理能建立 Microsoft 365 群組的使用者</span><span class="sxs-lookup"><span data-stu-id="deb2a-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="deb2a-104">根據預設，所有使用者都可以建立 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="deb2a-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="deb2a-105">這是建議的方法，因為它可讓使用者在不需要協助的情況下開始合作。</span><span class="sxs-lookup"><span data-stu-id="deb2a-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="deb2a-106">如果您的公司需要限制誰可以建立群組，您可以將 Microsoft 365 群組建立限制在特定 Microsoft 365 群組或安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="deb2a-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="deb2a-107">如果您擔心使用者建立的小組或群組不符合您的商務標準，請考慮要求使用者完成訓練課程，然後將其新增至允許的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="deb2a-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="deb2a-108">當您限制誰可以建立群組時，它會影響依賴群組進行存取的所有服務，包括：</span><span class="sxs-lookup"><span data-stu-id="deb2a-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="deb2a-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="deb2a-109">Outlook</span></span>
- <span data-ttu-id="deb2a-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="deb2a-110">SharePoint</span></span>
- <span data-ttu-id="deb2a-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="deb2a-111">Yammer</span></span>
- <span data-ttu-id="deb2a-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="deb2a-112">Microsoft Teams</span></span>
- <span data-ttu-id="deb2a-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="deb2a-113">Microsoft Stream</span></span>
- <span data-ttu-id="deb2a-114">Planner</span><span class="sxs-lookup"><span data-stu-id="deb2a-114">Planner</span></span>
- <span data-ttu-id="deb2a-115">Power BI (古典) </span><span class="sxs-lookup"><span data-stu-id="deb2a-115">Power BI (classic)</span></span>
- <span data-ttu-id="deb2a-116">web/藍圖的 Project</span><span class="sxs-lookup"><span data-stu-id="deb2a-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="deb2a-117">本文中的步驟不會防止某些角色的成員建立群組。</span><span class="sxs-lookup"><span data-stu-id="deb2a-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="deb2a-118">Office 365全域管理員可以透過 Microsoft 365 系統管理中心、Planner、Exchange 和 SharePoint 來建立群組。</span><span class="sxs-lookup"><span data-stu-id="deb2a-118">Office 365 Global admins can create Groups via the Microsoft 365 admin center, Planner, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="deb2a-119">其他角色可以透過有限的方式建立群組，如下所列。</span><span class="sxs-lookup"><span data-stu-id="deb2a-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="deb2a-120">Exchange系統管理員： Exchange 系統管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb2a-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="deb2a-121">第1層支援： Microsoft 365 系統管理中心、Exchange admin center、Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb2a-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="deb2a-122">合作夥伴第2層支援： Microsoft 365 系統管理中心、Exchange 系統管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb2a-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="deb2a-123">目錄編寫者： Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb2a-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="deb2a-124">SharePoint系統管理員： SharePoint 系統管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb2a-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="deb2a-125">Teams服務管理員： Teams 系統管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb2a-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="deb2a-126">使用者管理員： Microsoft 365 Admin center，Azure AD</span><span class="sxs-lookup"><span data-stu-id="deb2a-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="deb2a-127">如果您是其中一個角色的成員，您可以為受限制的使用者建立 Microsoft 365 群組，然後將該使用者指派為群組的擁有者。</span><span class="sxs-lookup"><span data-stu-id="deb2a-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="deb2a-128">授權需求</span><span class="sxs-lookup"><span data-stu-id="deb2a-128">Licensing requirements</span></span>

<span data-ttu-id="deb2a-129">若要管理群組的建立者，下列人員必須已指派 Azure AD 進階版授權或 Azure AD 基本 EDU 授權：</span><span class="sxs-lookup"><span data-stu-id="deb2a-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="deb2a-130">設定這些群組建立設定的系統管理員</span><span class="sxs-lookup"><span data-stu-id="deb2a-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="deb2a-131">允許建立群組的群組成員</span><span class="sxs-lookup"><span data-stu-id="deb2a-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="deb2a-132">如需如何指派 Azure 授權的詳細資訊，請參閱[指派或移除 Azure Active Directory 入口網站中的授權](/azure/active-directory/fundamentals/license-users-groups)。</span><span class="sxs-lookup"><span data-stu-id="deb2a-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="deb2a-133">下列人員不需要指派 Azure AD 進階版或 Azure AD 基本 EDU 授權給它們：</span><span class="sxs-lookup"><span data-stu-id="deb2a-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="deb2a-134">屬於 Microsoft 365 群組成員的人員，以及沒有建立其他群組的能力。</span><span class="sxs-lookup"><span data-stu-id="deb2a-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="deb2a-135">步驟1：為需要建立 Microsoft 365 群組的使用者建立群組</span><span class="sxs-lookup"><span data-stu-id="deb2a-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="deb2a-136">您組織中只有一個群組可以用來控制誰可以建立群組。</span><span class="sxs-lookup"><span data-stu-id="deb2a-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="deb2a-137">不過，您可以將其他群組嵌套為此群組的成員。</span><span class="sxs-lookup"><span data-stu-id="deb2a-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="deb2a-138">以上所列角色中的系統管理員不需要是此群組的成員：他們保留其建立群組的能力。</span><span class="sxs-lookup"><span data-stu-id="deb2a-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="deb2a-139">在系統管理中心中，移至 [ [群組] 頁面](https://admin.microsoft.com/adminportal/home#/groups)。</span><span class="sxs-lookup"><span data-stu-id="deb2a-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="deb2a-140">按一下 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="deb2a-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="deb2a-141">選擇您想要的群組類型。</span><span class="sxs-lookup"><span data-stu-id="deb2a-141">Choose the group type you want.</span></span> <span data-ttu-id="deb2a-142">請記下群組名稱！</span><span class="sxs-lookup"><span data-stu-id="deb2a-142">Remember the name of the group!</span></span> <span data-ttu-id="deb2a-143">以便後續步驟使用。</span><span class="sxs-lookup"><span data-stu-id="deb2a-143">You'll need it later.</span></span>

4. <span data-ttu-id="deb2a-144">完成設定群組，新增您想要在您的組織中建立群組的人員或其他群組。</span><span class="sxs-lookup"><span data-stu-id="deb2a-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="deb2a-145">如需詳細指示，請參閱[建立、編輯或刪除安全性群組的 Microsoft 365 系統管理中心](../admin/email/create-edit-or-delete-a-security-group.md)。</span><span class="sxs-lookup"><span data-stu-id="deb2a-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="deb2a-146">步驟 2：執行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="deb2a-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="deb2a-147">您必須使用 Azure Active Directory 的預覽版本 [PowerShell Graph (AzureAD](/powershell/azure/active-directory/install-adv2))  (模組名稱 **AzureADPreview**) ，以變更群組層級來賓存取設定：</span><span class="sxs-lookup"><span data-stu-id="deb2a-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="deb2a-148">如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)，並遵循指示來安裝公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="deb2a-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="deb2a-149">如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。</span><span class="sxs-lookup"><span data-stu-id="deb2a-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="deb2a-150">如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。</span><span class="sxs-lookup"><span data-stu-id="deb2a-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="deb2a-151">將下列腳本複製到文字編輯器，例如記事本或[Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)。</span><span class="sxs-lookup"><span data-stu-id="deb2a-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="deb2a-152">*\<GroupName\>* 以您建立的群組名稱取代。</span><span class="sxs-lookup"><span data-stu-id="deb2a-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="deb2a-153">例如：</span><span class="sxs-lookup"><span data-stu-id="deb2a-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="deb2a-154">將檔案儲存為 GroupCreators.ps1。</span><span class="sxs-lookup"><span data-stu-id="deb2a-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="deb2a-155">在 [PowerShell] 視窗中，流覽至您儲存檔案的位置， (輸入 "CD <FileLocation> " ) 。</span><span class="sxs-lookup"><span data-stu-id="deb2a-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="deb2a-156">輸入下列命令以執行腳本：</span><span class="sxs-lookup"><span data-stu-id="deb2a-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="deb2a-157">系統提示時，請 [使用系統管理員帳戶登入](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) 。</span><span class="sxs-lookup"><span data-stu-id="deb2a-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

<span data-ttu-id="deb2a-158">腳本的最後一行會顯示更新的設定：</span><span class="sxs-lookup"><span data-stu-id="deb2a-158">The last line of the script will display the updated settings:</span></span>

![PowerShell 腳本輸出的螢幕擷取畫面。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="deb2a-160">如果您想要變更所使用的群組，您可以使用新群組的名稱重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="deb2a-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="deb2a-161">如果您想關閉群組建立限制，並再次允許所有使用者建立群組，請將 $GroupName 設定為 ""，並 $AllowGroupCreation 為 "True"，然後重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="deb2a-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="deb2a-162">步驟 3：驗證命令能正常運作</span><span class="sxs-lookup"><span data-stu-id="deb2a-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="deb2a-163">變更可能需要30分鐘以上的時間才會生效。</span><span class="sxs-lookup"><span data-stu-id="deb2a-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="deb2a-164">您可以執行下列動作來驗證新的設定：</span><span class="sxs-lookup"><span data-stu-id="deb2a-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="deb2a-165">使用不具備建立群組功能之人員的使用者帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="deb2a-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="deb2a-166">也就是說，它們不是您所建立之群組的成員，或是管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="deb2a-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="deb2a-167">選取 [ **Planner** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="deb2a-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="deb2a-168">在 Planner 中，選取左側導覽中的 [ **新增方案** ]，以建立計畫。</span><span class="sxs-lookup"><span data-stu-id="deb2a-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="deb2a-169">您應該會收到一則停用計畫和群組建立的訊息。</span><span class="sxs-lookup"><span data-stu-id="deb2a-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="deb2a-170">請使用群組的成員重新嘗試相同的程式。</span><span class="sxs-lookup"><span data-stu-id="deb2a-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="deb2a-171">[！注意] 如果群組的成員無法建立群組，請檢查未透過 [OWA 信箱原則](/powershell/module/exchange/set-owamailboxpolicy)封鎖這些群組。</span><span class="sxs-lookup"><span data-stu-id="deb2a-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="deb2a-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="deb2a-172">Related topics</span></span>

[<span data-ttu-id="deb2a-173">共同作業管理規劃逐步</span><span class="sxs-lookup"><span data-stu-id="deb2a-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="deb2a-174">建立共同作業管理計畫</span><span class="sxs-lookup"><span data-stu-id="deb2a-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="deb2a-175">開始使用 Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="deb2a-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="deb2a-176">在 Azure Active Directory 中設定自助群組管理</span><span class="sxs-lookup"><span data-stu-id="deb2a-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="deb2a-177">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="deb2a-177">Set-ExecutionPolicy</span></span>](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="deb2a-178">用於設定群組設定的 Azure Active Directory Cmdlet</span><span class="sxs-lookup"><span data-stu-id="deb2a-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
