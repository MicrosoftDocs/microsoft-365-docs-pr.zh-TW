---
title: 部署 Exchange Online Microsoft 365 enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: 逐步解說規劃、 啟用、 及 Microsoft 365 enterprise 驅動的 Exchange Online 值整個組織的程序的步驟。
ms.openlocfilehash: 36b24290acd4467400eab86b4c2760ccad65deab
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866741"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="9e687-103">部署 Exchange Online Microsoft 365 enterprise</span><span class="sxs-lookup"><span data-stu-id="9e687-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9e687-p101">Exchange Online 是您的電子郵件的主要雲端服務和行事曆的可幫助您的使用者共同作業不需要即時聊天或集中式文件儲存區的方式。Exchange Online 是您執行個別及小型群組短期通訊及排程並且 Microsoft 365 企業版的團隊合作值的內建的關鍵元素。Exchange Online 可讓您完成多及更有效率地使用已知的 Outlook 應用程式，不論您是在何種裝置。</span><span class="sxs-lookup"><span data-stu-id="9e687-p101">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage. Exchange Online is how you do individual and small group short-lived communication and scheduling and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise. Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="9e687-p102">Exchange Online 也具有進階安全性功能，包括反惡意程式碼和反垃圾郵件篩選保護信箱並防止使用者遭傳送機密資訊給未經授權人士的資料遺失防護功能。Exchange Online 安全性是 Microsoft 365 企業版的智慧型安全性值的關鍵元素。</span><span class="sxs-lookup"><span data-stu-id="9e687-p102">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people. Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="9e687-109">如果您是全新 Exchange online，請參閱[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="9e687-109">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="9e687-110">下列階段與步驟引導您進行想像變換一系列的漸進式部署至 Exchange Online 組織的 Exchange Online 組織 onboarding 中的角色及驅動的 Exchange Online 的使用狀況的程序和其為一般使用者的值。</span><span class="sxs-lookup"><span data-stu-id="9e687-110">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="9e687-111">Microsoft 365 enterprise 完成您[foundation 基礎結構](deploy-foundation-infrastructure.md)後才應該遵循這些部署指示。</span><span class="sxs-lookup"><span data-stu-id="9e687-111">These deployment instructions should be followed only after you’ve completed your [foundation infrastructure](deploy-foundation-infrastructure.md) for Microsoft 365 Enterprise.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="9e687-112">第 1 階段：構想</span><span class="sxs-lookup"><span data-stu-id="9e687-112">Phase 1: Envision</span></span>

<span data-ttu-id="9e687-113">在此階段中，您收集 Exchange Online 部署的人員，並決定如何組織會使用 Exchange Online 工具來處理其業務需求。</span><span class="sxs-lookup"><span data-stu-id="9e687-113">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="9e687-114">步驟 1： 收集您的 Exchange Online 部署成員</span><span class="sxs-lookup"><span data-stu-id="9e687-114">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="9e687-p103">成功部署的 Exchange Online 上的 Microsoft 365 [foundation 基礎結構](deploy-foundation-infrastructure.md)功能，您需要輸入及意見反應取得適當的人員。主要人員包括商業性決策負責人、 IT 人員如架構師和實施者注意事項，以及適用於使用者的代言人。</span><span class="sxs-lookup"><span data-stu-id="9e687-p103">For a successful deployment of Exchange Online on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="9e687-117">這三個群組請確定您的 Exchange Online 部署包含解決的業務需求、 技術方面的信箱移轉與安全性，及結果會是某個項目將會使用一般使用者的考量。</span><span class="sxs-lookup"><span data-stu-id="9e687-117">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="9e687-118">結果</span><span class="sxs-lookup"><span data-stu-id="9e687-118">Result</span></span>

