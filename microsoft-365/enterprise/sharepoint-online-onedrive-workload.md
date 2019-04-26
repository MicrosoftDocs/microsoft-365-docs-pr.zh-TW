---
title: 部署適用於 Microsoft 365 企業版的 SharePoint Online 和商務用 OneDrive
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 推行並發揮 Microsoft 365 企業版 SharePoint Online 在組織中的價值，規劃這整個程序的步驟。
ms.openlocfilehash: 30fe3a971a869a4609d6b8ef2809692b4d4e5420
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290897"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a><span data-ttu-id="3b690-103">部署適用於 Microsoft 365 企業版的 SharePoint Online 和商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="3b690-103">Deploy SharePoint Online for Business for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3b690-104">*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="3b690-104">*This step is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="3b690-105">當您進行檔案儲存與共用、內容管理及共同作業時，SharePoint Online 和 Microsoft Teams 就是您的最佳選擇，也是打造 Microsoft 365 企業版團隊合作價值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="3b690-105">SharePoint Online and Microsoft Teams is how you do file storage and sharing, content management, and collaboration and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="3b690-p101">SharePoint Online 也具有進階的安全性功能，包括存取控制和權限，以及在執行中及靜態加密。SharePoint Online 安全性是 Microsoft 365 企業版情報安全性價值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="3b690-p101">SharePoint Online also has advanced security capabilities including access control and permissions and encryption in flight and at rest. SharePoint Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="3b690-108">如果您是 SharePoint Online 新手，請參閱 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 與 [SharePoint 入門](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)。</span><span class="sxs-lookup"><span data-stu-id="3b690-108">If you are brand new to SharePoint Online, see [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) and [Get Started with SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).</span></span>

<span data-ttu-id="3b690-109">以下的階段與步驟會帶領您構想 SharePoint Online 在貴組織中的角色，透過一系列的漸進式推行讓組織導入，並向使用者推廣其使用價值。</span><span class="sxs-lookup"><span data-stu-id="3b690-109">The following phases and steps guide you through the process of envisioning the role of SharePoint Online in your organization, onboarding your organization through a series of progressive rollouts, and driving usage its value to your end users. These deployment instructions should be followed only after you've completed your foundation infrastructure.</span></span> <span data-ttu-id="3b690-110">開始之前，請確定您已設定正確的[基礎結構](deploy-foundation-infrastructure.md)階段，您的 SharePoint Online 網站才能具備您需要的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="3b690-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-foundation-infrastructure.md) phases so that your SharePoint Online sites have the security capabilities you need.</span></span> 

