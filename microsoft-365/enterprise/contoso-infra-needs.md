---
title: Contoso 的 IT 基礎結構與業務需求
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 內部部署 IT 基礎結構的基本結構，以及 Microsoft 365 企業版如何符合其業務需求。
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369584"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="1f02e-103">Contoso 的 IT 基礎結構與業務需求</span><span class="sxs-lookup"><span data-stu-id="1f02e-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="1f02e-104">**摘要：** 了解 Contoso 內部部署 IT 基礎結構的基本結構，以及 Microsoft 365 企業版如何符合其業務需求。</span><span class="sxs-lookup"><span data-stu-id="1f02e-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="1f02e-105">Contoso 已進行基礎結構轉型作業，即將從內部部署的集中式 IT 基礎結構轉換至整合雲端的個人生產力工作負載和應用程式之融合雲端的 IT 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="1f02e-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="1f02e-106">Contoso 的現有 IT 基礎結構</span><span class="sxs-lookup"><span data-stu-id="1f02e-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="1f02e-107">Contoso 使用絕大部分屬於集中式的內部部署 IT 基礎結構，配合位於巴黎總部的應用程式資料中心。</span><span class="sxs-lookup"><span data-stu-id="1f02e-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="1f02e-108">圖 1 顯示總部辦公室與應用程式資料中心、DMZ 和網際網路。</span><span class="sxs-lookup"><span data-stu-id="1f02e-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Contoso 的現有 IT 基礎結構](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="1f02e-110">**圖 1：Contoso 的現有 IT 基礎結構**</span><span class="sxs-lookup"><span data-stu-id="1f02e-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="1f02e-111">內部部署應用程式資料中心裝載：</span><span class="sxs-lookup"><span data-stu-id="1f02e-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="1f02e-112">使用 SQL Server 與其他 Linux 資料庫的自訂企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f02e-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="1f02e-113">一組舊版 SharePoint 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f02e-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="1f02e-114">用於檔案儲存的組織和小組層級伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f02e-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="1f02e-115">此外，每個區域中樞辦公室都支援一組有類似應用程式的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1f02e-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="1f02e-116">這些伺服器都受到區域 IT 部門的控制。</span><span class="sxs-lookup"><span data-stu-id="1f02e-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="1f02e-117">這些個別多地理區域資料中心之應用程式和資料的可搜尋性，一直是個挑戰。</span><span class="sxs-lookup"><span data-stu-id="1f02e-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="1f02e-118">在 Contoso 的總部 DMZ 中，不同的伺服器組合提供︰</span><span class="sxs-lookup"><span data-stu-id="1f02e-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="1f02e-119">Contoso 客戶訂購產品、零件、耗材或服務的公用網站主機服務。</span><span class="sxs-lookup"><span data-stu-id="1f02e-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="1f02e-120">用於合作夥伴通訊和共同作業的 Contoso 合作夥伴外部網路主機服務。</span><span class="sxs-lookup"><span data-stu-id="1f02e-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="1f02e-121">為巴黎總部的員工提供連結至 Contoso 內部網路的虛擬私人網路 (VPN) 型遠端存取與 Web Proxy 處理。</span><span class="sxs-lookup"><span data-stu-id="1f02e-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="1f02e-122">Contoso 的業務需求</span><span class="sxs-lookup"><span data-stu-id="1f02e-122">Contoso's business needs</span></span>

<span data-ttu-id="1f02e-123">Contoso 的業務需求分成五個主要類別。</span><span class="sxs-lookup"><span data-stu-id="1f02e-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="1f02e-124">生產力：</span><span class="sxs-lookup"><span data-stu-id="1f02e-124">Productivity:</span></span>

- <span data-ttu-id="1f02e-125">讓共同作業更輕鬆</span><span class="sxs-lookup"><span data-stu-id="1f02e-125">Make collaboration easier</span></span>

  <span data-ttu-id="1f02e-126">使用線上模型取代電子郵件和檔案共用型共同作業，該模型允許對文件即時變更、線上會議更簡單，以及擷取對話串。</span><span class="sxs-lookup"><span data-stu-id="1f02e-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="1f02e-127">改善遠端和行動工作者的生產力</span><span class="sxs-lookup"><span data-stu-id="1f02e-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="1f02e-128">有許多員工是在家或在現場工作，透過有效率地存取雲端中的 Contoso 資料與資源，來取代有瓶頸的 VPN 解決方案。</span><span class="sxs-lookup"><span data-stu-id="1f02e-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="1f02e-129">增加創意和創新</span><span class="sxs-lookup"><span data-stu-id="1f02e-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="1f02e-130">利用最新的視覺學習和想法開發方法，包括筆跡和 3D 視覺效果。</span><span class="sxs-lookup"><span data-stu-id="1f02e-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="1f02e-131">安全性：</span><span class="sxs-lookup"><span data-stu-id="1f02e-131">Security:</span></span>

