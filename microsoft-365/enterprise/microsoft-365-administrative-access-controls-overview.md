---
title: Microsoft 365 中的管理存取控制
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 本文提供 Microsoft 365 中的「管理存取控制」和「資料分類」的概述。
ms.openlocfilehash: b5063f89e89b6cffffda53a5df3088a80f89c242
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688307"
---
# <a name="administrative-access-controls-in-microsoft-365"></a><span data-ttu-id="f7469-103">Microsoft 365 中的管理存取控制</span><span class="sxs-lookup"><span data-stu-id="f7469-103">Administrative access controls in Microsoft 365</span></span> 

<span data-ttu-id="f7469-104">Microsoft 投入大量的系統和控制，可自動化大多數的 Microsoft 365 作業，並在 Microsoft 中故意限制存取客戶內容。</span><span class="sxs-lookup"><span data-stu-id="f7469-104">Microsoft has invested heavily in systems and controls that automate most Microsoft 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="f7469-105">人工管理服務，軟體會運作服務。</span><span class="sxs-lookup"><span data-stu-id="f7469-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="f7469-106">這可讓 Microsoft 以比例管理 Microsoft 365，以管理對客戶內容的內部威脅風險。</span><span class="sxs-lookup"><span data-stu-id="f7469-106">This enables Microsoft to manage Microsoft 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="f7469-107">根據預設，Microsoft 工程師在使用 Microsoft 365 的系統管理許可權中有零的管理許可權，且可以存取客戶內容。</span><span class="sxs-lookup"><span data-stu-id="f7469-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Microsoft 365.</span></span> <span data-ttu-id="f7469-108">Microsoft 工程師在有限的時間內，可對客戶的內容進行有限、經過審核和安全的存取。</span><span class="sxs-lookup"><span data-stu-id="f7469-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="f7469-109">只有在服務作業必要時才能存取，而且只有在 Microsoft 高層管理成員核准時，才可存取。</span><span class="sxs-lookup"><span data-stu-id="f7469-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="f7469-110">針對客戶密碼箱授權的客戶，客戶可對其主控于 Microsoft 365 的內容提供存取核准。</span><span class="sxs-lookup"><span data-stu-id="f7469-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Microsoft 365.</span></span>

<span data-ttu-id="f7469-111">Microsoft 提供使用多種形式的雲端傳遞的線上服務：</span><span class="sxs-lookup"><span data-stu-id="f7469-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="f7469-112">**公用雲彩：** 包含多承租人版本的 Microsoft 365、Azure 及其他主控于北美、南美洲、歐洲、亞洲、澳大利亞等的服務。</span><span class="sxs-lookup"><span data-stu-id="f7469-112">**Public clouds:** Includes multi-tenant versions of Microsoft 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="f7469-113">**國家雲彩：** 包括美國以外的所有以及主權和協力廠商運作的雲彩 (，但除了上述) 之外，它是由 Microsoft 運作的中國 (中的 Microsoft 365，而由 Microsoft 使用的德國) 中的 Microsoft 365，但在該模型下，在此模型中，您可以控制並監控 Microsoft 對客戶資料和包含客戶資料 (的系統的存取。</span><span class="sxs-lookup"><span data-stu-id="f7469-113">**National clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Microsoft 365 in China (operated by 21Vianet), and Microsoft 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to customer data and systems that contain customer data).</span></span>
- <span data-ttu-id="f7469-114">**政府雲彩：** 包含適用于美國政府客戶的 Microsoft 365 和 Azure 服務。</span><span class="sxs-lookup"><span data-stu-id="f7469-114">**Government clouds:** Includes Microsoft 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="f7469-115">基於本文的目的，Microsoft 365 服務包括：</span><span class="sxs-lookup"><span data-stu-id="f7469-115">For purposes of this article, Microsoft 365 services include:</span></span>

