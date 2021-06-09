---
title: 適用于企業的 Microsoft 365 租使用者管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: 您的 Microsoft 365 承租人的規劃、部署及日常運作的概況。
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405675"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a><span data-ttu-id="47a6c-103">適用于企業的 Microsoft 365 租使用者管理</span><span class="sxs-lookup"><span data-stu-id="47a6c-103">Tenant management for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="47a6c-104">若要建立您組織的數位轉換與雲端計算的路徑，需要一個可靠的基礎，讓您的工作人員可以以生產力、共同作業、效能、隱私權、合規性和安全性為基礎。</span><span class="sxs-lookup"><span data-stu-id="47a6c-104">Creating a path to your organization's digital transformation with cloud computing requires a firm foundation upon which your workers can rely for productivity, collaboration, performance, privacy, compliance, and security.</span></span>

<span data-ttu-id="47a6c-105">正確設定 Microsoft 365 租使用者可提供該基礎，讓您的工作人員致力於完成其工作，並讓您的 IT 部門專注于提供其他商業價值的端對端解決方案。</span><span class="sxs-lookup"><span data-stu-id="47a6c-105">Correct configuration of your Microsoft 365 tenants provides that foundation, leaving your workers to focus on getting their work done and your IT department to focus on end-to-end solutions that provide additional business value.</span></span> 

<span data-ttu-id="47a6c-106">此解決方案會透過下列步驟，透過該基礎進行設定：</span><span class="sxs-lookup"><span data-stu-id="47a6c-106">This solution takes you through the configuration of that foundation in these steps:</span></span>

1. <span data-ttu-id="47a6c-107">決定您的承租人</span><span class="sxs-lookup"><span data-stu-id="47a6c-107">Determine your tenants</span></span>
2. <span data-ttu-id="47a6c-108">優化網路</span><span class="sxs-lookup"><span data-stu-id="47a6c-108">Optimize your networking</span></span>
3. <span data-ttu-id="47a6c-109">同步處理您的身分識別並強制執行安全登入</span><span class="sxs-lookup"><span data-stu-id="47a6c-109">Synchronize your identities and enforce secure sign-ins</span></span>
4. <span data-ttu-id="47a6c-110">遷移您的 Windows 裝置、Office 用戶端，以及內部部署 Office 伺服器及資料</span><span class="sxs-lookup"><span data-stu-id="47a6c-110">Migrate your Windows devices, Office clients, and on-premises Office servers and data</span></span>
5. <span data-ttu-id="47a6c-111">部署裝置和應用程式管理</span><span class="sxs-lookup"><span data-stu-id="47a6c-111">Deploy device and app management</span></span>

<span data-ttu-id="47a6c-112">不過，首先讓我們花一些時間來瞭解租使用者是什麼，以及提供公司基礎的承租人的外觀。</span><span class="sxs-lookup"><span data-stu-id="47a6c-112">But first, let's take a moment to understand what a tenant is and what a tenant that provides a firm foundation looks like.</span></span>

## <a name="a-microsoft-365-tenant-defined"></a><span data-ttu-id="47a6c-113">定義的 Microsoft 365 租使用者</span><span class="sxs-lookup"><span data-stu-id="47a6c-113">A Microsoft 365 tenant defined</span></span>

<span data-ttu-id="47a6c-114">Microsoft 365 租使用者是 Microsoft 365 服務的專用實例，以及儲存在特定預設位置（例如歐洲或北美地區）的組織資料。</span><span class="sxs-lookup"><span data-stu-id="47a6c-114">A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America.</span></span> <span data-ttu-id="47a6c-115">當您為組織建立租使用者時，就會指定此位置。</span><span class="sxs-lookup"><span data-stu-id="47a6c-115">This location is specified when you create the tenant for your organization.</span></span> <span data-ttu-id="47a6c-116">每個 Microsoft 365 租使用者都是獨特、獨特的，並與其他所有 Microsoft 365 承租人分開。</span><span class="sxs-lookup"><span data-stu-id="47a6c-116">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="47a6c-117">當您購買一或多個 Microsoft 的產品，例如 Microsoft 365 E3 或 E5，以及每個產品的授權集時，您會建立 Microsoft 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="47a6c-117">You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.</span></span>

