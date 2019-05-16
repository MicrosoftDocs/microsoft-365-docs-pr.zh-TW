---
title: Contoso 的 IT 基礎結構與業務需求
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 內部部署 IT 基礎結構的基本結構，以及 Microsoft 365 企業版如何符合其業務需求。
ms.openlocfilehash: e50a2b17544c1a551d25dffd751d12aec1c15ecd
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072613"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="b3c01-103">Contoso 的 IT 基礎結構與業務需求</span><span class="sxs-lookup"><span data-stu-id="b3c01-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="b3c01-104">**摘要：** 了解 Contoso 內部部署 IT 基礎結構的基本結構，以及 Microsoft 365 企業版如何符合其業務需求。</span><span class="sxs-lookup"><span data-stu-id="b3c01-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>


<span data-ttu-id="b3c01-105">Contoso 已進行基礎結構轉型作業，即將從內部部署的集中式 IT 基礎結構轉換至整合雲端的個人生產力工作負載和應用程式之融合雲端的 IT 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="b3c01-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="b3c01-106">Contoso 的現有 IT 基礎結構</span><span class="sxs-lookup"><span data-stu-id="b3c01-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="b3c01-107">Contoso 使用絕大部分屬於集中式的內部部署 IT 基礎結構，配合位於巴黎總部的應用程式資料中心。</span><span class="sxs-lookup"><span data-stu-id="b3c01-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="b3c01-108">圖 1 顯示總部辦公室與應用程式資料中心、DMZ 和網際網路。</span><span class="sxs-lookup"><span data-stu-id="b3c01-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="b3c01-109">**圖 1：Contoso 的現有 IT 基礎結構**</span><span class="sxs-lookup"><span data-stu-id="b3c01-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="b3c01-110">內部部署應用程式資料中心裝載：</span><span class="sxs-lookup"><span data-stu-id="b3c01-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="b3c01-111">使用 SQL Server 與其他 Linux 資料庫的自訂企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3c01-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="b3c01-112">一組舊版 SharePoint 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b3c01-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="b3c01-113">用於檔案儲存的組織和小組層級伺服器。</span><span class="sxs-lookup"><span data-stu-id="b3c01-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="b3c01-p101">此外，還有支援一組伺服器與一組類似應用程式的每個區域中樞辦公室。這些伺服器受區域 IT 部門的控制。</span><span class="sxs-lookup"><span data-stu-id="b3c01-p101">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="b3c01-116">這些個別多地理區域資料中心之應用程式和資料的可搜尋性，一直是個挑戰。</span><span class="sxs-lookup"><span data-stu-id="b3c01-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="b3c01-117">在 Contoso 的總部 DMZ 中，不同的伺服器組合提供︰</span><span class="sxs-lookup"><span data-stu-id="b3c01-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="b3c01-118">為巴黎總部的員工提供連結至 Contoso 內部網路的 VPN 型遠端存取與 Web Proxy 處理。</span><span class="sxs-lookup"><span data-stu-id="b3c01-118">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>
- <span data-ttu-id="b3c01-119">Contoso 客戶訂購產品、零件、耗材或服務的公用網站主機服務。</span><span class="sxs-lookup"><span data-stu-id="b3c01-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="b3c01-120">用於合作夥伴通訊和共同作業的 Contoso 合作夥伴外部網路主機服務。</span><span class="sxs-lookup"><span data-stu-id="b3c01-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="b3c01-121">Contoso 的業務需求</span><span class="sxs-lookup"><span data-stu-id="b3c01-121">Contoso's business needs</span></span>

<span data-ttu-id="b3c01-122">Contoso 的業務需求分成五個主要類別。</span><span class="sxs-lookup"><span data-stu-id="b3c01-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="b3c01-123">生產力：</span><span class="sxs-lookup"><span data-stu-id="b3c01-123">Productivity:</span></span>

- <span data-ttu-id="b3c01-124">讓共同作業更輕鬆</span><span class="sxs-lookup"><span data-stu-id="b3c01-124">Make collaboration easier</span></span>

  <span data-ttu-id="b3c01-125">使用線上模型取代電子郵件和檔案共用型共同作業，該模型允許對文件即時變更、線上會議更簡單，以及擷取對話串。</span><span class="sxs-lookup"><span data-stu-id="b3c01-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="b3c01-126">改善遠端和行動工作者的生產力</span><span class="sxs-lookup"><span data-stu-id="b3c01-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="b3c01-127">有許多員工是在家或在現場工作，透過有效率地存取雲端中的 Contoso 資料與資源，來取代有瓶頸的 VPN 解決方案。</span><span class="sxs-lookup"><span data-stu-id="b3c01-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="b3c01-128">增加創意和創新</span><span class="sxs-lookup"><span data-stu-id="b3c01-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="b3c01-129">利用最新的視覺學習和想法開發方法，包括筆跡和 3D 視覺效果。</span><span class="sxs-lookup"><span data-stu-id="b3c01-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="b3c01-130">安全性：</span><span class="sxs-lookup"><span data-stu-id="b3c01-130">Security:</span></span>