- [<span data-ttu-id="f7469-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f7469-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="f7469-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f7469-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="f7469-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f7469-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="f7469-119">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f7469-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="f7469-120">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="f7469-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="f7469-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7469-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="f7469-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="f7469-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a><span data-ttu-id="f7469-123">Microsoft 365 存取控制</span><span class="sxs-lookup"><span data-stu-id="f7469-123">Microsoft 365 access controls</span></span>

<span data-ttu-id="f7469-124">針對存取控制目的，Microsoft 會將 Microsoft 365 資料分類為客戶資料或其他類型的資料。</span><span class="sxs-lookup"><span data-stu-id="f7469-124">For access control purposes, Microsoft categorizes Microsoft 365 data as customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="f7469-125">客戶資料</span><span class="sxs-lookup"><span data-stu-id="f7469-125">Customer data</span></span>

<span data-ttu-id="f7469-126">「客戶資料」是使用 Microsoft 365 服務時，代表客戶提供的所有資料。</span><span class="sxs-lookup"><span data-stu-id="f7469-126">Customer data is all data provided by or on behalf of a customer when using Microsoft 365 services.</span></span> <span data-ttu-id="f7469-127">這是 Microsoft 365 使用者直接建立或上傳的客戶內容，包括：</span><span class="sxs-lookup"><span data-stu-id="f7469-127">This is customer content directly created or uploaded by Microsoft 365 users, including:</span></span>

- <span data-ttu-id="f7469-128">電子郵件</span><span class="sxs-lookup"><span data-stu-id="f7469-128">Emails</span></span>
- <span data-ttu-id="f7469-129">SharePoint 線上內容</span><span class="sxs-lookup"><span data-stu-id="f7469-129">SharePoint Online content</span></span>
- <span data-ttu-id="f7469-130">立即訊息</span><span class="sxs-lookup"><span data-stu-id="f7469-130">Instant messages</span></span>
- <span data-ttu-id="f7469-131">行事曆專案</span><span class="sxs-lookup"><span data-stu-id="f7469-131">Calendar items</span></span>
- <span data-ttu-id="f7469-132">文件</span><span class="sxs-lookup"><span data-stu-id="f7469-132">Documents</span></span>
- <span data-ttu-id="f7469-133">Contacts</span><span class="sxs-lookup"><span data-stu-id="f7469-133">Contacts</span></span>
- <span data-ttu-id="f7469-134">使用者識別資訊 (EUII () 使用者特有或 linkable 個別使用者的資料，但不包括客戶內容) </span><span class="sxs-lookup"><span data-stu-id="f7469-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content)</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="f7469-135">其他類型的資料</span><span class="sxs-lookup"><span data-stu-id="f7469-135">Other types of data</span></span>

<span data-ttu-id="f7469-136">其他類型的資料包括：</span><span class="sxs-lookup"><span data-stu-id="f7469-136">Other types of data include:</span></span>

- <span data-ttu-id="f7469-137">**帳戶資料：** 包含系統管理員在註冊或購買服務) 時所提供的管理資料 (資訊，以及付款資料 (相關的付款資訊，例如信用卡詳細資料) 。</span><span class="sxs-lookup"><span data-stu-id="f7469-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="f7469-138">**組織識別資訊：** 包含用來識別租使用者、使用狀況資料，而不是 linkable 給個別使用者或包含在客戶內容中的資料。</span><span class="sxs-lookup"><span data-stu-id="f7469-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="f7469-139">**系統中繼資料：** 包含服務記錄，包含有關訂閱及承租人的設定設定、系統狀態、Microsoft IP 位址和技術資訊。</span><span class="sxs-lookup"><span data-stu-id="f7469-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="f7469-140">Microsoft 已建立存取控制機制，以確保沒有人撤銷對客戶資料或存取控制資料的存取。</span><span class="sxs-lookup"><span data-stu-id="f7469-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="f7469-141">存取控制資料可管理環境中其他類型的資料或功能，包括存取客戶內容或 EUII、Microsoft 密碼、安全性憑證及其他驗證相關資料。</span><span class="sxs-lookup"><span data-stu-id="f7469-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="f7469-142">存取控制機制也會防止對 Microsoft 365 生產環境進行未核准的實體、邏輯或遠端存取。</span><span class="sxs-lookup"><span data-stu-id="f7469-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Microsoft 365 production environment.</span></span>

<span data-ttu-id="f7469-143">Microsoft 使用 Microsoft 365 的存取控制類別有三種：</span><span class="sxs-lookup"><span data-stu-id="f7469-143">There are three categories of access controls used by Microsoft for operating Microsoft 365:</span></span>

- <span data-ttu-id="f7469-144">隔離控制項</span><span class="sxs-lookup"><span data-stu-id="f7469-144">Isolation controls</span></span>
- <span data-ttu-id="f7469-145">人員控制</span><span class="sxs-lookup"><span data-stu-id="f7469-145">Personnel controls</span></span>
- <span data-ttu-id="f7469-146">技術控制項</span><span class="sxs-lookup"><span data-stu-id="f7469-146">Technology controls</span></span>

<span data-ttu-id="f7469-147">結合時，這些控制項可協助防止及偵測 Microsoft 365 中的惡意動作。</span><span class="sxs-lookup"><span data-stu-id="f7469-147">When combined, these controls help prevent and detect malicious actions in Microsoft 365.</span></span> <span data-ttu-id="f7469-148">除了 Microsoft 所用的隔離、人員和技術控制項之外，還有第四個控制項類別：由客戶實施。</span><span class="sxs-lookup"><span data-stu-id="f7469-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="f7469-149">Microsoft 365 可讓您在內部部署環境中管理資料的方式相同。</span><span class="sxs-lookup"><span data-stu-id="f7469-149">Microsoft 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="f7469-150">註冊 Microsoft 365 組織的人員，會自動成為全域管理員。</span><span class="sxs-lookup"><span data-stu-id="f7469-150">The person who signs up an organization for Microsoft 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="f7469-151">全域管理員可以存取管理入口網站中的所有功能，而且可以：</span><span class="sxs-lookup"><span data-stu-id="f7469-151">The global admin has access to all features in management portals and can:</span></span>

- <span data-ttu-id="f7469-152">建立或編輯使用者</span><span class="sxs-lookup"><span data-stu-id="f7469-152">Create or edit users</span></span>
- <span data-ttu-id="f7469-153">指派系統管理員角色給其他人</span><span class="sxs-lookup"><span data-stu-id="f7469-153">Assign admin roles to others</span></span>
- <span data-ttu-id="f7469-154">重設使用者密碼</span><span class="sxs-lookup"><span data-stu-id="f7469-154">Reset user passwords</span></span>
- <span data-ttu-id="f7469-155">管理使用者授權</span><span class="sxs-lookup"><span data-stu-id="f7469-155">Manage user licenses</span></span>
- <span data-ttu-id="f7469-156">管理網域</span><span class="sxs-lookup"><span data-stu-id="f7469-156">Manage domains</span></span>
- <span data-ttu-id="f7469-157">核准客戶加密箱要求</span><span class="sxs-lookup"><span data-stu-id="f7469-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="f7469-158">建議每個組織至少要設定兩個系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="f7469-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="f7469-159">對於大型企業組織，我們建議針對不同功能的特殊系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="f7469-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="f7469-160">如需指派系統管理員角色和許可權的相關資訊，請參閱 [指派系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) 及 [關於系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="f7469-160">For information about assigning admin roles and permissions, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) and [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-links"></a><span data-ttu-id="f7469-161">相關連結</span><span class="sxs-lookup"><span data-stu-id="f7469-161">Related Links</span></span>

- [<span data-ttu-id="f7469-162">隔離控制項</span><span class="sxs-lookup"><span data-stu-id="f7469-162">Isolation Controls</span></span>](microsoft-365-isolation-controls.md)
- [<span data-ttu-id="f7469-163">人員控制</span><span class="sxs-lookup"><span data-stu-id="f7469-163">Personnel Controls</span></span>](microsoft-365-personnel-controls.md)
- [<span data-ttu-id="f7469-164">技術控制項</span><span class="sxs-lookup"><span data-stu-id="f7469-164">Technology Controls</span></span>](microsoft-365-technology-controls.md)
- [<span data-ttu-id="f7469-165">監視及稽核的存取控制</span><span class="sxs-lookup"><span data-stu-id="f7469-165">Monitoring and Auditing Access Controls</span></span>](microsoft-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="f7469-166">Yammer 企業存取控制</span><span class="sxs-lookup"><span data-stu-id="f7469-166">Yammer Enterprise Access Controls</span></span>](microsoft-365-yammer-enterprise-access-controls.md)