<span data-ttu-id="47a6c-118">您的 Microsoft 365 租使用者也包含 Azure Active Directory (azure ad) 租使用者，該租使用者帳戶、群組及其他物件的 azure ad 專用實例。</span><span class="sxs-lookup"><span data-stu-id="47a6c-118">Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects.</span></span> <span data-ttu-id="47a6c-119">每個 Azure AD 租使用者皆為 distinct，unique，與其他所有 Azure AD 租使用者分開。</span><span class="sxs-lookup"><span data-stu-id="47a6c-119">Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.</span></span> <span data-ttu-id="47a6c-120">雖然您的組織可以有多個可使用 azure 訂閱設定的 azure ad 租使用者，Microsoft 365 租使用者才能使用單一 Azure ad 租使用者，這是您建立租使用者時所建立的承租人。</span><span class="sxs-lookup"><span data-stu-id="47a6c-120">While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.</span></span> 

<span data-ttu-id="47a6c-121">範例如下：</span><span class="sxs-lookup"><span data-stu-id="47a6c-121">Here is an example:</span></span>

![使用 Azure AD 租使用者 Microsoft 365 承租人的範例](../media/tenant-management-overview/tenant-management-example-tenant.png)

<span data-ttu-id="47a6c-123">*租使用者管理* 是 Microsoft 365 承租人的規劃、部署及日常運作。</span><span class="sxs-lookup"><span data-stu-id="47a6c-123">*Tenant management* is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.</span></span> 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a><span data-ttu-id="47a6c-124">設計完善且運作租使用者的屬性</span><span class="sxs-lookup"><span data-stu-id="47a6c-124">Attributes of a well-designed and operating tenant</span></span>

<span data-ttu-id="47a6c-125">除了正確的承租人名稱和位置以外，還有其他一些元素可用於規劃、部署和管理，以確保您的使用者體驗 &mdash; Microsoft Teams 和 Exchange Online 等雲端生產力應用程式 &mdash; 是有效、安全和高性能。</span><span class="sxs-lookup"><span data-stu-id="47a6c-125">Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps&mdash;such as Microsoft Teams and Exchange Online&mdash;are effective, secure, and performant.</span></span>

<span data-ttu-id="47a6c-126">以下是元素：</span><span class="sxs-lookup"><span data-stu-id="47a6c-126">Here are the elements:</span></span>

- <span data-ttu-id="47a6c-127">您有一組正確的產品 (訂閱) 和授權。</span><span class="sxs-lookup"><span data-stu-id="47a6c-127">You have the correct set of products (subscriptions) and licenses.</span></span>
  - <span data-ttu-id="47a6c-128">產品集合符合您的業務、IT 及安全性需求。</span><span class="sxs-lookup"><span data-stu-id="47a6c-128">The set of products match your business, IT, and security needs.</span></span>
  - <span data-ttu-id="47a6c-129">您的工作人員和人員的預期變更有適當數量的授權。</span><span class="sxs-lookup"><span data-stu-id="47a6c-129">There is an adequate number of licenses for your workers and anticipated changes in staffing.</span></span>
- <span data-ttu-id="47a6c-130">若為網路：</span><span class="sxs-lookup"><span data-stu-id="47a6c-130">For networking:</span></span>
  - <span data-ttu-id="47a6c-131">您已設定正確的 DNS 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="47a6c-131">You have configured the correct DNS domain names.</span></span>
  - <span data-ttu-id="47a6c-132">針對商業網路，您已針對現場工作者的 Microsoft 網路優化網路流量。</span><span class="sxs-lookup"><span data-stu-id="47a6c-132">For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.</span></span>
  - <span data-ttu-id="47a6c-133">您已針對使用 VPN 用戶端的遠端工作者優化網路流量。</span><span class="sxs-lookup"><span data-stu-id="47a6c-133">You have optimized network traffic for remote workers who are using a VPN client.</span></span>
- <span data-ttu-id="47a6c-134">您已同步處理 Active Directory 網域服務 (AD DS) 帳戶、群組及其他物件。</span><span class="sxs-lookup"><span data-stu-id="47a6c-134">You have synchronized your Active Directory Domain Services (AD DS) accounts, groups, and other objects.</span></span>
  - <span data-ttu-id="47a6c-135">您的 Azure AD 租使用者帳戶會對應至具有正確 DNS 網域之電子郵件地址的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="47a6c-135">Your Azure AD tenant accounts are mapped to Exchange Online mailboxes with the correct DNS domains for email addresses.</span></span>
  - <span data-ttu-id="47a6c-136">您的使用者帳戶已被指派正確購買產品 (例如 Microsoft 365 E3 或 E5) 的授權。</span><span class="sxs-lookup"><span data-stu-id="47a6c-136">Your user accounts have been assigned the correct licenses from the correct purchased products (such as Microsoft 365 E3 or E5).</span></span>