- <span data-ttu-id="b3c01-131">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="b3c01-131">Identity and access management</span></span>

  <span data-ttu-id="b3c01-132">強制執行多重要素和其他形式的驗證，保護使用者和系統管理員帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="b3c01-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="b3c01-133">威脅防護</span><span class="sxs-lookup"><span data-stu-id="b3c01-133">Threat protection</span></span>

  <span data-ttu-id="b3c01-134">防範外部安全性威脅，包括電子郵件和作業系統型惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="b3c01-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="b3c01-135">資訊保護</span><span class="sxs-lookup"><span data-stu-id="b3c01-135">Information protection</span></span>

  <span data-ttu-id="b3c01-136">加密高價值數位資產並鎖定其存取權，例如客戶資料、設計規格和員工資訊。</span><span class="sxs-lookup"><span data-stu-id="b3c01-136">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="b3c01-137">安全性管理</span><span class="sxs-lookup"><span data-stu-id="b3c01-137">Security management</span></span>

  <span data-ttu-id="b3c01-138">監視安全性狀態，以便偵測並即時回應威脅。</span><span class="sxs-lookup"><span data-stu-id="b3c01-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="b3c01-139">遠端和行動裝置存取與商務合作夥伴：</span><span class="sxs-lookup"><span data-stu-id="b3c01-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="b3c01-140">更好的遠端和行動工作者安全性</span><span class="sxs-lookup"><span data-stu-id="b3c01-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="b3c01-141">制定攜帶您自己的裝置 (BYOD) 和公司擁有裝置管理措施，以確保安全的存取、正確的應用程式行為，以及公司資料保護。</span><span class="sxs-lookup"><span data-stu-id="b3c01-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="b3c01-142">減少員工的遠端存取基礎結構</span><span class="sxs-lookup"><span data-stu-id="b3c01-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="b3c01-143">藉由將經常存取的資源移至雲端，減少維護和支援成本並且改善遠端存取解決方案的效能。</span><span class="sxs-lookup"><span data-stu-id="b3c01-143">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="b3c01-144">針對企業對企業 (B2B) 的交易提供更好的連線能力並降低額外負荷</span><span class="sxs-lookup"><span data-stu-id="b3c01-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="b3c01-145">以使用同盟驗證的雲端式解決方案來取代過時且昂貴的合作夥伴外部網路。</span><span class="sxs-lookup"><span data-stu-id="b3c01-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="b3c01-146">合規性：</span><span class="sxs-lookup"><span data-stu-id="b3c01-146">Compliance:</span></span>

- <span data-ttu-id="b3c01-147">遵循地區性法規的需求</span><span class="sxs-lookup"><span data-stu-id="b3c01-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="b3c01-148">成為並持續符合產業與區域的法規，包括資料儲存、加密、資料隱私權和個人資料法規，例如歐盟的一般資料保護規定 (GDPR)。</span><span class="sxs-lookup"><span data-stu-id="b3c01-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="b3c01-149">管理：</span><span class="sxs-lookup"><span data-stu-id="b3c01-149">Management:</span></span>

