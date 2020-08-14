---
title: 從特定群組封鎖來賓使用者
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 從特定群組封鎖來賓使用者
ms.openlocfilehash: 923a9e5cd09d232f377f55fd6a9f499f8f536a84
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662535"
---
# <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="fa7d0-103">從特定群組封鎖來賓使用者</span><span class="sxs-lookup"><span data-stu-id="fa7d0-103">Block guest users from a specific group</span></span>

<span data-ttu-id="fa7d0-104">如果您想要允許來賓存取大多數群組，但要讓某些地方禁止來賓存取，您可以封鎖個別群組的「來賓存取」。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-104">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups.</span></span>

<span data-ttu-id="fa7d0-105">如果您在組織中使用敏感度標籤，我們建議您在每個群組的基礎上使用敏感度標籤來控制訪客存取。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-105">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="fa7d0-106">如需如何執行此動作的詳細資訊，請 [使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-106">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="fa7d0-107">這是建議方式。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-107">This is the recommended approach.</span></span>

<span data-ttu-id="fa7d0-108">您也可以使用 Microsoft PowerShell，封鎖個別群組的 guest 存取權。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-108">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="fa7d0-109">您必須使用預覽版本的 [Azure Active Directory PowerShell，以](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (模組名稱 **AzureADPreview**) 才能變更群組層級來賓存取設定：</span><span class="sxs-lookup"><span data-stu-id="fa7d0-109">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="fa7d0-110">如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)，並遵循指示來安裝公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-110">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="fa7d0-111">如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-111">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="fa7d0-112">如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-112">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="fa7d0-113">您必須具有全域系統管理員許可權，才可執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-113">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="fa7d0-114">執行下列腳本，將 */<GroupName/>* 其變更為您要封鎖來賓存取的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-114">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="fa7d0-115">若要驗證您的設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fa7d0-115">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="fa7d0-116">驗證看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="fa7d0-116">The verification looks like this:</span></span>
    
![顯示「來賓群組存取」已設定為 false PowerShell 視窗的螢幕擷取畫面。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="fa7d0-118">根據網域允許或封鎖來賓存取</span><span class="sxs-lookup"><span data-stu-id="fa7d0-118">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="fa7d0-119">您可以允許或封鎖使用特定網域的來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-119">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="fa7d0-120">例如，如果您的 business (Contoso) 與其他商務 (Fabrikam) 有合作關係，您可以將 Fabrikam 新增至您的允許清單，讓您的使用者可以將這些來賓新增至他們的群組。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-120">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="fa7d0-121">如需詳細資訊，請參閱 [允許或封鎖從特定組織 B2B 使用者的邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-121">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="fa7d0-122">將客人新增至全域通訊清單</span><span class="sxs-lookup"><span data-stu-id="fa7d0-122">Add guests to the global address list</span></span>

<span data-ttu-id="fa7d0-123">根據預設，來賓在 Exchange 全域通訊清單中不會顯示。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-123">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="fa7d0-124">使用下列步驟，讓來賓在全域通訊清單中可見。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-124">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="fa7d0-125">執行下列動作，尋找來賓使用者的 ObjectID：</span><span class="sxs-lookup"><span data-stu-id="fa7d0-125">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="fa7d0-126">然後，使用 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的適當值來執行下列各項。</span><span class="sxs-lookup"><span data-stu-id="fa7d0-126">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="fa7d0-127">相關文章</span><span class="sxs-lookup"><span data-stu-id="fa7d0-127">Related articles</span></span>

[<span data-ttu-id="fa7d0-128">管理 Microsoft 365 系統管理中心中的群組成員資格</span><span class="sxs-lookup"><span data-stu-id="fa7d0-128">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="fa7d0-129">Azure Active Directory 存取評論</span><span class="sxs-lookup"><span data-stu-id="fa7d0-129">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="fa7d0-130">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="fa7d0-130">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)