- <span data-ttu-id="47a6c-137">您已設定強身分識別和存取管理。</span><span class="sxs-lookup"><span data-stu-id="47a6c-137">You have configured strong identity and access management.</span></span>
  - <span data-ttu-id="47a6c-138">您需要使用 passwordless 或多重要素驗證 (MFA) 進行安全的使用者登入。</span><span class="sxs-lookup"><span data-stu-id="47a6c-138">You are requiring secure user sign-in with passwordless or multi-factor authentication (MFA).</span></span>
  - <span data-ttu-id="47a6c-139">您有條件式存取原則，可強制登入需求和限制更高的安全性層級。</span><span class="sxs-lookup"><span data-stu-id="47a6c-139">You have Conditional Access policies that enforce sign-in requirements and restrictions for higher levels of security.</span></span>
- <span data-ttu-id="47a6c-140">內部部署 Office 伺服器及其資料已遷移至雲端應用程式，或是混合式設定中使用。</span><span class="sxs-lookup"><span data-stu-id="47a6c-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span></span>
- <span data-ttu-id="47a6c-141">您正在使用 Microsoft 365 內建的 Intune 或基本行動及安全性進行裝置管理。</span><span class="sxs-lookup"><span data-stu-id="47a6c-141">You are doing device management with Intune or Basic Mobility and Security built into Microsoft 365.</span></span>
  - <span data-ttu-id="47a6c-142">組織擁有的裝置會註冊並管理。</span><span class="sxs-lookup"><span data-stu-id="47a6c-142">Your organization-owned devices are enrolled and managed.</span></span>
  - <span data-ttu-id="47a6c-143">管理個人裝置的應用程式。</span><span class="sxs-lookup"><span data-stu-id="47a6c-143">The apps for personal devices are managed.</span></span>

<span data-ttu-id="47a6c-144">以下是具有所有這些元素的 Microsoft 365 承租人的範例。</span><span class="sxs-lookup"><span data-stu-id="47a6c-144">Here is an example of a Microsoft 365 tenant with all these elements in place.</span></span>

![承租人 Microsoft 365 範例](../media/tenant-management-overview/tenant-management-tenant-config.png)

<span data-ttu-id="47a6c-146">在此圖中，Microsoft 365 承租人包括：</span><span class="sxs-lookup"><span data-stu-id="47a6c-146">In this illustration, the Microsoft 365 tenant includes:</span></span>

- <span data-ttu-id="47a6c-147">Microsoft 365 E3 和 E5 的產品及授權。</span><span class="sxs-lookup"><span data-stu-id="47a6c-147">Products and licenses for Microsoft 365 E3 and E5.</span></span>
- <span data-ttu-id="47a6c-148">Microsoft 365 生產力應用程式。</span><span class="sxs-lookup"><span data-stu-id="47a6c-148">Microsoft 365 productivity apps.</span></span>
- <span data-ttu-id="47a6c-149">使用註冊裝置和裝置及應用程式原則的 Intune。</span><span class="sxs-lookup"><span data-stu-id="47a6c-149">Intune with enrolled devices and device and application policies.</span></span>
- <span data-ttu-id="47a6c-150">具有同步處理使用者帳戶 (群組和其他目錄物件的 Azure AD 租使用者不會顯示) 、網域和條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="47a6c-150">An Azure AD tenant that has synchronized user account (groups and other directory objects are not shown), domains, and Conditional Access policies.</span></span>

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a><span data-ttu-id="47a6c-151">適用于企業的 Microsoft 365 租使用者功能</span><span class="sxs-lookup"><span data-stu-id="47a6c-151">Tenant capabilities for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="47a6c-152">下列各節和表格列出此方案中步驟的主要功能及授權。</span><span class="sxs-lookup"><span data-stu-id="47a6c-152">The following sections and table list the key capabilities and licensing for the steps in this solution.</span></span>

### <a name="tenant"></a><span data-ttu-id="47a6c-153">租用戶</span><span class="sxs-lookup"><span data-stu-id="47a6c-153">Tenant</span></span>

