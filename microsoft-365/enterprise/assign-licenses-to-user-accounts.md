---
title: 將 Microsoft 365 授權指派給使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: 說明如何將 Microsoft 365 授權指派給使用者帳戶（個別或根據群組成員資格）。
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051529"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="d7fff-103">將 Microsoft 365 授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="d7fff-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="d7fff-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="d7fff-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d7fff-105">針對僅限雲端的身分識別模型，您可以在建立使用者帳戶時，根據建立的方式，將 Microsoft 365 授權指派給他們。</span><span class="sxs-lookup"><span data-stu-id="d7fff-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="d7fff-106">針對混合式識別模型，當第一次同步處理 Active Directory 網域服務 (AD DS) 使用者帳戶時，將不會自動指派位置或 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="d7fff-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="d7fff-107">**您必須在指派授權之前或之前，設定每個使用者帳戶的使用者位置。**</span><span class="sxs-lookup"><span data-stu-id="d7fff-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="d7fff-108">在這兩種情況下，您必須指派授權給使用者帳戶，讓您的使用者能夠存取 Microsoft 365 服務，例如電子郵件和 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="d7fff-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="d7fff-109">您可以透過群組成員資格個別或自動將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d7fff-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="d7fff-110">若要將 Microsoft 365 授權指派給個別使用者帳戶，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="d7fff-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="d7fff-111">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d7fff-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="d7fff-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7fff-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="d7fff-113">Azure AD 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="d7fff-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="d7fff-114">群組型授權</span><span class="sxs-lookup"><span data-stu-id="d7fff-114">Group-based licensing</span></span>

<span data-ttu-id="d7fff-115">您可以在 Azure AD 中設定安全性群組，以自動將一組訂閱的授權指派給群組的所有成員。</span><span class="sxs-lookup"><span data-stu-id="d7fff-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="d7fff-116">這稱為 *群組型授權*。</span><span class="sxs-lookup"><span data-stu-id="d7fff-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="d7fff-117">如果在群組中新增或移除使用者帳戶，則將自動指派或從使用者帳戶中取消指派群組訂閱的授權。</span><span class="sxs-lookup"><span data-stu-id="d7fff-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="d7fff-118">請確定您有足夠的授權可供所有群組成員使用。</span><span class="sxs-lookup"><span data-stu-id="d7fff-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="d7fff-119">如果您用完了授權，除非有授權可供使用，否則將不會對新使用者指派授權。</span><span class="sxs-lookup"><span data-stu-id="d7fff-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="d7fff-120">您不應為包含 Azure 企業對企業 (B2B) 帳戶的群組設定以群組為基礎的授權。</span><span class="sxs-lookup"><span data-stu-id="d7fff-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="d7fff-121">如需更多 informaion，請參閱 [在 AZURE AD 中以群組為基礎的授權](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="d7fff-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7fff-122">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d7fff-122">Next steps</span></span>

<span data-ttu-id="d7fff-123">使用已獲指派授權的適當使用者帳戶集，您現在可以：</span><span class="sxs-lookup"><span data-stu-id="d7fff-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="d7fff-124">實施安全性</span><span class="sxs-lookup"><span data-stu-id="d7fff-124">Implement security</span></span>](../security/defender-365-security/security-roadmap.md)
- [<span data-ttu-id="d7fff-125">部署用戶端軟體，例如 Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="d7fff-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="d7fff-126">設定裝置管理</span><span class="sxs-lookup"><span data-stu-id="d7fff-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="d7fff-127">設定服務和應用程式</span><span class="sxs-lookup"><span data-stu-id="d7fff-127">Configure services and applications</span></span>](configure-services-and-applications.md)