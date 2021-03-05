---
title: 在 Microsoft 365 群組中管理來賓存取
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 瞭解如何將來賓新增至 Microsoft 365 群組、查看來賓使用者，以及使用 PowerShell 來控制來賓存取。
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453654"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="cc548-103">在 Microsoft 365 群組中管理來賓存取</span><span class="sxs-lookup"><span data-stu-id="cc548-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="cc548-104">根據預設，針對您的組織開啟來賓存取權 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="cc548-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="cc548-105">系統管理員可以控制是否允許來賓存取整個組織或個別群組的群組。</span><span class="sxs-lookup"><span data-stu-id="cc548-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="cc548-106">當其開啟時，群組成員可以透過網頁上的 Outlook 邀請來賓使用者加入 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="cc548-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="cc548-107">邀請會傳送給群組擁有者以供核准。</span><span class="sxs-lookup"><span data-stu-id="cc548-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="cc548-108">一旦核准，就會將來賓使用者新增至目錄和群組。</span><span class="sxs-lookup"><span data-stu-id="cc548-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="cc548-109">處於原生模式或 [歐盟地理](https://go.microsoft.com/fwlink/?linkid=2107357) 位置的 Yammer Enterprise 網路不支援網路來賓。</span><span class="sxs-lookup"><span data-stu-id="cc548-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="cc548-110">Microsoft 365 連線的 Yammer 群組目前不支援來賓存取，但您可以在 Yammer 網路中建立未連線的外部群組。</span><span class="sxs-lookup"><span data-stu-id="cc548-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="cc548-111">如需相關指示，請參閱 [建立及管理 Yammer 中的外部群組](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 。</span><span class="sxs-lookup"><span data-stu-id="cc548-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="cc548-112">群組中的來賓存取通常是用來包括 SharePoint 或小組的更廣泛案例的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc548-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="cc548-113">這些服務有自己的來賓共用設定。</span><span class="sxs-lookup"><span data-stu-id="cc548-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="cc548-114">如需設定各群組、SharePoint 及小組之來賓共用的完整指示，請參閱：</span><span class="sxs-lookup"><span data-stu-id="cc548-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="cc548-115">在網站中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="cc548-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="cc548-116">在小組中與來賓共同作業</span><span class="sxs-lookup"><span data-stu-id="cc548-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="cc548-117">管理群組來賓存取</span><span class="sxs-lookup"><span data-stu-id="cc548-117">Manage groups guest access</span></span>

<span data-ttu-id="cc548-118">如果您想要啟用或停用群組中的「來賓存取」，您可以在 Microsoft 365 系統管理中心進行。</span><span class="sxs-lookup"><span data-stu-id="cc548-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="cc548-119">在系統管理中心中，移至 [ **顯示所有** \> **設定** \> 的 **組織設定** ]，然後在 [ **服務** ] 索引標籤上，選取 [ **Microsoft 365 群組**]。</span><span class="sxs-lookup"><span data-stu-id="cc548-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="cc548-120">在 [ **Microsoft 365 群組** ] 頁面上，選擇您是否要讓組織外部人員存取群組資源，或讓群組擁有者將組織外部人員新增至群組。</span><span class="sxs-lookup"><span data-stu-id="cc548-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="cc548-121">從系統管理中心新增來賓至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="cc548-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="cc548-122">如果您的目錄中已存在來賓，您可以從 Microsoft 365 系統管理中心將其新增至您的群組。</span><span class="sxs-lookup"><span data-stu-id="cc548-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="cc548-123">具有動態成員資格的 (群組必須 [在 Azure Active Directory 中管理](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule)。 ) </span><span class="sxs-lookup"><span data-stu-id="cc548-123">(Groups with dynamic membership must be [managed in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="cc548-124">在系統管理中心中，移至 [**群組**  >  **群組**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cc548-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="cc548-125">按一下您要新增來賓的群組，然後選取 [**成員**] 索引標籤上的 [**全部查看] 和 [管理成員**]。</span><span class="sxs-lookup"><span data-stu-id="cc548-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="cc548-126">選取 [ **新增成員**]，然後選擇您要新增的客人名稱。</span><span class="sxs-lookup"><span data-stu-id="cc548-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="cc548-127">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="cc548-127">Select **Save**.</span></span>

<span data-ttu-id="cc548-128">如果您想要直接將來賓新增至目錄，您可以 [在 azure 入口網站中新增 Azure Active directory B2B 協同作業使用者](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。</span><span class="sxs-lookup"><span data-stu-id="cc548-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="cc548-129">如果您想要編輯來賓的任何資訊，可以 [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="cc548-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="cc548-130">請參閱</span><span class="sxs-lookup"><span data-stu-id="cc548-130">See also</span></span>

[<span data-ttu-id="cc548-131">從特定群組封鎖來賓使用者</span><span class="sxs-lookup"><span data-stu-id="cc548-131">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="cc548-132">管理 Microsoft 365 系統管理中心中的群組成員資格</span><span class="sxs-lookup"><span data-stu-id="cc548-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="cc548-133">Azure Active Directory 存取評論</span><span class="sxs-lookup"><span data-stu-id="cc548-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="cc548-134">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="cc548-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
