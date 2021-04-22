---
title: '將存取權授與受管理的安全性服務提供者 (MSSP) '
description: 採取必要的步驟設定 MSSP 整合與 Microsoft Defender for Endpoint
keywords: 受管理的安全性服務提供者、mssp、configure、integration
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
ms.openlocfilehash: 320355f838db5dbb1540350e95e4cc0645acd805
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932748"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="a94b3-104">授與受管理的安全性服務提供者 (MSSP) access (預覽) </span><span class="sxs-lookup"><span data-stu-id="a94b3-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a94b3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="a94b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="a94b3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a94b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a94b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a94b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a94b3-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a94b3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a94b3-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="a94b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="a94b3-110">部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。</span><span class="sxs-lookup"><span data-stu-id="a94b3-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a94b3-111">Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。</span><span class="sxs-lookup"><span data-stu-id="a94b3-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a94b3-112">若要執行多租使用者委派存取解決方案，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a94b3-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="a94b3-113">在 [Defender for Endpoint] 中啟用以 [角色為基礎的存取控制](rbac.md) ，並使用 Active DIRECTORY (AD) 群組進行連線。</span><span class="sxs-lookup"><span data-stu-id="a94b3-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="a94b3-114">設定存取要求與布建的控管 [訪問套件](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) 。</span><span class="sxs-lookup"><span data-stu-id="a94b3-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="a94b3-115">在 [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)中管理存取要求和審核。</span><span class="sxs-lookup"><span data-stu-id="a94b3-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="a94b3-116">在 Microsoft Defender for Endpoint 中啟用以角色為基礎的存取控制</span><span class="sxs-lookup"><span data-stu-id="a94b3-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="a94b3-117">**在客戶 AAD 中建立 MSSP 資源的訪問群組：群組**</span><span class="sxs-lookup"><span data-stu-id="a94b3-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="a94b3-118">這些群組會連結至您在 [Defender for Endpoint] 中建立的角色。</span><span class="sxs-lookup"><span data-stu-id="a94b3-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="a94b3-119">若要這麼做，請在客戶 AD 承租人中建立三個群組。</span><span class="sxs-lookup"><span data-stu-id="a94b3-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="a94b3-120">在我們的範例方法中，我們建立下列群組：</span><span class="sxs-lookup"><span data-stu-id="a94b3-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="a94b3-121">第1層分析員</span><span class="sxs-lookup"><span data-stu-id="a94b3-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="a94b3-122">第2層分析員</span><span class="sxs-lookup"><span data-stu-id="a94b3-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="a94b3-123">MSSP 分析員核准者</span><span class="sxs-lookup"><span data-stu-id="a94b3-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="a94b3-124">為 Endpoint 的客戶 Defender 中的適當訪問層級建立適用于端點角色的 Defender。</span><span class="sxs-lookup"><span data-stu-id="a94b3-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="a94b3-125">若要在客戶 Microsoft Defender Security Center 中啟用 RBAC，請從具有全域管理員或安全性管理員許可權的使用者帳戶，存取 **設定 > 許可權 > 角色** 和「開啟角色」。</span><span class="sxs-lookup"><span data-stu-id="a94b3-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP 存取的影像](images/mssp-access.png)

    <span data-ttu-id="a94b3-127">接著，建立 RBAC 角色，以符合 MSSP SOC 層需求。</span><span class="sxs-lookup"><span data-stu-id="a94b3-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="a94b3-128">透過「指派的使用者群組」將這些角色連結到建立的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="a94b3-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="a94b3-129">兩個可能的角色：</span><span class="sxs-lookup"><span data-stu-id="a94b3-129">Two possible roles:</span></span>

    - <span data-ttu-id="a94b3-130">**第1層分析員**</span><span class="sxs-lookup"><span data-stu-id="a94b3-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="a94b3-131">執行除 live response 以外的所有動作和管理安全性設定。</span><span class="sxs-lookup"><span data-stu-id="a94b3-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="a94b3-132">**第2層分析員**</span><span class="sxs-lookup"><span data-stu-id="a94b3-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="a94b3-133">與[live 回應](live-response.md)外的第1層功能</span><span class="sxs-lookup"><span data-stu-id="a94b3-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="a94b3-134">如需詳細資訊，請參閱 [使用以角色為基礎的存取控制](rbac.md)。</span><span class="sxs-lookup"><span data-stu-id="a94b3-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="a94b3-135">設定調控訪問套件</span><span class="sxs-lookup"><span data-stu-id="a94b3-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="a94b3-136">**在客戶 AAD 中以連線的組織形式新增 MSSP：身分識別管理**</span><span class="sxs-lookup"><span data-stu-id="a94b3-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="a94b3-137">將 MSSP 新增為連線的組織，可讓 MSSP 要求並已布建存取權。</span><span class="sxs-lookup"><span data-stu-id="a94b3-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="a94b3-138">若要這麼做，請在客戶 AD 承租人中存取身分識別管理：連線的組織。</span><span class="sxs-lookup"><span data-stu-id="a94b3-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="a94b3-139">透過租使用者識別碼或網域，新增組織並搜尋 MSSP 分析租使用者。</span><span class="sxs-lookup"><span data-stu-id="a94b3-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="a94b3-140">建議您為 MSSP 分析員建立個別的 AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="a94b3-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="a94b3-141">**在客戶 AAD 中建立資原始目錄：身分識別管理**</span><span class="sxs-lookup"><span data-stu-id="a94b3-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="a94b3-142">資原始目錄是 access 套件的邏輯集合，在客戶 AD 租使用者中建立。</span><span class="sxs-lookup"><span data-stu-id="a94b3-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="a94b3-143">若要這麼做，請在客戶 AD 承租人中存取身分識別管理：編目，並 **新增目錄**。</span><span class="sxs-lookup"><span data-stu-id="a94b3-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="a94b3-144">在我們的範例中，我們會致電 **MSSP 存取**。</span><span class="sxs-lookup"><span data-stu-id="a94b3-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![新目錄的影像](images/goverance-catalog.png)

    <span data-ttu-id="a94b3-146">進一步資訊，請參閱 [建立資源的目錄](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)。</span><span class="sxs-lookup"><span data-stu-id="a94b3-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="a94b3-147">**建立 MSSP 資源的存取套件客戶 AAD：身分識別控管**</span><span class="sxs-lookup"><span data-stu-id="a94b3-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="a94b3-148">Access 套件是權利和存取權的集合，會在核准時授與要求。</span><span class="sxs-lookup"><span data-stu-id="a94b3-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="a94b3-149">若要這麼做，請在客戶 AD 承租人中存取身分識別管理：存取套件，以及新增 **訪問套件**。</span><span class="sxs-lookup"><span data-stu-id="a94b3-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="a94b3-150">為 MSSP 核准者和每個分析員層建立存取套件。</span><span class="sxs-lookup"><span data-stu-id="a94b3-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="a94b3-151">例如，下列第1層分析員設定會建立下列專案的訪問套件：</span><span class="sxs-lookup"><span data-stu-id="a94b3-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="a94b3-152">需要 AD 群組 **MSSP 分析員核准者** 的成員來授權新的要求</span><span class="sxs-lookup"><span data-stu-id="a94b3-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="a94b3-153">具有年度存取權檢查，在此情況下，SOC 分析程式可以要求存取分機</span><span class="sxs-lookup"><span data-stu-id="a94b3-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="a94b3-154">只能由 MSSP SOC 租使用者中的使用者要求</span><span class="sxs-lookup"><span data-stu-id="a94b3-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="a94b3-155">Access auto 會在365天后到期</span><span class="sxs-lookup"><span data-stu-id="a94b3-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a94b3-156">![新訪問套件的影像](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="a94b3-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="a94b3-157">如需詳細資訊，請參閱 [建立新的 access 套件](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)。</span><span class="sxs-lookup"><span data-stu-id="a94b3-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="a94b3-158">**提供存取權要求從客戶 AAD：身分識別控管 MSSP 資源的連結**</span><span class="sxs-lookup"><span data-stu-id="a94b3-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="a94b3-159">MSSP SOC 分析員使用「我的 Access 入口網站」連結，透過建立的訪問套件要求存取權。</span><span class="sxs-lookup"><span data-stu-id="a94b3-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="a94b3-160">連結是持久的，這表示新分析員的時間可能會使用相同的連結。</span><span class="sxs-lookup"><span data-stu-id="a94b3-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="a94b3-161">分析員要求會進入佇列供 **MSSP 分析員核准者** 核准。</span><span class="sxs-lookup"><span data-stu-id="a94b3-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a94b3-162">![Access 屬性的影像](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="a94b3-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="a94b3-163">此連結位於每個 access 套件的 [概述] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="a94b3-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="a94b3-164">管理存取權</span><span class="sxs-lookup"><span data-stu-id="a94b3-164">Manage access</span></span> 

1. <span data-ttu-id="a94b3-165">在客戶和/或 MSSP myaccess 中複查和授權存取要求。</span><span class="sxs-lookup"><span data-stu-id="a94b3-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="a94b3-166">存取要求是由 MSSP 分析員核准者群組的成員在客戶存取。</span><span class="sxs-lookup"><span data-stu-id="a94b3-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="a94b3-167">若要這麼做，請使用：來存取客戶的 myaccess  `https://myaccess.microsoft.com/@<Customer Domain >` 。</span><span class="sxs-lookup"><span data-stu-id="a94b3-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="a94b3-168">範例： `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="a94b3-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="a94b3-169">在 UI 的 [ **核准** ] 區段中核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="a94b3-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="a94b3-170">此時，已布建分析者存取權，且每個分析員都應該可以存取客戶的 Microsoft Defender 安全中心： `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="a94b3-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="a94b3-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="a94b3-171">Related topics</span></span>
- [<span data-ttu-id="a94b3-172">存取 MSSP 客戶入口網站</span><span class="sxs-lookup"><span data-stu-id="a94b3-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="a94b3-173">設定警示通知</span><span class="sxs-lookup"><span data-stu-id="a94b3-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="a94b3-174">從客戶租用戶中抓取警示</span><span class="sxs-lookup"><span data-stu-id="a94b3-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

