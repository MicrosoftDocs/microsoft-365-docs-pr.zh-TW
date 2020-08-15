---
title: 將 Microsoft 365 授權指派給使用者帳戶
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
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
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688301"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="f5ae1-103">將 Microsoft 365 授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="f5ae1-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="f5ae1-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="f5ae1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f5ae1-105">針對僅限雲端的身分識別模型，您可以根據建立的方式，將 Microsoft 365 授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f5ae1-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="f5ae1-106">針對混合式身分識別模型，當第一次同步處理 Active Directory 網域服務 (AD DS) 使用者帳戶時，系統不會自動將其指派給 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="f5ae1-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license.</span></span> <span data-ttu-id="f5ae1-107">您必須先設定使用者位置的每個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f5ae1-107">You must first configure each user account with a user location.</span></span>

<span data-ttu-id="f5ae1-108">在這兩種情況下，您必須指派授權給使用者帳戶，讓您的使用者能夠存取 Microsoft 365 服務，例如電子郵件和 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="f5ae1-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="f5ae1-109">您可以透過群組成員資格個別或自動將授權指派給使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f5ae1-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="f5ae1-110">若要將 Microsoft 365 授權指派給個別使用者帳戶，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="f5ae1-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="f5ae1-111">Microsoft 365 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="f5ae1-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="f5ae1-112">適用於 Microsoft 365 的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5ae1-112">PowerShell for Microsoft 365</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

<span data-ttu-id="f5ae1-113">若要進行自動授權指派，請參閱 [在 AZURE AD 中以群組為基礎的授權](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="f5ae1-113">For automatic license assignment, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5ae1-114">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f5ae1-114">Next steps</span></span>

<span data-ttu-id="f5ae1-115">透過已獲指派授權的完整使用者帳戶，您現在可以：</span><span class="sxs-lookup"><span data-stu-id="f5ae1-115">With the full set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="f5ae1-116">實施安全性</span><span class="sxs-lookup"><span data-stu-id="f5ae1-116">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="f5ae1-117">部署用戶端軟體，例如 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="f5ae1-117">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="f5ae1-118">在 Microsoft 365 中設定行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="f5ae1-118">Set up Mobile Device Management in Microsoft 365</span></span>](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [<span data-ttu-id="f5ae1-119">設定服務和應用程式</span><span class="sxs-lookup"><span data-stu-id="f5ae1-119">Configure services and applications</span></span>](configure-services-and-applications.md)