| <span data-ttu-id="47a6c-154">功能</span><span class="sxs-lookup"><span data-stu-id="47a6c-154">Capability or feature</span></span> | <span data-ttu-id="47a6c-155">描述</span><span class="sxs-lookup"><span data-stu-id="47a6c-155">Description</span></span> | <span data-ttu-id="47a6c-156">授權</span><span class="sxs-lookup"><span data-stu-id="47a6c-156">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="47a6c-157">多個租用戶</span><span class="sxs-lookup"><span data-stu-id="47a6c-157">Multiple tenants</span></span> | <span data-ttu-id="47a6c-158">每個 Microsoft 365 租使用者都是獨特、獨特的，並與其他所有 Microsoft 365 承租人分開。</span><span class="sxs-lookup"><span data-stu-id="47a6c-158">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="47a6c-159">使用多個承租人時，在管理及為使用者提供服務時會有一些限制與其他考慮。</span><span class="sxs-lookup"><span data-stu-id="47a6c-159">With multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span> | <span data-ttu-id="47a6c-160">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-161">跨租用戶信箱移轉</span><span class="sxs-lookup"><span data-stu-id="47a6c-161">Cross-tenant mailbox migration</span></span> | <span data-ttu-id="47a6c-162">租使用者管理員可以在承租人之間移動信箱，但其內部部署系統中的基礎結構相依性最低。</span><span class="sxs-lookup"><span data-stu-id="47a6c-162">Tenant administrators can move mailboxes between tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="47a6c-163">這樣就不再需要離線和上架信箱。</span><span class="sxs-lookup"><span data-stu-id="47a6c-163">This removes the need to off-board and onboard mailboxes.</span></span> | <span data-ttu-id="47a6c-164">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-164">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-165">多地理位置</span><span class="sxs-lookup"><span data-stu-id="47a6c-165">Multi-Geo</span></span> | <span data-ttu-id="47a6c-166">您的租使用者可以將靜態資料儲存在其他資料中心地理位置，您已選擇這些地理位置，以符合資料派駐要求。</span><span class="sxs-lookup"><span data-stu-id="47a6c-166">Your tenant can store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements.</span></span> | <span data-ttu-id="47a6c-167">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-168">將核心資料移至新的資料中心地理位置</span><span class="sxs-lookup"><span data-stu-id="47a6c-168">Move core data to a new datacenter geo</span></span> | <span data-ttu-id="47a6c-169">當 Microsoft 新增新的資料中心 geos 以取得額外的容量及計算資源時，您可以針對您的核心客戶資料要求針對地理位置的資料派駐服務，要求資料中心地理位置移動。</span><span class="sxs-lookup"><span data-stu-id="47a6c-169">As Microsoft adds new datacenter geos for additional capacity and compute resources, you can request a datacenter geo move for in-geo data residency for your core customer data.</span></span> | <span data-ttu-id="47a6c-170">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-170">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="networking"></a><span data-ttu-id="47a6c-171">網路功能</span><span class="sxs-lookup"><span data-stu-id="47a6c-171">Networking</span></span>

| <span data-ttu-id="47a6c-172">功能</span><span class="sxs-lookup"><span data-stu-id="47a6c-172">Capability or feature</span></span> | <span data-ttu-id="47a6c-173">描述</span><span class="sxs-lookup"><span data-stu-id="47a6c-173">Description</span></span> | <span data-ttu-id="47a6c-174">授權</span><span class="sxs-lookup"><span data-stu-id="47a6c-174">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="47a6c-175">網路洞察力</span><span class="sxs-lookup"><span data-stu-id="47a6c-175">Network Insights</span></span> | <span data-ttu-id="47a6c-176">從 Microsoft 365 租使用者收集的網路效能度量，協助您為辦公室位置設計網路周邊。</span><span class="sxs-lookup"><span data-stu-id="47a6c-176">Network performance metrics collected from your Microsoft 365 tenant to help you design network perimeters for your office locations.</span></span> | <span data-ttu-id="47a6c-177">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-177">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-178">自動化端點更新</span><span class="sxs-lookup"><span data-stu-id="47a6c-178">Automate endpoint updates</span></span> | <span data-ttu-id="47a6c-179">為用戶端 PAC 檔案和網路裝置及服務中的 Microsoft 365 端點自動化設定和持續更新。</span><span class="sxs-lookup"><span data-stu-id="47a6c-179">Automate the configuration and ongoing updates for Microsoft 365 endpoints in your client PAC files and network devices and services.</span></span> | <span data-ttu-id="47a6c-180">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-180">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="identity"></a><span data-ttu-id="47a6c-181">身分識別</span><span class="sxs-lookup"><span data-stu-id="47a6c-181">Identity</span></span>

