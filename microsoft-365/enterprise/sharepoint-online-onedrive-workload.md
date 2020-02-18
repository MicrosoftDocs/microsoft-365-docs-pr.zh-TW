---
title: 部署適用於 Microsoft 365 企業版的 SharePoint 和 OneDrive
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: 推行並發揮 SharePoint 在組織中的價值，規劃這整個程序的步驟。
ms.openlocfilehash: cb0cf16df328d667d796008ac7cabfc98c21ad17
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/20/2019
ms.locfileid: "39886320"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a><span data-ttu-id="1e1e9-103">部署適用於 Microsoft 365 企業版的 SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="1e1e9-103">Deploy SharePoint and OneDrive for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1e1e9-104">*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="1e1e9-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="1e1e9-105">當您進行檔案儲存與共用、內容管理及共同作業時，SharePoint 和 Microsoft Teams 就是您的最佳選擇，也是打造 Microsoft 365 企業版團隊合作價值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-105">SharePoint and Microsoft Teams are how you do file storage and sharing, content management, and collaboration and are key elements of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="1e1e9-p101">SharePoint 也具有進階的安全性功能，包括存取控制和權限，以及動態和靜態加密。SharePoint 安全性是 Microsoft 365 企業版情報安全性價值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-p101">SharePoint also has advanced security capabilities including access control with permissions and encryption in flight and at rest. SharePoint security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="1e1e9-108">如果您是 SharePoint 新手，請參閱 [SharePoint ](https://products.office.com/sharepoint/collaboration) 與 [SharePoint 快速入門](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121)。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-108">If you are brand new to SharePoint, see [SharePoint](https://products.office.com/sharepoint/collaboration) and [Get Started with SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).</span></span>

<span data-ttu-id="1e1e9-109">以下的階段與步驟會帶領您構想 SharePoint 在貴組織中的角色，透過一系列的漸進式推行讓組織導入，並向使用者推廣其使用價值。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-109">The following phases and steps guide you through the process of envisioning the role of SharePoint in your organization, onboarding your organization through a series of progressive rollouts, and driving usage and its value to your end users.</span></span> <span data-ttu-id="1e1e9-110">開始之前，請確定您已設定正確的[基礎結構](deploy-workloads.md#foundation-infrastructure-prerequisites)階段，您的 SharePoint 網站才能具備您需要的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-workloads.md#foundation-infrastructure-prerequisites) phases so that your SharePoint sites have the security capabilities you need.</span></span> 

<span data-ttu-id="1e1e9-111">若要部署適用於 Microsoft 365 企業版的 OneDrive，請參閱[適用於企業的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-111">To deploy OneDrive for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="1e1e9-112">第 1 階段：構想</span><span class="sxs-lookup"><span data-stu-id="1e1e9-112">Phase 1: Envision</span></span>
<span data-ttu-id="1e1e9-113">在這個階段，您要召集負責 SharePoint 部署的組織夥伴，並決定組織將如何使用 SharePoint 來解決業務需求。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-113">In this phase, you gather the organization partners for your SharePoint deployment and determine how your organization will use SharePoint to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-deployment-members"></a><span data-ttu-id="1e1e9-114">步驟 1：召集 SharePoint 部署成員</span><span class="sxs-lookup"><span data-stu-id="1e1e9-114">Step 1: Gather your SharePoint deployment members</span></span>

<span data-ttu-id="1e1e9-p103">為了將 SharePoint 成功部署在 [Microsoft 365 企業版基礎結構](deploy-foundation-infrastructure.md)上，您需要找到適當的人員，以獲得相關想法和意見反應。關鍵人員包括企業決策者、IT 人員 (如架構師與實作者) 以及使用者提倡者。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-p103">For a successful deployment of SharePoint on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="1e1e9-117">這三種人員可確保部署涵蓋各種考量，從而解決業務需求和技術層面的資料夾和文件移轉與安全性，讓結果成為一般使用者會使用的工具。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="1e1e9-118">結果</span><span class="sxs-lookup"><span data-stu-id="1e1e9-118">Result</span></span>

<span data-ttu-id="1e1e9-119">分別代表組織的業務、技術、使用者這三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-119">A list of people that represent the business, technical, and end user perspectives of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a><span data-ttu-id="1e1e9-120">步驟 2：決定 SharePoint 商務案例並訂定優先順序</span><span class="sxs-lookup"><span data-stu-id="1e1e9-120">Step 2: Determine and prioritize your SharePoint business scenarios</span></span>

<span data-ttu-id="1e1e9-p104">SharePoint 可用於不同的用途。您必須判斷哪些用途對應到您的業務需求。您應該將 SharePoint 的重點放在解決小組、部門或整個組織的文件儲存與共用、內容管理及共同作業的需求。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-p104">SharePoint can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="1e1e9-124">您可在 [SharePoint](https://products.office.com/sharepoint/collaboration ) 中查看案例和功能清單。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-124">See the list of scenarios and capabilities at [SharePoint](https://products.office.com/sharepoint/collaboration ).</span></span>

<span data-ttu-id="1e1e9-125">下列商務要點可解決貴組織的需求：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="1e1e9-126">共用和共同作業</span><span class="sxs-lookup"><span data-stu-id="1e1e9-126">Share and Work Together</span></span> | <span data-ttu-id="1e1e9-127">利用小組網站、通訊網站及同步處理。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-127">Take advantage of team sites, communication sites, and sync.</span></span> |
| <span data-ttu-id="1e1e9-128">通知並保持互動</span><span class="sxs-lookup"><span data-stu-id="1e1e9-128">Inform and Engage</span></span> | <span data-ttu-id="1e1e9-129">未來的資訊傳入。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-129">Information coming in the future.</span></span> |
| <span data-ttu-id="1e1e9-130">轉換</span><span class="sxs-lookup"><span data-stu-id="1e1e9-130">Transform</span></span> | <span data-ttu-id="1e1e9-131">使用 Flow 在應用程式和服務之間建立自動化工作流程。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-131">Uses Flow to create automated workflows between apps and services.</span></span> |
| <span data-ttu-id="1e1e9-132">充分利用集體知識</span><span class="sxs-lookup"><span data-stu-id="1e1e9-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="1e1e9-133">使用搜尋來授與貴組織所需的結果。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="1e1e9-134">保護</span><span class="sxs-lookup"><span data-stu-id="1e1e9-134">Protect</span></span> | <span data-ttu-id="1e1e9-135">確保貴組織受到保護，且有正確的規範。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-135">Ensures your organization is secured and has the correct compliance.</span></span> |
|||

<span data-ttu-id="1e1e9-136">請參閱 [SharePoint 系統管理](https://docs.microsoft.com/sharepoint/sharepoint-online)，取得如何依需求設定 SharePoint 的資源。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-136">See [SharePoint admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint for your needs.</span></span>

<span data-ttu-id="1e1e9-p105">要查看 SharePoint 優點的其中一個方法，是檢查個人、小組、部門或整個組織現今互動的方式，並找出適當的案例，提供更輕鬆的方法來儲存及共用檔案。請注意，[Microsoft Teams](teams-workload.md) 對您部分的案例而言可能是較好的選擇。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-p105">One way to see the benefits of SharePoint is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

#### <a name="sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="1e1e9-139">適用於高度管制資料的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="1e1e9-139">SharePoint site for highly regulated data</span></span>

<span data-ttu-id="1e1e9-140">高度管制資料受地區法規約束，或者是您組織中最有價值的資料，例如營業機密、財務或人力資源資訊以及組織策略。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-140">Highly regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span> <span data-ttu-id="1e1e9-141">您可以針對此類型的資料，設定 SharePoint 網站進行限制存取、資料分類、資料遺失防護和加密。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-141">You can configure a SharePoint site for restricted access, data classification, data loss prevention, and encryption for this type of data.</span></span> <span data-ttu-id="1e1e9-142">如需詳細資料，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-142">For the details, see [Microsoft Teams and SharePoint sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="1e1e9-143">結果</span><span class="sxs-lookup"><span data-stu-id="1e1e9-143">Result</span></span>
<span data-ttu-id="1e1e9-144">SharePoint 的案例清單，能解決組織對於文件儲存與共用、內容管理、共同作業與安全性的需求。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-144">A list of SharePoint scenarios that address your organization’s needs for document storage and sharing, content management, collaboration, and security.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="1e1e9-145">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="1e1e9-145">Phase 2: Onboard</span></span>

<span data-ttu-id="1e1e9-146">在這個階段，您會規劃 SharePoint 部署的技術層面，然後開始向所選的使用者群組推行。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-146">In this phase, you plan for the technical aspects of a SharePoint deployment and start rolling them out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="1e1e9-147">必要條件：身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="1e1e9-147">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="1e1e9-148">若要保護 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-148">To protect access to SharePoint sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="1e1e9-149">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="1e1e9-149">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="1e1e9-150">開始技術規劃之前，請先決定是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-150">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="1e1e9-151">如果貴組織擁有超過 50 個基座，且參與[合格方案](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，您可以使用 FastTrack 權益而無需額外費用，它可引導您完成規劃、移轉、部署及服務導入。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-151">If your organization has more than 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use FastTrack benefits, available at no additional cost to guide you through planning, migration, deployment, and service adoption.</span></span> <span data-ttu-id="1e1e9-152">或者，您可以使用 FastTrack 導入精靈來完成這項工作，只要您使用 Microsoft 365 帳戶登入後，就能從 [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) 使用該精靈。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-152">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="1e1e9-153">如果您要自行規劃，或者搭配 FastTrack 使用，則需要確定您的網路和組織是否已準備好使用 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-153">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint.</span></span> <span data-ttu-id="1e1e9-154">請務必符合基礎結構的[網路允出準則](networking-exit-criteria.md)，特別注意網際網路頻寬、輸送量、流量延遲，以達到可用於 SharePoint 型文件其他流量的最佳效能。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-154">It is especially important that you meet the [exit criteria for networking](networking-exit-criteria.md) in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint-based documents.</span></span>

<span data-ttu-id="1e1e9-155">使用[移轉至 SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 來為您的 SharePoint 推出進行準備：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-155">Use [Migrate to SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) to prepare for your SharePoint rollout:</span></span> 

<span data-ttu-id="1e1e9-156">如需更深入了解 SharePoint 的安全性，請檢閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-156">For a better understanding of security in SharePoint, review the following resources:</span></span>

-   [<span data-ttu-id="1e1e9-157">SharePoint 和 OneDrive 如何保護您在雲端的資料</span><span class="sxs-lookup"><span data-stu-id="1e1e9-157">How SharePoint and OneDrive safeguard your data in the cloud</span></span>](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [<span data-ttu-id="1e1e9-158">OneDrive 和 SharePoint 中的資料加密</span><span class="sxs-lookup"><span data-stu-id="1e1e9-158">Data Encryption in OneDrive and SharePoint</span></span>](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a><span data-ttu-id="1e1e9-159">結果</span><span class="sxs-lookup"><span data-stu-id="1e1e9-159">Result</span></span>

<span data-ttu-id="1e1e9-160">您了解 SharePoint 網站和內部部署資料夾與文件移轉及安全性，並準備好開始將 SharePoint 推出至貴組織中的指定群組。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-160">You understand SharePoint sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="1e1e9-161">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="1e1e9-161">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="1e1e9-162">在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-162">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="1e1e9-163">在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-163">During the IT pilot:</span></span>

- <span data-ttu-id="1e1e9-164">選擇 SharePoint 商務案例，讓您的 IT 試驗參與者可以加以練習。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-164">Choose a SharePoint business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="1e1e9-165">為試驗參與者提供一組練習，來測試 SharePoint 文件儲存、共用、共同作業，以及其他功能。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-165">Give your pilot participants a set of exercises to test SharePoint document storage, sharing, collaboration, and other capabilities.</span></span>
- <span data-ttu-id="1e1e9-166">決定您的變更管理策略，並製作可提升整個組織使用者採用 SharePoint 的資料。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-166">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint.</span></span> <span data-ttu-id="1e1e9-167">變更管理資料可包含電子郵件公告文字、內部訓練計畫、走道海報和簡報。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-167">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="1e1e9-168">這些資料可將 SharePoint 及其優點通報給您的組織，以提高認知度並推動使用。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-168">These materials will inform your organization about SharePoint and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="1e1e9-169">請參閱 [SharePoint 採用資源](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/)來開始。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-169">See the [SharePoint adoption resources](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) to get started.</span></span>
- <span data-ttu-id="1e1e9-170">讓您的 IT 試驗參與者根據經驗審查變更管理資料。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-170">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="1e1e9-171">他們可以提供最佳做法的秘訣，以及如何最貼切地描述 SharePoint 的優點和使用方法。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-171">They can provide tips on best practices and advice on how to best describe the benefits of SharePoint and how to use it.</span></span>

#### <a name="result"></a><span data-ttu-id="1e1e9-172">結果</span><span class="sxs-lookup"><span data-stu-id="1e1e9-172">Result</span></span>

<span data-ttu-id="1e1e9-173">您已完成 SharePoint 的 IT 試驗，並已開發、審核、調整首次變更管理的資料。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-173">Your SharePoint IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="1e1e9-174">步驟 3：推行至業務小組</span><span class="sxs-lookup"><span data-stu-id="1e1e9-174">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="1e1e9-175">完成 IT 試驗後，將 SharePoint 推行至貴組織中的業務小組或部門。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-175">After completing your IT pilot, roll out SharePoint to a business group or department in your organization.</span></span> <span data-ttu-id="1e1e9-176">這個推行應包括：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-176">This rollout should include:</span></span>

- <span data-ttu-id="1e1e9-177">識別不同業務小組中，SharePoint 的重要業務案例。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-177">Identification of key business scenarios for SharePoint within the business group.</span></span>
- <span data-ttu-id="1e1e9-178">透過公告活動通知使用者在部門及工作或專案團隊中使用 SharePoint 的相關事先通知和時間表。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-178">Announcement activities to inform users of the expectations and timelines for SharePoint usage for departments and for working or project teams.</span></span>
- <span data-ttu-id="1e1e9-179">業務小組成員的內部部署資料夾和文件移轉到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-179">Migration of on-premises folders and documents of your business group members to SharePoint.</span></span>
- <span data-ttu-id="1e1e9-180">提供使用者訓練或資源連結，以介紹 SharePoint 及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-180">Delivering user training or links to resources to introduce SharePoint and how to use it.</span></span> <span data-ttu-id="1e1e9-181">請參閱 [SharePoint 影片訓練](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23)。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-181">See [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) video training.</span></span>
- <span data-ttu-id="1e1e9-182">用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-182">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="1e1e9-183">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-183">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="1e1e9-184">結果</span><span class="sxs-lookup"><span data-stu-id="1e1e9-184">Result</span></span>

<span data-ttu-id="1e1e9-185">已使用 SharePoint 建立並執行業務小組，且已測試並調整變更管理的資料。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-185">A business group is up and running with SharePoint and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="1e1e9-186">第 3 階段：發揮價值</span><span class="sxs-lookup"><span data-stu-id="1e1e9-186">Phase 3: Drive value</span></span>

<span data-ttu-id="1e1e9-187">在這個階段，您會完成 SharePoint 的推行並協助使用者了解其優點。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-187">In this phase, you complete the rollout of SharePoint and help your users realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="1e1e9-188">步驟 1：將推行至組織的其他單位</span><span class="sxs-lookup"><span data-stu-id="1e1e9-188">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="1e1e9-189">推行至貴組織其餘單位應包含：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-189">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="1e1e9-190">識別不同業務小組中，SharePoint Online 的重要業務案例。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-190">Identification of key business scenarios for SharePoint Online within separate business groups.</span></span>
- <span data-ttu-id="1e1e9-191">在公告活動中使用調整過的變更管理資料，通知貴組織使用事先通知和時間表。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-191">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="1e1e9-192">將組織其餘的資料夾和文件移轉至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-192">Migration of folders and documents for the rest of your organization to SharePoint.</span></span>
- <span data-ttu-id="1e1e9-193">提供使用者訓練或提供資源連結，以介紹 SharePoint 及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-193">Delivering user training or provide links to resources to introduce SharePoint and how to use it.</span></span>
- <span data-ttu-id="1e1e9-p114">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="1e1e9-197">結果</span><span class="sxs-lookup"><span data-stu-id="1e1e9-197">Result</span></span>
<span data-ttu-id="1e1e9-198">組織已經準備好，且變更管理策略已經準備就緒，可以通知、訓練並讓使用者開始使用 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-198">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="1e1e9-199">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="1e1e9-199">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="1e1e9-200">推行至整個組織後，您必須繼續使用變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-200">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="1e1e9-201">請管理階層推廣 SharePoint，做為文件儲存與共用的主要工具。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-201">Have your leadership promote SharePoint as the primary tool for document storage and sharing.</span></span>
- <span data-ttu-id="1e1e9-202">鼓勵個人在業務小組、部門和工作及專案小組之間使用它來進行文件儲存與共用。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-202">Encourage individuals to use it for document storage and sharing among business groups, departments, and working and project teams.</span></span>

<span data-ttu-id="1e1e9-203">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-203">Here are some suggested activities:</span></span>

- <span data-ttu-id="1e1e9-204">請參閱 [Office 365 的成功要素](https://aka.ms/successfactors) (英文) 以了解雲端服務導入的一般最佳做法。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-204">See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="1e1e9-p115">請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-p115">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="1e1e9-207">監控您的意見反應管道 (位於中央 Teams 團隊或 Yammer 中的公共頻道)，以發現個人在使用 SharePoint 上的問題和意見反應。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-207">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint.</span></span> <span data-ttu-id="1e1e9-208">快速解決問題，避免使用者在使用上感到挫折，並展現出對推行的支援。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-208">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="1e1e9-209">在每個業務小組中找出並培養擁護者，並特別表彰他們在使用 SharePoint 上的成就和最佳作法。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-209">Identify and nurture champions in each business group and highlight their accomplishments and best practices when using SharePoint.</span></span> <span data-ttu-id="1e1e9-210">向組織反映他們的成功，以顯示專案的成功和導入成效。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-210">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="1e1e9-211">透過業務小組內的技術領導者的認可，可以對領導者和同儕產生強大的影響力。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-211">Endorsement by technical leaders within a business group can exert a powerful influence over leadership and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="1e1e9-212">結果</span><span class="sxs-lookup"><span data-stu-id="1e1e9-212">Result</span></span>

<span data-ttu-id="1e1e9-213">貴組織已導入 Microsoft 365 企業版的 SharePoint 來支援文件儲存與共同作業。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-213">Your organization has adopted SharePoint in Microsoft 365 Enterprise to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="1e1e9-214">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="1e1e9-214">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="1e1e9-215">若要深入查看 Microsoft 並了解公司部署 SharePoint 的方式，請參閱 [SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration) (英文)。</span><span class="sxs-lookup"><span data-stu-id="1e1e9-215">To peek inside Microsoft and learn how we deployed SharePoint, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1e1e9-216">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1e1e9-216">Next steps</span></span>

<span data-ttu-id="1e1e9-217">請參閱下列資源，了解 SharePoint 的後續維護：</span><span class="sxs-lookup"><span data-stu-id="1e1e9-217">See these resources for the ongoing maintenance of SharePoint:</span></span> 

- [<span data-ttu-id="1e1e9-218">了解 SharePoint 中的權限等級</span><span class="sxs-lookup"><span data-stu-id="1e1e9-218">Understanding permission levels in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [<span data-ttu-id="1e1e9-219">自訂 SharePoint 網站權限</span><span class="sxs-lookup"><span data-stu-id="1e1e9-219">Customize SharePoint site permissions</span></span>](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [<span data-ttu-id="1e1e9-220">開啟或關閉 SharePoint 的外部共用功能</span><span class="sxs-lookup"><span data-stu-id="1e1e9-220">Turn external sharing on or off for SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [<span data-ttu-id="1e1e9-221">設定及管理存取要求</span><span class="sxs-lookup"><span data-stu-id="1e1e9-221">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
