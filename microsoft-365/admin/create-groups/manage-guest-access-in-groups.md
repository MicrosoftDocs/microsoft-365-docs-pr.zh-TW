---
title: 管理 Office 365 群組中的來賓存取
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 瞭解如何將來賓新增至 Office 365 群組、查看來賓使用者，以及使用 PowerShell 來控制來賓存取。
ms.openlocfilehash: e76718ccb20843b252c939be48653c61c7c1f0a9
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894500"
---
# <a name="manage-guest-access-in-office-365-groups"></a><span data-ttu-id="55b75-103">管理 Office 365 群組中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="55b75-103">Manage guest access in Office 365 Groups</span></span>

<span data-ttu-id="55b75-104">依預設，會為您的組織開啟 Office 365 群組的來賓存取。</span><span class="sxs-lookup"><span data-stu-id="55b75-104">By default, guest access for Office 365 groups is turned on for your organization.</span></span> <span data-ttu-id="55b75-105">系統管理員可以控制是否允許來賓存取整個組織或個別群組的群組。</span><span class="sxs-lookup"><span data-stu-id="55b75-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="55b75-106">當其開啟時，群組成員可以透過網頁上的 Outlook 邀請來賓使用者加入 Office 365 群組。</span><span class="sxs-lookup"><span data-stu-id="55b75-106">When it's turned on, group members can invite guest users to an Office 365 group through Outlook on Web.</span></span> <span data-ttu-id="55b75-107">邀請會傳送給群組擁有者以供核准。</span><span class="sxs-lookup"><span data-stu-id="55b75-107">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="55b75-108">處於原生模式或[歐盟地理](https://go.microsoft.com/fwlink/?linkid=2107357)位置的 Yammer Enterprise 網路不支援網路來賓。</span><span class="sxs-lookup"><span data-stu-id="55b75-108">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="55b75-109">Office 365 連線的 Yammer 群組目前不支援來賓存取，但您可以在 Yammer 網路中建立未連線的外部群組。</span><span class="sxs-lookup"><span data-stu-id="55b75-109">Office 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="55b75-110">如需相關指示，請參閱[建立及管理 Yammer 中的外部群組](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx)。</span><span class="sxs-lookup"><span data-stu-id="55b75-110">See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="55b75-111">編輯來賓資訊</span><span class="sxs-lookup"><span data-stu-id="55b75-111">Edit guest information</span></span>

<span data-ttu-id="55b75-112">一旦核准，就會將來賓使用者新增至目錄和群組。</span><span class="sxs-lookup"><span data-stu-id="55b75-112">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="55b75-113">群組中的來賓存取通常是用來包括 SharePoint 或小組的更廣泛案例的一部分。</span><span class="sxs-lookup"><span data-stu-id="55b75-113">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="55b75-114">這些服務有自己的來賓共用設定。</span><span class="sxs-lookup"><span data-stu-id="55b75-114">These services have their own guest sharing settings.</span></span> <span data-ttu-id="55b75-115">如需設定各群組、SharePoint 及小組之來賓共用的完整指示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="55b75-115">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="55b75-116">在網站中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="55b75-116">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="55b75-117">在小組中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="55b75-117">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="55b75-118">管理群組來賓存取</span><span class="sxs-lookup"><span data-stu-id="55b75-118">Manage groups guest access</span></span>

<span data-ttu-id="55b75-119">如果您想要啟用或停用群組中的「來賓存取」，您可以在 Microsoft 365 系統管理中心進行。</span><span class="sxs-lookup"><span data-stu-id="55b75-119">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="55b75-120">在系統管理中心中，移至 [**設定** \> ] **[設定]，然後選取**[ **Office 365 群組**]。</span><span class="sxs-lookup"><span data-stu-id="55b75-120">In the admin center, go to the **Settings** \> **Settings** and select **Office 365 Groups**.</span></span>
  
2. <span data-ttu-id="55b75-121">在 [ **Office 365 群組**] 頁面上，選擇您是否要讓組織外部人員存取群組資源，或讓群組擁有者將組織外部人員新增至群組。</span><span class="sxs-lookup"><span data-stu-id="55b75-121">On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a><span data-ttu-id="55b75-122">從系統管理中心新增來賓至 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="55b75-122">Add guests to an Office 365 group from the admin center</span></span>