- <span data-ttu-id="1f02e-132">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="1f02e-132">Identity and access management</span></span>

  <span data-ttu-id="1f02e-133">強制執行多重要素和其他形式的驗證，保護使用者和系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="1f02e-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="1f02e-134">威脅防護</span><span class="sxs-lookup"><span data-stu-id="1f02e-134">Threat protection</span></span>

  <span data-ttu-id="1f02e-135">防範外部安全性威脅，包括電子郵件和作業系統型惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="1f02e-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="1f02e-136">資訊保護</span><span class="sxs-lookup"><span data-stu-id="1f02e-136">Information protection</span></span>

  <span data-ttu-id="1f02e-137">加密高價值數位資產並鎖定其存取權，例如客戶資料、設計與製造規格和員工資訊。</span><span class="sxs-lookup"><span data-stu-id="1f02e-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="1f02e-138">安全性管理</span><span class="sxs-lookup"><span data-stu-id="1f02e-138">Security management</span></span>

  <span data-ttu-id="1f02e-139">監視安全性狀態，以便偵測並即時回應威脅。</span><span class="sxs-lookup"><span data-stu-id="1f02e-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="1f02e-140">遠端和行動裝置存取與商務合作夥伴：</span><span class="sxs-lookup"><span data-stu-id="1f02e-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="1f02e-141">更好的遠端和行動工作者安全性</span><span class="sxs-lookup"><span data-stu-id="1f02e-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="1f02e-142">制定攜帶您自己的裝置 (BYOD) 和公司擁有裝置管理措施，以確保安全的存取、正確的應用程式行為，以及公司資料保護。</span><span class="sxs-lookup"><span data-stu-id="1f02e-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="1f02e-143">減少員工的遠端存取基礎結構</span><span class="sxs-lookup"><span data-stu-id="1f02e-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="1f02e-144">藉由將經常存取的資源移至雲端，減少維護和支援成本並且改善遠端存取解決方案的效能。</span><span class="sxs-lookup"><span data-stu-id="1f02e-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="1f02e-145">針對企業對企業 (B2B) 的交易提供更好的連線能力並降低額外負荷</span><span class="sxs-lookup"><span data-stu-id="1f02e-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="1f02e-146">以使用同盟驗證的雲端式解決方案來取代過時且昂貴的合作夥伴外部網路。</span><span class="sxs-lookup"><span data-stu-id="1f02e-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="1f02e-147">合規性：</span><span class="sxs-lookup"><span data-stu-id="1f02e-147">Compliance:</span></span>

- <span data-ttu-id="1f02e-148">遵循地區性法規的需求</span><span class="sxs-lookup"><span data-stu-id="1f02e-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="1f02e-149">成為並持續符合產業與區域的法規，包括資料儲存、加密、資料隱私權和個人資料法規，例如歐盟的一般資料保護規定 (GDPR)。</span><span class="sxs-lookup"><span data-stu-id="1f02e-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="1f02e-150">管理：</span><span class="sxs-lookup"><span data-stu-id="1f02e-150">Management:</span></span>

