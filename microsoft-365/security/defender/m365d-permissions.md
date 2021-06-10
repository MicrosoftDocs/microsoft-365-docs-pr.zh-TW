---
title: 管理 Microsoft 365 security center 中 Microsoft 365 Defender 資料的存取權
description: 瞭解如何在 Microsoft 365 Defender 中管理資料的許可權
keywords: access、許可權、Microsoft 365 Defender、M365、security、MCAS、雲端 App 安全性、Microsoft Defender for 端點、範圍、範圍、RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 52e4e9fc8c73d1adca0c24c5bebb50f9dcf7ac6f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935626"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="b8821-104">使用 Azure Active Directory 通用角色管理 Microsoft 365 Defender 的存取權</span><span class="sxs-lookup"><span data-stu-id="b8821-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8821-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b8821-105">**Applies to:**</span></span>
- <span data-ttu-id="b8821-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8821-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b8821-107">有兩種方式可管理 Microsoft 365 Defender 的存取權</span><span class="sxs-lookup"><span data-stu-id="b8821-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="b8821-108">**全域 Azure Active Directory (AD) 角色**</span><span class="sxs-lookup"><span data-stu-id="b8821-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="b8821-109">**自訂角色存取**</span><span class="sxs-lookup"><span data-stu-id="b8821-109">**Custom role access**</span></span>

<span data-ttu-id="b8821-110">指派下列 **全域 Azure Active Directory 的帳戶 (AD) 角色** 可以存取 Microsoft 365 的 Defender 功能和資料：</span><span class="sxs-lookup"><span data-stu-id="b8821-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="b8821-111">全域管理員</span><span class="sxs-lookup"><span data-stu-id="b8821-111">Global administrator</span></span>
- <span data-ttu-id="b8821-112">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="b8821-112">Security administrator</span></span>
- <span data-ttu-id="b8821-113">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="b8821-113">Security Operator</span></span>
- <span data-ttu-id="b8821-114">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="b8821-114">Global Reader</span></span>
- <span data-ttu-id="b8821-115">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="b8821-115">Security Reader</span></span>

<span data-ttu-id="b8821-116">若要檢閱具有這些角色的帳戶，請[在 Microsoft 365 安全性中心檢視權限](https://security.microsoft.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="b8821-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="b8821-117">**自訂角色** 存取是 Microsoft 365 Defender 中的新功能，可讓您管理 Microsoft defender 365 中特定資料、工作及功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="b8821-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="b8821-118">自訂角色比全域 Azure AD 角色提供更多的控制權，只為使用者提供必要的存取權最低的角色。</span><span class="sxs-lookup"><span data-stu-id="b8821-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="b8821-119">除了全域 Azure AD 角色之外，還可以建立自訂角色。</span><span class="sxs-lookup"><span data-stu-id="b8821-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="b8821-120">[深入瞭解自訂角色](custom-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b8821-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="b8821-121">!記本文僅適用于管理全域 Azure Active Directory 角色。</span><span class="sxs-lookup"><span data-stu-id="b8821-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="b8821-122">如需使用自訂角色型存取控制的詳細資訊，請參閱 [自訂角色的自訂角色的存取控制](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="b8821-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="b8821-123">存取功能</span><span class="sxs-lookup"><span data-stu-id="b8821-123">Access to functionality</span></span>
<span data-ttu-id="b8821-124">特定功能的存取權由您的 [Azure AD 角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)決定。</span><span class="sxs-lookup"><span data-stu-id="b8821-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="b8821-125">如果您得存取需要為您或使用者群組指派新角色的特定功能，請與全域管理員連絡。</span><span class="sxs-lookup"><span data-stu-id="b8821-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="b8821-126">核准擱置的自動化工作</span><span class="sxs-lookup"><span data-stu-id="b8821-126">Approve pending automated tasks</span></span>
<span data-ttu-id="b8821-127">[自動化調查和補救](m365d-autoir-actions.md)可針對電子郵件、轉寄規則、檔案、持續性機制和調查期間找到的其他成品採取動作。</span><span class="sxs-lookup"><span data-stu-id="b8821-127">[Automated investigation and remediation](m365d-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="b8821-128">若要核准或拒絕需要明確核准的擱置中動作，您必須在 Microsoft 365 中指派特定角色。</span><span class="sxs-lookup"><span data-stu-id="b8821-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="b8821-129">若要深入瞭解，請參閱[重要訊息中心權限](m365d-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="b8821-129">To learn more, see [Action center permissions](m365d-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="b8821-130">資料存取權</span><span class="sxs-lookup"><span data-stu-id="b8821-130">Access to data</span></span>
<span data-ttu-id="b8821-131">您可以使用指派給 Microsoft defender 中使用者群組的範圍來控制對 Microsoft 365 defender 資料的存取，以用於以端點角色為基礎的存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="b8821-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="b8821-132">如果您的存取未限定在 Defender for Endpoint 中的特定裝置集，您就可以完全存取 Microsoft 365 defender 中的資料。</span><span class="sxs-lookup"><span data-stu-id="b8821-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="b8821-133">不過，一旦您的帳戶限定範圍設定完畢，就只會看到範圍內裝置的相關資料。</span><span class="sxs-lookup"><span data-stu-id="b8821-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="b8821-134">例如，如果您只隸屬于一個具有 Microsoft Defender for Endpoint role 的使用者群組，且該使用者群組已獲得對銷售裝置的存取權，您只會看到 Microsoft 365 Defender 中的銷售裝置相關資料。</span><span class="sxs-lookup"><span data-stu-id="b8821-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="b8821-135">深入瞭解 Microsoft Defender for Endpoint 中的 RBAC 設定</span><span class="sxs-lookup"><span data-stu-id="b8821-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="b8821-136">Microsoft Cloud App Security 存取控制</span><span class="sxs-lookup"><span data-stu-id="b8821-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="b8821-137">在預覽期間，Microsoft 365 Defender 不會根據雲端 App 安全性設定來強制執行存取控制。</span><span class="sxs-lookup"><span data-stu-id="b8821-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="b8821-138">這些設定不會影響 Microsoft 365 Defender 資料的存取。</span><span class="sxs-lookup"><span data-stu-id="b8821-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b8821-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="b8821-139">Related topics</span></span>
- [<span data-ttu-id="b8821-140">Microsoft 365 Defender 的角色型存取控制中的自訂角色</span><span class="sxs-lookup"><span data-stu-id="b8821-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="b8821-141">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="b8821-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="b8821-142">Microsoft Defender for Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="b8821-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="b8821-143">Cloud App Security 角色</span><span class="sxs-lookup"><span data-stu-id="b8821-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)