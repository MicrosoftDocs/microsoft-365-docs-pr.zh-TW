---
title: 防止來賓加入特定群組
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 瞭解如何防止來賓新增至特定群組
ms.openlocfilehash: 572746a666586920ad85dafddbd78997940490d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907937"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="35373-103">防止客人新增至特定的 Microsoft 365 群組或 Microsoft 團隊小組</span><span class="sxs-lookup"><span data-stu-id="35373-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="35373-104">如果您想要允許來賓存取大多數群組和小組，但要讓某些地方禁止來賓存取，您可以封鎖個別群組和小組的「來賓存取」。</span><span class="sxs-lookup"><span data-stu-id="35373-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="35373-105"> (封鎖來賓存取權，可透過封鎖關聯群組的 guest 存取來完成。 ) 這會防止新增來賓，但不會移除群組或小組中已存在的客人。</span><span class="sxs-lookup"><span data-stu-id="35373-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="35373-106">如果您在組織中使用敏感度標籤，我們建議您在每個群組的基礎上使用敏感度標籤來控制訪客存取。</span><span class="sxs-lookup"><span data-stu-id="35373-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="35373-107">如需如何執行此動作的詳細資訊，請 [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="35373-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="35373-108">這是建議方式。</span><span class="sxs-lookup"><span data-stu-id="35373-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="35373-109">使用 Microsoft PowerShell 變更群組設定</span><span class="sxs-lookup"><span data-stu-id="35373-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="35373-110">您也可以使用 PowerShell，避免將新的客人加入個別群組。</span><span class="sxs-lookup"><span data-stu-id="35373-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="35373-111"> (請記住，小組關聯的 SharePoint 網站有 [個別的來賓共用控制](/sharepoint/change-external-sharing-site)。 ) </span><span class="sxs-lookup"><span data-stu-id="35373-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="35373-112">您必須使用預覽版本的 [Azure Active Directory PowerShell，以](/powershell/azure/active-directory/install-adv2) (模組名稱 **AzureADPreview**) 才能變更群組層級來賓存取設定：</span><span class="sxs-lookup"><span data-stu-id="35373-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="35373-113">如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)，並遵循指示來安裝公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="35373-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="35373-114">如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。</span><span class="sxs-lookup"><span data-stu-id="35373-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="35373-115">如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。</span><span class="sxs-lookup"><span data-stu-id="35373-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="35373-116">您必須具有全域系統管理員許可權，才可執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="35373-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="35373-117">執行下列腳本，將 */<GroupName/>* 其變更為您要封鎖來賓存取的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="35373-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="35373-118">若要驗證您的設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="35373-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="35373-119">驗證看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="35373-119">The verification looks like this:</span></span>
    
![顯示「來賓群組存取」已設定為 false PowerShell 視窗的螢幕擷取畫面。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="35373-121">根據網域允許或封鎖來賓存取</span><span class="sxs-lookup"><span data-stu-id="35373-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="35373-122">您可以允許或封鎖使用特定網域的客人。</span><span class="sxs-lookup"><span data-stu-id="35373-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="35373-123">例如，如果您的 business (Contoso) 與其他商務 (Fabrikam) 有合作關係，您可以將 Fabrikam 新增至您的允許清單，讓您的使用者可以將這些來賓新增至他們的群組。</span><span class="sxs-lookup"><span data-stu-id="35373-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="35373-124">如需詳細資訊，請參閱 [允許或封鎖從特定組織 B2B 使用者的邀請](/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="35373-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="35373-125">將客人新增至全域通訊清單</span><span class="sxs-lookup"><span data-stu-id="35373-125">Add guests to the global address list</span></span>

<span data-ttu-id="35373-126">根據預設，來賓在 Exchange 全域通訊清單中不會顯示。</span><span class="sxs-lookup"><span data-stu-id="35373-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="35373-127">使用下列步驟，讓來賓在全域通訊清單中可見。</span><span class="sxs-lookup"><span data-stu-id="35373-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="35373-128">執行下列動作，尋找訪客的 ObjectID：</span><span class="sxs-lookup"><span data-stu-id="35373-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="35373-129">然後，使用 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的適當值來執行下列各項。</span><span class="sxs-lookup"><span data-stu-id="35373-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="35373-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="35373-130">Related topics</span></span>

[<span data-ttu-id="35373-131">共同作業管理規劃逐步</span><span class="sxs-lookup"><span data-stu-id="35373-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="35373-132">建立共同作業管理計畫</span><span class="sxs-lookup"><span data-stu-id="35373-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="35373-133">管理 Microsoft 365 系統管理中心中的群組成員資格</span><span class="sxs-lookup"><span data-stu-id="35373-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="35373-134">Azure Active Directory 存取評論</span><span class="sxs-lookup"><span data-stu-id="35373-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="35373-135">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="35373-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)