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
description: 瞭解如何使用 PowerShell 來管理 Microsoft 365 使用者帳戶、授權和群組。
ms.openlocfilehash: ec60fcfe3c3d2c0e26cb2cca6a56741067d154c0
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073122"
---
# <a name="manage-microsoft-365-user-accounts-licenses-and-groups-with-powershell"></a><span data-ttu-id="545d5-103">以 PowerShell 管理 Microsoft 365 使用者帳戶、授權和群組</span><span class="sxs-lookup"><span data-stu-id="545d5-103">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>

<span data-ttu-id="545d5-104">*本文適用於 Microsoft 365 企業版和 Office 365 企業版。*</span><span class="sxs-lookup"><span data-stu-id="545d5-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="545d5-105">Microsoft 365 管理員需要管理使用者帳戶、授權和群組。</span><span class="sxs-lookup"><span data-stu-id="545d5-105">Microsoft 365 administrators need to manage user accounts, licenses, and groups.</span></span> <span data-ttu-id="545d5-106">雖然您可以在 Microsoft 365 系統管理中心中執行大部分工作，但在 PowerShell 中，有些工作會比較容易。</span><span class="sxs-lookup"><span data-stu-id="545d5-106">Although you can do most of these tasks in the Microsoft 365 admin center, some are easier in PowerShell.</span></span>

<span data-ttu-id="545d5-107">如需詳細資訊，請參閱下列文章。</span><span class="sxs-lookup"><span data-stu-id="545d5-107">For more information, see the following articles.</span></span>

## <a name="user-accounts"></a><span data-ttu-id="545d5-108">使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="545d5-108">User accounts</span></span>

- [<span data-ttu-id="545d5-109">建立使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="545d5-109">Create user accounts</span></span>](create-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-110">檢視使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="545d5-110">View user accounts</span></span>](view-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-111">設定使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="545d5-111">Configure user account properties</span></span>](configure-user-account-properties-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-112">指派角色給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="545d5-112">Assign roles to user accounts</span></span>](assign-roles-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-113">刪除和還原使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="545d5-113">Delete and restore user accounts</span></span>](delete-and-restore-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-114">封鎖使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="545d5-114">Block user accounts</span></span>](block-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-115">密碼</span><span class="sxs-lookup"><span data-stu-id="545d5-115">Passwords</span></span>](manage-passwords-with-microsoft-365-powershell.md)

## <a name="licenses-and-services"></a><span data-ttu-id="545d5-116">授權與服務</span><span class="sxs-lookup"><span data-stu-id="545d5-116">Licenses and services</span></span>
- [<span data-ttu-id="545d5-117">檢視授權與服務</span><span class="sxs-lookup"><span data-stu-id="545d5-117">View licenses and services</span></span>](view-licenses-and-services-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-118">檢視授權和未授權使用者</span><span class="sxs-lookup"><span data-stu-id="545d5-118">View licensed and unlicensed users</span></span>](view-licensed-and-unlicensed-users-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-119">將授權指派給使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="545d5-119">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-120">檢視帳戶授權與服務詳細資料</span><span class="sxs-lookup"><span data-stu-id="545d5-120">View account license and service details</span></span>](view-account-license-and-service-details-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-121">停用服務存取權</span><span class="sxs-lookup"><span data-stu-id="545d5-121">Disable access to services</span></span>](disable-access-to-services-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="545d5-122">停用 Sway 存取權</span><span class="sxs-lookup"><span data-stu-id="545d5-122">Disable access to Sway</span></span>](disable-access-to-sway-with-microsoft-365-powershell.md)
  - [<span data-ttu-id="545d5-123">停用服務存取權，並指派使用者授權</span><span class="sxs-lookup"><span data-stu-id="545d5-123">Disable access to services while assigning user licenses</span></span>](disable-access-to-services-while-assigning-user-licenses.md)
- [<span data-ttu-id="545d5-124">從使用者帳戶移除授權</span><span class="sxs-lookup"><span data-stu-id="545d5-124">Remove licenses from user accounts</span></span>](remove-licenses-from-user-accounts-with-microsoft-365-powershell.md)

## <a name="groups"></a><span data-ttu-id="545d5-125">群組</span><span class="sxs-lookup"><span data-stu-id="545d5-125">Groups</span></span>
- [<span data-ttu-id="545d5-126">維護群組成員資格</span><span class="sxs-lookup"><span data-stu-id="545d5-126">Maintain group membership</span></span>](maintain-group-membership-with-microsoft-365-powershell.md)
- [<span data-ttu-id="545d5-127">管理 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="545d5-127">Manage Microsoft 365 groups</span></span>](manage-microsoft-365-groups-with-powershell.md)
