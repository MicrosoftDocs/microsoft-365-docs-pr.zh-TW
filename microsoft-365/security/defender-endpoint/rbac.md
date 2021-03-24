---
title: 使用以角色為基礎的存取控制，以將微調存取權授與 Microsoft Defender 安全中心
description: 在安全性作業內建立角色和群組，以授與入口網站的存取權。
keywords: rbac，角色，基礎，access，control，groups，control，該級，aad
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
ms.openlocfilehash: d95163bd7caf6e05295fc35b3f9c2bf95230dc83
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058183"
---
# <a name="manage-portal-access-using-role-based-access-control"></a><span data-ttu-id="781ad-104">使用以角色為基礎的存取控制管理入口網站存取</span><span class="sxs-lookup"><span data-stu-id="781ad-104">Manage portal access using role-based access control</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="781ad-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="781ad-105">**Applies to:**</span></span>
- <span data-ttu-id="781ad-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="781ad-106">Azure Active Directory</span></span>
- <span data-ttu-id="781ad-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="781ad-107">Office 365</span></span>

> <span data-ttu-id="781ad-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="781ad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="781ad-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="781ad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-rbac-abovefoldlink)

<span data-ttu-id="781ad-110">使用以角色為基礎的存取控制 (RBAC) ，您可以在安全性作業小組中建立角色和群組，以授與入口網站的適當存取權。</span><span class="sxs-lookup"><span data-stu-id="781ad-110">Using role-based access control (RBAC), you can create roles and groups within your security operations team to grant appropriate access to the  portal.</span></span> <span data-ttu-id="781ad-111">您可以根據您建立的角色和群組，精確控制具有入口網站存取權的使用者可以查看及執行的動作。</span><span class="sxs-lookup"><span data-stu-id="781ad-111">Based on the roles and groups you create, you have fine-grained control over what users with access to the portal can see and do.</span></span> 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bJ2a]

<span data-ttu-id="781ad-112">大型地理分散的安全性運作小組通常採用以階層為基礎的模型，以指派及授權對安全性入口網站的存取。</span><span class="sxs-lookup"><span data-stu-id="781ad-112">Large geo-distributed security operations teams typically adopt a tier-based model to assign and authorize access to security portals.</span></span> <span data-ttu-id="781ad-113">一般層級包括下列三個層級：</span><span class="sxs-lookup"><span data-stu-id="781ad-113">Typical tiers include the following three levels:</span></span>

<span data-ttu-id="781ad-114">層</span><span class="sxs-lookup"><span data-stu-id="781ad-114">Tier</span></span> | <span data-ttu-id="781ad-115">描述</span><span class="sxs-lookup"><span data-stu-id="781ad-115">Description</span></span>
:---|:---
<span data-ttu-id="781ad-116">第1層</span><span class="sxs-lookup"><span data-stu-id="781ad-116">Tier 1</span></span> | <span data-ttu-id="781ad-117">**本機安全作業小組/IT 小組**</span><span class="sxs-lookup"><span data-stu-id="781ad-117">**Local security operations team / IT team**</span></span> <br> <span data-ttu-id="781ad-118">此小組通常會 triages 並調查包含在其地理位置內的警示，並在需要使用中修復的情況下升級至第2層。</span><span class="sxs-lookup"><span data-stu-id="781ad-118">This team usually triages and investigates alerts contained within their geolocation and escalates to Tier 2 in cases where an active remediation is required.</span></span>
<span data-ttu-id="781ad-119">第2層</span><span class="sxs-lookup"><span data-stu-id="781ad-119">Tier 2</span></span> | <span data-ttu-id="781ad-120">**區域安全性運作小組**</span><span class="sxs-lookup"><span data-stu-id="781ad-120">**Regional security operations team**</span></span> <br> <span data-ttu-id="781ad-121">此小組可以查看其地區的所有裝置，並執行修正動作。</span><span class="sxs-lookup"><span data-stu-id="781ad-121">This team can see all the devices for their region and perform remediation actions.</span></span>
<span data-ttu-id="781ad-122">第3層</span><span class="sxs-lookup"><span data-stu-id="781ad-122">Tier 3</span></span> | <span data-ttu-id="781ad-123">**全域安全性運作小組**</span><span class="sxs-lookup"><span data-stu-id="781ad-123">**Global security operations team**</span></span> <br> <span data-ttu-id="781ad-124">此小組由安全性專家組成，並有權從入口網站查看及執行所有動作。</span><span class="sxs-lookup"><span data-stu-id="781ad-124">This team consists of security experts and are authorized to see and perform all actions from the portal.</span></span>

<span data-ttu-id="781ad-125">Defender for Endpoint RBAC 是專門設計用來支援您的分層或以角色為基礎的模型，其可讓您細微地控制哪些角色可以查看、可以存取的裝置，以及可以採取的動作。</span><span class="sxs-lookup"><span data-stu-id="781ad-125">Defender for Endpoint RBAC is designed to support your tier- or role-based model of choice and gives you granular control over what roles can see, devices they can access, and actions they can take.</span></span> <span data-ttu-id="781ad-126">RBAC 架構會以下列控制項為中心：</span><span class="sxs-lookup"><span data-stu-id="781ad-126">The RBAC framework is centered around the following controls:</span></span>

- <span data-ttu-id="781ad-127">**控制誰可以採取特定動作**</span><span class="sxs-lookup"><span data-stu-id="781ad-127">**Control who can take specific action**</span></span>
  - <span data-ttu-id="781ad-128">建立自訂角色並控制其可透過細微性存取的任何 Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="781ad-128">Create custom roles and control what Defender for Endpoint capabilities they can access with granularity.</span></span>
 
