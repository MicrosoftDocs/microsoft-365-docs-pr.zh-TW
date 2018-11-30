---
title: 部署 Microsoft 365 企業版的 Microsoft Teams
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 推行並發揮 Microsoft 365 企業版 Microsoft Teams 在組織中的價值，規劃這整個程序的步驟。
ms.openlocfilehash: 25329c7024f267983a83c4e719f18df6ad613bf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866764"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a><span data-ttu-id="54791-103">部署 Microsoft 365 企業版的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="54791-103">Deploy Microsoft Teams for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="54791-p101">Microsoft Teams 將交談、會議、共用文件、往來對話整合在一起，讓您在群組間輕鬆建立及共用內容。Teams 是進行 Microsoft 365 企業版團隊合作和共同作業的工具，是專門為了 Microsoft 365 團隊合作而打造的重要元素。如果您沒用過 Teams，請參閱 [Microsoft Teams 概觀](https://docs.microsoft.com/MicrosoftTeams/teams-overview)。</span><span class="sxs-lookup"><span data-stu-id="54791-p101">Microsoft Teams brings together chat, conferencing, document sharing, and threaded conversations in a way that makes it easy to create and share content across groups. Teams is the way you do teamwork and collaboration for Microsoft 365 Enterprise and is a key element of the Built for Teamwork value of Microsoft 365. If you are brand new to Teams, see [Overview of Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).</span></span>
 
