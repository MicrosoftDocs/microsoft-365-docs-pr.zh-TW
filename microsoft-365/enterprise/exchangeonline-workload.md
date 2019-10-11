---
title: 部署 Microsoft 365 企業版適用於 Exchange Online
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
description: 逐步說明的規劃、 推行並發揮值的 Exchange Online 中 Microsoft 365 企業版整個組織的程序。
ms.openlocfilehash: 30ba71fbf2af684afbbffe0a2e2b1720a8eeec2c
ms.sourcegitcommit: 255e8194bb5767a9983d54d16e79d628732a1d97
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/11/2019
ms.locfileid: "37453859"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="7648e-103">部署 Microsoft 365 企業版適用於 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7648e-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7648e-104">*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="7648e-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7648e-105">Exchange Online 是您主要的電子郵件和行事曆雲端服務，可協助讓使用者以不需要即時聊天或集中化文件儲存區的方式進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="7648e-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="7648e-106">Exchange Online 會針對 Microsoft 365 企業版的團隊合作值內建的重要元素。</span><span class="sxs-lookup"><span data-stu-id="7648e-106">Exchange Online is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="7648e-107">Exchange Online 可讓您達成更多，並與已知的 Outlook 應用程式，無論您是哪一種裝置更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="7648e-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="7648e-108">Exchange Online 也有可保護信箱的進階安全性功能 (包括反惡意程式碼和反垃圾郵件篩選)，以及可防止使用者將敏感資訊誤傳給未經授權人員的資料外洩防護功能。</span><span class="sxs-lookup"><span data-stu-id="7648e-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="7648e-109">Exchange Online 安全性是 Microsoft 365 企業版的智慧型安全性值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="7648e-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="7648e-110">如果您從未使用過 Exchange Online，請參閱 [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="7648e-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="7648e-111">下列階段與步驟逐步引導您想像的 Exchange Online 組織上架中的角色變換一系列的漸進式發行至 Exchange Online 組織並發揮的 Exchange Online 的使用狀況的程序和其您的使用者值。</span><span class="sxs-lookup"><span data-stu-id="7648e-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="7648e-112">您已完成[階段 2-的身分識別的 Microsoft 365 企業版底層基礎結構](identity-infrastructure.md)之後，才應該遵循下列部署指示。</span><span class="sxs-lookup"><span data-stu-id="7648e-112">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity of the Microsoft 365 Enterprise foundation infrastructure](identity-infrastructure.md).</span></span>
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a><span data-ttu-id="7648e-113">第 1 階段： 構想 Exchange Online 部署</span><span class="sxs-lookup"><span data-stu-id="7648e-113">Phase 1: Envision your Exchange Online deployment</span></span>

<span data-ttu-id="7648e-114">在這個階段，您要召集負責 Exchange Online 部署的人員，並決定組織將如何使用 Exchange Online 來解決其商業需求。</span><span class="sxs-lookup"><span data-stu-id="7648e-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="7648e-115">步驟 1： 收集您的 Exchange Online 部署成員</span><span class="sxs-lookup"><span data-stu-id="7648e-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="7648e-116">適用於成功部署的 Exchange Online 上的 Microsoft 365 企業版底層基礎結構的[階段 2-Identity](identity-infrastructure.md) ，您需要收集的輸入和意見反應正確的人員。</span><span class="sxs-lookup"><span data-stu-id="7648e-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to gather the right people for input and feedback.</span></span> <span data-ttu-id="7648e-117">主要人員包括商務決策者、 IT 人員，例如架構師和實作者注意事項，與使用者的代言人。</span><span class="sxs-lookup"><span data-stu-id="7648e-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="7648e-118">這三個群組請確定您 Exchange Online 的部署包含解決業務需求、 技術方面的信箱移轉及安全性]，和結果是某個項目會使用一般使用者的考量。</span><span class="sxs-lookup"><span data-stu-id="7648e-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result is something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="7648e-119">結果</span><span class="sxs-lookup"><span data-stu-id="7648e-119">Result</span></span>