- <span data-ttu-id="b3c01-150">降低針對在電腦和裝置上執行之軟體進行管理的 IT 額外負荷</span><span class="sxs-lookup"><span data-stu-id="b3c01-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="b3c01-151">自動安裝更新到整個組織的 Windows 作業系統和 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="b3c01-151">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="b3c01-152">將 Contoso 的業務需求對應至 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="b3c01-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b3c01-153">Contoso 的 IT 部門決定在部署之前，將下列業務需求對應至 Microsoft 365 企業版 E5 功能：</span><span class="sxs-lookup"><span data-stu-id="b3c01-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="b3c01-154">**類別**</span><span class="sxs-lookup"><span data-stu-id="b3c01-154">**Category**</span></span> | <span data-ttu-id="b3c01-155">**業務需求**</span><span class="sxs-lookup"><span data-stu-id="b3c01-155">**Business need**</span></span> | <span data-ttu-id="b3c01-156">**Microsoft 365 企業版產品或功能**</span><span class="sxs-lookup"><span data-stu-id="b3c01-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="b3c01-157">生產力</span><span class="sxs-lookup"><span data-stu-id="b3c01-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="b3c01-158">讓共同作業更輕鬆</span><span class="sxs-lookup"><span data-stu-id="b3c01-158">Make collaboration easier</span></span> | <span data-ttu-id="b3c01-159">Teams、SharePoint Online、商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b3c01-159">Teams, SharePoint Online, Skype for Business Online</span></span> |
|  | <span data-ttu-id="b3c01-160">改善遠端和行動工作者的生產力</span><span class="sxs-lookup"><span data-stu-id="b3c01-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="b3c01-161">Office 365 工作負載和雲端式資料</span><span class="sxs-lookup"><span data-stu-id="b3c01-161">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b3c01-162">增加創意和創新</span><span class="sxs-lookup"><span data-stu-id="b3c01-162">Increase creativity and innovation</span></span> | <span data-ttu-id="b3c01-163">Windows Ink、Cortana at Work、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b3c01-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="b3c01-164">安全性</span><span class="sxs-lookup"><span data-stu-id="b3c01-164">Security</span></span> |  |  |
|  | <span data-ttu-id="b3c01-165">身分識別和存取管理</span><span class="sxs-lookup"><span data-stu-id="b3c01-165">Identity & access management</span></span> | <span data-ttu-id="b3c01-166">具有多重要素驗證 (MFA) 與 Azure AD Privileged Identity Management (PIM) 的專用全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="b3c01-166">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="b3c01-167">適用於所有使用者帳戶的 MFA</span><span class="sxs-lookup"><span data-stu-id="b3c01-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="b3c01-168">條件式存取</span><span class="sxs-lookup"><span data-stu-id="b3c01-168">Conditional access</span></span> <BR> <span data-ttu-id="b3c01-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="b3c01-169">Windows Hello</span></span> <BR> <span data-ttu-id="b3c01-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="b3c01-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="b3c01-171">威脅防護</span><span class="sxs-lookup"><span data-stu-id="b3c01-171">Threat protection</span></span> | <span data-ttu-id="b3c01-172">進階威脅分析</span><span class="sxs-lookup"><span data-stu-id="b3c01-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="b3c01-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b3c01-173">Windows Defender</span></span> <BR> <span data-ttu-id="b3c01-174">進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b3c01-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b3c01-175">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="b3c01-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="b3c01-176">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="b3c01-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="b3c01-177">資訊保護</span><span class="sxs-lookup"><span data-stu-id="b3c01-177">Information protection</span></span> | <span data-ttu-id="b3c01-178">Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="b3c01-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="b3c01-179">Office 365 資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="b3c01-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="b3c01-180">Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="b3c01-180">Windows Information Protection</span></span> <BR> <span data-ttu-id="b3c01-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3c01-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="b3c01-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b3c01-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b3c01-183">安全性管理</span><span class="sxs-lookup"><span data-stu-id="b3c01-183">Security management</span></span> | <span data-ttu-id="b3c01-184">Azure 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="b3c01-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="b3c01-185">Windows Defender 資訊安全中心</span><span class="sxs-lookup"><span data-stu-id="b3c01-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="b3c01-186">遠端和行動裝置存取與商務合作夥伴</span><span class="sxs-lookup"><span data-stu-id="b3c01-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="b3c01-187">更好的遠端和行動工作者安全性</span><span class="sxs-lookup"><span data-stu-id="b3c01-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="b3c01-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b3c01-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="b3c01-189">減少員工的遠端存取基礎結構</span><span class="sxs-lookup"><span data-stu-id="b3c01-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="b3c01-190">Office 365 工作負載和雲端式資料</span><span class="sxs-lookup"><span data-stu-id="b3c01-190">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="b3c01-191">針對 B2B 的交易提供更好的連線能力並降低額外負荷</span><span class="sxs-lookup"><span data-stu-id="b3c01-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="b3c01-192">同盟驗證和雲端式資源</span><span class="sxs-lookup"><span data-stu-id="b3c01-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="b3c01-193">合規性</span><span class="sxs-lookup"><span data-stu-id="b3c01-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="b3c01-194">遵循地區性法規的需求</span><span class="sxs-lookup"><span data-stu-id="b3c01-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="b3c01-195">Office 365 中的 GDPR 功能</span><span class="sxs-lookup"><span data-stu-id="b3c01-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="b3c01-196">管理</span><span class="sxs-lookup"><span data-stu-id="b3c01-196">Management</span></span> |  |  |
|  | <span data-ttu-id="b3c01-197">降低安裝用戶端更新的 IT 額外負荷</span><span class="sxs-lookup"><span data-stu-id="b3c01-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="b3c01-198">部署通道</span><span class="sxs-lookup"><span data-stu-id="b3c01-198">Deployment rings</span></span> <BR> <span data-ttu-id="b3c01-199">Windows 10 就地升級和 Autopilot</span><span class="sxs-lookup"><span data-stu-id="b3c01-199">Windows 10 upgrade in place and Autopilot</span></span> <BR> <span data-ttu-id="b3c01-200">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="b3c01-200">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="b3c01-201">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b3c01-201">Next step</span></span>

<span data-ttu-id="b3c01-202">[了解](contoso-networking.md) Contoso Corporation 內部部署網路，以及它如何針對整個組織 Microsoft 365 雲端式資源的存取和延遲最佳化。</span><span class="sxs-lookup"><span data-stu-id="b3c01-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3c01-203">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b3c01-203">See also</span></span>

[<span data-ttu-id="b3c01-204">部署指南</span><span class="sxs-lookup"><span data-stu-id="b3c01-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b3c01-205">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="b3c01-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