<span data-ttu-id="54791-p102">如果您目前使用商務用 Skype，我們正在將商務用 Skype 的功能建置在 Teams 之中。這會在一段時間後完成，Teams 最終會變成單一用戶端體驗。您是重要的商務用 Skype 客戶，Microsoft 在此支援您。如需詳細資訊，請參閱[從商務用 Skype 到 Microsoft Teams 的旅程](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="54791-p102">If you’re currently using Skype for Business, we’re building Skype for Business capabilities into Teams. This will happen over time, and ultimately Teams will become the single client experience. As a valued Skype for Business customer, Microsoft is here to support you. See the [Journey from Skype for Business to Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams) for more information.</span></span>

<span data-ttu-id="54791-111">以下的階段與步驟會帶領您構想 Teams 在組織中的角色，透過一系列的漸進式推行讓組織導入 Teams，並向使用者推廣 Teams 的使用和價值。</span><span class="sxs-lookup"><span data-stu-id="54791-111">The following phases and steps guide you through the process of envisioning the role of Teams in your organization, onboarding your organization to Teams through a series of progressive rollouts, and driving usage of Teams and its value to your end users.</span></span> 

>[!Note]
><span data-ttu-id="54791-112">請在您完成 Microsoft 365 企業版的[基本基礎結構](deploy-foundation-infrastructure.md)之後，遵循下列部署指示。</span><span class="sxs-lookup"><span data-stu-id="54791-112">These deployment instructions should be followed only after you've completed your [foundation infrastructure](deploy-foundation-infrastructure.md) for Microsoft 365 Enterprise.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="54791-113">第 1 階段：構想</span><span class="sxs-lookup"><span data-stu-id="54791-113">Phase 1: Envision</span></span>

<span data-ttu-id="54791-114">在這個階段，您要召集負責 Teams 部署的人員，並決定組織將如何使用 Teams 解決業務需求。</span><span class="sxs-lookup"><span data-stu-id="54791-114">In this phase, you gather the people for your Teams deployment and determine how your organization will use Teams to address its business needs.</span></span>

### <a name="step-1-gather-your-teams-deployment-members"></a><span data-ttu-id="54791-115">步驟 1：召集 Teams 部署成員</span><span class="sxs-lookup"><span data-stu-id="54791-115">Step 1: Gather your Teams deployment members</span></span>
<span data-ttu-id="54791-p103">為了將 Teams 成功部署在 Microsoft 365 [基本基礎結構](deploy-foundation-infrastructure.md)上，您需要找到適當的人員取得相關想法和意見反應。重點人物包括企業決策者、IT 人員 (如架構與實作者)、使用者提倡者。</span><span class="sxs-lookup"><span data-stu-id="54791-p103">For a successful deployment of Teams on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="54791-118">這三種人可確保 Teams 的部署涵蓋各種考量，可以解決業務需求和技術層面的授權與安全性，讓 Teams 成為一般使用者會使用的工具。</span><span class="sxs-lookup"><span data-stu-id="54791-118">These three groups ensure that your Teams deployment includes considerations that address business needs, technical aspects of licensing and security, and that Teams will be something that your typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="54791-119">結果</span><span class="sxs-lookup"><span data-stu-id="54791-119">Result</span></span>

<span data-ttu-id="54791-120">代表組織的業務、技術、使用者三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="54791-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a><span data-ttu-id="54791-121">步驟 2：決定 Teams 商務案例並定立優先順序</span><span class="sxs-lookup"><span data-stu-id="54791-121">Step 2: Determine and prioritize your Teams business scenarios</span></span>
<span data-ttu-id="54791-p104">Teams 可以用於許多不同的用途。您必須決定哪些用途對應到組織中業務需求、業務群組、部門、個別工作與專案小組的不同層級。如需範例請參閱 [Microsoft 365 生產力文件庫](https://www.microsoft.com/microsoft-365/success)，來協助您定義 Teams 案例。</span><span class="sxs-lookup"><span data-stu-id="54791-p104">Teams can be used for many different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, and individual working and project teams. Take a look at the [Microsoft 365 Productivity Library](https://www.microsoft.com/microsoft-365/success) for examples to help you define Teams scenarios.</span></span> 

<span data-ttu-id="54791-p105">您應該將 Teams 的目標放在處理進展快速且高度共同作業的小組，他們密切合作並需要電子郵件和 Exchange Online 以外的更多功能。像是具有歷程記錄的即時群組聊天、用通用易找的位置儲存檔案和備忘稿。</span><span class="sxs-lookup"><span data-stu-id="54791-p105">You should target Teams to address fast-moving and highly collaborative teams that work closely together and require many more facilities than just email with Exchange Online can provide. Examples are live group chats with a recorded history and a common and easy-to-find place to store files and notes.</span></span> 

<span data-ttu-id="54791-127">看見 Teams 優點的其中一個方法是查看小組或虛擬小組今天的互動，然後找出可取代互動並提供更輕鬆共同作業方式的適當 Teams 案例，再提供額外的功能。</span><span class="sxs-lookup"><span data-stu-id="54791-127">One way to see the benefits of Teams is to examine how a team or v-team interacts today, and then find an appropriate Teams scenario that replaces the interaction and provides easier ways to collaborate and provide additional capabilities.</span></span>

<span data-ttu-id="54791-128">Teams 達成了 Microsoft 365 企業版的這些策略商務案例：</span><span class="sxs-lookup"><span data-stu-id="54791-128">Teams enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="54791-129">與小組溝通以取得最新資訊、要求輸入，並建立凝聚力和共識</span><span class="sxs-lookup"><span data-stu-id="54791-129">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="54791-130">與第一線員工互動，啟用數位轉型</span><span class="sxs-lookup"><span data-stu-id="54791-130">Engage your firstline workers to enable your Digital Transformation</span></span>
- <span data-ttu-id="54791-131">了解您的工作習慣以提升影響力</span><span class="sxs-lookup"><span data-stu-id="54791-131">Understand your work habits to improve your influence and impact</span></span>

<span data-ttu-id="54791-132">如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。</span><span class="sxs-lookup"><span data-stu-id="54791-132">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="microsoft-teams-for-highly-regulated-data"></a><span data-ttu-id="54791-133">適用於高管制資料的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="54791-133">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="54791-p106">高管制資料受限於區域法規，或者是貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。您可以設定小組以進行限制存取、資料分類、資料外洩防護以及此資料類型的加密。如需詳細資訊，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)。</span><span class="sxs-lookup"><span data-stu-id="54791-p106">Highy regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>

#### <a name="result"></a><span data-ttu-id="54791-137">結果</span><span class="sxs-lookup"><span data-stu-id="54791-137">Result</span></span>

<span data-ttu-id="54791-138">解決組織共同作業和團隊合作需求的 Teams 案例清單。</span><span class="sxs-lookup"><span data-stu-id="54791-138">A list of Teams scenarios that address your organization’s needs for collaboration and teamwork.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="54791-139">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="54791-139">Phase 2: Onboard</span></span>

<span data-ttu-id="54791-140">在這個階段，規劃 Teams 部署的技術層面，並開始向所選的使用者群組推行 Teams。</span><span class="sxs-lookup"><span data-stu-id="54791-140">In this phase, you plan for the technical aspects of a Teams deployment and start rolling out Teams to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="54791-141">必要條件：身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="54791-141">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="54791-142">若要保護 Teams 的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 SharePoint Online 存取原則](sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="54791-142">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="54791-143">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="54791-143">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="54791-p107">開始技術規劃之前，先決定您是否要使用 FastTrack。如果組織有超過 50 個基座，並參與[合格方案](https://technet.microsoft.com/library/dn783224.aspx)，您可以使用[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365) (不另外收費) 來逐步引導您規劃、部署及採用服務。或者，您可以使用我們的「FastTrack 導入精靈」自己完成這項工作，您可以使用 Office 365 帳戶登入，即可從 [FastTrack](https://fasttrack.microsoft.com/) 取得此精靈。</span><span class="sxs-lookup"><span data-stu-id="54791-p107">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment and service adoption. Or, you can complete this work yourself using our FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="54791-p108">如果您要執行自己的規劃 (或搭配 FastTrack)，必須判斷您的網路和組織是否準備好使用 Teams。請務必符合[基本基礎結構](deploy-foundation-infrastructure.md)的網路允出準則，特別注意頻寬、輸送量、流量延遲，達到以 Teams 舉行會議的最佳效能。</span><span class="sxs-lookup"><span data-stu-id="54791-p108">If you are doing your own planning (or in conjunction with FastTrack), you need to determine if your network and organization are ready for Teams. It is especially important that you meet the exit criteria for networking in your [foundation infrastructure](deploy-foundation-infrastructure.md), with special attention to bandwidth, throughput, and traffic delays to maximize performance for Teams-based meetings.</span></span>

<span data-ttu-id="54791-149">使用以下資源來準備組織推行 Teams 的技術層面：</span><span class="sxs-lookup"><span data-stu-id="54791-149">Use these resources to prepare the technical aspects of your organization for a Teams rollout:</span></span> 

- [<span data-ttu-id="54791-150">檢查環境的 Teams 整備程度</span><span class="sxs-lookup"><span data-stu-id="54791-150">Check your environment's readiness for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [<span data-ttu-id="54791-151">準備用於 Teams 的網路</span><span class="sxs-lookup"><span data-stu-id="54791-151">Prepare your network for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [<span data-ttu-id="54791-152">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="54791-152">Office 365 URLs and IP address ranges</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

<span data-ttu-id="54791-153">若要更深入了解 Teams 的安全性，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="54791-153">For a better understanding of security in Teams, review the following additional resources:</span></span>

- [<span data-ttu-id="54791-154">Teams 的安全性與合規性概觀</span><span class="sxs-lookup"><span data-stu-id="54791-154">Overview of security and compliance in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [<span data-ttu-id="54791-155">Office 365 群組與 Teams</span><span class="sxs-lookup"><span data-stu-id="54791-155">Office 365 groups and Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [<span data-ttu-id="54791-156">Teams 中的來賓存取</span><span class="sxs-lookup"><span data-stu-id="54791-156">Guest access in Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

<span data-ttu-id="54791-157">接下來，使用這些資源以了解 Teams 授權，以及執行組織的 Teams 設定：</span><span class="sxs-lookup"><span data-stu-id="54791-157">Next, use these resources to understand Teams licensing and to perform the setup of Teams for your organization:</span></span>

- [<span data-ttu-id="54791-158">Office 365 的 Teams 授權</span><span class="sxs-lookup"><span data-stu-id="54791-158">Office 365 licensing for Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [<span data-ttu-id="54791-159">管理使用者對 Microsoft Teams 的存取</span><span class="sxs-lookup"><span data-stu-id="54791-159">Manage user access to Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [<span data-ttu-id="54791-160">取得 Microsoft Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="54791-160">Get clients for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [<span data-ttu-id="54791-161">開啟 Office 365 組織中的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="54791-161">Turn on Microsoft Teams in your Office 365 organization</span></span>](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [<span data-ttu-id="54791-162">管理 Office 365 組織中的 Microsoft Teams 功能</span><span class="sxs-lookup"><span data-stu-id="54791-162">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)

#### <a name="result"></a><span data-ttu-id="54791-163">結果</span><span class="sxs-lookup"><span data-stu-id="54791-163">Result</span></span>

<span data-ttu-id="54791-164">您已完成網路、安全性、Office 365 授權的規劃，您已可以開始向組織中所選的群組推行 Teams。</span><span class="sxs-lookup"><span data-stu-id="54791-164">Your network, security, and Office 365 licensing planning is done and you are ready to begin rolling out Teams to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="54791-165">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="54791-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="54791-p109">在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="54791-p109">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="54791-p110">選擇 IT 試驗參與者可以練習的 Teams 商務案例。請參閱 [Microsoft Teams 快速入門套件](http://microsoft.com/download/56505)中的想法。</span><span class="sxs-lookup"><span data-stu-id="54791-p110">Choose a Teams business scenario in which your IT pilot participants can practice. See the [Microsoft Teams getting started kit](http://microsoft.com/download/56505) for ideas.</span></span>
- <span data-ttu-id="54791-170">給試驗參與者一些練習，來測試透過 Teams 進行的聊天、檔案儲存、會議及其他功能。</span><span class="sxs-lookup"><span data-stu-id="54791-170">Give your pilot participants a set of exercises to test Teams-based chats, file storage, meetings, and other capabilities.</span></span>
- <span data-ttu-id="54791-p111">判斷您的變更管理策略，並產生材料來推動整個組織的使用者採用。變更管理的材料可包含電子郵件公告文字、內部訓練計劃、走廊海報和簡報。這些材料向組織宣傳 Teams 相關事宜及其優點，目的是要引發認知和促進使用。請參閱[Microsoft Teams 的變更管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)中的一些想法。</span><span class="sxs-lookup"><span data-stu-id="54791-p111">Determine your change management strategy and produce materials to drive organization-wide user adoption. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Teams and its benefits with the goals of raising awareness and driving usage. See [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) for some ideas.</span></span>
- <span data-ttu-id="54791-p112">讓 IT 試驗參與者根據他們的經驗檢閱變更管理策略的材料。他們可以提供最佳做法的祕訣，以及最能描述 Teams 優點以及如何用於共同作業和團隊合作的建議。</span><span class="sxs-lookup"><span data-stu-id="54791-p112">Have your IT pilot participants review the change management strategy materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Teams and how to use it for collaboration and teamwork.</span></span>

#### <a name="result"></a><span data-ttu-id="54791-177">結果</span><span class="sxs-lookup"><span data-stu-id="54791-177">Result</span></span>

<span data-ttu-id="54791-178">完成 Teams 的 IT 試驗，且已經開發、檢閱、精簡首次變更管理的材料。</span><span class="sxs-lookup"><span data-stu-id="54791-178">Your Teams IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="54791-179">步驟 3：推行至商務群組</span><span class="sxs-lookup"><span data-stu-id="54791-179">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="54791-p113">完成 IT 試驗後，將 Teams 推行至組織中的商務群組或部門。此推行應包含：</span><span class="sxs-lookup"><span data-stu-id="54791-p113">After completing your IT pilot, roll out Teams to a business group or department in your organization. This rollout should include:</span></span>

- <span data-ttu-id="54791-182">識別商務群組中的 Teams 重要商務案例。</span><span class="sxs-lookup"><span data-stu-id="54791-182">Identification of key business scenarios for Teams within the business group.</span></span>
- <span data-ttu-id="54791-183">用公告活動通知使用者有關在部門、工作或專案小組使用 Teams 的預期變更和時間表。</span><span class="sxs-lookup"><span data-stu-id="54791-183">Announcement activities to inform users of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="54791-184">引導使用者參與 Teams 訓練，或使用介紹 Teams 與用法的資源連結。</span><span class="sxs-lookup"><span data-stu-id="54791-184">Direct user training on Teams or links to resources to introduce Teams and how to use it.</span></span>
- <span data-ttu-id="54791-185">用意見反應機制 (例如包含商務群組中每個人的中央小組) 收集商務群組使用者的意見和問題。</span><span class="sxs-lookup"><span data-stu-id="54791-185">A feedback mechanism, such as a central team containing everyone in the business group, to collect comments and issues from users in the business group.</span></span>

<span data-ttu-id="54791-186">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="54791-186">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="54791-187">結果</span><span class="sxs-lookup"><span data-stu-id="54791-187">Result</span></span>

<span data-ttu-id="54791-188">已使用 Teams 建立並執行商務群組，且已經測試並精簡變更管理的材料。</span><span class="sxs-lookup"><span data-stu-id="54791-188">A business group is up and running with Teams and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="54791-189">階段 3：發揮價值</span><span class="sxs-lookup"><span data-stu-id="54791-189">Phase 3: Drive value</span></span>

<span data-ttu-id="54791-190">在這個階段，您要將 Teams 推行至組織，並支援使用者讓他們知道其優點。</span><span class="sxs-lookup"><span data-stu-id="54791-190">In this phase, you complete the rollout of Teams to your organization and support your users so that they are realizing its benefits.</span></span>

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a><span data-ttu-id="54791-191">步驟 1：將 Teams 推行至組織的其他單位</span><span class="sxs-lookup"><span data-stu-id="54791-191">Step 1: Roll out Teams to the rest of your organization</span></span>

<span data-ttu-id="54791-p114">推行至目標商務群組之後，將 Teams 推行至組織中的其他單位。此推行應包含：</span><span class="sxs-lookup"><span data-stu-id="54791-p114">After completing your rollout to a targeted business group, roll out Teams to the rest of your organization. This rollout should include:</span></span>

- <span data-ttu-id="54791-194">識別個別商務群組中的 Teams 重要商務案例。</span><span class="sxs-lookup"><span data-stu-id="54791-194">Identification of key business scenarios for Teams within your separate business groups.</span></span>
- <span data-ttu-id="54791-195">在公告活動中使用精簡過的變更管理材料，通知組織有關在部門、工作或專案小組使用 Teams 的預期變更和時間表。</span><span class="sxs-lookup"><span data-stu-id="54791-195">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Teams usage for departmental, work, or project teams.</span></span>
- <span data-ttu-id="54791-p115">提供 Teams 訓練給使用者，或提供介紹 Teams 與用法的資源連結。請參閱 [Microsoft Teams 使用者訓練](https://docs.microsoft.com/microsoftteams/enduser-training)的訓練資源。</span><span class="sxs-lookup"><span data-stu-id="54791-p115">Delivering user training on Teams or links to resources to introduce Teams and how to use it. See the training resources at [End user training for Microsoft Teams](https://docs.microsoft.com/microsoftteams/enduser-training).</span></span>
- <span data-ttu-id="54791-p116">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和針對問題採取的行動。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="54791-p116">A feedback mechanism, such as a central team containing everyone, to collect comments and act on issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="54791-201">結果</span><span class="sxs-lookup"><span data-stu-id="54791-201">Result</span></span>

<span data-ttu-id="54791-202">已使用 Teams 建立並執行組織，且變更管理策略已經準備就緒，可以通知、訓練並讓使用者開始使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="54791-202">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to begin using Teams.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="54791-203">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="54791-203">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="54791-204">將 Teams 推行至整個組織後，您必須繼續使用變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="54791-204">After rolling out Teams to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="54791-205">讓領導者將 Teams 提升為組織的團隊合作和共同作業的工具。</span><span class="sxs-lookup"><span data-stu-id="54791-205">Have your leadership promote Teams as the teamwork and collaboration tool for the organization.</span></span>
- <span data-ttu-id="54791-206">鼓勵個人將 Teams 用於商務群組、部門、工作、專案小組的溝通和共同作業。</span><span class="sxs-lookup"><span data-stu-id="54791-206">Encourage individuals to use it for business group, departmental, work, and project team communications and collaboration.</span></span>

<span data-ttu-id="54791-207">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="54791-207">Here are some suggested activities:</span></span>

- <span data-ttu-id="54791-208">請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。</span><span class="sxs-lookup"><span data-stu-id="54791-208">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="54791-p117">請參閱 [Office 365 活動報告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)以了解整個組織的 Office 365 服務用法。如果組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人，讓您可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="54791-p117">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is to grant your user account Reports Reader permissions so you can access activity reports.</span></span>
- <span data-ttu-id="54791-p118">監控意見反應區 (中央小組或 Yammer 中的公用通道) 了解個人的使用 Teams 的 問題和意見反應。盡快解決疑問和問題，以避免個人使用 Teams 的挫折感甚至放棄 Teams。</span><span class="sxs-lookup"><span data-stu-id="54791-p118">Monitor your feedback venue (a public channel in a central team or Yammer) for issues and feedback from individuals about their experiences with Teams. Address questions and issues as quickly as you can to prevent frustration and abandonment of Teams by individuals.</span></span>
- <span data-ttu-id="54791-p119">在每個商務群組中找出高手並加強培養，強調他們使用 Teams 的成就和最佳做法。在組織中反映出他們的成功，以彰顯專案的成功與採。商務群組技術主管的背書對領導者和同儕有強大的影響。</span><span class="sxs-lookup"><span data-stu-id="54791-p119">Identify and nurture your champions in each business group and highlight their accomplishments and best practices using Teams. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="54791-216">結果</span><span class="sxs-lookup"><span data-stu-id="54791-216">Result</span></span>

<span data-ttu-id="54791-217">組織已經採用 Teams 作為共同作業和團隊合作的工具。</span><span class="sxs-lookup"><span data-stu-id="54791-217">Your organization has adopted Teams as its collaboration and teamwork tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="54791-218">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="54791-218">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="54791-219">若要深入了解 Microsoft 並了解該公司如何部署及使用 Microsoft Teams 進行共同作業，請參閱：</span><span class="sxs-lookup"><span data-stu-id="54791-219">To peek inside Microsoft and learn how the company deployed and is using Microsoft Teams for collaboration, see:</span></span>

- [<span data-ttu-id="54791-220">部署 Microsoft Teams 可簡化共同作業並提升團隊合作</span><span class="sxs-lookup"><span data-stu-id="54791-220">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="54791-221">Microsoft Teams 可在 Microsoft 的現代化工作場所增進共同作業</span><span class="sxs-lookup"><span data-stu-id="54791-221">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a><span data-ttu-id="54791-222">後續步驟</span><span class="sxs-lookup"><span data-stu-id="54791-222">Next steps</span></span>

- [<span data-ttu-id="54791-223">管理 Office 365 組織中的 Microsoft Teams 功能</span><span class="sxs-lookup"><span data-stu-id="54791-223">Manage Microsoft Teams features in your Office 365 organization</span></span>](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [<span data-ttu-id="54791-224">Microsoft Teams 的管理訓練</span><span class="sxs-lookup"><span data-stu-id="54791-224">Admin training for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
