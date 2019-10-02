---
title: 部署適用於 Microsoft 365 企業版的 SharePoint 和 OneDrive
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: 推行並發揮 SharePoint 在組織中的價值，規劃這整個程序的步驟。
ms.openlocfilehash: d8a61a6bc6b4dae431d94e7ccfb9fb0ea8019427
ms.sourcegitcommit: a77c4889c5b7d3b8f16e74917079300e8f222941
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2019
ms.locfileid: "37329202"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a><span data-ttu-id="e1b28-103">部署適用於 Microsoft 365 企業版的 SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="e1b28-103">Deploy SharePoint Online and OneDrive for Business for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e1b28-104">*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="e1b28-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="e1b28-105">當您進行檔案儲存與共用、內容管理及共同作業時，SharePoint 和 Microsoft Teams 就是您的最佳選擇，也是打造 Microsoft 365 企業版團隊合作價值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="e1b28-105">SharePoint Online and Microsoft Teams is how you do file storage and sharing, content management, and collaboration and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="e1b28-p101">SharePoint 也具有進階的安全性功能，包括存取控制和權限，以及動態和靜態加密。SharePoint 安全性是 Microsoft 365 企業版情報安全性價值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="e1b28-p101">SharePoint Online also has advanced security capabilities including access control and permissions and encryption in flight and at rest. SharePoint Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="e1b28-108">如果您是 SharePoint 新手，請參閱 [SharePoint ](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 與 [SharePoint 快速入門](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics)。</span><span class="sxs-lookup"><span data-stu-id="e1b28-108">If you are brand new to SharePoint Online, see [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) and [Get Started with SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).</span></span>

<span data-ttu-id="e1b28-109">以下的階段與步驟會帶領您構想 SharePoint 在貴組織中的角色，透過一系列的漸進式推行讓組織導入，並向使用者推廣其使用價值。</span><span class="sxs-lookup"><span data-stu-id="e1b28-109">The following phases and steps guide you through the process of envisioning the role of SharePoint Online in your organization, onboarding your organization through a series of progressive rollouts, and driving usage its value to your end users.</span></span> <span data-ttu-id="e1b28-110">開始之前，請確定您已設定正確的[基礎結構](deploy-workloads.md#foundation-infrastructure-prerequisites)階段，您的 SharePoint 網站才能具備您需要的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="e1b28-110">Before you begin, make sure you've configured the right [foundation infrastructure](deploy-workloads.md#foundation-infrastructure-prerequisites) phases so that your SharePoint Online sites have the security capabilities you need.</span></span> 

<span data-ttu-id="e1b28-111">若要部署適用於 Microsoft 365 企業版的 OneDrive，請參閱[適用於企業的 OneDrive 指南](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="e1b28-111">To deploy OneDrive for Business for Microsoft 365 Enterprise, see the [OneDrive guide for enterprises](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span>

## <a name="phase-1-envision"></a><span data-ttu-id="e1b28-112">第 1 階段：構想</span><span class="sxs-lookup"><span data-stu-id="e1b28-112">Phase 1: Envision</span></span>
<span data-ttu-id="e1b28-113">在這個階段，您要召集負責 SharePoint 部署的組織夥伴，並決定組織將如何使用 SharePoint 來解決業務需求。</span><span class="sxs-lookup"><span data-stu-id="e1b28-113">In this phase, you gather the people for your SharePoint Online deployment and determine how your organization will use them to address its business needs.</span></span>

### <a name="step-1-gather-your-sharepoint-deployment-members"></a><span data-ttu-id="e1b28-114">步驟 1：召集 SharePoint 部署成員</span><span class="sxs-lookup"><span data-stu-id="e1b28-114">Step 1: Gather your SharePoint Online deployment members</span></span>

<span data-ttu-id="e1b28-p103">為了將 SharePoint 成功部署在 [Microsoft 365 企業版基礎結構](deploy-foundation-infrastructure.md)上，您需要找到適當的人員，以獲得相關想法和意見反應。關鍵人員包括企業決策者、IT 人員 (如架構師與實作者) 以及使用者提倡者。</span><span class="sxs-lookup"><span data-stu-id="e1b28-p103">For a successful deployment of SharePoint Online on top of the [Microsoft 365 Enterprise foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="e1b28-117">這三種人員可確保部署涵蓋各種考量，從而解決業務需求和技術層面的資料夾和文件移轉與安全性，讓結果成為一般使用者會使用的工具。</span><span class="sxs-lookup"><span data-stu-id="e1b28-117">These three groups ensure that your deployment includes considerations that address business needs, technical aspects of folder and document migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="e1b28-118">結果</span><span class="sxs-lookup"><span data-stu-id="e1b28-118">Result</span></span>

<span data-ttu-id="e1b28-119">分別代表組織的業務、技術、使用者這三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="e1b28-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a><span data-ttu-id="e1b28-120">步驟 2：決定 SharePoint 商務案例並訂定優先順序</span><span class="sxs-lookup"><span data-stu-id="e1b28-120">Step 2: Determine and prioritize your SharePoint Online business scenarios</span></span>

<span data-ttu-id="e1b28-p104">SharePoint 可用於不同的用途。您必須判斷哪些用途對應到您的業務需求。您應該將 SharePoint 的重點放在解決小組、部門或整個組織的文件儲存與共用、內容管理及共同作業的需求。</span><span class="sxs-lookup"><span data-stu-id="e1b28-p104">SharePoint Online can be used for different purposes. You need to figure out which purposes map to your business needs. You should target SharePoint Online to address the document storage and sharing, content management, and collaboration needs of your teams, your division, or your entire organization.</span></span> 

<span data-ttu-id="e1b28-124">您可在 [SharePoint](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) 中查看案例和功能清單。</span><span class="sxs-lookup"><span data-stu-id="e1b28-124">See the list of scenarios and capabilities at [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).</span></span>

<span data-ttu-id="e1b28-125">下列商務要點可解決貴組織的需求：</span><span class="sxs-lookup"><span data-stu-id="e1b28-125">The following business pillars can address your organization’s needs:</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="e1b28-126">共用和共同作業</span><span class="sxs-lookup"><span data-stu-id="e1b28-126">Share and Work Together</span></span> | <span data-ttu-id="e1b28-127">利用小組網站、共同作業網站及同步處理。</span><span class="sxs-lookup"><span data-stu-id="e1b28-127">Take advantage of team sites, collaboration sites, and sync.</span></span> |
| <span data-ttu-id="e1b28-128">通知並保持互動</span><span class="sxs-lookup"><span data-stu-id="e1b28-128">Inform and Engage</span></span> | <span data-ttu-id="e1b28-129">未來的資訊傳入。</span><span class="sxs-lookup"><span data-stu-id="e1b28-129">Information coming in the future.</span></span> |
| <span data-ttu-id="e1b28-130">轉換</span><span class="sxs-lookup"><span data-stu-id="e1b28-130">Transform</span></span> | <span data-ttu-id="e1b28-131">使用流程來建立儲存區或工作流程。</span><span class="sxs-lookup"><span data-stu-id="e1b28-131">Uses Flow to create a store or workflow.</span></span> |
| <span data-ttu-id="e1b28-132">充分利用集體知識</span><span class="sxs-lookup"><span data-stu-id="e1b28-132">Harness Collective Knowledge</span></span> | <span data-ttu-id="e1b28-133">使用搜尋來授與貴組織所需的結果。</span><span class="sxs-lookup"><span data-stu-id="e1b28-133">Uses Search to give the desired results within your organization.</span></span> |
| <span data-ttu-id="e1b28-134">保護</span><span class="sxs-lookup"><span data-stu-id="e1b28-134">Protect</span></span> | <span data-ttu-id="e1b28-135">確保貴組織受到保護，且有正確的規範。</span><span class="sxs-lookup"><span data-stu-id="e1b28-135">Ensures your organization is secured and has the correct compliance.</span></span> |
| <span data-ttu-id="e1b28-136">外部/開發</span><span class="sxs-lookup"><span data-stu-id="e1b28-136">External/Develop</span></span> | <span data-ttu-id="e1b28-137">讓組織使用 SharePoint 架構來開發自訂解決方案和應用程式。</span><span class="sxs-lookup"><span data-stu-id="e1b28-137">Lets your organization develop customize solutions and apps by using the SharePoint Framework.</span></span> |
|||

<span data-ttu-id="e1b28-138">請參閱 [SharePoint 系統管理](https://docs.microsoft.com/sharepoint/sharepoint-online)，取得如何依需求設定 SharePoint 的資源。</span><span class="sxs-lookup"><span data-stu-id="e1b28-138">See [SharePoint Online admin](https://docs.microsoft.com/sharepoint/sharepoint-online) for resources on how to configure SharePoint Online for your needs.</span></span>

<span data-ttu-id="e1b28-p105">要查看 SharePoint 優點的其中一個方法，是檢查個人、小組、部門或整個組織現今互動的方式，並找出適當的案例，提供更輕鬆的方法來儲存及共用檔案。請注意，[Microsoft Teams](teams-workload.md) 對您部分的案例而言可能是較好的選擇。</span><span class="sxs-lookup"><span data-stu-id="e1b28-p105">One way to see the benefits of SharePoint Online is to examine how individuals, a team, a division, or your entire organization interact today, and then find an appropriate scenario that provides easier ways to store and share files collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your scenarios.</span></span>

#### <a name="sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="e1b28-141">適用於高度管制資料的 SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="e1b28-141">SharePoint Online site for highly regulated data</span></span>

<span data-ttu-id="e1b28-142">高度管制資料受地區法規約束，或者是您組織中最有價值的資料，例如營業機密、財務或人力資源資訊以及組織策略。</span><span class="sxs-lookup"><span data-stu-id="e1b28-142">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see Microsoft Teams and SharePoint Online sites for highly regulated data.</span></span> <span data-ttu-id="e1b28-143">您可以針對此類型的資料，設定 SharePoint 網站進行限制存取、資料分類、資料遺失防護和加密。</span><span class="sxs-lookup"><span data-stu-id="e1b28-143">You can configure a SharePoint site for restricted access, data classification, data loss prevention, and encryption for this type of data.</span></span> <span data-ttu-id="e1b28-144">如需詳細資料，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b28-144">For more information, see the [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

#### <a name="result"></a><span data-ttu-id="e1b28-145">結果</span><span class="sxs-lookup"><span data-stu-id="e1b28-145">Result</span></span>
<span data-ttu-id="e1b28-146">SharePoint 的案例清單，能解決組織對於文件儲存與共用、內容管理、共同作業與安全性的需求。</span><span class="sxs-lookup"><span data-stu-id="e1b28-146">A list of SharePoint Online scenarios that address your organization’s needs for document storage and sharing, content management, and collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="e1b28-147">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="e1b28-147">Phase 2: Onboard</span></span>

<span data-ttu-id="e1b28-148">在這個階段，您會規劃 SharePoint 部署的技術層面，然後開始向所選的使用者群組推行。</span><span class="sxs-lookup"><span data-stu-id="e1b28-148">In this phase, you plan for the technical aspects of a SharePoint Online deployment and start rolling then out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="e1b28-149">必要條件：身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="e1b28-149">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="e1b28-150">若要保護 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e1b28-150">To protect access to SharePoint Online sites, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="e1b28-151">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="e1b28-151">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="e1b28-152">開始技術規劃之前，請先決定是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="e1b28-152">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="e1b28-153">如果貴組織擁有超過 50 個基座，且參與[合格方案](https://technet.microsoft.com/library/dn783224.aspx)，您可以使用 FastTrack 權益而無需額外費用，它可引導您完成規劃、移轉、部署及服務導入。</span><span class="sxs-lookup"><span data-stu-id="e1b28-153">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use FastTrack benefits, available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from FastTrack once you sign in with your Office 365 account.</span></span> <span data-ttu-id="e1b28-154">或者，您可以使用 FastTrack 導入精靈來完成這項工作，只要您使用 Microsoft 365 帳戶登入後，就能從 [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) 使用該精靈。</span><span class="sxs-lookup"><span data-stu-id="e1b28-154">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="e1b28-155">如果您要自行規劃，或者搭配 FastTrack 使用，則需要確定您的網路和組織是否已準備好使用 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e1b28-155">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint.</span></span> <span data-ttu-id="e1b28-156">請務必符合基礎結構的網路允出準則，特別注意網際網路頻寬、輸送量、流量延遲，以達到可用於 SharePoint 型文件其他流量的最佳效能。</span><span class="sxs-lookup"><span data-stu-id="e1b28-156">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for SharePoint Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for SharePoint Online-based documents.</span></span>

<span data-ttu-id="e1b28-157">您可以使用以下資源來準備推行 SharePoint 的技術層面工作：</span><span class="sxs-lookup"><span data-stu-id="e1b28-157">Use these resources to prepare for the technical aspects of a SharePoint Online rollout:</span></span> 

- [<span data-ttu-id="e1b28-158">SharePoint 規劃指南</span><span class="sxs-lookup"><span data-stu-id="e1b28-158">SharePoint Online planning guide</span></span>](https://docs.microsoft.com/sharepoint/planning-guide)
- [<span data-ttu-id="e1b28-159">移轉至 SharePoint</span><span class="sxs-lookup"><span data-stu-id="e1b28-159">Migrate  to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

<span data-ttu-id="e1b28-160">如需更深入了解 SharePoint 的安全性，請檢閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="e1b28-160">For a better understanding of security in SharePoint Online, review the following resources:</span></span>

-   [<span data-ttu-id="e1b28-161">SharePoint 和 OneDrive 如何保護您在雲端的資料</span><span class="sxs-lookup"><span data-stu-id="e1b28-161">How SharePoint Online and OneDrive safeguard your data in the cloud</span></span>](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   <span data-ttu-id="e1b28-162">[OneDrive 和 SharePoint 中的資料加密](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo) (機器翻譯)</span><span class="sxs-lookup"><span data-stu-id="e1b28-162">[Data Encryption in OneDrive for Business and SharePoint Online](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)</span></span>

#### <a name="result"></a><span data-ttu-id="e1b28-163">結果</span><span class="sxs-lookup"><span data-stu-id="e1b28-163">Result</span></span>

<span data-ttu-id="e1b28-164">您了解 SharePoint 網站和內部部署資料夾與文件移轉及安全性，並準備好開始將 SharePoint 推出至貴組織中的指定群組。</span><span class="sxs-lookup"><span data-stu-id="e1b28-164">You understand SharePoint Online sites and on-premises folder and document migration and security and are ready to begin rolling out SharePoint Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="e1b28-165">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="e1b28-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="e1b28-166">在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。</span><span class="sxs-lookup"><span data-stu-id="e1b28-166">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span> <span data-ttu-id="e1b28-167">在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="e1b28-167">During the IT pilot:</span></span>

- <span data-ttu-id="e1b28-168">選擇 SharePoint 商務案例，讓您的 IT 試驗參與者可以加以練習。</span><span class="sxs-lookup"><span data-stu-id="e1b28-168">Choose a SharePoint Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="e1b28-169">為試驗參與者提供一組練習，來測試 SharePoint 文件儲存、共用、共同作業、小組排程，以及其他功能。</span><span class="sxs-lookup"><span data-stu-id="e1b28-169">Give your pilot participants a set of exercises to test SharePoint Online document storage, sharing, collaboration, team-based scheduling, and other capabilities.</span></span>
- <span data-ttu-id="e1b28-170">決定您的變更管理策略，並製作可提升整個組織使用者採用 SharePoint 的資料。</span><span class="sxs-lookup"><span data-stu-id="e1b28-170">Determine your change management strategy and produce materials to drive organization-wide user adoption of SharePoint.</span></span> <span data-ttu-id="e1b28-171">變更管理資料可包含電子郵件公告文字、內部訓練計畫、走道海報和簡報。</span><span class="sxs-lookup"><span data-stu-id="e1b28-171">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="e1b28-172">這些資料可將 SharePoint 及其優點通報給您的組織，以提高認知度並推動使用。</span><span class="sxs-lookup"><span data-stu-id="e1b28-172">These materials will inform your organization about SharePoint and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="e1b28-173">請參閱 [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) 的變更管理策略文章，以取得一些想法。</span><span class="sxs-lookup"><span data-stu-id="e1b28-173">See the change management strategy for [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="e1b28-174">讓您的 IT 試驗參與者根據經驗審查變更管理資料。</span><span class="sxs-lookup"><span data-stu-id="e1b28-174">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="e1b28-175">他們可以提供最佳做法的秘訣，以及如何最貼切地描述 SharePoint 的優點和使用方法。</span><span class="sxs-lookup"><span data-stu-id="e1b28-175">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of SharePoint Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="e1b28-176">結果</span><span class="sxs-lookup"><span data-stu-id="e1b28-176">Result</span></span>

<span data-ttu-id="e1b28-177">您已完成 SharePoint 的 IT 試驗，並已開發、審核、調整首次變更管理的資料。</span><span class="sxs-lookup"><span data-stu-id="e1b28-177">Your SharePoint Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="e1b28-178">步驟 3：推行至業務小組</span><span class="sxs-lookup"><span data-stu-id="e1b28-178">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="e1b28-179">完成 IT 試驗後，將 SharePoint 推行至貴組織中的業務小組或部門。</span><span class="sxs-lookup"><span data-stu-id="e1b28-179">After completing your IT pilot, roll out SharePoint Online to a business group or department in your organization. This rollout should include:</span></span> <span data-ttu-id="e1b28-180">這個推行應包括：</span><span class="sxs-lookup"><span data-stu-id="e1b28-180">This rollout should include:</span></span>

- <span data-ttu-id="e1b28-181">識別不同業務小組中，SharePoint 的重要業務案例。</span><span class="sxs-lookup"><span data-stu-id="e1b28-181">Identification of key business scenarios for SharePoint Online within the business group.</span></span>
- <span data-ttu-id="e1b28-182">透過公告活動通知使用者在部門及工作或專案團隊中使用 SharePoint 的相關事先通知和時間表。</span><span class="sxs-lookup"><span data-stu-id="e1b28-182">Announcement activities to inform users of the expectations and timelines for SharePoint Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="e1b28-183">業務小組成員的內部部署資料夾和文件移轉到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e1b28-183">Migration of on-premises folders and documents of your business group members to SharePoint Online.</span></span>
- <span data-ttu-id="e1b28-184">提供使用者訓練或資源連結，以介紹 SharePoint 及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="e1b28-184">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span> <span data-ttu-id="e1b28-185">請參閱 [SharePoint 影片訓練](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23)。</span><span class="sxs-lookup"><span data-stu-id="e1b28-185">[SharePoint Online video training](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23)</span></span>
- <span data-ttu-id="e1b28-186">用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。</span><span class="sxs-lookup"><span data-stu-id="e1b28-186">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>
 
<span data-ttu-id="e1b28-187">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="e1b28-187">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="e1b28-188">結果</span><span class="sxs-lookup"><span data-stu-id="e1b28-188">Result</span></span>

<span data-ttu-id="e1b28-189">已使用 SharePoint 建立並執行業務小組，且已測試並調整變更管理的資料。</span><span class="sxs-lookup"><span data-stu-id="e1b28-189">A business group is up and running with SharePoint Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="e1b28-190">第 3 階段：發揮價值</span><span class="sxs-lookup"><span data-stu-id="e1b28-190">Phase 3: Drive value</span></span>

<span data-ttu-id="e1b28-191">在這個階段，您會完成 SharePoint 的推行並協助使用者了解其優點。</span><span class="sxs-lookup"><span data-stu-id="e1b28-191">In this phase, you complete the rollout of SharePoint Online support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a><span data-ttu-id="e1b28-192">步驟 1：將推行至組織的其他單位</span><span class="sxs-lookup"><span data-stu-id="e1b28-192">Step 1: Roll out to the rest of your organization</span></span>

<span data-ttu-id="e1b28-193">推行至貴組織其餘單位應包含：</span><span class="sxs-lookup"><span data-stu-id="e1b28-193">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="e1b28-194">識別不同業務小組中，SharePoint Online 的重要業務案例。</span><span class="sxs-lookup"><span data-stu-id="e1b28-194">Identification of key business scenarios for SharePoint Online Online within separate business groups.</span></span>
- <span data-ttu-id="e1b28-195">在公告活動中使用調整過的變更管理資料，通知貴組織使用事先通知和時間表。</span><span class="sxs-lookup"><span data-stu-id="e1b28-195">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for usage.</span></span>
- <span data-ttu-id="e1b28-196">將組織其餘的資料夾和文件移轉至 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e1b28-196">Migration of folders and documents for the rest of your organization to SharePoint Online.</span></span>
- <span data-ttu-id="e1b28-197">提供使用者訓練或提供資源連結，以介紹 SharePoint 及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="e1b28-197">Delivering user training or provide links to resources to introduce SharePoint Online and how to use it.</span></span>
- <span data-ttu-id="e1b28-p114">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="e1b28-p114">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="e1b28-201">結果</span><span class="sxs-lookup"><span data-stu-id="e1b28-201">Result</span></span>
<span data-ttu-id="e1b28-202">組織已經準備好，且變更管理策略已經準備就緒，可以通知、訓練並讓使用者開始使用 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="e1b28-202">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use SharePoint Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="e1b28-203">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="e1b28-203">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="e1b28-204">推行至整個組織後，您必須繼續使用變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="e1b28-204">After rolling out to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="e1b28-205">請管理階層推廣 SharePoint，做為文件儲存與共用的主要工具。</span><span class="sxs-lookup"><span data-stu-id="e1b28-205">Have your leadership promote SharePoint Online as the primary tool for document storage and sharing and team, division, or organization-wide collaboration.</span></span>
- <span data-ttu-id="e1b28-206">鼓勵個人在業務小組、部門和工作及專案小組之間使用它來進行文件儲存與共用。</span><span class="sxs-lookup"><span data-stu-id="e1b28-206">Encourage individuals to use it for document storage and sharing among business groups, departments, and working and project teams.</span></span>

<span data-ttu-id="e1b28-207">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="e1b28-207">Here are some suggested activities:</span></span>

- <span data-ttu-id="e1b28-208">請參閱 [Office 365 的成功要素](https://aka.ms/successfactors) (英文) 以了解雲端服務導入的一般最佳做法。</span><span class="sxs-lookup"><span data-stu-id="e1b28-208">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="e1b28-p115">請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="e1b28-p115">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="e1b28-211">監控您的意見反應管道 (位於中央 Teams 團隊或 Yammer 中的公共頻道)，以發現個人在使用 SharePoint 上的問題和意見反應。</span><span class="sxs-lookup"><span data-stu-id="e1b28-211">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span> <span data-ttu-id="e1b28-212">快速解決問題，避免使用者在使用上感到挫折，並展現出對推行的支援。</span><span class="sxs-lookup"><span data-stu-id="e1b28-212">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with SharePoint Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="e1b28-213">在每個業務小組中找出並培養擁護者，並特別表彰他們在使用 SharePoint 上的成就和最佳作法。</span><span class="sxs-lookup"><span data-stu-id="e1b28-213">Identify and nurture champions in each business group and highlight their accomplishments and best practices when using SharePoint.</span></span> <span data-ttu-id="e1b28-214">向組織反映他們的成功，以顯示專案的成功和導入成效。</span><span class="sxs-lookup"><span data-stu-id="e1b28-214">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="e1b28-215">透過業務小組內的技術領導者的認可，可以對領導者和同儕產生強大的影響力。</span><span class="sxs-lookup"><span data-stu-id="e1b28-215">Endorsement by technical leaders within a business group can exert a powerful influence over leadership and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="e1b28-216">結果</span><span class="sxs-lookup"><span data-stu-id="e1b28-216">Result</span></span>

<span data-ttu-id="e1b28-217">貴組織已導入 Microsoft 365 企業版的 SharePoint 來支援文件儲存與共同作業。</span><span class="sxs-lookup"><span data-stu-id="e1b28-217">Your organization has adopted SharePoint in Microsoft 365 Enterprise to support documentation storage and collaboration.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="e1b28-218">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="e1b28-218">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e1b28-219">若要深入查看 Microsoft 並了解公司部署 SharePoint 的方式，請參閱 [SharePoint 至雲端：深入了解 Microsoft 如何執行自己的移轉](https://www.microsoft.com/zh-TW/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e1b28-219">To peek inside Microsoft and learn how the company deployed SharePoint Online, see [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/zh-TW/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e1b28-220">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e1b28-220">Next steps</span></span>

<span data-ttu-id="e1b28-221">請參閱下列資源，了解 SharePoint 的後續維護：</span><span class="sxs-lookup"><span data-stu-id="e1b28-221">See these resources for the ongoing maintenance of SharePoint Online:</span></span> 

- [<span data-ttu-id="e1b28-222">了解 SharePoint 中的權限等級</span><span class="sxs-lookup"><span data-stu-id="e1b28-222">Understanding permission levels in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [<span data-ttu-id="e1b28-223">自訂 SharePoint 網站權限</span><span class="sxs-lookup"><span data-stu-id="e1b28-223">Customize SharePoint site permissions</span></span>](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [<span data-ttu-id="e1b28-224">開啟或關閉 SharePoint 的外部共用功能</span><span class="sxs-lookup"><span data-stu-id="e1b28-224">Turn external sharing on or off for SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [<span data-ttu-id="e1b28-225">設定及管理存取要求</span><span class="sxs-lookup"><span data-stu-id="e1b28-225">Set up and manage access requests</span></span>](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
