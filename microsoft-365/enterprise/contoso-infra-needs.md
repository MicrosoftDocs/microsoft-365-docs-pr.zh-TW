---
title: Contoso IT 基礎結構和業務需求
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 瞭解 Contoso 內部部署 IT 基礎結構的基本結構，以及 Microsoft 365 for enterprise 如何滿足公司的業務需求。
ms.openlocfilehash: 767374097efa116f116cff6f6ddf96d075eb71ed
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754583"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="a091d-103">Contoso IT 基礎結構和業務需求</span><span class="sxs-lookup"><span data-stu-id="a091d-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="a091d-104">Contoso 會從內部部署的集中式 IT 基礎結構轉換至包含雲端式個人生產力工作負載和應用程式的雲端包容安裝。</span><span class="sxs-lookup"><span data-stu-id="a091d-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="a091d-105">現有 Contoso IT 基礎結構</span><span class="sxs-lookup"><span data-stu-id="a091d-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="a091d-106">Contoso 使用絕大部分屬於集中式的內部部署 IT 基礎結構，配合位於巴黎總部的應用程式資料中心。</span><span class="sxs-lookup"><span data-stu-id="a091d-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="a091d-107">以下是具有應用程式資料中心、DMZ 和網際網路的總部辦公室。</span><span class="sxs-lookup"><span data-stu-id="a091d-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![現有 Contoso IT 基礎結構](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="a091d-109">內部部署應用程式資料中心裝載：</span><span class="sxs-lookup"><span data-stu-id="a091d-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="a091d-110">使用 SQL Server 及其他 Linux 資料庫的自訂企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="a091d-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="a091d-111">一組舊版 SharePoint 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a091d-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="a091d-112">用於檔案儲存的組織和小組層級伺服器。</span><span class="sxs-lookup"><span data-stu-id="a091d-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="a091d-113">此外，每個區域中樞辦公室都支援一組有類似應用程式的伺服器。</span><span class="sxs-lookup"><span data-stu-id="a091d-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="a091d-114">這些伺服器都受到區域 IT 部門的控制。</span><span class="sxs-lookup"><span data-stu-id="a091d-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="a091d-115">這些個別多地理區域資料中心之應用程式和資料的可搜尋性，一直是個挑戰。</span><span class="sxs-lookup"><span data-stu-id="a091d-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="a091d-116">在 Contoso 總部 DMZ 中，不同的伺服器組提供：</span><span class="sxs-lookup"><span data-stu-id="a091d-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="a091d-117">Contoso 公開網站的主機服務，可供客戶定購產品、元件、用品及服務。</span><span class="sxs-lookup"><span data-stu-id="a091d-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="a091d-118">用於合作夥伴通訊和共同作業的 Contoso 合作夥伴外部網路主機服務。</span><span class="sxs-lookup"><span data-stu-id="a091d-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="a091d-119">為巴黎總部的員工提供連結至 Contoso 內部網路的虛擬私人網路 (VPN) 型遠端存取與 Web Proxy 處理。</span><span class="sxs-lookup"><span data-stu-id="a091d-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="a091d-120">Contoso 商務需求</span><span class="sxs-lookup"><span data-stu-id="a091d-120">Contoso business needs</span></span>

<span data-ttu-id="a091d-121">Contoso 商務需求分為五個主要類別：</span><span class="sxs-lookup"><span data-stu-id="a091d-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="a091d-122">**生產力**</span><span class="sxs-lookup"><span data-stu-id="a091d-122">**Productivity**</span></span>

- <span data-ttu-id="a091d-123">讓共同作業更輕鬆</span><span class="sxs-lookup"><span data-stu-id="a091d-123">Make collaboration easier</span></span>

  <span data-ttu-id="a091d-124">以線上模型取代電子郵件和檔案共用型共同作業，可讓您即時變更檔、更輕鬆的線上會議，以及已捕獲的交談執行緒。</span><span class="sxs-lookup"><span data-stu-id="a091d-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="a091d-125">改善遠端和行動工作者的生產力</span><span class="sxs-lookup"><span data-stu-id="a091d-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="a091d-126">透過家裡或現場運作的許多員工，使用雲端的可存取權資料和資源，取代瓶頸的 VPN 解決方案。</span><span class="sxs-lookup"><span data-stu-id="a091d-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="a091d-127">增加創意和創新</span><span class="sxs-lookup"><span data-stu-id="a091d-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="a091d-128">利用最新的視覺學習和想法開發方法，包括筆跡和 3D 視覺效果。</span><span class="sxs-lookup"><span data-stu-id="a091d-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="a091d-129">**安全性**</span><span class="sxs-lookup"><span data-stu-id="a091d-129">**Security**</span></span>

- <span data-ttu-id="a091d-130">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="a091d-130">Identity and access management</span></span>

  <span data-ttu-id="a091d-131">強制執行多重要素和其他形式的驗證，並保護使用者和系統管理員帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="a091d-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="a091d-132">威脅防護</span><span class="sxs-lookup"><span data-stu-id="a091d-132">Threat protection</span></span>

  <span data-ttu-id="a091d-133">防範外部安全性威脅，包括電子郵件和作業系統型惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="a091d-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="a091d-134">資訊保護</span><span class="sxs-lookup"><span data-stu-id="a091d-134">Information protection</span></span>

  <span data-ttu-id="a091d-135">加密高價值數位資產並鎖定其存取權，例如客戶資料、設計與製造規格和員工資訊。</span><span class="sxs-lookup"><span data-stu-id="a091d-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="a091d-136">安全性管理</span><span class="sxs-lookup"><span data-stu-id="a091d-136">Security management</span></span>

  <span data-ttu-id="a091d-137">監視安全狀況，並即時偵測威脅並加以回應。</span><span class="sxs-lookup"><span data-stu-id="a091d-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="a091d-138">**遠端和行動裝置存取與商務合作夥伴**</span><span class="sxs-lookup"><span data-stu-id="a091d-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="a091d-139">改進遠端和行動工作者的安全性</span><span class="sxs-lookup"><span data-stu-id="a091d-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="a091d-140">實施會將您自己的裝置 (BYOD) 和公司所擁有的裝置管理，以確保安全的存取、正確的應用程式行為，以及公司資料保護。</span><span class="sxs-lookup"><span data-stu-id="a091d-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="a091d-141">減少員工的遠端存取基礎結構</span><span class="sxs-lookup"><span data-stu-id="a091d-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="a091d-142">將經常存取的資源移至雲端，以降低維護和支援成本並改善遠端存取解決方案的效能。</span><span class="sxs-lookup"><span data-stu-id="a091d-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="a091d-143">為商務對 susiness (B2B) 交易提供更好的連線能力並降低額外負荷</span><span class="sxs-lookup"><span data-stu-id="a091d-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="a091d-144">使用採用同盟驗證的雲端式解決方案，取代老化且昂貴的合作夥伴外部網路。</span><span class="sxs-lookup"><span data-stu-id="a091d-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="a091d-145">**合規性**</span><span class="sxs-lookup"><span data-stu-id="a091d-145">**Compliance**</span></span>

- <span data-ttu-id="a091d-146">遵循地區性法規的需求</span><span class="sxs-lookup"><span data-stu-id="a091d-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="a091d-147">確定針對資料儲存、加密、資料隱私權和個人資料法規（如一般資料保護法規）的行業和地區性法規，如歐盟的一般資料保護法規 (GDPR) 。</span><span class="sxs-lookup"><span data-stu-id="a091d-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="a091d-148">**管理**</span><span class="sxs-lookup"><span data-stu-id="a091d-148">**Management**</span></span>

- <span data-ttu-id="a091d-149">降低在用戶端電腦和裝置上執行軟體的管理成本。</span><span class="sxs-lookup"><span data-stu-id="a091d-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="a091d-150">自動將更新安裝至整個組織中的 Windows 作業系統和 Microsoft 365 應用程式。</span><span class="sxs-lookup"><span data-stu-id="a091d-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="a091d-151">將 Contoso 商務需求對應至 Microsoft 365 for enterprise</span><span class="sxs-lookup"><span data-stu-id="a091d-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="a091d-152">Contoso IT 部門決定在部署之前，下列業務需求對應至 Microsoft 365 E5 功能：</span><span class="sxs-lookup"><span data-stu-id="a091d-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="a091d-153">類別</span><span class="sxs-lookup"><span data-stu-id="a091d-153">Category</span></span> | <span data-ttu-id="a091d-154">商務需求</span><span class="sxs-lookup"><span data-stu-id="a091d-154">Business need</span></span> | <span data-ttu-id="a091d-155">適用于企業產品或功能的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a091d-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="a091d-156">生產力</span><span class="sxs-lookup"><span data-stu-id="a091d-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="a091d-157">讓共同作業更輕鬆</span><span class="sxs-lookup"><span data-stu-id="a091d-157">Make collaboration easier</span></span> | <span data-ttu-id="a091d-158">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="a091d-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="a091d-159">改善遠端和行動工作者的生產力</span><span class="sxs-lookup"><span data-stu-id="a091d-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="a091d-160">Microsoft 365 工作負載和雲端式資料</span><span class="sxs-lookup"><span data-stu-id="a091d-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="a091d-161">增加創意和創新</span><span class="sxs-lookup"><span data-stu-id="a091d-161">Increase creativity and innovation</span></span> | <span data-ttu-id="a091d-162">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="a091d-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="a091d-163">安全性</span><span class="sxs-lookup"><span data-stu-id="a091d-163">Security</span></span> |  |  |
|  | <span data-ttu-id="a091d-164">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="a091d-164">Identity & access management</span></span> | <span data-ttu-id="a091d-165">具備 Azure Multi-Factor 驗證 (MFA) 和 Azure Active Directory 特權身分識別管理 (PIM) 的專屬全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="a091d-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="a091d-166">適用於所有使用者帳戶的 MFA</span><span class="sxs-lookup"><span data-stu-id="a091d-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="a091d-167">條件式存取</span><span class="sxs-lookup"><span data-stu-id="a091d-167">Conditional Access</span></span> <BR> <span data-ttu-id="a091d-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="a091d-168">Windows Hello</span></span> <BR> <span data-ttu-id="a091d-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="a091d-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="a091d-170">威脅防護</span><span class="sxs-lookup"><span data-stu-id="a091d-170">Threat protection</span></span> | <span data-ttu-id="a091d-171">進階威脅分析</span><span class="sxs-lookup"><span data-stu-id="a091d-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="a091d-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="a091d-172">Windows Defender</span></span> <BR> <span data-ttu-id="a091d-173">進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a091d-173">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="a091d-174">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="a091d-174">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="a091d-175">Microsoft 365 威脅調查和回應</span><span class="sxs-lookup"><span data-stu-id="a091d-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="a091d-176">資訊保護</span><span class="sxs-lookup"><span data-stu-id="a091d-176">Information protection</span></span> | <span data-ttu-id="a091d-177">Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="a091d-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="a091d-178">資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a091d-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="a091d-179">Windows 資訊保護 (WIP)</span><span class="sxs-lookup"><span data-stu-id="a091d-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="a091d-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a091d-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="a091d-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a091d-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="a091d-182">安全性管理</span><span class="sxs-lookup"><span data-stu-id="a091d-182">Security management</span></span> | <span data-ttu-id="a091d-183">Azure 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="a091d-183">Azure Security Center</span></span>  <BR> <span data-ttu-id="a091d-184">Windows Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="a091d-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="a091d-185">遠端和行動裝置存取與商務合作夥伴</span><span class="sxs-lookup"><span data-stu-id="a091d-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="a091d-186">更好的遠端和行動工作者安全性</span><span class="sxs-lookup"><span data-stu-id="a091d-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="a091d-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a091d-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="a091d-188">減少員工的遠端存取基礎結構</span><span class="sxs-lookup"><span data-stu-id="a091d-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="a091d-189">Microsoft 365 工作負載和雲端式資料</span><span class="sxs-lookup"><span data-stu-id="a091d-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="a091d-190">提高 B2B 交易的連線能力並降低負荷</span><span class="sxs-lookup"><span data-stu-id="a091d-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="a091d-191">同盟驗證和雲端式資源</span><span class="sxs-lookup"><span data-stu-id="a091d-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="a091d-192">合規性</span><span class="sxs-lookup"><span data-stu-id="a091d-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="a091d-193">遵循地區性法規的需求</span><span class="sxs-lookup"><span data-stu-id="a091d-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="a091d-194">Microsoft 365 中的 GDPR 功能</span><span class="sxs-lookup"><span data-stu-id="a091d-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="a091d-195">管理</span><span class="sxs-lookup"><span data-stu-id="a091d-195">Management</span></span> |  |  |
|  | <span data-ttu-id="a091d-196">降低安裝用戶端更新的 IT 負荷</span><span class="sxs-lookup"><span data-stu-id="a091d-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="a091d-197">Windows 10 企業版更新</span><span class="sxs-lookup"><span data-stu-id="a091d-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="a091d-198">Microsoft 365 Apps 企業版更新</span><span class="sxs-lookup"><span data-stu-id="a091d-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="a091d-199">下一步</span><span class="sxs-lookup"><span data-stu-id="a091d-199">Next step</span></span>

<span data-ttu-id="a091d-200">深入瞭解 Contoso Corporation [內部部署網路](contoso-networking.md) ，以及其如何針對 Microsoft 365 雲端架構資源進行存取和延遲優化。</span><span class="sxs-lookup"><span data-stu-id="a091d-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="a091d-201">請參閱</span><span class="sxs-lookup"><span data-stu-id="a091d-201">See also</span></span>

[<span data-ttu-id="a091d-202">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="a091d-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a091d-203">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="a091d-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
