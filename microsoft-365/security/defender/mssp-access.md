---
title: 提供受管理的安全性服務提供者 (MSSP) 存取權
description: 深入瞭解 Microsoft Defender Security Center to the Microsoft 365 Security center 中的變更
keywords: Microsoft 365 security center 快速入門，Microsoft Defender for Office 365，Microsoft Defender for Endpoint，MDO，MDE，單一窗格的玻璃，融合入口網站，安全性入口網站，Defender 安全性入口網站
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 4b34d3ea20716fb2424d9317b8a51c088a5714a6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935350"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="3caf0-104">提供受管理的安全性服務提供者 (MSSP) 存取權</span><span class="sxs-lookup"><span data-stu-id="3caf0-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="3caf0-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3caf0-105">**Applies to:**</span></span>

- [<span data-ttu-id="3caf0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3caf0-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="3caf0-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3caf0-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="3caf0-108">若要執行多租使用者委派存取解決方案，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="3caf0-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="3caf0-109">在 Microsoft 365 security center 的 Defender for Endpoint 中啟用以 [角色為基礎的存取控制](/windows/security/threat-protection/microsoft-defender-atp/rbac) ，並聯機至 Azure Active Directory (azure AD) 群組。</span><span class="sxs-lookup"><span data-stu-id="3caf0-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="3caf0-110">設定存取要求與布建的控管 [訪問套件](/azure/active-directory/governance/identity-governance-overview) 。</span><span class="sxs-lookup"><span data-stu-id="3caf0-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="3caf0-111">在 [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve)中管理存取要求和審核。</span><span class="sxs-lookup"><span data-stu-id="3caf0-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="3caf0-112">在 Microsoft 365 安全中心的 Microsoft Defender for Endpoint 中啟用角色型存取控制</span><span class="sxs-lookup"><span data-stu-id="3caf0-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="3caf0-113">**在客戶 AAD 中建立 MSSP 資源的訪問群組：群組**</span><span class="sxs-lookup"><span data-stu-id="3caf0-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="3caf0-114">這些群組會連結至您在 Microsoft 365 安全中心的 [Defender for Endpoint] 中建立的角色。</span><span class="sxs-lookup"><span data-stu-id="3caf0-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="3caf0-115">若要這麼做，請在客戶 AD 承租人中建立三個群組。</span><span class="sxs-lookup"><span data-stu-id="3caf0-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="3caf0-116">在我們的範例方法中，我們建立下列群組：</span><span class="sxs-lookup"><span data-stu-id="3caf0-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="3caf0-117">第1層分析員</span><span class="sxs-lookup"><span data-stu-id="3caf0-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="3caf0-118">第2層分析員</span><span class="sxs-lookup"><span data-stu-id="3caf0-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="3caf0-119">MSSP 分析員核准者</span><span class="sxs-lookup"><span data-stu-id="3caf0-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="3caf0-120">在 Microsoft 365 的安全性中心角色和群組中為端點的客戶 Defender 建立適當的訪問層級的 Endpoint role 建立 Defender。</span><span class="sxs-lookup"><span data-stu-id="3caf0-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="3caf0-121">若要在客戶 Microsoft 365 的安全性中心啟用 RBAC，使用具有全域管理員或安全性管理員許可權的使用者帳戶， **> 端點角色 & 群組 > 角色** 的存取許可權。</span><span class="sxs-lookup"><span data-stu-id="3caf0-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![MSSP 存取的影像](../../media/mssp-access.png)

    <span data-ttu-id="3caf0-123">接著，建立 RBAC 角色，以符合 MSSP SOC 層需求。</span><span class="sxs-lookup"><span data-stu-id="3caf0-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="3caf0-124">透過「指派的使用者群組」將這些角色連結到建立的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="3caf0-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="3caf0-125">兩個可能的角色：</span><span class="sxs-lookup"><span data-stu-id="3caf0-125">Two possible roles:</span></span>

    - <span data-ttu-id="3caf0-126">**第1層分析員**</span><span class="sxs-lookup"><span data-stu-id="3caf0-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="3caf0-127">執行除 live response 以外的所有動作和管理安全性設定。</span><span class="sxs-lookup"><span data-stu-id="3caf0-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="3caf0-128">**第2層分析員**</span><span class="sxs-lookup"><span data-stu-id="3caf0-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="3caf0-129">與[live 回應](/windows/security/threat-protection/microsoft-defender-atp/live-response)外的第1層功能</span><span class="sxs-lookup"><span data-stu-id="3caf0-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="3caf0-130">如需詳細資訊，請參閱 [使用以角色為基礎的存取控制](/windows/security/threat-protection/microsoft-defender-atp/rbac)。</span><span class="sxs-lookup"><span data-stu-id="3caf0-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="3caf0-131">設定調控訪問套件</span><span class="sxs-lookup"><span data-stu-id="3caf0-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="3caf0-132">**在客戶 AAD 中以連線的組織形式新增 MSSP：身分識別管理**</span><span class="sxs-lookup"><span data-stu-id="3caf0-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="3caf0-133">將 MSSP 新增為連線的組織，可讓 MSSP 要求並已布建存取權。</span><span class="sxs-lookup"><span data-stu-id="3caf0-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="3caf0-134">若要這麼做，請在客戶 AD 承租人中存取身分識別管理：連線的組織。</span><span class="sxs-lookup"><span data-stu-id="3caf0-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="3caf0-135">透過租使用者識別碼或網域，新增組織並搜尋 MSSP 分析租使用者。</span><span class="sxs-lookup"><span data-stu-id="3caf0-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="3caf0-136">建議您為 MSSP 分析員建立個別的 AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="3caf0-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="3caf0-137">**在客戶 AAD 中建立資原始目錄：身分識別管理**</span><span class="sxs-lookup"><span data-stu-id="3caf0-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="3caf0-138">資原始目錄是 access 套件的邏輯集合，在客戶 AD 租使用者中建立。</span><span class="sxs-lookup"><span data-stu-id="3caf0-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="3caf0-139">若要這麼做，請在客戶 AD 承租人中存取身分識別管理：編目，並 **新增目錄**。</span><span class="sxs-lookup"><span data-stu-id="3caf0-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="3caf0-140">在我們的範例中，我們會致電 **MSSP 存取**。</span><span class="sxs-lookup"><span data-stu-id="3caf0-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![新目錄的影像](../../media/goverance-catalog.png)

    <span data-ttu-id="3caf0-142">進一步資訊，請參閱 [建立資源的目錄](/azure/active-directory/governance/entitlement-management-catalog-create)。</span><span class="sxs-lookup"><span data-stu-id="3caf0-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="3caf0-143">**建立 MSSP 資源的存取套件客戶 AAD：身分識別控管**</span><span class="sxs-lookup"><span data-stu-id="3caf0-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="3caf0-144">Access 套件是權利和存取權的集合，會在核准時授與要求。</span><span class="sxs-lookup"><span data-stu-id="3caf0-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="3caf0-145">若要這麼做，請在客戶 AD 承租人中存取身分識別管理：存取套件，以及新增 **訪問套件**。</span><span class="sxs-lookup"><span data-stu-id="3caf0-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="3caf0-146">為 MSSP 核准者和每個分析員層建立存取套件。</span><span class="sxs-lookup"><span data-stu-id="3caf0-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="3caf0-147">例如，下列第1層分析員設定會建立下列專案的訪問套件：</span><span class="sxs-lookup"><span data-stu-id="3caf0-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="3caf0-148">需要 AD 群組 **MSSP 分析員核准者** 的成員來授權新的要求</span><span class="sxs-lookup"><span data-stu-id="3caf0-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="3caf0-149">具有年度存取權檢查，在此情況下，SOC 分析程式可以要求存取分機</span><span class="sxs-lookup"><span data-stu-id="3caf0-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="3caf0-150">只能由 MSSP SOC 租使用者中的使用者要求</span><span class="sxs-lookup"><span data-stu-id="3caf0-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="3caf0-151">Access auto 會在365天后到期</span><span class="sxs-lookup"><span data-stu-id="3caf0-151">Access auto expires after 365 days</span></span>

    ![新訪問套件的影像](../../media/new-access-package.png)

    <span data-ttu-id="3caf0-153">如需詳細資訊，請參閱 [建立新的 access 套件](/azure/active-directory/governance/entitlement-management-access-package-create)。</span><span class="sxs-lookup"><span data-stu-id="3caf0-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="3caf0-154">**提供存取權要求從客戶 AAD：身分識別控管 MSSP 資源的連結**</span><span class="sxs-lookup"><span data-stu-id="3caf0-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="3caf0-155">MSSP SOC 分析員使用「我的 Access 入口網站」連結，透過建立的訪問套件要求存取權。</span><span class="sxs-lookup"><span data-stu-id="3caf0-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="3caf0-156">連結是持久的，這表示新分析員的時間可能會使用相同的連結。</span><span class="sxs-lookup"><span data-stu-id="3caf0-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="3caf0-157">分析員要求會進入佇列供 **MSSP 分析員核准者** 核准。</span><span class="sxs-lookup"><span data-stu-id="3caf0-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Access 屬性的影像](../../media/access-properties.png)

    <span data-ttu-id="3caf0-159">此連結位於每個 access 套件的 [概述] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="3caf0-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="3caf0-160">管理存取權</span><span class="sxs-lookup"><span data-stu-id="3caf0-160">Manage access</span></span> 

1. <span data-ttu-id="3caf0-161">在客戶和/或 MSSP myaccess 中複查和授權存取要求。</span><span class="sxs-lookup"><span data-stu-id="3caf0-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="3caf0-162">存取要求是由 MSSP 分析員核准者群組的成員在客戶存取。</span><span class="sxs-lookup"><span data-stu-id="3caf0-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="3caf0-163">若要這麼做，請使用：來存取客戶的 myaccess  `https://myaccess.microsoft.com/@<Customer Domain >` 。</span><span class="sxs-lookup"><span data-stu-id="3caf0-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="3caf0-164">範例： `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="3caf0-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="3caf0-165">在 UI 的 [ **核准** ] 區段中核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="3caf0-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="3caf0-166">此時，已布建分析者存取權，且每個分析員都應該可以存取客戶的 Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="3caf0-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="3caf0-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` 具有所指派的許可權和角色。</span><span class="sxs-lookup"><span data-stu-id="3caf0-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3caf0-168">Microsoft 365 security center 中的 Microsoft Defender for Endpoint 的委派存取權目前允許存取每個瀏覽器視窗的單一承租人。</span><span class="sxs-lookup"><span data-stu-id="3caf0-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>