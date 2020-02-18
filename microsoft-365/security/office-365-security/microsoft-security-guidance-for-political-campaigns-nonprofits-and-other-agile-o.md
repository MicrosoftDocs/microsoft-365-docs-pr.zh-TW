---
title: 適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.custom: Strat_O365_Enterprise
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 摘要：此計劃與實作指南適用於因快速發展而導致威脅增加的組織。
ms.openlocfilehash: 475707f2c98ade03f3bd558d5e9ea9eb9b5c64df
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082526"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="c92cc-103">適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南</span><span class="sxs-lookup"><span data-stu-id="c92cc-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

 <span data-ttu-id="c92cc-104">**摘要：** 此計劃與實作指南適用於因快速發展而導致威脅增加的組織。</span><span class="sxs-lookup"><span data-stu-id="c92cc-104">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>
  
<span data-ttu-id="c92cc-p101">如果您的組織很彈性、您擁有小型 IT 團隊，而且您的威脅狀況比一般高，本指南可謂是專為您所設計。 此解決方案示範如何從頭開始快速地建立具有基本雲端服務的環境，這些服務會包含安全控制項。 本指南包含規範的安全性建議，可用來保護行動裝置中的資料、身分識別、電子郵件和存取權。</span><span class="sxs-lookup"><span data-stu-id="c92cc-p101">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you. This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start. This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>
  
## <a name="security-solution-guidance"></a><span data-ttu-id="c92cc-108">安全性解決方案指南</span><span class="sxs-lookup"><span data-stu-id="c92cc-108">Security solution guidance</span></span>

<span data-ttu-id="c92cc-p102">此指南描述如何實作安全的雲端環境。 任何組織都可以使用此解決方案指南。 它為具有 BYOD 存取權和來賓帳戶的彈性組織提供額外的說明。 您可以使用此指南作為起點，來設計您自己的環境。 歡迎您透過 [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com) 提供寶貴的意見。</span><span class="sxs-lookup"><span data-stu-id="c92cc-p102">This guidance describes how to implement a secure cloud environment. The solution guidance can be used by any organization. It includes extra help for agile organizations with BYOD access and guest accounts. You can use this guidance as a starting-point for designing your own environment. We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c92cc-114">**項目**</span><span class="sxs-lookup"><span data-stu-id="c92cc-114">**Item**</span></span> <br/> |<span data-ttu-id="c92cc-115">**描述**</span><span class="sxs-lookup"><span data-stu-id="c92cc-115">**Description**</span></span> <br/> |
|<span data-ttu-id="c92cc-116">**適用於政治活動的 Microsoft 安全性指南**</span><span class="sxs-lookup"><span data-stu-id="c92cc-116">**Microsoft Security Guidance for Political Campaigns**</span></span> <br/> <span data-ttu-id="c92cc-117">[![迷你海報集的縮略圖。](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="c92cc-117">[![Thumb nail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)          ](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br/> <span data-ttu-id="c92cc-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="c92cc-118">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)  \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span> <br/> |<span data-ttu-id="c92cc-p103">此指南以政治活動組織為例。您可以針對任何環境使用此指南作為起點。</span><span class="sxs-lookup"><span data-stu-id="c92cc-p103">This guidance uses a political campaign organization as an example. Use this guidance as a starting point for any environment.</span></span>  <br/> |
|<span data-ttu-id="c92cc-121">**適用於非營利組織的 Microsoft 安全性指南**</span><span class="sxs-lookup"><span data-stu-id="c92cc-121">**Microsoft Security Guidance for Nonprofits**</span></span> <br/> <span data-ttu-id="c92cc-122">[![可下載的檔案的縮略圖](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)          ](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="c92cc-122">[![Thumnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)          ](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br/> <span data-ttu-id="c92cc-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="c92cc-123">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)  \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span> <br/> |<span data-ttu-id="c92cc-p104">此指南已針對非營利組織稍做修改。 例如，它會參考 Office 365 非營利組織版方案。 其技術指導與政治活動解決方案指南相同。</span><span class="sxs-lookup"><span data-stu-id="c92cc-p104">This guide is slightly revised for nonprofit organizations. For example, it references Office 365 Nonprofit plans. The technical guidance is the same as the political campaign solution guide.</span></span>  <br/> |
   
## <a name="test-lab-guides"></a><span data-ttu-id="c92cc-127">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="c92cc-127">Test Lab Guides</span></span>

<span data-ttu-id="c92cc-128">若要建立此解決方案的開發/測試環境，請使用以下測試實驗室指南：</span><span class="sxs-lookup"><span data-stu-id="c92cc-128">To create a dev/test environment for this solution, use the following test lab guides:</span></span> 
  
- [<span data-ttu-id="c92cc-129">設定政治活動開發/測試環境的群組和使用者</span><span class="sxs-lookup"><span data-stu-id="c92cc-129">Configure groups and users for a political campaign dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/configure-groups-and-users-for-a-political-campaign-dev-test-environment)
    
     <span data-ttu-id="c92cc-130">建立 Office 365 和 EMS 的試用訂閱，然後建立代表性政治活動的群組和使用者。</span><span class="sxs-lookup"><span data-stu-id="c92cc-130">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>
    
- [<span data-ttu-id="c92cc-131">在政治活動開發/測試環境中建立小組網站</span><span class="sxs-lookup"><span data-stu-id="c92cc-131">Create team sites in a political campaign dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/create-team-sites-in-a-political-campaign-dev-test-environment)
    
    <span data-ttu-id="c92cc-132">建立 4 個分別具有內部、私人、敏感性及高度機密安全性層級的 SharePoint Online 小組網站。</span><span class="sxs-lookup"><span data-stu-id="c92cc-132">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>
    
<span data-ttu-id="c92cc-133">如需示範的其他安全性功能或概念證明，請參閱＜[Office 365 測試實驗室指南](https://aka.ms/o365tlgs)＞。</span><span class="sxs-lookup"><span data-stu-id="c92cc-133">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c92cc-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c92cc-134">See Also</span></span>

[<span data-ttu-id="c92cc-135">雲端採用測試實驗室指南 (TLG)</span><span class="sxs-lookup"><span data-stu-id="c92cc-135">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)
  
[<span data-ttu-id="c92cc-136">Microsoft Cloud IT 架構資源</span><span class="sxs-lookup"><span data-stu-id="c92cc-136">Microsoft Cloud IT architecture resources</span></span>](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources)



