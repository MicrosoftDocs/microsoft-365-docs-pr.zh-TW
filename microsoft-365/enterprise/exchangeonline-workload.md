---
title: 部署 Microsoft 365 Enterprise 的 Exchange Online
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 逐步完成規劃、將 Exchange Online 的價值放入組織中的 Microsoft 365 企業版的程式。
ms.openlocfilehash: 9214796c37e9cb5ca9fcb07ced5db7efd8e0f7d0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634143"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="80802-103">部署 Microsoft 365 Enterprise 的 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80802-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="80802-104">*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="80802-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="80802-105">Exchange Online 是您主要的電子郵件和行事曆雲端服務，可協助讓使用者以不需要即時聊天或集中化文件儲存區的方式進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="80802-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="80802-106">Exchange Online 是 Microsoft 365 企業版的專為團隊合作價值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="80802-106">Exchange Online is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="80802-107">Exchange Online 可讓您在眾所周知的 Outlook 應用程式（不論您在哪個裝置上），以更有效率地完成工作。</span><span class="sxs-lookup"><span data-stu-id="80802-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you're on.</span></span>

<span data-ttu-id="80802-108">Exchange Online 也有可保護信箱的進階安全性功能 (包括反惡意程式碼和反垃圾郵件篩選)，以及可防止使用者將敏感資訊誤傳給未經授權人員的資料外洩防護功能。</span><span class="sxs-lookup"><span data-stu-id="80802-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="80802-109">Exchange Online 安全性是 Microsoft 365 企業版之智慧安全性值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="80802-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="80802-110">如果您從未使用過 Exchange Online，請參閱 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="80802-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="80802-111">下列階段和步驟會引導您完成構思組織中的 Exchange Online 角色的程式，透過一系列漸進式推廣，將組織加入 Exchange Online，並推動 Exchange Online 和其對您的使用者的價值。</span><span class="sxs-lookup"><span data-stu-id="80802-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="80802-112">只有在完成[Microsoft 365 Enterprise foundation 基礎結構的階段 2](identity-infrastructure.md)之後，才應該遵循這些部署指示。</span><span class="sxs-lookup"><span data-stu-id="80802-112">These deployment instructions should be followed only after you've completed [Phase 2-Identity of the Microsoft 365 Enterprise foundation infrastructure](identity-infrastructure.md).</span></span>
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a><span data-ttu-id="80802-113">階段1：構想您的 Exchange Online 部署</span><span class="sxs-lookup"><span data-stu-id="80802-113">Phase 1: Envision your Exchange Online deployment</span></span>

<span data-ttu-id="80802-114">在此階段中，您會收集 Exchange Online 部署的人員，並決定組織將如何使用 Exchange Online 來滿足其業務需求。</span><span class="sxs-lookup"><span data-stu-id="80802-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="80802-115">步驟1：收集您的 Exchange Online 部署成員</span><span class="sxs-lookup"><span data-stu-id="80802-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="80802-116">若要在 Microsoft 365 Enterprise foundation 基礎結構的[第2階段](identity-infrastructure.md)（身分識別）上成功部署 Exchange Online，您需要收集適當的人員來輸入與意見反應。</span><span class="sxs-lookup"><span data-stu-id="80802-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to gather the right people for input and feedback.</span></span> <span data-ttu-id="80802-117">主要人員包括業務決策者、IT 人員（如架構師與實施者），以及對您的使用者的支援。</span><span class="sxs-lookup"><span data-stu-id="80802-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="80802-118">這三個群組可確保您的 Exchange Online 部署包含滿足業務需求的考慮、信箱遷移和安全性的技術層面，以及結果是一般使用者會使用的內容。</span><span class="sxs-lookup"><span data-stu-id="80802-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result is something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="80802-119">結果</span><span class="sxs-lookup"><span data-stu-id="80802-119">Result</span></span>

