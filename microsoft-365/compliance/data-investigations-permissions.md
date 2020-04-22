---
title: 指派資料調查的許可權（預覽）
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明如何在 Microsoft 365 中設定使用「資料調查」工具所需的許可權。
ms.openlocfilehash: 47a7923d38cfa0ea3bad6c4c266f580f8104c429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637755"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="931be-103">指派資料調查的許可權（預覽）</span><span class="sxs-lookup"><span data-stu-id="931be-103">Assign permissions for Data Investigations (Preview)</span></span>

<span data-ttu-id="931be-104">若要存取 Office 365 或 Microsoft 365 規範中心的資料調查，您必須是「資料調查人員」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="931be-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="931be-105">若要將成員新增至角色群組，您必須是「組織管理」角色群組的成員，或是在 [安全性 & 規範中心] 中指派角色管理角色。</span><span class="sxs-lookup"><span data-stu-id="931be-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="931be-106">當使用者成為資料調查人員角色群組的成員後，他們就可以在您所屬的資料調查中建立、存取和進行調查。</span><span class="sxs-lookup"><span data-stu-id="931be-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="931be-107">若要指派資料調查許可權：</span><span class="sxs-lookup"><span data-stu-id="931be-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="931be-108">移至[https://protection.office.com](https://protection.office.com)並使用您組織中的系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="931be-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="931be-109">在 [安全性 & 規範中心] 中，按一下 [**許可權**]。</span><span class="sxs-lookup"><span data-stu-id="931be-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="931be-110">按一下 [**資料調查**人員] 角色群組，然後按一下彈出頁面上 [**成員**] 旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="931be-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="931be-111">按一下 **[選擇成員**]，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="931be-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="931be-112">選取您要新增為數據調查人員的使用者，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="931be-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="931be-113">在您新增所有使用者之後，按一下 [**完成**]，然後按一下 [**儲存**]，將變更儲存到角色群組。</span><span class="sxs-lookup"><span data-stu-id="931be-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="931be-114">指派給資料調查人員角色群組的資料調查管理角色，提供在 Office 365 或 Microsoft 365 規範中心存取「資料調查」工具所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="931be-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="931be-115">根據預設，此角色不會指派給「組織管理」角色群組，這表示您組織中的全域系統管理員可能無法存取「資料調查」工具（預設）。</span><span class="sxs-lookup"><span data-stu-id="931be-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="931be-116">若要修正此問題，您可以將全域系統管理員新增至資料調查人員角色群組，或將資料調查管理角色新增至組織管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="931be-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="931be-117">第三個選項是建立自訂角色群組，並指派「資料調查管理」角色（及其他角色），然後再新增適當的成員。</span><span class="sxs-lookup"><span data-stu-id="931be-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="931be-118">如需角色群組和角色的相關資訊，請參閱[安全性 & 合規性中心的許可權](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="931be-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
