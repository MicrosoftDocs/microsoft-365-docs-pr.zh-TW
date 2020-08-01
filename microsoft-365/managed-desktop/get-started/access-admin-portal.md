---
title: 存取系統管理入口網站
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: 420cdaabb607eacf0d7a7109827fe5437e2f999c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530220"
---
# <a name="access-the-admin-portal"></a><span data-ttu-id="b15d0-103">存取管理員入口網站</span><span class="sxs-lookup"><span data-stu-id="b15d0-103">Access the admin portal</span></span>

<span data-ttu-id="b15d0-104">您的 Microsoft Managed 桌面服務閘道是 Microsoft [Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="b15d0-104">Your gateway to the Microsoft Managed Desktop service is the Microsoft [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="b15d0-105">如需更多有關使用和自訂 Azure 入口網站體驗的詳細資訊，請參閱[azure 入口網站檔](https://docs.microsoft.com/azure/azure-portal/)。</span><span class="sxs-lookup"><span data-stu-id="b15d0-105">For more about using and customizing your Azure portal experience generally, see the [Azure portal documentation](https://docs.microsoft.com/azure/azure-portal/).</span></span> <span data-ttu-id="b15d0-106">可用於預覽現在，您也可以在[Microsoft 端點管理員](https://endpoint.microsoft.com/)中找到 Microsoft 受管理的桌面。</span><span class="sxs-lookup"><span data-stu-id="b15d0-106">Available in preview now, you can also find Microsoft Managed Desktop in the [Microsoft Endpoint Manager](https://endpoint.microsoft.com/).</span></span> <span data-ttu-id="b15d0-107">如果您不熟悉此入口網站的裝置管理功能，請參閱[Microsoft 端點管理員的檔](https://docs.microsoft.com/mem/)。</span><span class="sxs-lookup"><span data-stu-id="b15d0-107">If you are unfamiliar with the capabilities of this portal for device management see the [Microsoft Endpoint Manager documentation](https://docs.microsoft.com/mem/).</span></span>

<span data-ttu-id="b15d0-108">您的管理帳戶需要特定許可權，才能存取 Microsoft 受管理的桌面系統管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="b15d0-108">Your administrative account needs specific permissions in order to access the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="b15d0-109">您可以使用角色型存取控制（RBAC）管理組織內這些功能的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="b15d0-109">You can manage admin access to these features within your organization by using Role-based Access Control (RBAC).</span></span> <span data-ttu-id="b15d0-110">如需 Azure Active Directory 角色的詳細資訊，請參閱[在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="b15d0-110">For more information about Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

<span data-ttu-id="b15d0-111">指派系統管理員使用者帳戶下列任何角色，以確保存取權：</span><span class="sxs-lookup"><span data-stu-id="b15d0-111">Assign your admin user accounts any of the following roles to ensure access:</span></span>

|<span data-ttu-id="b15d0-112">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="b15d0-112">Azure AD role</span></span>  |<span data-ttu-id="b15d0-113">Microsoft 受管理的桌面許可權</span><span class="sxs-lookup"><span data-stu-id="b15d0-113">Microsoft Managed Desktop permissions</span></span>  |
|---------|---------|
|<span data-ttu-id="b15d0-114">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="b15d0-114">Global Administrator</span></span>     | <span data-ttu-id="b15d0-115">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。</span><span class="sxs-lookup"><span data-stu-id="b15d0-115">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="b15d0-116">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="b15d0-116">Global Reader</span></span>     | <span data-ttu-id="b15d0-117">具有此角色的系統管理員對 Microsoft Managed Desktop Admin 入口網站中的所有功能具有**唯讀許可權**。</span><span class="sxs-lookup"><span data-stu-id="b15d0-117">Admins with this role will have **read-only permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |
|<span data-ttu-id="b15d0-118">Intune 服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="b15d0-118">Intune Service Administrator</span></span>     |  <span data-ttu-id="b15d0-119">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。</span><span class="sxs-lookup"><span data-stu-id="b15d0-119">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>       |
|<span data-ttu-id="b15d0-120">服務支援系統管理員</span><span class="sxs-lookup"><span data-stu-id="b15d0-120">Service Support Administrator</span></span>     | <span data-ttu-id="b15d0-121">具有此角色的系統管理員具有 Microsoft Managed Desktop Admin 入口網站中所有功能的**讀取和寫入權限**。</span><span class="sxs-lookup"><span data-stu-id="b15d0-121">Admins with this role will have **read and write permissions** to all features in the Microsoft Managed Desktop Admin portal.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="b15d0-122">只有全域系統管理員角色具有在 Microsoft Managed Desktop 中*註冊*您的組織所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="b15d0-122">Only the Global Administrator role has the necessary permissions to *enroll* your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="b15d0-123">請注意，Azure Active Directory 角色將會在各種 Microsoft 服務中提供使用者帳戶的許可權。</span><span class="sxs-lookup"><span data-stu-id="b15d0-123">Be aware that Azure Active Directory roles will give user accounts privileges across a variety of Microsoft services.</span></span> <span data-ttu-id="b15d0-124">在 Microsoft 受管理的桌面完成註冊後，您應該永遠使用該角色，以完成其他工作所需的*最低*許可權。</span><span class="sxs-lookup"><span data-stu-id="b15d0-124">After completing enrollment with Microsoft Managed Desktop, you should always use the role with the *least* privileges necessary to accomplish your other tasks.</span></span>

## <a name="assigning-roles-to-administrators"></a><span data-ttu-id="b15d0-125">將角色指派給系統管理員</span><span class="sxs-lookup"><span data-stu-id="b15d0-125">Assigning roles to administrators</span></span>

<span data-ttu-id="b15d0-126">如果您需要協助指派 Azure Active Directory 角色，請參閱[在 Azure Active directory 中的系統管理員角色許可權](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="b15d0-126">If you need help assigning Azure Active Directory roles, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>