<span data-ttu-id="55b75-123">如果您的目錄中已存在來賓，您可以從 Microsoft 365 系統管理中心將其新增至您的群組。</span><span class="sxs-lookup"><span data-stu-id="55b75-123">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="55b75-124">在系統管理中心中，移至 [**群組** > **群組**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="55b75-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="55b75-125">按一下您要新增來賓的群組，然後選取 [**成員**] 索引標籤上的 [**全部查看] 和 [管理成員**]。</span><span class="sxs-lookup"><span data-stu-id="55b75-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="55b75-126">選取 [**新增成員**]，然後選擇您要新增的客人名稱。</span><span class="sxs-lookup"><span data-stu-id="55b75-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="55b75-127">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55b75-127">Select **Save**.</span></span>

<span data-ttu-id="55b75-128">如果您想要直接將來賓新增至目錄，您可以[在 azure 入口網站中新增 Azure Active directory B2B 協同作業使用者](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。</span><span class="sxs-lookup"><span data-stu-id="55b75-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="55b75-129">如果您想要編輯來賓的任何資訊，可以[使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="55b75-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="55b75-130">從特定群組封鎖來賓使用者</span><span class="sxs-lookup"><span data-stu-id="55b75-130">Block guest users from a specific group</span></span>

<span data-ttu-id="55b75-131">如果您想要允許來賓存取大多數群組，但要讓某些地方禁止來賓存取，您可以使用 Microsoft PowerShell 封鎖個別群組的 guest 存取。</span><span class="sxs-lookup"><span data-stu-id="55b75-131">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="55b75-132">您必須使用預覽版本的 [ [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （模組名稱**AzureADPreview**）來變更群組層級來賓存取設定：</span><span class="sxs-lookup"><span data-stu-id="55b75-132">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="55b75-133">如果您之前尚未安裝任何版本的 Azure AD PowerShell 模組，請參閱[安裝 Azure AD 模組](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)，並遵循指示來安裝公開預覽版本。</span><span class="sxs-lookup"><span data-stu-id="55b75-133">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="55b75-134">如果您已安裝 Azure AD PowerShell 模組(AzureAD) 的通用版本 2.0，您必須先在 PowerShell 工作階段中執行 `Uninstall-Module AzureAD` 將其解除安裝，然後執行 `Install-Module AzureADPreview` 來安裝預覽版本。</span><span class="sxs-lookup"><span data-stu-id="55b75-134">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="55b75-135">如果您已安裝預覽版本，請執行 `Install-Module AzureADPreview` 以確定這是本模組的最新版本。</span><span class="sxs-lookup"><span data-stu-id="55b75-135">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="55b75-136">您必須具有全域系統管理員許可權，才可執行這些命令。</span><span class="sxs-lookup"><span data-stu-id="55b75-136">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="55b75-137">執行下列腳本，將其\* / \*變更為您要封鎖來賓存取的群組名稱。</span><span class="sxs-lookup"><span data-stu-id="55b75-137">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="55b75-138">若要驗證您的設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="55b75-138">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="55b75-139">驗證看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="55b75-139">The verification looks like this:</span></span>
    
![顯示「來賓群組存取」已設定為 false PowerShell 視窗的螢幕擷取畫面。](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="55b75-141">根據網域允許或封鎖來賓存取</span><span class="sxs-lookup"><span data-stu-id="55b75-141">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="55b75-142">您可以允許或封鎖使用特定網域的來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="55b75-142">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="55b75-143">例如，如果您的企業（Contoso）與另一部業務（Fabrikam）有合作關係，您可以將 Fabrikam 新增至您的允許清單，讓您的使用者可以將這些來賓新增至他們的群組。</span><span class="sxs-lookup"><span data-stu-id="55b75-143">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="55b75-144">如需詳細資訊，請參閱[允許或封鎖從特定組織 B2B 使用者的邀請](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="55b75-144">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="55b75-145">將客人新增至全域通訊清單</span><span class="sxs-lookup"><span data-stu-id="55b75-145">Add guests to the global address list</span></span>

<span data-ttu-id="55b75-146">根據預設，來賓在 Exchange 全域通訊清單中不會顯示。</span><span class="sxs-lookup"><span data-stu-id="55b75-146">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="55b75-147">使用下列步驟，讓來賓在全域通訊清單中可見。</span><span class="sxs-lookup"><span data-stu-id="55b75-147">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="55b75-148">執行下列動作，尋找來賓使用者的 ObjectID：</span><span class="sxs-lookup"><span data-stu-id="55b75-148">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="55b75-149">然後，使用 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的適當值來執行下列各項。</span><span class="sxs-lookup"><span data-stu-id="55b75-149">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="55b75-150">相關文章</span><span class="sxs-lookup"><span data-stu-id="55b75-150">Related articles</span></span>

[<span data-ttu-id="55b75-151">管理 Microsoft 365 系統管理中心中的群組成員資格</span><span class="sxs-lookup"><span data-stu-id="55b75-151">Manage Group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="55b75-152">Azure Active Directory 存取評論</span><span class="sxs-lookup"><span data-stu-id="55b75-152">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="55b75-153">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="55b75-153">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