| <span data-ttu-id="47a6c-182">功能</span><span class="sxs-lookup"><span data-stu-id="47a6c-182">Capability or feature</span></span> | <span data-ttu-id="47a6c-183">描述</span><span class="sxs-lookup"><span data-stu-id="47a6c-183">Description</span></span> | <span data-ttu-id="47a6c-184">授權</span><span class="sxs-lookup"><span data-stu-id="47a6c-184">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="47a6c-185">使用您的 Azure AD 租使用者同步處理內部部署 Active Directory 網域服務 (AD DS) </span><span class="sxs-lookup"><span data-stu-id="47a6c-185">Synchronize on-premises Active Directory Domain Services (AD DS) with your Azure AD tenant</span></span>    | <span data-ttu-id="47a6c-186">針對使用者帳戶、群組及其他物件，利用您的內部部署身分識別提供者。</span><span class="sxs-lookup"><span data-stu-id="47a6c-186">Leverage your on-premises identity provider for user accounts, groups, and other objects.</span></span> | <span data-ttu-id="47a6c-187">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-187">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="47a6c-188">採用安全性預設值強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="47a6c-188">MFA enforced with security defaults</span></span>   | <span data-ttu-id="47a6c-189">要求第二種形式的登入驗證，以防止身分識別和裝置遭到入侵。安全性預設值要求所有使用者帳戶使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="47a6c-189">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="47a6c-190">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-190">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="47a6c-191">使用條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="47a6c-191">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="47a6c-192">根據具有條件式存取原則之登入的屬性，需要 MFA。</span><span class="sxs-lookup"><span data-stu-id="47a6c-192">Require MFA based on the attributes of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="47a6c-193">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-193">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-194">使用風險型條件式存取強制執行 MFA</span><span class="sxs-lookup"><span data-stu-id="47a6c-194">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="47a6c-195">根據使用適用於身分識別的 Microsoft Defender 的使用者登入的風險，要求使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="47a6c-195">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="47a6c-196">Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權)</span><span class="sxs-lookup"><span data-stu-id="47a6c-196">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="47a6c-197">自助式密碼重設 (SSPR)</span><span class="sxs-lookup"><span data-stu-id="47a6c-197">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="47a6c-198">允許您的使用者重設或解除鎖定他們的密碼或帳戶。</span><span class="sxs-lookup"><span data-stu-id="47a6c-198">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="47a6c-199">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-199">Microsoft 365 E3 or E5</span></span> |
||||

### <a name="migration"></a><span data-ttu-id="47a6c-200">移轉</span><span class="sxs-lookup"><span data-stu-id="47a6c-200">Migration</span></span>

| <span data-ttu-id="47a6c-201">功能</span><span class="sxs-lookup"><span data-stu-id="47a6c-201">Capability or feature</span></span> | <span data-ttu-id="47a6c-202">描述</span><span class="sxs-lookup"><span data-stu-id="47a6c-202">Description</span></span> | <span data-ttu-id="47a6c-203">授權</span><span class="sxs-lookup"><span data-stu-id="47a6c-203">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="47a6c-204">移轉至 Windows 10</span><span class="sxs-lookup"><span data-stu-id="47a6c-204">Migrate to Windows 10</span></span> | <span data-ttu-id="47a6c-205">將執行 Windows 7 或 Windows 8.1 的裝置遷移至 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="47a6c-205">Migrate your devices that run Windows 7 or Windows 8.1 to Windows 10 Enterprise.</span></span> | <span data-ttu-id="47a6c-206">Windows 10 企業版包含 Microsoft 365 E3 或 E5 的授權</span><span class="sxs-lookup"><span data-stu-id="47a6c-206">Windows 10 Enterprise licenses included with Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-207">遷移至 Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="47a6c-207">Migrate to Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="47a6c-208">將 Office 用戶端應用程式（如 Word）和 PowerPoint，遷移至以新功能更新的雲端版本。</span><span class="sxs-lookup"><span data-stu-id="47a6c-208">Migrate your Office client apps such as Word and PowerPoint to the versions installed from the cloud that are updated with new features.</span></span> | <span data-ttu-id="47a6c-209">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-209">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-210">將內部部署伺服器和資料移轉至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="47a6c-210">Migrate on-premises servers and data to Microsoft 365</span></span> | <span data-ttu-id="47a6c-211">將您的 Exchange 信箱、SharePoint 網站和商務用 Skype 線上遷移，以 Microsoft 365 雲端服務。</span><span class="sxs-lookup"><span data-stu-id="47a6c-211">Migrate your Exchange mailboxes, SharePoint sites, and Skype for Business Online to Microsoft 365 cloud services.</span></span> | <span data-ttu-id="47a6c-212">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-212">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="device-and-app-management"></a><span data-ttu-id="47a6c-213">裝置和應用程式管理</span><span class="sxs-lookup"><span data-stu-id="47a6c-213">Device and app management</span></span>