<span data-ttu-id="7648e-120">代表組織的業務、技術、使用者三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="7648e-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="7648e-121">步驟 2： 決定您 Exchange Online 商務案例並優先順序</span><span class="sxs-lookup"><span data-stu-id="7648e-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="7648e-122">Exchange Online 可以用於不同用途。</span><span class="sxs-lookup"><span data-stu-id="7648e-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="7648e-123">您要找出哪些用途對應至您的業務需求，在您的組織、 您的業務團隊、 部門或個別的工作和專案小組的不同層級上。</span><span class="sxs-lookup"><span data-stu-id="7648e-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="7648e-124">您應該針對 Exchange Online，以解決您個別及小型群組短暫通訊和排程需求。</span><span class="sxs-lookup"><span data-stu-id="7648e-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="7648e-125">若要查看 Exchange Online 的好處的其中一個方法是檢查如何個人、 小組成員或 v 小組互動今日，然後尋找適當的案例，提供更容易的方法來進行通訊，排程會議，並進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="7648e-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="7648e-126">請記住， [Microsoft Teams](teams-workload.md)可能是比較好的選擇，某些共同作業案例。</span><span class="sxs-lookup"><span data-stu-id="7648e-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

#### <a name="result"></a><span data-ttu-id="7648e-127">結果</span><span class="sxs-lookup"><span data-stu-id="7648e-127">Result</span></span>
<span data-ttu-id="7648e-128">Exchange Online 案例，能解決貴組織的需求為通訊、 排程及短暫的共同作業清單。</span><span class="sxs-lookup"><span data-stu-id="7648e-128">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="7648e-129">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="7648e-129">Phase 2: Onboard</span></span>

<span data-ttu-id="7648e-130">在這個階段，規劃的 Exchange Online 部署的技術層面，然後開始向所選的使用者群組推行。</span><span class="sxs-lookup"><span data-stu-id="7648e-130">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="7648e-131">必要條件：身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="7648e-131">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="7648e-132">若要保護 Exchange Online 信箱的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7648e-132">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="7648e-133">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="7648e-133">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="7648e-134">開始技術規劃之前，請先決定是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="7648e-134">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="7648e-135">如果您的組織有超過 50 個基座，並參與[符合資格的方案](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)，您可以使用[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，*沒有額外的費用可*引導您完成規劃、 部署及服務採用。</span><span class="sxs-lookup"><span data-stu-id="7648e-135">If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *available at no additional cost* to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="7648e-136">或者，您可以使用 FastTrack 導入精靈來完成這項工作，只要您使用 Microsoft 365 帳戶登入後，就能從 [FastTrack](https://fasttrack.microsoft.com/) 使用該精靈。</span><span class="sxs-lookup"><span data-stu-id="7648e-136">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Microsoft 365 account.</span></span>

