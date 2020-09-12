---
title: 僅限 Microsoft 365 雲端身分識別
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/09/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 說明當您的 Microsoft 365 訂閱使用僅限雲端身分識別時，如何建立使用者和群組。
ms.openlocfilehash: 6ec727ea3648f1daa3af42763e5f497715b987a2
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547755"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="09b8a-103">僅限 Microsoft 365 雲端身分識別</span><span class="sxs-lookup"><span data-stu-id="09b8a-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="09b8a-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="09b8a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="09b8a-105">使用僅限雲端身分識別，所有的使用者、群組和連絡人都儲存在 Microsoft 365 訂閱的 Azure Active Directory (Azure AD) 租使用者中。</span><span class="sxs-lookup"><span data-stu-id="09b8a-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="09b8a-106">以下是僅限雲端身分識別的基本元件。</span><span class="sxs-lookup"><span data-stu-id="09b8a-106">Here are the basic components of cloud-only identity.</span></span>
 
![僅限雲端身分識別的基本元件](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="09b8a-108">組織中的使用者和他們的使用者帳戶可以多種方式分類。</span><span class="sxs-lookup"><span data-stu-id="09b8a-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="09b8a-109">例如，有些員工是員工，且具有永久狀態。</span><span class="sxs-lookup"><span data-stu-id="09b8a-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="09b8a-110">有些是具有暫存檔狀態的廠商、合同工或合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="09b8a-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="09b8a-111">有些外部使用者沒有使用者帳戶，但仍然必須授與特定服務和資源的存取權，以支援互動和協同作業。</span><span class="sxs-lookup"><span data-stu-id="09b8a-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="09b8a-112">例如：</span><span class="sxs-lookup"><span data-stu-id="09b8a-112">For example:</span></span>

- <span data-ttu-id="09b8a-113">租用戶帳戶代表您為雲端服務授權之組織內的使用者</span><span class="sxs-lookup"><span data-stu-id="09b8a-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="09b8a-114">企業對企業 (B2B) 帳戶代表不屬於您邀請參與共同作業之組織的使用者</span><span class="sxs-lookup"><span data-stu-id="09b8a-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="09b8a-115">在您的組織中製作使用者類型的股份。</span><span class="sxs-lookup"><span data-stu-id="09b8a-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="09b8a-116">分組的群組為何？</span><span class="sxs-lookup"><span data-stu-id="09b8a-116">What are the groupings?</span></span> <span data-ttu-id="09b8a-117">例如，您可以將高層次的功能或目的群組的使用者群組為您的組織。</span><span class="sxs-lookup"><span data-stu-id="09b8a-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="09b8a-p104">此外，某些雲端服務可以與組織外的使用者共用，而不需使用任何使用者帳戶。您也必須識別使用者的這些群組。</span><span class="sxs-lookup"><span data-stu-id="09b8a-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="09b8a-120">您可以針對多種目的使用 Azure AD 中的群組，以簡化雲端環境的管理。</span><span class="sxs-lookup"><span data-stu-id="09b8a-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="09b8a-121">例如，使用 Azure AD 群組時，您可以：</span><span class="sxs-lookup"><span data-stu-id="09b8a-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="09b8a-122">使用以群組為基礎的授權，可在新增為成員時，自動將 Microsoft 365 的授權指派給您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="09b8a-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="09b8a-123">根據使用者帳戶屬性（例如部門名稱），以動態方式將使用者帳戶新增至特定群組。</span><span class="sxs-lookup"><span data-stu-id="09b8a-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="09b8a-124">自動將軟體的使用者布建為服務 (SaaS) 的應用程式，並使用多重要素驗證 (MFA) 和其他條件式存取原則，來保護這些應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="09b8a-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="09b8a-125">為 SharePoint Online 小組網站提供許可權和存取層級。</span><span class="sxs-lookup"><span data-stu-id="09b8a-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

<span data-ttu-id="09b8a-126">您可以使用下列方式建立新的 ***使用者*** ：</span><span class="sxs-lookup"><span data-stu-id="09b8a-126">You create new ***users*** with:</span></span>

- [<span data-ttu-id="09b8a-127">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="09b8a-127">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/add-users/add-users)
- [<span data-ttu-id="09b8a-128">適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="09b8a-128">PowerShell for Microsoft 365</span></span>](create-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="09b8a-129">您可以使用下列方式建立新的 ***群組*** ：</span><span class="sxs-lookup"><span data-stu-id="09b8a-129">You create new ***groups*** with:</span></span>

- [<span data-ttu-id="09b8a-130">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="09b8a-130">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/office365/admin/create-groups/create-groups)
- [<span data-ttu-id="09b8a-131">適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="09b8a-131">PowerShell for Microsoft 365</span></span>](manage-microsoft-365-groups-with-powershell.md)


## <a name="next-step-for-cloud-only-identity"></a><span data-ttu-id="09b8a-132">僅限雲端身分識別的下一個步驟</span><span class="sxs-lookup"><span data-stu-id="09b8a-132">Next step for cloud-only identity</span></span>

[<span data-ttu-id="09b8a-133">將授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="09b8a-133">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
