---
title: 使用基本許可權來存取 Microsoft Defender 資訊安全中心
description: 瞭解如何使用基本許可權來存取 Microsoft Defender for Endpoint 入口網站。
keywords: 指派使用者角色、指派讀取和寫入權限、指派唯讀存取、使用者、使用者角色、角色
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2d022e903111c498d6f3b7411857748fcb637b64
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844655"
---
# <a name="use-basic-permissions-to-access-the-portal"></a><span data-ttu-id="7aaa1-104">使用基本權限存取入口網站</span><span class="sxs-lookup"><span data-stu-id="7aaa1-104">Use basic permissions to access the portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7aaa1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7aaa1-105">**Applies to:**</span></span>
- <span data-ttu-id="7aaa1-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7aaa1-106">Azure Active Directory</span></span>
- [<span data-ttu-id="7aaa1-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7aaa1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7aaa1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7aaa1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7aaa1-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="7aaa1-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7aaa1-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-basicaccess-abovefoldlink)

<span data-ttu-id="7aaa1-111">請參閱下列指示，以使用基本的版權管理。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-111">Refer to the instructions below to use basic permissions management.</span></span>

<span data-ttu-id="7aaa1-112">您可以使用下列任一種解決方案：</span><span class="sxs-lookup"><span data-stu-id="7aaa1-112">You can use either of the following solutions:</span></span>
- <span data-ttu-id="7aaa1-113">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7aaa1-113">Azure PowerShell</span></span>
- <span data-ttu-id="7aaa1-114">Azure 入口網站</span><span class="sxs-lookup"><span data-stu-id="7aaa1-114">Azure portal</span></span>

<span data-ttu-id="7aaa1-115">若要對許可權進行精細的控制，請 [切換至以角色為基礎的存取控制](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-115">For granular control over permissions, [switch to role-based access control](rbac.md).</span></span>

## <a name="assign-user-access-using-azure-powershell"></a><span data-ttu-id="7aaa1-116">使用 Azure PowerShell 指派使用者存取</span><span class="sxs-lookup"><span data-stu-id="7aaa1-116">Assign user access using Azure PowerShell</span></span>
<span data-ttu-id="7aaa1-117">您可以將下列其中一個許可權等級指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="7aaa1-117">You can assign users with one of the following levels of permissions:</span></span>
- <span data-ttu-id="7aaa1-118"> (讀寫) 的完整存取權</span><span class="sxs-lookup"><span data-stu-id="7aaa1-118">Full access (Read and Write)</span></span>
- <span data-ttu-id="7aaa1-119">唯讀存取權</span><span class="sxs-lookup"><span data-stu-id="7aaa1-119">Read-only access</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="7aaa1-120">開始之前</span><span class="sxs-lookup"><span data-stu-id="7aaa1-120">Before you begin</span></span>

- <span data-ttu-id="7aaa1-121">安裝 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-121">Install Azure PowerShell.</span></span> <span data-ttu-id="7aaa1-122">如需詳細資訊，請參閱[如何安裝和設定 Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/)。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-122">For more information, see, [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span><br>

    > [!NOTE]
    > <span data-ttu-id="7aaa1-123">您必須在已提升許可權的命令列中執行 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-123">You need to run the PowerShell cmdlets in an elevated command-line.</span></span>

- <span data-ttu-id="7aaa1-124">連線 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-124">Connect to your Azure Active Directory.</span></span> <span data-ttu-id="7aaa1-125">如需詳細資訊，請參閱[Connect-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-125">For more information, see [Connect-MsolService](/powershell/module/msonline/connect-msolservice?view=azureadps-1.0&preserve-view=true).</span></span>

<span data-ttu-id="7aaa1-126">**完全存取**</span><span class="sxs-lookup"><span data-stu-id="7aaa1-126">**Full access**</span></span> <br>
<span data-ttu-id="7aaa1-127">具有完整存取權的使用者可以登入、查看所有系統資訊及解決提醒、提交檔案進行深層分析，以及下載上架套件。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-127">Users with full access can log in, view all system information and resolve alerts, submit files for deep analysis, and download the onboarding package.</span></span>
<span data-ttu-id="7aaa1-128">指派「完整存取」許可權時，需要將使用者新增至「安全性管理員」或「全域系統管理員」 AAD 內建角色。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-128">Assigning full access rights requires adding the users to the "Security Administrator" or "Global Administrator" AAD built-in roles.</span></span>

<span data-ttu-id="7aaa1-129">**唯讀存取權**</span><span class="sxs-lookup"><span data-stu-id="7aaa1-129">**Read-only access**</span></span> <br>
<span data-ttu-id="7aaa1-130">具有唯讀存取權的使用者可以登入、查看所有警示和相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-130">Users with read-only access can log in, view all alerts, and related information.</span></span>
<span data-ttu-id="7aaa1-131">他們將無法變更警示狀態、提交檔案進行深入分析，或執行任何狀態變更作業。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-131">They will not be able to change alert states, submit files for deep analysis or perform any state changing operations.</span></span>
<span data-ttu-id="7aaa1-132">指派唯讀存取權限時，需要將使用者新增至「Security Reader」 Azure AD 內建角色。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-132">Assigning read-only access rights requires adding the users to the "Security Reader" Azure AD built-in role.</span></span>

<span data-ttu-id="7aaa1-133">使用下列步驟來指派安全性角色：</span><span class="sxs-lookup"><span data-stu-id="7aaa1-133">Use the following steps to assign security roles:</span></span>

- <span data-ttu-id="7aaa1-134">若要進行 **讀取和寫入** 存取，請使用下列命令，將使用者指派給安全性管理員角色：</span><span class="sxs-lookup"><span data-stu-id="7aaa1-134">For **read and write** access, assign users to the security administrator role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Administrator" -RoleMemberEmailAddress "secadmin@Contoso.onmicrosoft.com"
  ```
  
- <span data-ttu-id="7aaa1-135">若為 **唯讀** 存取，請使用下列命令，將使用者指派給 security reader role：</span><span class="sxs-lookup"><span data-stu-id="7aaa1-135">For **read-only** access, assign users to the security reader role by using the following command:</span></span>

  ```PowerShell
  Add-MsolRoleMember -RoleName "Security Reader" -RoleMemberEmailAddress "reader@Contoso.onmicrosoft.com"
  ```

<span data-ttu-id="7aaa1-136">如需詳細資訊，請參閱[使用 Azure Active Directory 新增或移除群組成員](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-136">For more information, see [Add or remove group members using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal).</span></span>

## <a name="assign-user-access-using-the-azure-portal"></a><span data-ttu-id="7aaa1-137">使用 Azure 入口網站指派使用者存取</span><span class="sxs-lookup"><span data-stu-id="7aaa1-137">Assign user access using the Azure portal</span></span>

<span data-ttu-id="7aaa1-138">如需詳細資訊，請參閱[使用 Azure Active Directory 指派系統管理員和非系統管理員角色給使用者](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="7aaa1-138">For more information, see [Assign administrator and non-administrator roles to users with Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>

## <a name="related-topic"></a><span data-ttu-id="7aaa1-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="7aaa1-139">Related topic</span></span>

- [<span data-ttu-id="7aaa1-140">使用 RBAC 管理入口網站存取</span><span class="sxs-lookup"><span data-stu-id="7aaa1-140">Manage portal access using RBAC</span></span>](rbac.md)
