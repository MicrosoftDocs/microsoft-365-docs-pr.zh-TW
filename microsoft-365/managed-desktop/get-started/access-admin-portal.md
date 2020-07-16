---
title: 存取管理員入口網站
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b6310849f27200adbbcbcb1584903011fbdf6145
ms.sourcegitcommit: 9af890ef1b1c95bfc7cc52f7f4e395b62dc5263f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2020
ms.locfileid: "45146262"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="e7333-103">存取管理員入口網站</span><span class="sxs-lookup"><span data-stu-id="e7333-103">Access the admin portal</span></span>

<span data-ttu-id="e7333-104">您的 Microsoft Managed 桌面服務閘道是 Microsoft [Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="e7333-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="e7333-105">如需更多有關使用和自訂 Azure 入口網站體驗的詳細資訊，請參閱[azure 入口網站檔](https://docs.microsoft.com/azure/azure-portal/)。</span><span class="sxs-lookup"><span data-stu-id="e7333-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> 

<span data-ttu-id="e7333-106">您的管理帳戶需要特定許可權，才能存取 Microsoft 受管理的桌面系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="e7333-106">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="e7333-107">您可以使用角色型存取控制（RBAC）管理組織內這些功能的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="e7333-107">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="e7333-108">如需 Azure Active Directory 角色的詳細資訊，請參閱[在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="e7333-108">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="e7333-109">指派系統管理員使用者帳戶下列任何角色，以確保存取權：</span><span class="sxs-lookup"><span data-stu-id="e7333-109">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="e7333-110">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="e7333-110">Azure AD role</span></span>  |<span data-ttu-id="e7333-111">Microsoft 受管理的桌面許可權</span><span class="sxs-lookup"><span data-stu-id="e7333-111">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="e7333-112">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7333-112">Global Administrator</span></span>     | <span data-ttu-id="e7333-113">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。</span><span class="sxs-lookup"><span data-stu-id="e7333-113">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="e7333-114">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="e7333-114">Global Reader</span></span>     | <span data-ttu-id="e7333-115">具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的所有功能具有**唯讀許可權**。</span><span class="sxs-lookup"><span data-stu-id="e7333-115">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="e7333-116">Intune 服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7333-116">Intune Service Administrator</span></span>     |  <span data-ttu-id="e7333-117">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。</span><span class="sxs-lookup"><span data-stu-id="e7333-117">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="e7333-118">服務支援系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7333-118">Service Support Administrator</span></span>     | <span data-ttu-id="e7333-119">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。</span><span class="sxs-lookup"><span data-stu-id="e7333-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="e7333-120">只有全域系統管理員角色具有在 Microsoft Managed Desktop 中*註冊*您的組織所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="e7333-120">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="e7333-121">請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶的許可權。</span><span class="sxs-lookup"><span data-stu-id="e7333-121">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="e7333-122">在 Microsoft 受管理的桌面完成註冊後，您應該永遠使用該角色，以完成其他工作所需的*最低*許可權。</span><span class="sxs-lookup"><span data-stu-id="e7333-122">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="e7333-123">將角色指派給系統管理員</span><span class="sxs-lookup"><span data-stu-id="e7333-123">Assigning roles to administrators</span></span>

<span data-ttu-id="e7333-124">如果您需要協助指派 Azure Active Directory 角色，請參閱[在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="e7333-124">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
