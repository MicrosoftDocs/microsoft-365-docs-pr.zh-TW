---
title: 以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/13/2020
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: 26b9ff81-93b0-4251-beaf-3c9f1d7c80c8
description: 瞭解如何使用 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組。
ms.openlocfilehash: d3745b9365c67615efe32881408d1a717b8dbbed
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371533"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="89955-103">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="89955-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="89955-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="89955-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="89955-105">Microsoft 365 管理員需要管理使用者帳戶、授權和群組。</span><span class="sxs-lookup"><span data-stu-id="89955-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="89955-106">雖然您可以在 Microsoft 365 系統管理中心內執行大部分工作，但在 PowerShell 中，有些工作會比較容易。</span><span class="sxs-lookup"><span data-stu-id="89955-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="89955-107">如需詳細資訊，請參閱下列文章。</span><span class="sxs-lookup"><span data-stu-id="89955-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="89955-108">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89955-108">User accounts</span></span>

- [<span data-ttu-id="89955-109">建立使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89955-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-110">檢視使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89955-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-111">設定使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="89955-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-112">指派角色給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89955-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-113">刪除和還原使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89955-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-114">封鎖使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89955-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-115">密碼</span><span class="sxs-lookup"><span data-stu-id="89955-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="89955-116">授權與服務</span><span class="sxs-lookup"><span data-stu-id="89955-116">Licenses and services</span></span>
- [<span data-ttu-id="89955-117">檢視授權與服務</span><span class="sxs-lookup"><span data-stu-id="89955-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-118">檢視授權和未授權使用者</span><span class="sxs-lookup"><span data-stu-id="89955-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-119">將授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="89955-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-120">檢視帳戶授權與服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="89955-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-121">停用服務存取權</span><span class="sxs-lookup"><span data-stu-id="89955-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="89955-122">停用 Sway 存取權</span><span class="sxs-lookup"><span data-stu-id="89955-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="89955-123">停用服務存取權，並指派使用者授權</span><span class="sxs-lookup"><span data-stu-id="89955-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="89955-124">從使用者帳戶移除授權</span><span class="sxs-lookup"><span data-stu-id="89955-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="89955-125">群組</span><span class="sxs-lookup"><span data-stu-id="89955-125">Groups</span></span>
- [<span data-ttu-id="89955-126">管理安全性群組</span><span class="sxs-lookup"><span data-stu-id="89955-126">Manage security groups</span></span>](manage-security-groups-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-127">維護安全性群組成員資格</span><span class="sxs-lookup"><span data-stu-id="89955-127">Maintain security group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="89955-128">管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="89955-128">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
