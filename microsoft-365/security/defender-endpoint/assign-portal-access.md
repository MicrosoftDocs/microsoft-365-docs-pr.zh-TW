---
title: 指派使用者對 Microsoft Defender 資訊安全中心的存取權
description: 對 Microsoft Defender for Endpoint 入口網站指派讀取和寫入或唯讀存取權。
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
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164749"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="65971-104">指派使用者對 Microsoft Defender 資訊安全中心的存取權</span><span class="sxs-lookup"><span data-stu-id="65971-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="65971-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="65971-105">**Applies to:**</span></span>
- <span data-ttu-id="65971-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="65971-106">Azure Active Directory</span></span>
- <span data-ttu-id="65971-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="65971-107">Office 365</span></span>
- [<span data-ttu-id="65971-108">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="65971-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65971-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65971-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="65971-110">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="65971-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="65971-111">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="65971-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="65971-112">Defender for Endpoint 支援兩種管理許可權的方式：</span><span class="sxs-lookup"><span data-stu-id="65971-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="65971-113">**基本版權管理**：將許可權設定為「完整存取」或「唯讀」。</span><span class="sxs-lookup"><span data-stu-id="65971-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="65971-114">以 **角色為基礎的存取控制 (RBAC)**：透過定義角色、指派 Azure AD 使用者群組和授予使用者群組存取裝置群組，來設定細微許可權。</span><span class="sxs-lookup"><span data-stu-id="65971-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="65971-115">如需 RBAC 的詳細資訊，請參閱 [使用以角色為基礎的存取控制管理入口網站存取](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="65971-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="65971-116">如果您已指派基本許可權，您可以隨時切換至 RBAC。</span><span class="sxs-lookup"><span data-stu-id="65971-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="65971-117">進行切換之前，請先考慮下列專案：</span><span class="sxs-lookup"><span data-stu-id="65971-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="65971-118">在 Azure AD) 中，在指派全域系統管理員或安全性管理員目錄角色的使用者上，具有完整 (存取權的使用者，系統會自動為端點系統管理員角色指派預設的 Defender，也就是具有完整存取權。</span><span class="sxs-lookup"><span data-stu-id="65971-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="65971-119">在切換至 RBAC 後，可將其他 Azure AD 使用者群組指派給 Defender for Endpoint 系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="65971-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="65971-120">只有指派給 Endpoint 系統管理員角色的使用者才能使用 RBAC 來管理許可權。</span><span class="sxs-lookup"><span data-stu-id="65971-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="65971-121">具有唯讀存取權的使用者 (的安全性讀取者) 在被指派角色後，才會失去對入口網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="65971-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="65971-122">請注意，只有 Azure AD 使用者群組可以指派角色下的 RBAC。</span><span class="sxs-lookup"><span data-stu-id="65971-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="65971-123">切換 RBAC 後，您將無法再切換回使用基本版權管理。</span><span class="sxs-lookup"><span data-stu-id="65971-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="65971-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="65971-124">Related topics</span></span>

- [<span data-ttu-id="65971-125">使用基本權限存取入口網站</span><span class="sxs-lookup"><span data-stu-id="65971-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="65971-126">使用 RBAC 管理入口網站存取</span><span class="sxs-lookup"><span data-stu-id="65971-126">Manage portal access using RBAC</span></span>](rbac.md)