<span data-ttu-id="7648e-137">如果您編寫自己的規劃，或與 FastTrack 一起使用，您需要判斷您的網路和組織是否準備好進行 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7648e-137">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="7648e-138">請務必特別是您在 [連線到您組織網路的使用者在基本基礎結構符合[網路](networking-infrastructure.md)的允出準則。</span><span class="sxs-lookup"><span data-stu-id="7648e-138">It is especially important that you meet the exit criteria for [networking](networking-infrastructure.md) in your foundation infrastructure for users connected to your organization network.</span></span> <span data-ttu-id="7648e-139">請特別注意網際網路頻寬、 輸送量及流量延遲，以最佳化效能的其他流量的 Exchange Online 式電子郵件和附件。</span><span class="sxs-lookup"><span data-stu-id="7648e-139">Pay special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="7648e-140">使用這些資源來準備 Exchange Online 推行的技術層面：</span><span class="sxs-lookup"><span data-stu-id="7648e-140">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="7648e-141">將多個電子郵件帳戶移轉到 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="7648e-141">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [<span data-ttu-id="7648e-142">將 Exchange Server 公用資料夾遷移至 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7648e-142">Migrate Exchange Server public folders to Exchange Online</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [<span data-ttu-id="7648e-143">Exchange Server 公用資料夾移轉到 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="7648e-143">Migrate Exchange Server public folders to Office 365 Groups</span></span>](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [<span data-ttu-id="7648e-144">共同作業中 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7648e-144">Collaboration in Exchange Online</span></span>](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [<span data-ttu-id="7648e-145">Exchange Online 中的收件者</span><span class="sxs-lookup"><span data-stu-id="7648e-145">Recipients in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [<span data-ttu-id="7648e-146">Outlook for iOS 和 Android</span><span class="sxs-lookup"><span data-stu-id="7648e-146">Outlook for iOS and Android</span></span>](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

<span data-ttu-id="7648e-147">進一步了解 Exchange Online 中的安全性，請先檢閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="7648e-147">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- [<span data-ttu-id="7648e-148">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="7648e-148">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [<span data-ttu-id="7648e-149">安全性與合規性的 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7648e-149">Security and compliance for Exchange Online</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [<span data-ttu-id="7648e-150">反垃圾郵件和反惡意程式碼防護</span><span class="sxs-lookup"><span data-stu-id="7648e-150">Anti-spam and anti-malware protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

<span data-ttu-id="7648e-151">接下來，使用這些資源來了解 Exchange Online 信箱管理：</span><span class="sxs-lookup"><span data-stu-id="7648e-151">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- [<span data-ttu-id="7648e-152">在 Exchange Online 中建立使用者信箱</span><span class="sxs-lookup"><span data-stu-id="7648e-152">Create user mailboxes in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [<span data-ttu-id="7648e-153">管理使用者信箱</span><span class="sxs-lookup"><span data-stu-id="7648e-153">Manage user mailboxes</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [<span data-ttu-id="7648e-154">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="7648e-154">Create and manage distribution groups</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a><span data-ttu-id="7648e-155">結果</span><span class="sxs-lookup"><span data-stu-id="7648e-155">Result</span></span>

<span data-ttu-id="7648e-156">您了解信箱移轉、 安全性和管理，並準備好要開始推出 Exchange Online 至組織中選取的群組。</span><span class="sxs-lookup"><span data-stu-id="7648e-156">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="7648e-157">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="7648e-157">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="7648e-158">針對最中型和大型的組織，您應該從階段 1、 早期採納者和技術愛好者 IT 試驗執行與專案關係人。</span><span class="sxs-lookup"><span data-stu-id="7648e-158">For most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts.</span></span> <span data-ttu-id="7648e-159">在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="7648e-159">During the IT pilot:</span></span>

- <span data-ttu-id="7648e-160">給試驗參與者 Microsoft 365 授權，並將其內部部署信箱遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7648e-160">Give your pilot participants Microsoft 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="7648e-161">給試驗參與者一些練習，來測試 Exchange Online 電子郵件、 排程及其他功能。</span><span class="sxs-lookup"><span data-stu-id="7648e-161">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="7648e-162">判斷您的變更管理策略，並產生到 Outlook 和 Exchange Online 的全組織的使用者採用的材料。</span><span class="sxs-lookup"><span data-stu-id="7648e-162">Determine your change management strategy and produce materials to drive organization-wide user adoption of Outlook and Exchange Online.</span></span> 
 
  <span data-ttu-id="7648e-163">變更管理資料可包含電子郵件公告文字、內部訓練計畫、走道海報和簡報。</span><span class="sxs-lookup"><span data-stu-id="7648e-163">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="7648e-164">這些資料會通知組織有關 Exchange Online 和以目標引發認知和主導流量及其優點。</span><span class="sxs-lookup"><span data-stu-id="7648e-164">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="7648e-165">請參閱[變更管理策略的 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)一些想法。</span><span class="sxs-lookup"><span data-stu-id="7648e-165">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>

- <span data-ttu-id="7648e-166">讓您的 IT 試驗參與者根據經驗審查變更管理資料。</span><span class="sxs-lookup"><span data-stu-id="7648e-166">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="7648e-167">他們可以提供的祕訣最佳作法和建議如何以最佳說明 Outlook 與 Exchange Online 的優點，以及如何用它來進行通訊，以及排程。</span><span class="sxs-lookup"><span data-stu-id="7648e-167">They can provide tips on best practices and advice on how to best describe the benefits of Outlook and Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="7648e-168">結果</span><span class="sxs-lookup"><span data-stu-id="7648e-168">Result</span></span>

<span data-ttu-id="7648e-169">Exchange Online 的 IT 試驗完成且次變更管理材料已開發、 檢閱、 並精簡。</span><span class="sxs-lookup"><span data-stu-id="7648e-169">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="7648e-170">步驟 3：推行至業務小組</span><span class="sxs-lookup"><span data-stu-id="7648e-170">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="7648e-171">完成後您的 IT 試驗，推出 Exchange Online 商務群組或組織中的部門。</span><span class="sxs-lookup"><span data-stu-id="7648e-171">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="7648e-172">如果您的組織使用內部部署電子郵件服務，例如 Exchange Server，此導入包含移轉的信箱。</span><span class="sxs-lookup"><span data-stu-id="7648e-172">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="7648e-173">這個推行應包括：</span><span class="sxs-lookup"><span data-stu-id="7648e-173">This rollout should include:</span></span>

- <span data-ttu-id="7648e-174">識別重要商務案例的 Exchange Online 商務群組中。</span><span class="sxs-lookup"><span data-stu-id="7648e-174">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="7648e-175">用公告活動通知使用者的預期變更和時間表部門及工作或專案小組的 Exchange Online 使用。</span><span class="sxs-lookup"><span data-stu-id="7648e-175">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="7648e-176">移轉至 Exchange Online 商務群組成員的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="7648e-176">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="7648e-177">提供在 Outlook 或連結的[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)資源介紹 Outlook 和如何加以使用。</span><span class="sxs-lookup"><span data-stu-id="7648e-177">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="7648e-178">用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。</span><span class="sxs-lookup"><span data-stu-id="7648e-178">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="7648e-179">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="7648e-179">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="7648e-180">結果</span><span class="sxs-lookup"><span data-stu-id="7648e-180">Result</span></span>

<span data-ttu-id="7648e-181">商務群組，且和執行與 Outlook 和 Exchange Online 變更管理的材料已測試並精簡。</span><span class="sxs-lookup"><span data-stu-id="7648e-181">A business group is up and running with Outlook and Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="7648e-182">第 3 階段：發揮價值</span><span class="sxs-lookup"><span data-stu-id="7648e-182">Phase 3: Drive value</span></span>

<span data-ttu-id="7648e-183">在這個階段，您完成推出 Exchange Online，並支援您的使用者，以協助他們了解其優點。</span><span class="sxs-lookup"><span data-stu-id="7648e-183">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="7648e-184">步驟 1： 推行 Exchange Online 組織的其餘部分</span><span class="sxs-lookup"><span data-stu-id="7648e-184">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="7648e-185">推行至貴組織其餘單位應包含：</span><span class="sxs-lookup"><span data-stu-id="7648e-185">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="7648e-186">識別重要商務案例的 Exchange Online 中的個別商務群組。</span><span class="sxs-lookup"><span data-stu-id="7648e-186">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="7648e-187">使用精簡的變更管理的材料公告活動通知貴組織的預期變更和時間表的 Exchange Online 使用。</span><span class="sxs-lookup"><span data-stu-id="7648e-187">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="7648e-188">移轉至 Exchange Online 組織的其餘部分的信箱。</span><span class="sxs-lookup"><span data-stu-id="7648e-188">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="7648e-189">Outlook 提供[使用者訓練](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca)或提供的資源介紹 Outlook，以及如何使用它的連結。</span><span class="sxs-lookup"><span data-stu-id="7648e-189">Delivering [user training](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) on Outlook or provide links to resources to introduce Outlook and how to use it.</span></span>
- <span data-ttu-id="7648e-p112">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="7648e-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="7648e-193">結果</span><span class="sxs-lookup"><span data-stu-id="7648e-193">Result</span></span>

<span data-ttu-id="7648e-194">您的組織已啟動並執行和變更管理策略已經準備就緒，可以通知、 訓練並讓使用者使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7648e-194">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="7648e-195">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="7648e-195">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="7648e-196">推行後 Exchange Online 至整個組織，您必須繼續使用變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="7648e-196">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="7648e-197">讓領導者將 Exchange Online 升級為主要工具，進行個別和短暫的通訊和排程。</span><span class="sxs-lookup"><span data-stu-id="7648e-197">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="7648e-198">鼓勵個人將它用於商務群組、 部門、 工作和專案小組的溝通、 行事曆、 和共同作業。</span><span class="sxs-lookup"><span data-stu-id="7648e-198">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="7648e-199">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="7648e-199">Here are some suggested activities:</span></span>

- <span data-ttu-id="7648e-200">請參閱 [Office 365 的成功要素](https://aka.ms/successfactors) (英文) 以了解雲端服務導入的一般最佳做法。</span><span class="sxs-lookup"><span data-stu-id="7648e-200">See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="7648e-p113">請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="7648e-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="7648e-203">監視您的意見反應場所 （中央 microsoft Teams 小組或 Yammer 中的公用通道） 問題與從他們的經驗與 Exchange Online 相關的個人的意見反應。</span><span class="sxs-lookup"><span data-stu-id="7648e-203">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="7648e-204">快速解決問題，避免使用者在使用上感到挫折，並展現出對推行的支援。</span><span class="sxs-lookup"><span data-stu-id="7648e-204">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="7648e-205">識別並加強冠軍每個商務群組中的，並反白顯示其使用 Outlook 的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="7648e-205">Identify and nurture champions in each business group and highlight their best practices using Outlook.</span></span> <span data-ttu-id="7648e-206">向組織反映他們的成功，以顯示專案的成功和導入成效。</span><span class="sxs-lookup"><span data-stu-id="7648e-206">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="7648e-207">依商務群組內的技術主管適用的背書可以會強大的影響整個負責人及其等項目。</span><span class="sxs-lookup"><span data-stu-id="7648e-207">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="7648e-208">結果</span><span class="sxs-lookup"><span data-stu-id="7648e-208">Result</span></span>

<span data-ttu-id="7648e-209">貴組織已採用 Exchange Online 和 Outlook，為其主要的個別及小型群組短暫的通訊和排程的工具。</span><span class="sxs-lookup"><span data-stu-id="7648e-209">Your organization has adopted Exchange Online and Outlook as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="7648e-210">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="7648e-210">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7648e-211">一窺 Microsoft 並了解我們如何移轉至 Exchange Online 及使用 Exchange Online Protection 防範網路攻擊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="7648e-211">To peek inside Microsoft and learn how we migrated to Exchange Online and are using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="7648e-212">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7648e-212">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="7648e-213">Microsoft 會使用威脅情報來保護、偵測及回應威脅</span><span class="sxs-lookup"><span data-stu-id="7648e-213">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="7648e-214">Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試</span><span class="sxs-lookup"><span data-stu-id="7648e-214">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="7648e-215">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7648e-215">Next steps</span></span>

<span data-ttu-id="7648e-216">請參閱 Exchange Online 的持續維護這些資源：</span><span class="sxs-lookup"><span data-stu-id="7648e-216">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- [<span data-ttu-id="7648e-217">Exchange Online 中的 Exchange 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="7648e-217">Exchange admin center in Exchange Online</span></span>](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [<span data-ttu-id="7648e-218">監控、 報告和 Exchange Online 中的郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="7648e-218">Monitoring, reporting, and message tracing in Exchange Online</span></span>](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [<span data-ttu-id="7648e-219">備份電子郵件在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7648e-219">Backing up email in Exchange Online</span></span>](https://docs.microsoft.com/exchange/back-up-email) 