<span data-ttu-id="80802-120">代表組織的業務、技術、使用者三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="80802-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="80802-121">步驟2：決定 Exchange Online 商務案例並設定其優先順序</span><span class="sxs-lookup"><span data-stu-id="80802-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="80802-122">Exchange Online 可用於不同的目的。</span><span class="sxs-lookup"><span data-stu-id="80802-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="80802-123">您需要瞭解哪些目的對應到您的業務需求，取決於您組織的各個層級、業務群組、部門或個別的工作和專案小組。</span><span class="sxs-lookup"><span data-stu-id="80802-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="80802-124">您應以 Exchange Online 為目標，以解決您的個人和小群組短暫的通訊和排程需求。</span><span class="sxs-lookup"><span data-stu-id="80802-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="80802-125">查看 Exchange Online 效益的方法之一，是檢查個人、小組或 app-v 團隊的互動方式，然後尋找適當的案例，以提供更輕鬆的通訊、排程會議及共同作業的方式。</span><span class="sxs-lookup"><span data-stu-id="80802-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="80802-126">請記住， [Microsoft 小組](teams-workload.md)可能是一些共同作業案例的更佳選擇。</span><span class="sxs-lookup"><span data-stu-id="80802-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

#### <a name="result"></a><span data-ttu-id="80802-127">結果</span><span class="sxs-lookup"><span data-stu-id="80802-127">Result</span></span>
<span data-ttu-id="80802-128">Exchange Online 案例的清單，可滿足您組織的通訊、排程和短期共同作業的需求。</span><span class="sxs-lookup"><span data-stu-id="80802-128">A list of Exchange Online scenarios that address your organization's needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="80802-129">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="80802-129">Phase 2: Onboard</span></span>