<span data-ttu-id="3b690-111">若要部署適用於 Microsoft 365 企業版的商務用 OneDrive，請參閱[適用於企業的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="3b690-111">To deploy OneDrive for Business for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="3b690-112">第 1 階段：構想</span><span class="sxs-lookup"><span data-stu-id="3b690-112">Phase 1: Envision</span></span>
<span data-ttu-id="3b690-113">在這個階段，您要召集負責 SharePoint Online 部署的人員，並決定組織將如何使用它們來解決業務需求。</span><span class="sxs-lookup"><span data-stu-id="3b690-113">In this phase, you gather the people for your SharePoint Online deployment and determine how your organization will use them to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a><span data-ttu-id="3b690-114">步驟 1：收集您的 SharePoint Online 部署成員</span><span class="sxs-lookup"><span data-stu-id="3b690-114">Step 1: Gather your SharePoint Online deployment members</span></span>

<span data-ttu-id="3b690-p103">為了將 SharePoint Online 成功部署在 [Microsoft 365 企業版底層基礎結構](deploy-foundation-infrastructure.md)上，您需要找到適當的人員取得相關想法和意見反應。重點人物包括企業決策者、IT 人員 (如架構與實作者)、使用者提倡者。</span><span class="sxs-lookup"><span data-stu-id="3b690-p103">For a successful deployment of SharePoint Online on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="3b690-117">這三種人員可確保部署涵蓋各種考量，從而解決業務需求和技術層面的資料夾和文件移轉與安全性，讓結果成為一般使用者會使用的工具。</span><span class="sxs-lookup"><span data-stu-id="3b690-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="3b690-118">結果</span><span class="sxs-lookup"><span data-stu-id="3b690-118">Result</span></span>

<span data-ttu-id="3b690-119">代表組織的業務、技術、使用者三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="3b690-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a><span data-ttu-id="3b690-120">步驟 2：決定 SharePoint Online 商務案例並定立優先順序</span><span class="sxs-lookup"><span data-stu-id="3b690-120">Step 2: Determine and prioritize your SharePoint Online business scenarios</span></span>

<span data-ttu-id="3b690-p104">Sharepoint 可用於不同的用途。您必須判斷哪些用途是對應到您的業務需求。您應該著重於 SharePoint Online，來解決您小組、部門或整個組織的文件儲存與共用、內容管理及共同作業的需求。</span><span class="sxs-lookup"><span data-stu-id="3b690-p104">SharePoint Online can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint Online to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="3b690-124">您可在 [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 中查看案例和功能清單。</span><span class="sxs-lookup"><span data-stu-id="3b690-124">See the list of scenarios and capabilities at [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).</span></span>

<span data-ttu-id="3b690-125">下列商務要點可解決貴組織的需求：</span><span class="sxs-lookup"><span data-stu-id="3b690-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="3b690-126">共用和共同作業</span><span class="sxs-lookup"><span data-stu-id="3b690-126">Share and Work Together</span></span> | <span data-ttu-id="3b690-127">利用小組網站、共同作業網站及同步處理。</span><span class="sxs-lookup"><span data-stu-id="3b690-127">Take advantage of team sites, collaboration sites, and sync.</span></span> |
| <span data-ttu-id="3b690-128">通知並保持互動</span><span class="sxs-lookup"><span data-stu-id="3b690-128">Inform and Engage</span></span> | <span data-ttu-id="3b690-129">未來的資訊傳入。</span><span class="sxs-lookup"><span data-stu-id="3b690-129">Information coming in the future.</span></span> |
| <span data-ttu-id="3b690-130">轉換</span><span class="sxs-lookup"><span data-stu-id="3b690-130">Transform</span></span> | <span data-ttu-id="3b690-131">使用流程來建立儲存區或工作流程。</span><span class="sxs-lookup"><span data-stu-id="3b690-131">Uses Flow to create a store or workflow.</span></span> |
| <span data-ttu-id="3b690-132">充分利用集體知識</span><span class="sxs-lookup"><span data-stu-id="3b690-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="3b690-133">使用搜尋來授與貴組織所需的結果。</span><span class="sxs-lookup"><span data-stu-id="3b690-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="3b690-134">保護</span><span class="sxs-lookup"><span data-stu-id="3b690-134">Protect</span></span> | <span data-ttu-id="3b690-135">確保貴組織受到保護，且有正確的規範。</span><span class="sxs-lookup"><span data-stu-id="3b690-135">Ensures your organization is secured and has the correct compliance.</span></span> |
| <span data-ttu-id="3b690-136">外部/開發</span><span class="sxs-lookup"><span data-stu-id="3b690-136">External/Develop</span></span> | <span data-ttu-id="3b690-137">讓貴組織使用 SharePoint 架構來開發自訂解決方案和應用程式。</span><span class="sxs-lookup"><span data-stu-id="3b690-137">Lets your organization develop customize solutions and apps by using the SharePoint Framework.</span></span> |
|||

<span data-ttu-id="3b690-138">請參閱＜[SharePoint Online 管理](https://docs.microsoft.com/sharepoint/sharepoint-online)＞，取得如何依您需求設定 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="3b690-138">See [SharePoint Online admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint Online for your needs.</span></span>

<span data-ttu-id="3b690-p105">要查看 SharePoint Online 優點的其中一個方法，是檢查個人、小組、部門或整個組織現今互動的方式，並找出適當的案例，提供更輕鬆的方法來儲存及共用檔案共同作業。請注意，[Microsoft Teams](teams-workload.md) 對您部分的案例而言可能是較好的選擇。</span><span class="sxs-lookup"><span data-stu-id="3b690-p105">One way to see the benefits of SharePoint Online is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

<span data-ttu-id="3b690-141">SharePoint Online 達成了 Microsoft 365 企業版的這些策略商務案例：</span><span class="sxs-lookup"><span data-stu-id="3b690-141">SharePoint Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="3b690-142">與小組溝通以取得最新資訊、要求輸入，並建立凝聚力和共識</span><span class="sxs-lookup"><span data-stu-id="3b690-142">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="3b690-143">充分利用集體知識</span><span class="sxs-lookup"><span data-stu-id="3b690-143">Harness collective knowledge</span></span>
- <span data-ttu-id="3b690-144">讓使用者能夠轉換商務程序</span><span class="sxs-lookup"><span data-stu-id="3b690-144">Empower users to transform business processes</span></span>
- <span data-ttu-id="3b690-145">塑造公司的文化</span><span class="sxs-lookup"><span data-stu-id="3b690-145">Shape the company culture</span></span>
- <span data-ttu-id="3b690-146">管理專案、工作和截止日期，達成業務目標</span><span class="sxs-lookup"><span data-stu-id="3b690-146">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="3b690-147">與第一線員工互動，啟用數位轉型</span><span class="sxs-lookup"><span data-stu-id="3b690-147">Engage your firstline workers to enable your Digital Transformation</span></span>
- <span data-ttu-id="3b690-148">了解您的工作習慣以提升影響力</span><span class="sxs-lookup"><span data-stu-id="3b690-148">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="3b690-149">與合作夥伴、同事和客戶通訊</span><span class="sxs-lookup"><span data-stu-id="3b690-149">Communicate with partners, colleagues, and customers</span></span>
- <span data-ttu-id="3b690-150">在組織內外部儲存及共用檔案，順暢地跨越組織界限工作</span><span class="sxs-lookup"><span data-stu-id="3b690-150">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="3b690-151">隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式</span><span class="sxs-lookup"><span data-stu-id="3b690-151">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="3b690-152">保護您的資訊，並降低資料遺失風險</span><span class="sxs-lookup"><span data-stu-id="3b690-152">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="3b690-153">使用增強的隱私權和法規遵循來支援貴組織，以符合一般資料保護規定 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="3b690-153">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="3b690-154">如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。</span><span class="sxs-lookup"><span data-stu-id="3b690-154">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a><span data-ttu-id="3b690-155">適用於高管制資料的 SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="3b690-155">SharePoint Online site for highly regulated data</span></span>

<span data-ttu-id="3b690-p106">高管制資料受限於區域法規，或者是貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。您可以設定 SharePoint Online 網站以進行限制存取、資料分類、資料外洩防護以及此資料類型的加密。如需詳細資訊，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="3b690-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a SharePoint Online site for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="3b690-159">結果</span><span class="sxs-lookup"><span data-stu-id="3b690-159">Result</span></span>
<span data-ttu-id="3b690-160">SharePoint Online 的案例清單，能解決貴組織對於文件儲存與共用、內容管理及共同作業的需求。</span><span class="sxs-lookup"><span data-stu-id="3b690-160">A list of SharePoint Online scenarios that address your organization’s needs for document storage and sharing, content management, and collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="3b690-161">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="3b690-161">Phase 2: Onboard</span></span>

<span data-ttu-id="3b690-162">在這個階段，規劃 SharePoint Online 部署的技術層面，然後開始向所選的使用者群組推行。</span><span class="sxs-lookup"><span data-stu-id="3b690-162">In this phase, you plan for the technical aspects of a SharePoint Online deployment and start rolling then out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="3b690-163">必要條件：身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="3b690-163">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="3b690-164">若要保護 SharePoint Online 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint Online 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3b690-164">To protect access to SharePoint Online sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="3b690-165">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="3b690-165">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="3b690-p107">開始技術規劃之前，先決定您是否要使用 FastTrack。如果貴組織有超過 50 個基座，並參與[合格方案](https://technet.microsoft.com/library/dn783224.aspx) (英文)，您可以使用 FastTrack 優點來逐步引導您規劃、部署及採用服務而不必支付額外費用。或者，您可以使用 Office 365 帳戶登入後，從 [FastTrack](https://fasttrack.microsoft.com/) (英文) 取得「FastTrack 導入精靈」來完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="3b690-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use FastTrack benefits, available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="3b690-p108">如果您要執行自己的規劃 (或搭配 FastTrack)，必須判斷您的網路和組織是否準備好使用 SharePoint Online。請務必符合基本基礎結構的網路允出準則，特別注意網際網路頻寬、輸送量、流量延遲，達到可用於 SharePoint Online 型文件其他流量的最佳效能。</span><span class="sxs-lookup"><span data-stu-id="3b690-p108">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint Online-based documents.</span></span>

<span data-ttu-id="3b690-171">您可以使用這些資源，準備好使用 SharePoint Online 推行的技術層面：</span><span class="sxs-lookup"><span data-stu-id="3b690-171">Use these resources to prepare for the technical aspects of a SharePoint Online rollout:</span></span> 

- [<span data-ttu-id="3b690-172">SharePoint Online 規劃指南</span><span class="sxs-lookup"><span data-stu-id="3b690-172">SharePoint Online Planning Guide</span></span>](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [<span data-ttu-id="3b690-173">移轉至 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3b690-173">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

<span data-ttu-id="3b690-174">如需更深入了解 SharePoint Online 的安全性，請檢閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="3b690-174">For a better understanding of security in SharePoint Online, review the following resources:</span></span>

-   [<span data-ttu-id="3b690-175">SharePoint Online 和 OneDrive 如何保護您在雲端的資料</span><span class="sxs-lookup"><span data-stu-id="3b690-175">How SharePoint Online and OneDrive safeguard your data in the cloud</span></span>](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   <span data-ttu-id="3b690-176">[商務用 OneDrive 和 SharePoint Online 中的資料加密](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C) (英文)</span><span class="sxs-lookup"><span data-stu-id="3b690-176">[Data Encryption in OneDrive for Business and SharePoint Online](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)</span></span>

#### <a name="result"></a><span data-ttu-id="3b690-177">結果</span><span class="sxs-lookup"><span data-stu-id="3b690-177">Result</span></span>

<span data-ttu-id="3b690-178">您了解 SharePoint Online 網站和內部部署資料夾與文件移轉及安全性，並準備好開始將 SharePoint Online 推出至貴組織中的指定群組。</span><span class="sxs-lookup"><span data-stu-id="3b690-178">You understand SharePoint Online sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="3b690-179">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="3b690-179">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="3b690-p109">在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="3b690-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="3b690-182">選擇 SharePoint Online 商務案例，讓您的 IT 試驗參與者可以加以練習。</span><span class="sxs-lookup"><span data-stu-id="3b690-182">Choose a SharePoint Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="3b690-183">為試驗參與者提供一組練習，來測試 SharePoint Online 文件儲存、共用、共同作業、小組排程，以及其他功能。</span><span class="sxs-lookup"><span data-stu-id="3b690-183">Give your pilot participants a set of exercises to test SharePoint Online document storage, sharing, collaboration, team-based scheduling, and other capabilities.</span></span>
- <span data-ttu-id="3b690-p110">判斷您的變更管理策略，並產生材料來推動整個組織的使用者採用 SharePoint Online。變更管理的材料可包含電子郵件公告文字、內部訓練計劃、走廊海報和簡報。這些材料向組織宣傳 SharePoint Online 相關事宜及其優點，目的是要引發認知和促進使用。請參閱 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 一文中變更管理策略的一些想法。</span><span class="sxs-lookup"><span data-stu-id="3b690-p110">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about SharePoint Online and its benefits with the goals of raising awareness and driving usage. See the change management strategy for [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="3b690-p111">讓 IT 試驗參與者根據他們的經驗檢閱變更管理的材料。他們可以提供最佳做法的祕訣，以及最能描述 Microsoft Teams 優點以及如何用於通訊和排程的建議。</span><span class="sxs-lookup"><span data-stu-id="3b690-p111">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of SharePoint Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="3b690-190">結果</span><span class="sxs-lookup"><span data-stu-id="3b690-190">Result</span></span>

<span data-ttu-id="3b690-191">完成 SharePoint Online 的 IT 試驗，並已開發、檢閱、精簡首次變更管理的材料。</span><span class="sxs-lookup"><span data-stu-id="3b690-191">Your SharePoint Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="3b690-192">步驟 3：推行至商務群組</span><span class="sxs-lookup"><span data-stu-id="3b690-192">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="3b690-p112">完成 IT 試驗後，將 SharePoint Online 推行至貴組織中的商務群組或部門。此推行應包含：</span><span class="sxs-lookup"><span data-stu-id="3b690-p112">After completing your IT pilot, roll out SharePoint Online to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="3b690-195">識別商務群組中的 SharePoint Online 重要商務案例。</span><span class="sxs-lookup"><span data-stu-id="3b690-195">Identification of key business scenarios for SharePoint Online within the business group.</span></span>
- <span data-ttu-id="3b690-196">用公告活動通知使用者在部門及工作或專案小組使用 SharePoint Online 的相關預期變更和時間表。</span><span class="sxs-lookup"><span data-stu-id="3b690-196">Announcement activities to inform users of the expectations and timelines for SharePoint Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="3b690-197">將商務群組成員的內部部署資料夾和文件遷移到 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="3b690-197">Migration of on-premises folders and documents of your business group members to SharePoint Online.</span></span>
- <span data-ttu-id="3b690-p113">提供使用者訓練或 SharePoint Online 及其使用方式的資源介紹連結。請參閱 [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 影片訓練課程。</span><span class="sxs-lookup"><span data-stu-id="3b690-p113">Delivering user training or links to resources to introduce SharePoint Online and how to use it. See [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="3b690-200">用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。</span><span class="sxs-lookup"><span data-stu-id="3b690-200">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="3b690-201">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="3b690-201">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="3b690-202">結果</span><span class="sxs-lookup"><span data-stu-id="3b690-202">Result</span></span>

<span data-ttu-id="3b690-203">已使用 SharePoint Online 建立並執行商務群組，且已測試並精簡變更管理的材料。</span><span class="sxs-lookup"><span data-stu-id="3b690-203">A business group is up and running with SharePoint Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="3b690-204">第 3 階段：發揮價值</span><span class="sxs-lookup"><span data-stu-id="3b690-204">Phase 3: Drive value</span></span>

<span data-ttu-id="3b690-205">在這個階段，您完成推出 SharePoint Online 支援您的使用者，以協助他們了解其優點。</span><span class="sxs-lookup"><span data-stu-id="3b690-205">In this phase, you complete the rollout of SharePoint Online support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="3b690-206">步驟 1：將推行至組織的其他單位</span><span class="sxs-lookup"><span data-stu-id="3b690-206">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="3b690-207">推行至貴組織其餘單位應包含：</span><span class="sxs-lookup"><span data-stu-id="3b690-207">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="3b690-208">識別不同商務群組中的 SharePoint Online 重要商務案例。</span><span class="sxs-lookup"><span data-stu-id="3b690-208">Identification of key business scenarios for SharePoint Online Online within separate business groups.</span></span>
- <span data-ttu-id="3b690-209">在公告活動中使用精簡過的變更管理材料，通知貴組織使用的期望和時間表。</span><span class="sxs-lookup"><span data-stu-id="3b690-209">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="3b690-210">將貴組織其餘的資料夾和文件移轉至 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="3b690-210">Migration of folders and documents for the rest of your organization to SharePoint Online.</span></span>
- <span data-ttu-id="3b690-211">提供使用者訓練或提供 SharePoint Online 及其使用方式的資源介紹連結。</span><span class="sxs-lookup"><span data-stu-id="3b690-211">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span>
- <span data-ttu-id="3b690-p114">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="3b690-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="3b690-215">結果</span><span class="sxs-lookup"><span data-stu-id="3b690-215">Result</span></span>
<span data-ttu-id="3b690-216">已建立並執行組織，且變更管理策略已經準備就緒，可以通知、訓練並讓使用者開始使用 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="3b690-216">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="3b690-217">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="3b690-217">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="3b690-218">推行至整個組織後，您必須繼續使用變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="3b690-218">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="3b690-219">讓您的領導能力將 SharePoint Online 升階為主要工具，以進行文件儲存和共用，以及小組、部門或整個組織的共同作業。</span><span class="sxs-lookup"><span data-stu-id="3b690-219">Have your leadership promote SharePoint Online as the primary tool for document storage and sharing and team, division, or organization-wide collaboration.</span></span>
- <span data-ttu-id="3b690-220">鼓勵個人將它用於商務群組、部門、工作和專案小組的共同作業和行事曆編排。</span><span class="sxs-lookup"><span data-stu-id="3b690-220">Encourage individuals to use it for business group, departmental, work, and project team collaboration and calendaring.</span></span>

<span data-ttu-id="3b690-221">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="3b690-221">Here are some suggested activities:</span></span>

- <span data-ttu-id="3b690-222">請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3b690-222">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="3b690-p115">請參閱 [Office 365 系統管理中心的活動報告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="3b690-p115">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="3b690-p116">監控意見反應區 (中央 Teams 小組或 Yammer 中的公用通道) 了解個人 SharePoint Online 的使用體驗問題和意見反應。盡快解決疑問和問題，以避免個人的挫折感，並示範推出的支援。</span><span class="sxs-lookup"><span data-stu-id="3b690-p116">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="3b690-p117">在每個商務群組中找出高手並加強培養，強調他們使用 SharePoint Online 的成就和最佳做法。在組織中反映出他們的成功，以彰顯專案的成功與採用。商務群組技術主管的背書對領導者和同儕有強大的影響。</span><span class="sxs-lookup"><span data-stu-id="3b690-p117">Identify and nurture champions in each business group and highlight their accomplishments and best practices by using SharePoint Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="3b690-230">結果</span><span class="sxs-lookup"><span data-stu-id="3b690-230">Result</span></span>

<span data-ttu-id="3b690-231">貴組織已採用 SharePoint Online 作為服務，來支援文件儲存與共同作業。</span><span class="sxs-lookup"><span data-stu-id="3b690-231">Your organization has adopted SharePoint Online as a service to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="3b690-232">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="3b690-232">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="3b690-233">若要深入查看 Microsoft 並了解公司部署 SharePoint Online 的方式，請參閱 [SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)。</span><span class="sxs-lookup"><span data-stu-id="3b690-233">To peek inside Microsoft and learn how the company deployed SharePoint Online, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b690-234">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3b690-234">Next steps</span></span>

<span data-ttu-id="3b690-235">請參閱下列資源，了解 SharePoint Online 的後續維護：</span><span class="sxs-lookup"><span data-stu-id="3b690-235">See these resources for the ongoing maintenance of SharePoint Online:</span></span> 

- [<span data-ttu-id="3b690-236">了解 SharePoint 的權限等級</span><span class="sxs-lookup"><span data-stu-id="3b690-236">Understanding permission levels in SharePoint</span></span>](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- <span data-ttu-id="3b690-237">[自訂 SharePoint 網站的權限](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="3b690-237">[Customize SharePoint site permissions](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)</span></span>
- <span data-ttu-id="3b690-238">[開啟或關閉 SharePoint Online 的外部共用](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="3b690-238">[Turn external sharing on or off for SharePoint Online](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)</span></span>
- [<span data-ttu-id="3b690-239">設定及管理存取要求</span><span class="sxs-lookup"><span data-stu-id="3b690-239">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

