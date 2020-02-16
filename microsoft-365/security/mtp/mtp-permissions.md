---
title: 管理 Microsoft 365 安全性中心的 Microsoft 威脅防護資料的存取權
description: 了解如何在 Microsoft 威脅防護中管理資料的權限
keywords: 存取權, 權限, MTP, Microsoft 威脅防護, M365, 安全性, MCAS, MDATP, Cloud App Security, Microsoft Defender 進階威脅防護, 範圍, 約制, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1b6411d04c2ecc8c646072e4da61dea1c470db5a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086972"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="bcee3-104">管理 Microsoft 威脅防護的存取權</span><span class="sxs-lookup"><span data-stu-id="bcee3-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="bcee3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bcee3-105">**Applies to:**</span></span>
- <span data-ttu-id="bcee3-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="bcee3-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="bcee3-107">指派下列 Azure Active Directory (AD) 角色的帳戶可存取 Microsoft 威脅防護功能和資料：</span><span class="sxs-lookup"><span data-stu-id="bcee3-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="bcee3-108">全域管理員</span><span class="sxs-lookup"><span data-stu-id="bcee3-108">Global administrator</span></span>
- <span data-ttu-id="bcee3-109">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="bcee3-109">Security administrator</span></span>
- <span data-ttu-id="bcee3-110">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="bcee3-110">Security Operator</span></span>
- <span data-ttu-id="bcee3-111">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="bcee3-111">Global Reader</span></span>
- <span data-ttu-id="bcee3-112">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="bcee3-112">Security Reader</span></span>

<span data-ttu-id="bcee3-113">若要檢閱具有這些角色的帳戶，請[在 Microsoft 365 安全性中心檢視權限](https://security.microsoft.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="bcee3-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="bcee3-114">存取功能</span><span class="sxs-lookup"><span data-stu-id="bcee3-114">Access to functionality</span></span>
<span data-ttu-id="bcee3-115">特定功能的存取權由您的 [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)決定。</span><span class="sxs-lookup"><span data-stu-id="bcee3-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="bcee3-116">如果您得存取需要為您或使用者群組指派新角色的特定功能，請與全域管理員連絡。</span><span class="sxs-lookup"><span data-stu-id="bcee3-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="bcee3-117">核准擱置的自動化工作</span><span class="sxs-lookup"><span data-stu-id="bcee3-117">Approve pending automated tasks</span></span>
<span data-ttu-id="bcee3-118">[自動化調查和補救](mtp-autoir-actions.md)可針對電子郵件、轉寄規則、檔案、持續性機制和調查期間找到的其他成品採取動作。</span><span class="sxs-lookup"><span data-stu-id="bcee3-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="bcee3-119">若要核准或拒絕需要明確核准的擱置中動作，您必須在 Microsoft 365 中指派特定角色。</span><span class="sxs-lookup"><span data-stu-id="bcee3-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="bcee3-120">若要深入瞭解，請參閱[重要訊息中心權限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="bcee3-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="bcee3-121">資料存取權</span><span class="sxs-lookup"><span data-stu-id="bcee3-121">Access to data</span></span>
<span data-ttu-id="bcee3-122">存取 Microsoft 威脅防護資料可透過使用 Microsoft Defender ATP 角色型存取控制 (RBAC) 中指派給使用者群組的範圍加以控制。</span><span class="sxs-lookup"><span data-stu-id="bcee3-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="bcee3-123">如果您的存取權並未限定於 Microsoft Defender ATP 中的特定一組裝置，便能在 Microsoft 威脅防護完整存取資料。</span><span class="sxs-lookup"><span data-stu-id="bcee3-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="bcee3-124">不過，一旦您的帳戶限定範圍設定完畢，就只會看到範圍內裝置的相關資料。</span><span class="sxs-lookup"><span data-stu-id="bcee3-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="bcee3-125">例如，如果您只屬於具有一個 Microsoft Defender ATP 角色的單一使用者群組，且該使用者群組僅獲授權存取銷售裝置，您便只會在 Microsoft 威脅防護中看到銷售裝置的相關資料。</span><span class="sxs-lookup"><span data-stu-id="bcee3-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="bcee3-126">深入了解 Microsoft Defender ATP 中的 RBAC 設定</span><span class="sxs-lookup"><span data-stu-id="bcee3-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="bcee3-127">Microsoft Cloud App Security 存取控制</span><span class="sxs-lookup"><span data-stu-id="bcee3-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="bcee3-128">在預覽期間，Microsoft 威脅防護不會根據 Cloud App Security 設定強制執行存取控制。</span><span class="sxs-lookup"><span data-stu-id="bcee3-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="bcee3-129">這些設定不會影響存取 Microsoft 威脅防護資料。</span><span class="sxs-lookup"><span data-stu-id="bcee3-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bcee3-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="bcee3-130">Related topics</span></span>

- [<span data-ttu-id="bcee3-131">Azure AD 角色</span><span class="sxs-lookup"><span data-stu-id="bcee3-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="bcee3-132">Microsoft Defender ATP RBAC</span><span class="sxs-lookup"><span data-stu-id="bcee3-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="bcee3-133">Cloud App Security 角色</span><span class="sxs-lookup"><span data-stu-id="bcee3-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