<span data-ttu-id="80802-130">在此階段中，您會規劃 Exchange Online 部署的技術層面，然後開始向所選的使用者群組進行尋找。</span><span class="sxs-lookup"><span data-stu-id="80802-130">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="80802-131">必要條件：身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="80802-131">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="80802-132">若要保護對 Exchange Online 信箱的存取，請確定您已設定身分[識別與裝置存取原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="80802-132">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="80802-133">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="80802-133">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="80802-134">開始技術規劃之前，請先決定是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="80802-134">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="80802-135">如果您的組織有超過50的席位，且已參與[合格的計畫](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，您可以使用[Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，而*無需額外成本*，就能引導您規劃、部署和服務採用。</span><span class="sxs-lookup"><span data-stu-id="80802-135">If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *available at no additional cost* to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="80802-136">或者，您可以使用 FastTrack 導入精靈來完成這項工作，只要您使用 Microsoft 365 帳戶登入後，就能從 [FastTrack](https://fasttrack.microsoft.com/) 使用該精靈。</span><span class="sxs-lookup"><span data-stu-id="80802-136">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="80802-137">如果您要進行自己的規劃，或與 FastTrack 搭配使用，您必須判斷您的網路和組織是否準備好進行 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="80802-137">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="80802-138">針對連接至組織網路的使用者，您必須符合基礎結構中的[網路](networking-infrastructure.md)出口標準，這一點尤為重要。</span><span class="sxs-lookup"><span data-stu-id="80802-138">It is especially important that you meet the exit criteria for [networking](networking-infrastructure.md) in your foundation infrastructure for users connected to your organization network.</span></span> <span data-ttu-id="80802-139">特別注意網際網路頻寬、輸送量和流量延遲，以最大程度提高 Exchange Online 電子郵件和附件的流量效能。</span><span class="sxs-lookup"><span data-stu-id="80802-139">Pay special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="80802-140">您可以使用這些資源來準備 Exchange Online 部署的技術層面：</span><span class="sxs-lookup"><span data-stu-id="80802-140">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="80802-141">將多個電子郵件帳戶移轉到 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="80802-141">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [<span data-ttu-id="80802-142">將 Exchange Server 公用資料夾遷移至 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80802-142">Migrate Exchange Server public folders to Exchange Online</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [<span data-ttu-id="80802-143">將 Exchange Server 公用資料夾遷移至 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="80802-143">Migrate Exchange Server public folders to Microsoft 365 Groups</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [<span data-ttu-id="80802-144">Exchange Online 中的協同作業</span><span class="sxs-lookup"><span data-stu-id="80802-144">Collaboration in Exchange Online</span></span>](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [<span data-ttu-id="80802-145">Exchange Online 中的收件者</span><span class="sxs-lookup"><span data-stu-id="80802-145">Recipients in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [<span data-ttu-id="80802-146">Outlook for iOS 和 Android</span><span class="sxs-lookup"><span data-stu-id="80802-146">Outlook for iOS and Android</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

<span data-ttu-id="80802-147">如需更深入瞭解 Exchange Online 中的安全性，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="80802-147">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- [<span data-ttu-id="80802-148">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="80802-148">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [<span data-ttu-id="80802-149">Exchange Online 的安全性和合規性</span><span class="sxs-lookup"><span data-stu-id="80802-149">Security and compliance for Exchange Online</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [<span data-ttu-id="80802-150">反垃圾郵件和反惡意程式碼防護</span><span class="sxs-lookup"><span data-stu-id="80802-150">Anti-spam and anti-malware protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

<span data-ttu-id="80802-151">接下來，使用這些資源來瞭解 Exchange Online 信箱管理：</span><span class="sxs-lookup"><span data-stu-id="80802-151">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- [<span data-ttu-id="80802-152">在 Exchange Online 中建立使用者信箱</span><span class="sxs-lookup"><span data-stu-id="80802-152">Create user mailboxes in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [<span data-ttu-id="80802-153">管理使用者信箱</span><span class="sxs-lookup"><span data-stu-id="80802-153">Manage user mailboxes</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [<span data-ttu-id="80802-154">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="80802-154">Create and manage distribution groups</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a><span data-ttu-id="80802-155">結果</span><span class="sxs-lookup"><span data-stu-id="80802-155">Result</span></span>

<span data-ttu-id="80802-156">您瞭解信箱遷移、安全性和管理，並準備好開始將 Exchange Online 推出至組織中所選的群組。</span><span class="sxs-lookup"><span data-stu-id="80802-156">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="80802-157">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="80802-157">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="80802-158">對於大部分的大中型組織，您應該對您的專案關係人，從第1階段、早期的使用方式和技術愛好者執行 IT 試驗。</span><span class="sxs-lookup"><span data-stu-id="80802-158">For most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="80802-159">在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="80802-159">During the IT pilot:</span></span>

- <span data-ttu-id="80802-160">向您的試驗參與者提供 Microsoft 365 授權，並將其內部部署信箱遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="80802-160">Give your pilot participants Microsoft 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="80802-161">為您的試驗參與者提供一組練習，以測試 Exchange Online 電子郵件、排程和其他功能。</span><span class="sxs-lookup"><span data-stu-id="80802-161">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="80802-162">決定您的變更管理策略，並產生材料，以促進整個組織的使用者採用 Outlook 和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="80802-162">Determine your change management strategy and produce materials to drive organization-wide user adoption of Outlook and Exchange Online.</span></span> 
 
  <span data-ttu-id="80802-163">變更管理資料可包含電子郵件公告文字、內部訓練計畫、走道海報和簡報。</span><span class="sxs-lookup"><span data-stu-id="80802-163">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="80802-164">這些材料會將 Exchange Online 和其優點告知組織，以提出意識和驅車使用的目的。</span><span class="sxs-lookup"><span data-stu-id="80802-164">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="80802-165">如需一些創意，請參閱[Microsoft 小組文章的變更管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)。</span><span class="sxs-lookup"><span data-stu-id="80802-165">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>

- <span data-ttu-id="80802-166">讓您的 IT 試驗參與者根據經驗審查變更管理資料。</span><span class="sxs-lookup"><span data-stu-id="80802-166">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="80802-167">他們可以提供最佳作法和建議的秘訣，以最大的方式描述 Outlook 和 Exchange Online 的優點，以及如何使用它來進行通訊和排程。</span><span class="sxs-lookup"><span data-stu-id="80802-167">They can provide tips on best practices and advice on how to best describe the benefits of Outlook and Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="80802-168">結果</span><span class="sxs-lookup"><span data-stu-id="80802-168">Result</span></span>

<span data-ttu-id="80802-169">您的 Exchange Online IT 試驗已完成，而且最初的變更管理材料已開發、評審及完善。</span><span class="sxs-lookup"><span data-stu-id="80802-169">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="80802-170">步驟 3：推行至業務小組</span><span class="sxs-lookup"><span data-stu-id="80802-170">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="80802-171">完成您的 IT 試驗後，請將 Exchange Online 向組織中的公司群組或部門推出。</span><span class="sxs-lookup"><span data-stu-id="80802-171">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="80802-172">如果您的組織使用內部部署電子郵件服務（例如 Exchange Server），此首展會包含信箱遷移。</span><span class="sxs-lookup"><span data-stu-id="80802-172">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="80802-173">這個推行應包括：</span><span class="sxs-lookup"><span data-stu-id="80802-173">This rollout should include:</span></span>

- <span data-ttu-id="80802-174">識別商務群組內的 Exchange Online 重要商務案例。</span><span class="sxs-lookup"><span data-stu-id="80802-174">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="80802-175">宣告活動，告知使用者對部門和工作或專案小組的 Exchange Online 使用方式的預期和時程表。</span><span class="sxs-lookup"><span data-stu-id="80802-175">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="80802-176">將商務群組成員的內部部署信箱遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="80802-176">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="80802-177">在 Outlook 上提供[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)，或介紹如何使用 outlook 的資源連結。</span><span class="sxs-lookup"><span data-stu-id="80802-177">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="80802-178">用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。</span><span class="sxs-lookup"><span data-stu-id="80802-178">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="80802-179">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="80802-179">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="80802-180">結果</span><span class="sxs-lookup"><span data-stu-id="80802-180">Result</span></span>

<span data-ttu-id="80802-181">使用 Outlook 和 Exchange Online 來啟動和執行商務群組，且已測試並精簡變更管理的材料。</span><span class="sxs-lookup"><span data-stu-id="80802-181">A business group is up and running with Outlook and Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="80802-182">第 3 階段：發揮價值</span><span class="sxs-lookup"><span data-stu-id="80802-182">Phase 3: Drive value</span></span>

<span data-ttu-id="80802-183">在此階段中，您會完成 Exchange Online 的展示，並支援您的使用者，以協助他們實現其優點。</span><span class="sxs-lookup"><span data-stu-id="80802-183">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="80802-184">步驟1：向組織的其餘部分推出 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80802-184">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="80802-185">推行至貴組織其餘單位應包含：</span><span class="sxs-lookup"><span data-stu-id="80802-185">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="80802-186">在個別商務群組中識別 Exchange Online 的主要商務案例。</span><span class="sxs-lookup"><span data-stu-id="80802-186">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="80802-187">使用您精緻的變更管理材料進行宣告活動，告知組織 Exchange Online 使用的預期和時程表。</span><span class="sxs-lookup"><span data-stu-id="80802-187">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="80802-188">將組織中其他組織的信箱遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="80802-188">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="80802-189">在 Outlook 中傳送[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)或提供資源連結，以引進 outlook 及其使用方式。</span><span class="sxs-lookup"><span data-stu-id="80802-189">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or provide links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="80802-p112">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="80802-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="80802-193">結果</span><span class="sxs-lookup"><span data-stu-id="80802-193">Result</span></span>

<span data-ttu-id="80802-194">您的組織已啟動並執行，您的變更管理策略已到位，可通知、訓練及啟用使用者使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="80802-194">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="80802-195">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="80802-195">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="80802-196">將 Exchange Online 向整個組織推出後，您必須繼續使用變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="80802-196">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="80802-197">讓您的領導能力將 Exchange Online 提升為主要工具，以進行個別及短期限的通訊和排程。</span><span class="sxs-lookup"><span data-stu-id="80802-197">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="80802-198">鼓勵個人使用它進行商務群組、部門、工作和專案小組通訊、行事曆和共同作業。</span><span class="sxs-lookup"><span data-stu-id="80802-198">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="80802-199">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="80802-199">Here are some suggested activities:</span></span>

- <span data-ttu-id="80802-200">請參閱[Microsoft 365 的成功要素](https://aka.ms/successfactors)，以瞭解雲端服務採用的一般最佳作法。</span><span class="sxs-lookup"><span data-stu-id="80802-200">See [Success factors for Microsoft 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="80802-201">請參閱系統[管理中心的 Microsoft 365 報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以瞭解整個組織的服務使用方式。</span><span class="sxs-lookup"><span data-stu-id="80802-201">See [Microsoft 365 Reports in the admin center](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand service usage across your organization.</span></span> <span data-ttu-id="80802-202">如果您不是組織的全域系統管理員，請要求全域系統管理員將報告讀取者許可權授與您的使用者帳戶，這樣您就可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="80802-202">If you aren't a global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="80802-203">監視您的意見反應（一個中央小組小組或 Yammer 中的公用通道），以取得來自 Exchange Online 經驗之人員的問題和意見反應。</span><span class="sxs-lookup"><span data-stu-id="80802-203">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="80802-204">快速解決問題，避免使用者在使用上感到挫折，並展現出對推行的支援。</span><span class="sxs-lookup"><span data-stu-id="80802-204">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="80802-205">在每個業務群組中識別並 nurture 冠軍，並使用 Outlook 強調其最佳作法。</span><span class="sxs-lookup"><span data-stu-id="80802-205">Identify and nurture champions in each business group and highlight their best practices using Outlook.</span></span> <span data-ttu-id="80802-206">向組織反映他們的成功，以顯示專案的成功和導入成效。</span><span class="sxs-lookup"><span data-stu-id="80802-206">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="80802-207">由公司群組內的技術領導者認可哥對領導者和對等專案產生強大的影響。</span><span class="sxs-lookup"><span data-stu-id="80802-207">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="80802-208">結果</span><span class="sxs-lookup"><span data-stu-id="80802-208">Result</span></span>

<span data-ttu-id="80802-209">您的組織已採用 Exchange Online 和 Outlook 作為主要個人和小群組短壽命的通訊和排程工具。</span><span class="sxs-lookup"><span data-stu-id="80802-209">Your organization has adopted Exchange Online and Outlook as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="80802-210">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="80802-210">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="80802-211">若要在 Microsoft 中查看並瞭解如何遷移至 Exchange Online，以及如何使用 Exchange Online Protection 來防禦網路攻擊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="80802-211">To peek inside Microsoft and learn how we migrated to Exchange Online and are using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="80802-212">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="80802-212">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="80802-213">Microsoft 會使用威脅情報來保護、偵測及回應威脅</span><span class="sxs-lookup"><span data-stu-id="80802-213">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="80802-214">Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試</span><span class="sxs-lookup"><span data-stu-id="80802-214">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="80802-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="80802-215">Next steps</span></span>

<span data-ttu-id="80802-216">請參閱下列資源，以進行 Exchange Online 的日常維護：</span><span class="sxs-lookup"><span data-stu-id="80802-216">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- [<span data-ttu-id="80802-217">Exchange Online 中的 exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="80802-217">Exchange admin center in Exchange Online</span></span>](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [<span data-ttu-id="80802-218">Exchange Online 中的監控、報告和郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="80802-218">Monitoring, reporting, and message tracing in Exchange Online</span></span>](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [<span data-ttu-id="80802-219">在 Exchange Online 中備份電子郵件</span><span class="sxs-lookup"><span data-stu-id="80802-219">Backing up email in Exchange Online</span></span>](https://docs.microsoft.com/exchange/back-up-email) 
