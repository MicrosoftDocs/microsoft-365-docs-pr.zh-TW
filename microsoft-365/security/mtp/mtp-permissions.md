---
title: 在 Microsoft 365 資訊安全中心管理 Microsoft 365 Defender 資料的存取權
description: 瞭解如何在 Microsoft 365 Defender 中管理資料的許可權
keywords: 存取權, 權限, MTP, Microsoft 威脅防護, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 進階威脅防護, 範圍, 約制, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930135"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="89b26-104">管理 Microsoft 365 Defender 的存取權</span><span class="sxs-lookup"><span data-stu-id="89b26-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="89b26-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="89b26-105">**Applies to:**</span></span>
- <span data-ttu-id="89b26-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="89b26-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="89b26-107">指派有下列 Azure Active Directory 帳戶 (AD) 角色可以存取 Microsoft 365 Defender 功能和資料：</span><span class="sxs-lookup"><span data-stu-id="89b26-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="89b26-108">全域管理員</span><span class="sxs-lookup"><span data-stu-id="89b26-108">Global administrator</span></span>
- <span data-ttu-id="89b26-109">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="89b26-109">Security administrator</span></span>
- <span data-ttu-id="89b26-110">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="89b26-110">Security Operator</span></span>
- <span data-ttu-id="89b26-111">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="89b26-111">Global Reader</span></span>
- <span data-ttu-id="89b26-112">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="89b26-112">Security Reader</span></span>

<span data-ttu-id="89b26-113">若要檢閱具有這些角色的帳戶，請[在 Microsoft 365 安全性中心檢視權限](https://security.microsoft.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="89b26-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="89b26-114">存取功能</span><span class="sxs-lookup"><span data-stu-id="89b26-114">Access to functionality</span></span>
<span data-ttu-id="89b26-115">特定功能的存取權由您的 [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)決定。</span><span class="sxs-lookup"><span data-stu-id="89b26-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="89b26-116">如果您得存取需要為您或使用者群組指派新角色的特定功能，請與全域管理員連絡。</span><span class="sxs-lookup"><span data-stu-id="89b26-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="89b26-117">核准擱置的自動化工作</span><span class="sxs-lookup"><span data-stu-id="89b26-117">Approve pending automated tasks</span></span>
<span data-ttu-id="89b26-118">[自動化調查和補救](mtp-autoir-actions.md)可針對電子郵件、轉寄規則、檔案、持續性機制和調查期間找到的其他成品採取動作。</span><span class="sxs-lookup"><span data-stu-id="89b26-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="89b26-119">若要核准或拒絕需要明確核准的擱置中動作，您必須在 Microsoft 365 中指派特定角色。</span><span class="sxs-lookup"><span data-stu-id="89b26-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="89b26-120">若要深入瞭解，請參閱[重要訊息中心權限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="89b26-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="89b26-121">資料存取權</span><span class="sxs-lookup"><span data-stu-id="89b26-121">Access to data</span></span>
<span data-ttu-id="89b26-122">Microsoft 365 Defender 資料的存取權可以使用在 Microsoft Defender 中指派給使用者群組的範圍控制端點角色型存取控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="89b26-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="89b26-123">如果您的存取範圍尚未設定為端點的 Defender 中一組特定裝置，您將擁有 Microsoft 365 Defender 資料的完整存取權。</span><span class="sxs-lookup"><span data-stu-id="89b26-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="89b26-124">不過，一旦您的帳戶限定範圍設定完畢，就只會看到範圍內裝置的相關資料。</span><span class="sxs-lookup"><span data-stu-id="89b26-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="89b26-125">例如，如果您只屬於具有 Microsoft Defender 端點角色的一個使用者群組，而且該使用者群組僅取得銷售裝置的存取權限，您只會在 Microsoft 365 Defender 中看見銷售裝置的資料。</span><span class="sxs-lookup"><span data-stu-id="89b26-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="89b26-126">深入瞭解 Microsoft Defender for Endpoint 中的 RBAC 設定</span><span class="sxs-lookup"><span data-stu-id="89b26-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="89b26-127">Microsoft Cloud App Security 存取控制</span><span class="sxs-lookup"><span data-stu-id="89b26-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="89b26-128">在預覽期間，Microsoft 365 Defender 不會根據雲端 App 安全性設定強制執行存取控制。</span><span class="sxs-lookup"><span data-stu-id="89b26-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="89b26-129">存取 Microsoft 365 Defender 資料不受這些設定影響。</span><span class="sxs-lookup"><span data-stu-id="89b26-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="89b26-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="89b26-130">Related topics</span></span>

- [<span data-ttu-id="89b26-131">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="89b26-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="89b26-132">端點 RBAC 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="89b26-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="89b26-133">Cloud App Security 角色</span><span class="sxs-lookup"><span data-stu-id="89b26-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