<span data-ttu-id="9e687-119">代表組織的業務、技術、使用者三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="9e687-119">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="9e687-120">步驟 2： 決定與 Exchange Online 的商務案例的優先順序</span><span class="sxs-lookup"><span data-stu-id="9e687-120">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="9e687-p104">Exchange Online 可用於不同的用途。您必須了解哪些用途對應至您的業務需求的組織、 業務團隊、 部門或個別的工作及專案小組的不同層級上。您應該目標 Exchange Online，以解決您個別及小型群組短期通訊及排程需求。</span><span class="sxs-lookup"><span data-stu-id="9e687-p104">Exchange Online can be used for different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams. You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="9e687-p105">請參閱 Exchange Online 的優點的其中一個方法是檢查如何個人、 小組、 或 v 小組 today、 互動，然後尋找適當的案例提供更輕鬆地排程會議和共同作業的方式。請記住[的 Microsoft 小組](teams-workload.md)可能的共同作業案例的一些較佳的選擇。</span><span class="sxs-lookup"><span data-stu-id="9e687-p105">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate. Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

<span data-ttu-id="9e687-126">Exchange Online 達成了 Microsoft 365 企業版的這些策略商務案例：</span><span class="sxs-lookup"><span data-stu-id="9e687-126">Exchange Online enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="9e687-127">即時或自己運用時間在文件上共同作業，簡化共同建立的程序</span><span class="sxs-lookup"><span data-stu-id="9e687-127">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="9e687-128">管理專案、工作和截止日期，達成業務目標</span><span class="sxs-lookup"><span data-stu-id="9e687-128">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="9e687-129">了解您的工作習慣以提升影響力</span><span class="sxs-lookup"><span data-stu-id="9e687-129">Understand your work habits to improve your influence and impact</span></span>
- <span data-ttu-id="9e687-130">與小組溝通以取得最新資訊、要求輸入，並建立凝聚力和共識</span><span class="sxs-lookup"><span data-stu-id="9e687-130">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="9e687-131">在組織內外部儲存及共用檔案，順暢地跨越組織界限工作</span><span class="sxs-lookup"><span data-stu-id="9e687-131">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="9e687-132">隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式</span><span class="sxs-lookup"><span data-stu-id="9e687-132">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="9e687-133">保護您的資訊，並降低資料遺失風險</span><span class="sxs-lookup"><span data-stu-id="9e687-133">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="9e687-134">偵測及防範外部威脅</span><span class="sxs-lookup"><span data-stu-id="9e687-134">Detect and protect against external threats</span></span> 
- <span data-ttu-id="9e687-135">監控、 報告及分析活動回應立即提供組織的安全性</span><span class="sxs-lookup"><span data-stu-id="9e687-135">Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="9e687-136">使用增強的隱私權和法規遵循來支援貴組織，以符合一般資料保護規定 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="9e687-136">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>

<span data-ttu-id="9e687-137">如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9e687-137">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

#### <a name="result"></a><span data-ttu-id="9e687-138">結果</span><span class="sxs-lookup"><span data-stu-id="9e687-138">Result</span></span>
<span data-ttu-id="9e687-139">Exchange Online 解決貴組織的需求為通訊、 排程和短期的共同作業的案例清單。</span><span class="sxs-lookup"><span data-stu-id="9e687-139">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="9e687-140">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="9e687-140">Phase 2: Onboard</span></span>