| <span data-ttu-id="47a6c-214">功能</span><span class="sxs-lookup"><span data-stu-id="47a6c-214">Capability or feature</span></span> | <span data-ttu-id="47a6c-215">描述</span><span class="sxs-lookup"><span data-stu-id="47a6c-215">Description</span></span> | <span data-ttu-id="47a6c-216">授權</span><span class="sxs-lookup"><span data-stu-id="47a6c-216">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="47a6c-217">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="47a6c-217">Microsoft Intune</span></span> | <span data-ttu-id="47a6c-218">提供行動裝置管理 (MDM) 和行動應用程式管理 (MAM) 的雲端式服務，可控制組織的應用程式和裝置的使用方式，包括行動電話、平板電腦和可擕式電腦。</span><span class="sxs-lookup"><span data-stu-id="47a6c-218">A cloud-based service that provides mobile device management (MDM) and mobile application management (MAM) to control how your organization’s application and the devices are used, including mobile phones, tablets, and laptops.</span></span> | <span data-ttu-id="47a6c-219">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-219">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="47a6c-220">設定基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="47a6c-220">Basic Mobility and Security</span></span> | <span data-ttu-id="47a6c-221">使用此內建服務，保護和管理使用者的行動裝置，例如 iphone、ipad、Androids 和 Windows 電話。</span><span class="sxs-lookup"><span data-stu-id="47a6c-221">Secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones with this built-in service.</span></span>  | <span data-ttu-id="47a6c-222">Microsoft 365 E3 或 E5</span><span class="sxs-lookup"><span data-stu-id="47a6c-222">Microsoft 365 E3 or E5</span></span> | 
||||

## <a name="next-steps"></a><span data-ttu-id="47a6c-223">後續步驟</span><span class="sxs-lookup"><span data-stu-id="47a6c-223">Next steps</span></span>

<span data-ttu-id="47a6c-224">使用這些步驟來設定和管理您的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="47a6c-224">Use these steps to set up and manage your Microsoft 365 tenants.</span></span>

1. [<span data-ttu-id="47a6c-225">決定您的承租人</span><span class="sxs-lookup"><span data-stu-id="47a6c-225">Determine your tenants</span></span>](tenant-management-tenants.md)
2. [<span data-ttu-id="47a6c-226">優化網路</span><span class="sxs-lookup"><span data-stu-id="47a6c-226">Optimize your networking</span></span>](tenant-management-networking.md)
3. [<span data-ttu-id="47a6c-227">同步處理您的身分識別並強制執行安全登入</span><span class="sxs-lookup"><span data-stu-id="47a6c-227">Synchronize your identities and enforce secure sign-ins</span></span>](tenant-management-identity.md)
4. [<span data-ttu-id="47a6c-228">遷移內部部署 Office 伺服器與資料</span><span class="sxs-lookup"><span data-stu-id="47a6c-228">Migrate your on-premises Office servers and data</span></span>](tenant-management-migration.md)
5. [<span data-ttu-id="47a6c-229">部署裝置和應用程式管理</span><span class="sxs-lookup"><span data-stu-id="47a6c-229">Deploy device and app management</span></span>](tenant-management-device-management.md)

<span data-ttu-id="47a6c-230">[![部署及管理 Microsoft 365 租使用者的步驟](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="47a6c-230">[![The steps to deploy and manage a Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span></span>

<span data-ttu-id="47a6c-231">每個步驟都說明部署選項、摘要結果及日常維護工作。</span><span class="sxs-lookup"><span data-stu-id="47a6c-231">Each step describes deployment options, summarizes the results, and ongoing maintenance tasks.</span></span>

<span data-ttu-id="47a6c-232">若要瞭解虛構但具有代表性的跨國組織如何部署其 Microsoft 365 租使用者的元素，請參閱[Contoso 案例研究](../enterprise/contoso-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="47a6c-232">To understand how a fictional but representative multi-national organization deployed the elements of their Microsoft 365 tenant, see the [Contoso case study](../enterprise/contoso-case-study.md).</span></span>