- <span data-ttu-id="781ad-129">**控制誰可以查看特定裝置群組或群組的資訊**</span><span class="sxs-lookup"><span data-stu-id="781ad-129">**Control who can see information on specific device group or groups**</span></span>
  - <span data-ttu-id="781ad-130">依特定準則（例如名稱、標記、網域及其他）[建立裝置群組](machine-groups.md)，然後使用特定 Azure Active Directory (azure AD) 使用者群組，將角色存取權授與這些群組。</span><span class="sxs-lookup"><span data-stu-id="781ad-130">[Create device groups](machine-groups.md) by specific criteria such as names, tags, domains, and others, then grant role access to them using a specific  Azure Active Directory (Azure AD) user group.</span></span>

<span data-ttu-id="781ad-131">若要執行以角色為基礎的存取，您必須定義系統管理員角色、指派對應的許可權，以及指派指派給角色的 Azure AD 使用者群組。</span><span class="sxs-lookup"><span data-stu-id="781ad-131">To implement role-based access, you'll need to define admin roles, assign corresponding permissions, and assign Azure AD user groups assigned to the roles.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="781ad-132">開始之前</span><span class="sxs-lookup"><span data-stu-id="781ad-132">Before you begin</span></span>
<span data-ttu-id="781ad-133">使用 RBAC 之前，請務必瞭解可以授與許可權的角色，以及開啟 RBAC 的後果。</span><span class="sxs-lookup"><span data-stu-id="781ad-133">Before using RBAC, it's important that you understand the roles that can grant permissions and the consequences of turning on RBAC.</span></span>


> [!WARNING]
> <span data-ttu-id="781ad-134">在啟用該功能之前，請務必先在 Azure AD 中擁有全域系統管理員角色或安全性系統管理員角色，且您的 Azure AD 群組已準備好，以降低鎖定閘道網站的風險。</span><span class="sxs-lookup"><span data-stu-id="781ad-134">Before enabling the feature, it's important that you have a Global Administrator role or Security Administrator role in Azure AD and that you have your Azure AD groups ready to reduce the risk of being locked out of the portal.</span></span> 

<span data-ttu-id="781ad-135">當您第一次登入 Microsoft Defender Security Center 時，即會授與「完整存取」或「唯讀」存取權。</span><span class="sxs-lookup"><span data-stu-id="781ad-135">When you first log in to Microsoft Defender Security Center, you're granted either full access or read only access.</span></span> <span data-ttu-id="781ad-136">使用 Azure AD 中的安全性系統管理員或全域系統管理員角色，可將完整存取權授與使用者。</span><span class="sxs-lookup"><span data-stu-id="781ad-136">Full access rights are granted to users with Security Administrator or Global Administrator roles in Azure AD.</span></span> <span data-ttu-id="781ad-137">唯讀存取權授與 Azure AD 中具有安全性讀者角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="781ad-137">Read only access is granted to users with a Security Reader role in Azure AD.</span></span> 

<span data-ttu-id="781ad-138">具有端點全域系統管理員角色的人員，不論其裝置群組關聯和 Azure AD 使用者群組指派為何，都具有對所有裝置的無限制存取權</span><span class="sxs-lookup"><span data-stu-id="781ad-138">Someone with a Defender for Endpoint Global administrator role has unrestricted access to all devices, regardless of their device group association and the Azure AD user groups assignments</span></span>

> [!WARNING]
> <span data-ttu-id="781ad-139">起初，只有具備 Azure AD 全域系統管理員或安全性管理員許可權的人員才能在 Microsoft Defender 安全中心建立和指派角色，因此，在 Azure AD 中準備好適當的群組是很重要的。</span><span class="sxs-lookup"><span data-stu-id="781ad-139">Initially, only those with Azure AD Global Administrator or Security Administrator rights will be able to create and assign roles in Microsoft Defender Security Center, therefore, having the right groups ready in Azure AD is important.</span></span>
>
> <span data-ttu-id="781ad-140">**開啟以角色為基礎的存取控制會使具有唯讀許可權的使用者 (例如，已指派至 Azure AD Security reader 角色的使用者) 會在指派給角色之前喪失存取權。**</span><span class="sxs-lookup"><span data-stu-id="781ad-140">**Turning on role-based access control will cause users with read-only permissions (for example, users assigned to Azure AD Security reader role) to lose access until they are assigned to a role.**</span></span> 
>
><span data-ttu-id="781ad-141">具有系統管理員許可權的使用者會自動為端點全域系統管理員角色指派具有完整許可權的預設內建的 Defender。</span><span class="sxs-lookup"><span data-stu-id="781ad-141">Users with admin permissions are automatically assigned the default built-in Defender for Endpoint global administrator role with full permissions.</span></span> <span data-ttu-id="781ad-142">在您使用 RBAC 做後，您可以將不是 Azure AD 全域或安全性系統管理員的其他使用者指派給 Defender for Endpoint 全域系統管理員角色。</span><span class="sxs-lookup"><span data-stu-id="781ad-142">After opting in to use RBAC, you can assign additional users that are not Azure AD Global or Security Administrators to the Defender for Endpoint global administrator role.</span></span> 
>
> <span data-ttu-id="781ad-143">在您登入使用 RBAC 之後，當您第一次登入入口網站時，您無法還原為初始角色。</span><span class="sxs-lookup"><span data-stu-id="781ad-143">After opting in to use RBAC, you cannot revert to the initial roles as when you first logged into the portal.</span></span> 



## <a name="related-topic"></a><span data-ttu-id="781ad-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="781ad-144">Related topic</span></span>
- [<span data-ttu-id="781ad-145">在 Microsoft Defender for Endpoint 中建立及管理裝置群組</span><span class="sxs-lookup"><span data-stu-id="781ad-145">Create and manage device groups in Microsoft Defender for Endpoint</span></span>](machine-groups.md)