- <span data-ttu-id="1f02e-151">降低針對在電腦和裝置上執行之軟體進行管理的 IT 額外負荷</span><span class="sxs-lookup"><span data-stu-id="1f02e-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="1f02e-152">自動安裝更新到整個組織的 Windows 作業系統和 Microsoft Office 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="1f02e-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="1f02e-153">將 Contoso 的業務需求對應至 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="1f02e-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1f02e-154">Contoso 的 IT 部門決定在部署之前，將下列業務需求對應至 Microsoft 365 企業版 E5 功能：</span><span class="sxs-lookup"><span data-stu-id="1f02e-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="1f02e-155">**類別**</span><span class="sxs-lookup"><span data-stu-id="1f02e-155">**Category**</span></span> | <span data-ttu-id="1f02e-156">**業務需求**</span><span class="sxs-lookup"><span data-stu-id="1f02e-156">**Business need**</span></span> | <span data-ttu-id="1f02e-157">**Microsoft 365 企業版產品或功能**</span><span class="sxs-lookup"><span data-stu-id="1f02e-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="1f02e-158">生產力</span><span class="sxs-lookup"><span data-stu-id="1f02e-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="1f02e-159">讓共同作業更輕鬆</span><span class="sxs-lookup"><span data-stu-id="1f02e-159">Make collaboration easier</span></span> | <span data-ttu-id="1f02e-160">Microsoft Teams、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="1f02e-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="1f02e-161">改善遠端和行動工作者的生產力</span><span class="sxs-lookup"><span data-stu-id="1f02e-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="1f02e-162">Microsoft 365 工作負載和雲端式資料</span><span class="sxs-lookup"><span data-stu-id="1f02e-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="1f02e-163">增加創意和創新</span><span class="sxs-lookup"><span data-stu-id="1f02e-163">Increase creativity and innovation</span></span> | <span data-ttu-id="1f02e-164">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="1f02e-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="1f02e-165">安全性</span><span class="sxs-lookup"><span data-stu-id="1f02e-165">Security</span></span> |  |  |
|  | <span data-ttu-id="1f02e-166">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="1f02e-166">Identity & access management</span></span> | <span data-ttu-id="1f02e-167">具有 Azure 多重要素驗證 (MFA) 與 Azure AD Privileged Identity Management (PIM) 的專用全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="1f02e-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="1f02e-168">適用於所有使用者帳戶的 MFA</span><span class="sxs-lookup"><span data-stu-id="1f02e-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="1f02e-169">條件式存取</span><span class="sxs-lookup"><span data-stu-id="1f02e-169">Conditional access</span></span> <BR> <span data-ttu-id="1f02e-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="1f02e-170">Windows Hello</span></span> <BR> <span data-ttu-id="1f02e-171">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="1f02e-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="1f02e-172">威脅防護</span><span class="sxs-lookup"><span data-stu-id="1f02e-172">Threat protection</span></span> | <span data-ttu-id="1f02e-173">進階威脅分析</span><span class="sxs-lookup"><span data-stu-id="1f02e-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="1f02e-174">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="1f02e-174">Windows Defender</span></span> <BR> <span data-ttu-id="1f02e-175">進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="1f02e-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="1f02e-176">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="1f02e-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="1f02e-177">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="1f02e-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="1f02e-178">資訊保護</span><span class="sxs-lookup"><span data-stu-id="1f02e-178">Information protection</span></span> | <span data-ttu-id="1f02e-179">Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="1f02e-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="1f02e-180">Office 365 資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="1f02e-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="1f02e-181">Windows 資訊保護 (WIP)</span><span class="sxs-lookup"><span data-stu-id="1f02e-181">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="1f02e-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1f02e-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="1f02e-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1f02e-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="1f02e-184">安全性管理</span><span class="sxs-lookup"><span data-stu-id="1f02e-184">Security management</span></span> | <span data-ttu-id="1f02e-185">Azure 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="1f02e-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="1f02e-186">Windows Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="1f02e-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="1f02e-187">遠端和行動裝置存取與商務合作夥伴</span><span class="sxs-lookup"><span data-stu-id="1f02e-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="1f02e-188">更好的遠端和行動工作者安全性</span><span class="sxs-lookup"><span data-stu-id="1f02e-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="1f02e-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1f02e-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="1f02e-190">減少員工的遠端存取基礎結構</span><span class="sxs-lookup"><span data-stu-id="1f02e-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="1f02e-191">Microsoft 365 工作負載和雲端式資料</span><span class="sxs-lookup"><span data-stu-id="1f02e-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="1f02e-192">針對 B2B 的交易提供更好的連線能力並降低額外負荷</span><span class="sxs-lookup"><span data-stu-id="1f02e-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="1f02e-193">同盟驗證和雲端式資源</span><span class="sxs-lookup"><span data-stu-id="1f02e-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="1f02e-194">合規性</span><span class="sxs-lookup"><span data-stu-id="1f02e-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="1f02e-195">遵循地區性法規的需求</span><span class="sxs-lookup"><span data-stu-id="1f02e-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="1f02e-196">Office 365 中的 GDPR 功能</span><span class="sxs-lookup"><span data-stu-id="1f02e-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="1f02e-197">管理</span><span class="sxs-lookup"><span data-stu-id="1f02e-197">Management</span></span> |  |  |
|  | <span data-ttu-id="1f02e-198">降低安裝用戶端更新的 IT 額外負荷</span><span class="sxs-lookup"><span data-stu-id="1f02e-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="1f02e-199">部署通道</span><span class="sxs-lookup"><span data-stu-id="1f02e-199">Deployment rings</span></span> <BR> <span data-ttu-id="1f02e-200">Windows 10 企業版更新</span><span class="sxs-lookup"><span data-stu-id="1f02e-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="1f02e-201">Office 365 專業增強版更新</span><span class="sxs-lookup"><span data-stu-id="1f02e-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="1f02e-202">下一步</span><span class="sxs-lookup"><span data-stu-id="1f02e-202">Next step</span></span>

<span data-ttu-id="1f02e-203">[了解](contoso-networking.md) Contoso Corporation 內部部署網路，以及它如何針對 Microsoft 365 雲端式資源的存取和延遲最佳化。</span><span class="sxs-lookup"><span data-stu-id="1f02e-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f02e-204">請參閱</span><span class="sxs-lookup"><span data-stu-id="1f02e-204">See also</span></span>

[<span data-ttu-id="1f02e-205">部署指南</span><span class="sxs-lookup"><span data-stu-id="1f02e-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1f02e-206">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="1f02e-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