<span data-ttu-id="9e687-141">在此階段中，您的 Exchange Online 部署的技術方面的規劃，並啟動推出至選取的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="9e687-141">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="9e687-142">必要： 身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="9e687-142">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="9e687-143">若要保護 Exchange Online 信箱的存取權，請確定您已設定[身分識別與裝置存取的原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9e687-143">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="9e687-144">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="9e687-144">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="9e687-p106">開始技術規劃之前，請決定您是否要使用 FastTrack。如果您的組織有超過 50 基座及參與[合格的計劃](https://technet.microsoft.com/library/dn783224.aspx)中，您可以使用[Microsoft 365 FastTrack](https://fasttrack.microsoft.com/microsoft365)，可在引導您進行規劃、 部署及服務採用任何其他成本。或者，您可以使用 FastTrack Onboarding 精靈一旦您使用 Office 365 帳戶登入，均可在[FastTrack](https://fasttrack.microsoft.com/)自行完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="9e687-p106">Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment, and service adoption. Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="9e687-p107">如果您執行的動作您自己的規劃、 或 FastTrack 搭配，您必須決定您的網路和組織是否已準備好用於 Exchange Online。尤為重要 foundation 基礎結構，以特別注意的網際網路頻寬、 輸送量和流量延遲自學針對其他流量的 Exchange 中符合網路允出準則線上式電子郵件和附件。</span><span class="sxs-lookup"><span data-stu-id="9e687-p107">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online. It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="9e687-150">使用下列資源準備 Exchange Online 的導入的技術方面：</span><span class="sxs-lookup"><span data-stu-id="9e687-150">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="9e687-151">將多個電子郵件帳戶移轉到 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="9e687-151">Ways to migrate multiple email accounts to Office 365</span></span>](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
- <span data-ttu-id="9e687-152">[Office 365 郵件移轉顧問](https://portal.office.com/onboarding/mailsetupadvisor#/)（必須先登入您的 Office 365 訂閱）</span><span class="sxs-lookup"><span data-stu-id="9e687-152">[Office 365 mail migration advisor](https://portal.office.com/onboarding/mailsetupadvisor#/) (must be signed in to your Office 365 subscription)</span></span>
- <span data-ttu-id="9e687-153">[Exchange Online 中的協同作業](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-153">[Collaboration in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="9e687-154">[Exchange Online 中的收件者](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-154">[Recipients in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span></span>

<span data-ttu-id="9e687-155">搭配成效更深入了解 Exchange Online 中的安全性的檢閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="9e687-155">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- <span data-ttu-id="9e687-156">[Exchange Online 中的權限](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-156">[Permissions in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="9e687-157">[安全性及規範的 Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-157">[Security and compliance for Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="9e687-158">[反垃圾郵件和反惡意程式碼防護](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-158">[Anti-spam and anti-malware protection](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span></span>

<span data-ttu-id="9e687-159">接下來，了解 Exchange Online 信箱管理使用下列資源：</span><span class="sxs-lookup"><span data-stu-id="9e687-159">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- <span data-ttu-id="9e687-160">[在 Exchange Online 中建立使用者信箱](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-160">[Create user mailboxes in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="9e687-161">[管理使用者信箱](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-161">[Manage user mailboxes](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span></span> 
- [<span data-ttu-id="9e687-162">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="9e687-162">Create and manage distribution groups</span></span>](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a><span data-ttu-id="9e687-163">結果</span><span class="sxs-lookup"><span data-stu-id="9e687-163">Result</span></span>

<span data-ttu-id="9e687-164">您了解信箱移轉、 安全性和管理並準備開始啟用 Exchange Online 組織中所選群組。</span><span class="sxs-lookup"><span data-stu-id="9e687-164">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="9e687-165">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="9e687-165">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="9e687-p108">在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="9e687-p108">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="9e687-168">選擇您的 IT 試驗參與者可以在其中練習 Exchange Online 商務案例。</span><span class="sxs-lookup"><span data-stu-id="9e687-168">Choose an Exchange Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="9e687-169">Office 365 授權給您的試驗參與者並將其內部部署信箱遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9e687-169">Give your pilot participants Office 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="9e687-170">將授與您的試驗參與者練習測試 Exchange Online 電子郵件、 排程和其他功能。</span><span class="sxs-lookup"><span data-stu-id="9e687-170">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="9e687-p109">判斷您變更管理策略及產生的 Exchange Online 的磁碟機全組織使用者採用的運送。變更管理教材 （英文） 可以包含電子郵件宣告文字、 內部訓練計劃、 走廊海報與簡報。這些資料會通知您的組織有關 Exchange Online 與及其優點與引發傳達和主導流量的目標。請參閱[變更的 Microsoft 小組管理策略](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)的某些概念。</span><span class="sxs-lookup"><span data-stu-id="9e687-p109">Determine your change management strategy and produce materials to drive organization-wide user adoption of Exchange Online. Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage. See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="9e687-p110">請檢閱根據其體驗變更管理教材您 IT 試驗參與者。他們可以提供秘訣最佳作法和建議如何以最佳描述的 Exchange Online 優點及如何使用的通訊及排程。</span><span class="sxs-lookup"><span data-stu-id="9e687-p110">Have your IT pilot participants review the change management materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="9e687-177">結果</span><span class="sxs-lookup"><span data-stu-id="9e687-177">Result</span></span>

<span data-ttu-id="9e687-178">Exchange Online IT 試驗完成且初始變更管理教材 （英文） 已開發方法、 檢閱、 以及精簡。</span><span class="sxs-lookup"><span data-stu-id="9e687-178">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="9e687-179">步驟 3：推行至商務群組</span><span class="sxs-lookup"><span data-stu-id="9e687-179">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="9e687-p111">完成後 IT 試驗，導入 Exchange Online 商務群組或組織中的部門。如果您的組織會使用內部部署電子郵件服務，例如 Exchange Server，此導入包含移轉的信箱。此導入應該包括：</span><span class="sxs-lookup"><span data-stu-id="9e687-p111">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization. If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration. This rollout should include:</span></span>

- <span data-ttu-id="9e687-183">識別重要的商務案例的 Exchange Online 的商務群組中。</span><span class="sxs-lookup"><span data-stu-id="9e687-183">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="9e687-184">宣告的活動，告知使用者的期望與時間表的 Exchange Online 的部門和公司或專案小組使用。</span><span class="sxs-lookup"><span data-stu-id="9e687-184">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="9e687-185">移轉至 Exchange Online 您商務群組成員的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="9e687-185">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="9e687-186">提供在 Exchange Online 或連結的使用者訓練資源引進 Exchange Online 以及如何使用它。</span><span class="sxs-lookup"><span data-stu-id="9e687-186">Delivering user training on Exchange Online or links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="9e687-187">用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。</span><span class="sxs-lookup"><span data-stu-id="9e687-187">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="9e687-188">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="9e687-188">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="9e687-189">結果</span><span class="sxs-lookup"><span data-stu-id="9e687-189">Result</span></span>

<span data-ttu-id="9e687-190">商務群組已開啟並執行與 Exchange Online 和變更管理教材 （英文） 已測試及精簡。</span><span class="sxs-lookup"><span data-stu-id="9e687-190">A business group is up and running with Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="9e687-191">階段 3：發揮價值</span><span class="sxs-lookup"><span data-stu-id="9e687-191">Phase 3: Drive value</span></span>

<span data-ttu-id="9e687-192">在此階段中，您需要完成的 Exchange Online 導入並支援您的使用者來協助他們瞭解及其優點。</span><span class="sxs-lookup"><span data-stu-id="9e687-192">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="9e687-193">步驟 1： 導入 Exchange Online 組織的其餘部分</span><span class="sxs-lookup"><span data-stu-id="9e687-193">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="9e687-194">推行至貴組織其餘單位應包含：</span><span class="sxs-lookup"><span data-stu-id="9e687-194">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="9e687-195">識別的主要商務案例的 Exchange Online 內個別業務團隊。</span><span class="sxs-lookup"><span data-stu-id="9e687-195">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="9e687-196">使用您精簡的變更管理材料來通知您的組織的期望的宣告活動和時間表的 Exchange Online 使用。</span><span class="sxs-lookup"><span data-stu-id="9e687-196">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="9e687-197">移轉至 Exchange Online 組織的其餘使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="9e687-197">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="9e687-198">提供使用者訓練在 Exchange Online 或提供以引進 Exchange Online 以及如何使用它的資源連結。</span><span class="sxs-lookup"><span data-stu-id="9e687-198">Delivering user training on Exchange Online or provide links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="9e687-p112">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="9e687-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="9e687-202">結果</span><span class="sxs-lookup"><span data-stu-id="9e687-202">Result</span></span>

<span data-ttu-id="9e687-203">您的組織已開啟並執行與您變更管理策略可隨時通知、 訓練，並讓使用者使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9e687-203">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="9e687-204">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="9e687-204">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="9e687-205">後啟用 Exchange Online 至整個組織，您必須繼續將採用以變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="9e687-205">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="9e687-206">已將 Exchange Online 升級個別和短期通訊的主要工具為您領導及排程。</span><span class="sxs-lookup"><span data-stu-id="9e687-206">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="9e687-207">鼓勵使用商務群組、 部門、 工作、 個人和專案小組通訊、 行事曆、 及共同作業。</span><span class="sxs-lookup"><span data-stu-id="9e687-207">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="9e687-208">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="9e687-208">Here are some suggested activities:</span></span>

- <span data-ttu-id="9e687-209">請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。</span><span class="sxs-lookup"><span data-stu-id="9e687-209">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="9e687-p113">請參閱 [Office 365 系統管理中心的活動報告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="9e687-p113">See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="9e687-p114">監視問題及從其體驗與 Exchange Online 相關的個人的意見反應您的意見反應場所 （中央團隊小組或 Yammer 中的公用通道）。您可以防止挫折的個人及示範以支援導入以快速解決問題與問題。</span><span class="sxs-lookup"><span data-stu-id="9e687-p114">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online. Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="9e687-p115">識別及加強冠軍中每個商務群組並反白顯示其完成事項及使用 Exchange Online 的最佳作法。會反映出其成功顯示專案成功和採用組織。依商務群組內的技術主管適用的簽署可以會強大的影響整個負責人和等項目。</span><span class="sxs-lookup"><span data-stu-id="9e687-p115">Identify and nurture champions in each business group and highlight their accomplishments and best practices using Exchange Online. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="9e687-217">結果</span><span class="sxs-lookup"><span data-stu-id="9e687-217">Result</span></span>

<span data-ttu-id="9e687-218">您的組織已採用 Exchange Online 做為其主要的個別及小型群組短期通訊及排程的工具。</span><span class="sxs-lookup"><span data-stu-id="9e687-218">Your organization has adopted Exchange Online as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="9e687-219">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="9e687-219">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9e687-220">Microsoft 內鑽入並了解如何在公司移轉至 Exchange Online 及保護網路攻擊使用 Exchange Online Protection，請參閱：</span><span class="sxs-lookup"><span data-stu-id="9e687-220">To peek inside Microsoft and learn how the company migrated to Exchange Online and is using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="9e687-221">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9e687-221">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="9e687-222">Microsoft 會使用威脅情報來保護、偵測及回應威脅</span><span class="sxs-lookup"><span data-stu-id="9e687-222">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="9e687-223">Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試</span><span class="sxs-lookup"><span data-stu-id="9e687-223">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="9e687-224">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9e687-224">Next steps</span></span>

<span data-ttu-id="9e687-225">請參閱 Exchange online 持續的維護這些資源：</span><span class="sxs-lookup"><span data-stu-id="9e687-225">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- <span data-ttu-id="9e687-226">[Exchange Online 中的 Exchange 系統管理中心](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-226">[Exchange admin center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="9e687-227">[在 Exchange Online 中監控、報告和執行郵件追蹤](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-227">[Monitoring, reporting, and message tracing in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="9e687-228">[在 Exchange Online 中備份電子郵件](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="9e687-228">[Backing up email in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span></span> 
