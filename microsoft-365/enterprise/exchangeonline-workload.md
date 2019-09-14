---
title: 部署 Microsoft 365 企業版適用於 Exchange Online
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: 逐步說明的規劃、 推行並發揮值的 Exchange Online 中 Microsoft 365 企業版整個組織的程序。
ms.openlocfilehash: a13cb36dd313ef3e6763c6c48720bb2b3e935880
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981874"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a><span data-ttu-id="7501c-103">部署 Microsoft 365 企業版適用於 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7501c-103">Deploy Exchange Online for Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7501c-104">*此工作負載包含在 Microsoft 365 企業版的 E3 和 E5 版本中*</span><span class="sxs-lookup"><span data-stu-id="7501c-104">*This workload is included in both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7501c-105">Exchange Online 是您的電子郵件的主要雲端服務和行事曆，可協助您的使用者共同作業不需要即時聊天或集中式文件儲存方式。</span><span class="sxs-lookup"><span data-stu-id="7501c-105">Exchange Online is your primary cloud service for email and calendaring that helps your users collaborate in ways that do not require real-time chatting or centralized document storage.</span></span> <span data-ttu-id="7501c-106">Exchange Online 是具體做法個別及小型群組短暫的通訊和排程，Microsoft 365 企業版的團隊合作值內建的重要元素。</span><span class="sxs-lookup"><span data-stu-id="7501c-106">Exchange Online is how you do individual and small group short-lived communication and scheduling and is a key element of the Built for Teamwork value of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="7501c-107">Exchange Online 可讓您達成更多，並與已知的 Outlook 應用程式，無論您是哪一種裝置更有效率地運作。</span><span class="sxs-lookup"><span data-stu-id="7501c-107">Exchange Online lets you accomplish more and work more effectively with the well-known Outlook application, no matter what device you’re on.</span></span>

<span data-ttu-id="7501c-108">Exchange Online 也具有進階安全性功能，包括反惡意程式碼和反垃圾郵件篩選來保護信箱和資料遺失防護功能，防止使用者誤將機密資訊傳送給未經授權的人員。</span><span class="sxs-lookup"><span data-stu-id="7501c-108">Exchange Online also has advanced security capabilities including anti-malware and anti-spam filtering to protect mailboxes and data loss prevention capabilities that prevent users from mistakenly sending sensitive information to unauthorized people.</span></span> <span data-ttu-id="7501c-109">Exchange Online 安全性是 Microsoft 365 企業版的智慧型安全性值的重要元素。</span><span class="sxs-lookup"><span data-stu-id="7501c-109">Exchange Online security is a key element of the Intelligent Security value of Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="7501c-110">如果您是 Exchange online 新手，請參閱[Microsoft Exchange Online](https://products.office.com/exchange/exchange-online)。</span><span class="sxs-lookup"><span data-stu-id="7501c-110">If you are brand new to Exchange Online, see [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).</span></span>

<span data-ttu-id="7501c-111">下列階段與步驟逐步引導您想像的 Exchange Online 組織上架中的角色變換一系列的漸進式發行至 Exchange Online 組織並發揮的 Exchange Online 的使用狀況的程序和其您的使用者值。</span><span class="sxs-lookup"><span data-stu-id="7501c-111">The following phases and steps guide you through the process of envisioning the role of Exchange Online in your organization, onboarding your organization to Exchange Online through a series of progressive rollouts, and driving usage of Exchange Online and its value to your end users.</span></span>

>[!Note]
><span data-ttu-id="7501c-112">只有在您完成 Microsoft 365 企業版基礎結構的[階段 2-Identity](identity-infrastructure.md)之後，應該遵循下列部署指示。</span><span class="sxs-lookup"><span data-stu-id="7501c-112">These deployment instructions should be followed only after you’ve completed [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure.</span></span>
>

## <a name="phase-1-envision"></a><span data-ttu-id="7501c-113">第 1 階段：構想</span><span class="sxs-lookup"><span data-stu-id="7501c-113">Phase 1: Envision</span></span>

<span data-ttu-id="7501c-114">在這個階段，您要召集負責 Exchange Online 部署的人員，並決定組織將如何使用 Exchange Online 來解決其商業需求。</span><span class="sxs-lookup"><span data-stu-id="7501c-114">In this phase, you gather the people for your Exchange Online deployment and determine how your organization will use Exchange Online to address its business needs.</span></span>

### <a name="step-1-gather-your-exchange-online-deployment-members"></a><span data-ttu-id="7501c-115">步驟 1： 收集您的 Exchange Online 部署成員</span><span class="sxs-lookup"><span data-stu-id="7501c-115">Step 1: Gather your Exchange Online deployment members</span></span>

<span data-ttu-id="7501c-116">成功部署的 Exchange Online 上的 Microsoft 365 企業版底層基礎結構的[階段 2-Identity](identity-infrastructure.md) ，您必須取得正確的人員的輸入和意見反應。</span><span class="sxs-lookup"><span data-stu-id="7501c-116">For a successful deployment of Exchange Online on top of [Phase 2-Identity](identity-infrastructure.md) of the Microsoft 365 Enterprise foundation infrastructure, you need to get the right people for input and feedback.</span></span> <span data-ttu-id="7501c-117">主要人員包括商務決策者、 IT 人員，例如架構師和實作者注意事項，與使用者的代言人。</span><span class="sxs-lookup"><span data-stu-id="7501c-117">Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users.</span></span> 

<span data-ttu-id="7501c-118">這三個群組請確定您 Exchange Online 的部署包含解決業務需求、 信箱移轉和安全性、 的技術層面及結果將會發生一般使用者會使用的考量。</span><span class="sxs-lookup"><span data-stu-id="7501c-118">These three groups ensure that your Exchange Online deployment includes considerations that address business needs, technical aspects of mailbox migration and security, and that the result will be something that typical users will use.</span></span>

#### <a name="result"></a><span data-ttu-id="7501c-119">結果</span><span class="sxs-lookup"><span data-stu-id="7501c-119">Result</span></span>

<span data-ttu-id="7501c-120">代表組織的業務、技術、使用者三方面的人員清單。</span><span class="sxs-lookup"><span data-stu-id="7501c-120">A list of people that represent the business, technical, and end user aspects of your organization.</span></span>

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a><span data-ttu-id="7501c-121">步驟 2： 決定您 Exchange Online 商務案例並優先順序</span><span class="sxs-lookup"><span data-stu-id="7501c-121">Step 2: Determine and prioritize your Exchange Online business scenarios</span></span>

<span data-ttu-id="7501c-122">Exchange Online 可以用於不同用途。</span><span class="sxs-lookup"><span data-stu-id="7501c-122">Exchange Online can be used for different purposes.</span></span> <span data-ttu-id="7501c-123">您要找出哪些用途對應至您的業務需求，在您的組織、 您的業務團隊、 部門或個別的工作和專案小組的不同層級上。</span><span class="sxs-lookup"><span data-stu-id="7501c-123">You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, or individual working and project teams.</span></span> <span data-ttu-id="7501c-124">您應該針對 Exchange Online，以解決您個別及小型群組短暫通訊和排程需求。</span><span class="sxs-lookup"><span data-stu-id="7501c-124">You should target Exchange Online to address your individual and small group short-lived communication and scheduling needs.</span></span> 

<span data-ttu-id="7501c-125">若要查看 Exchange Online 的好處的其中一個方法是檢查如何個人、 小組成員或 v 小組互動今日，然後尋找適當的案例，提供更容易的方法來進行通訊，排程會議，並進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="7501c-125">One way to see the benefits of Exchange Online is to examine how individuals, a team, or v-team interact today, and then find an appropriate scenario that provides easier ways to communicate, schedule meetings, and collaborate.</span></span> <span data-ttu-id="7501c-126">請記住， [Microsoft Teams](teams-workload.md)可能是比較好的選擇，某些共同作業案例。</span><span class="sxs-lookup"><span data-stu-id="7501c-126">Keep in mind that [Microsoft Teams](teams-workload.md) might be a better choice for some of your collaboration scenarios.</span></span>

#### <a name="result"></a><span data-ttu-id="7501c-127">結果</span><span class="sxs-lookup"><span data-stu-id="7501c-127">Result</span></span>
<span data-ttu-id="7501c-128">Exchange Online 案例，能解決貴組織的需求為通訊、 排程及短暫的共同作業清單。</span><span class="sxs-lookup"><span data-stu-id="7501c-128">A list of Exchange Online scenarios that address your organization’s needs for communication, scheduling, and short-lived collaboration.</span></span>

## <a name="phase-2-onboard"></a><span data-ttu-id="7501c-129">第 2 階段：導入</span><span class="sxs-lookup"><span data-stu-id="7501c-129">Phase 2: Onboard</span></span>

<span data-ttu-id="7501c-130">在這個階段，規劃的 Exchange Online 部署的技術層面，然後開始向所選的使用者群組推行。</span><span class="sxs-lookup"><span data-stu-id="7501c-130">In this phase, you plan for the technical aspects of an Exchange Online deployment and start rolling it out to selected groups of users.</span></span>

### <a name="prerequisites-identity-and-device-access-configuration"></a><span data-ttu-id="7501c-131">必要條件：身分識別與裝置存取設定</span><span class="sxs-lookup"><span data-stu-id="7501c-131">Prerequisites: Identity and device access configuration</span></span>

<span data-ttu-id="7501c-132">若要保護 Exchange Online 信箱的存取權，請確定您已設定[身分識別與裝置存取原則](identity-access-policies.md)和[建議的 Exchange Online 存取原則](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="7501c-132">To protect access to Exchange Online mailboxes, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended Exchange Online access policies](secure-email-recommended-policies.md).</span></span>

### <a name="step-1-complete-your-technical-planning"></a><span data-ttu-id="7501c-133">步驟 1：完成技術規劃</span><span class="sxs-lookup"><span data-stu-id="7501c-133">Step 1: Complete your technical planning</span></span>

<span data-ttu-id="7501c-134">在您開始技術規劃之前，請決定您是否要使用 FastTrack。</span><span class="sxs-lookup"><span data-stu-id="7501c-134">Before you begin technical planning, determine whether you want to use FastTrack.</span></span> <span data-ttu-id="7501c-135">如果您的組織有超過 50 個基座，並參與[符合資格的方案](https://technet.microsoft.com/library/dn783224.aspx)，您可以使用[適用於 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)，可用以引導您進行規劃、 部署及服務採用沒有額外的費用。</span><span class="sxs-lookup"><span data-stu-id="7501c-135">If your organization has over 50 seats and is participating in an [eligible plan](https://technet.microsoft.com/library/dn783224.aspx), you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), available at no additional cost to guide you through planning, deployment, and service adoption.</span></span> <span data-ttu-id="7501c-136">或者，您可以使用 FastTrack 上架精靈]，也就是可從[FastTrack](https://fasttrack.microsoft.com/) ，一旦您使用您的 Office 365 帳戶登入自行完成這項工作。</span><span class="sxs-lookup"><span data-stu-id="7501c-136">Or, you can complete this work yourself using FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Office 365 account.</span></span>

<span data-ttu-id="7501c-137">如果您編寫自己的規劃，或與 FastTrack 一起使用，您需要判斷您的網路和組織是否準備好進行 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7501c-137">If you are doing your own planning, or in conjunction with FastTrack, you need to determine if your network and organization are ready for Exchange Online.</span></span> <span data-ttu-id="7501c-138">請務必特別是在您的基礎，具有特別注意的網際網路頻寬、 輸送量及流量延遲，以達到最佳效能的其他流量的 exchange 中符合網路的允出準則線上架構之電子郵件和附件。</span><span class="sxs-lookup"><span data-stu-id="7501c-138">It is especially important that you meet the exit criteria for networking in your foundation infrastructure, with special attention to Internet bandwidth, throughput, and traffic delays to maximize performance for the additional traffic for Exchange Online-based email and attachments.</span></span>

<span data-ttu-id="7501c-139">使用這些資源來準備 Exchange Online 推行的技術層面：</span><span class="sxs-lookup"><span data-stu-id="7501c-139">Use these resources to prepare for the technical aspects of an Exchange Online rollout:</span></span> 

- [<span data-ttu-id="7501c-140">將多個電子郵件帳戶移轉到 Office 365 的方法</span><span class="sxs-lookup"><span data-stu-id="7501c-140">Ways to migrate multiple email accounts to Office 365</span></span>](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- <span data-ttu-id="7501c-141">[共同作業中 Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-141">[Collaboration in Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="7501c-142">[Exchange Online 中的收件者](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-142">[Recipients in Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)</span></span>

<span data-ttu-id="7501c-143">進一步了解 Exchange Online 中的安全性，請先檢閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="7501c-143">For a better understanding of security in Exchange Online, review the following resources:</span></span>

- <span data-ttu-id="7501c-144">[權限在 Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-144">[Permissions in Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="7501c-145">[安全性與合規性的 Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-145">[Security and compliance for Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="7501c-146">[反垃圾郵件和反惡意程式碼防護](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-146">[Anti-spam and anti-malware protection](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)</span></span>

<span data-ttu-id="7501c-147">接下來，使用這些資源來了解 Exchange Online 信箱管理：</span><span class="sxs-lookup"><span data-stu-id="7501c-147">Next, use these resources to understand Exchange Online mailbox management:</span></span>

- <span data-ttu-id="7501c-148">[在 Exchange Online 中建立使用者信箱](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-148">[Create user mailboxes in Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="7501c-149">[管理使用者信箱](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-149">[Manage user mailboxes](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx)</span></span> 
- [<span data-ttu-id="7501c-150">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="7501c-150">Create and manage distribution groups</span></span>](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a><span data-ttu-id="7501c-151">結果</span><span class="sxs-lookup"><span data-stu-id="7501c-151">Result</span></span>

<span data-ttu-id="7501c-152">您了解信箱移轉、 安全性和管理，並準備好要開始推出 Exchange Online 至組織中選取的群組。</span><span class="sxs-lookup"><span data-stu-id="7501c-152">You understand mailbox migration, security, and management and are ready to begin rolling out Exchange Online to selected groups in your organization.</span></span>

### <a name="step-2-run-an-it-pilot"></a><span data-ttu-id="7501c-153">步驟 2：執行 IT 試驗</span><span class="sxs-lookup"><span data-stu-id="7501c-153">Step 2: Run an IT pilot</span></span>

<span data-ttu-id="7501c-p108">在多數中型和大型組織中，您應該和第 1 階段中的利害關係人以及早期採用者、技術愛好者一同執行 IT 試驗。在 IT 試驗期間：</span><span class="sxs-lookup"><span data-stu-id="7501c-p108">In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1 and early adopters and technical enthusiasts. During the IT pilot:</span></span>

- <span data-ttu-id="7501c-156">選擇 [Exchange Online 的商務案例，您的 IT 試驗參與者可以加以練習。</span><span class="sxs-lookup"><span data-stu-id="7501c-156">Choose an Exchange Online business scenario in which your IT pilot participants can practice.</span></span>
- <span data-ttu-id="7501c-157">Office 365 授權給試驗參與者，並將其內部部署信箱遷移至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7501c-157">Give your pilot participants Office 365 licenses and migrate their on-premises mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="7501c-158">給試驗參與者一些練習，來測試 Exchange Online 電子郵件、 排程及其他功能。</span><span class="sxs-lookup"><span data-stu-id="7501c-158">Give your pilot participants a set of exercises to test Exchange Online email, scheduling, and other capabilities.</span></span>
- <span data-ttu-id="7501c-159">判斷您的變更管理策略，並產生的 Exchange Online 的磁碟機全組織的使用者採用的材料。</span><span class="sxs-lookup"><span data-stu-id="7501c-159">Determine your change management strategy and produce materials to drive organization-wide user adoption of Exchange Online.</span></span> <span data-ttu-id="7501c-160">電子郵件通知文字、 內部訓練計劃、 走廊海報與簡報，可以包含的變更管理材料。</span><span class="sxs-lookup"><span data-stu-id="7501c-160">Change management materials can include email announcement text, internal training plans, hallway posters, and presentations.</span></span> <span data-ttu-id="7501c-161">這些資料會通知組織有關 Exchange Online 和以目標引發認知和主導流量及其優點。</span><span class="sxs-lookup"><span data-stu-id="7501c-161">These materials will inform your organization about Exchange Online and its benefits with the goals of raising awareness and driving usage.</span></span> <span data-ttu-id="7501c-162">請參閱[變更管理策略的 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)一些想法。</span><span class="sxs-lookup"><span data-stu-id="7501c-162">See the [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) article for some ideas.</span></span>
- <span data-ttu-id="7501c-163">需要 IT 試驗參與者檢閱變更管理的材料根據其體驗。</span><span class="sxs-lookup"><span data-stu-id="7501c-163">Have your IT pilot participants review the change management materials based on their experiences.</span></span> <span data-ttu-id="7501c-164">他們可以提供的祕訣最佳作法和建議如何以最佳說明 Exchange Online 的優點，以及如何用它來進行通訊，以及排程。</span><span class="sxs-lookup"><span data-stu-id="7501c-164">They can provide tips on best practices and advice on how to best describe the benefits of Exchange Online and how to use it for communication and scheduling.</span></span>

#### <a name="result"></a><span data-ttu-id="7501c-165">結果</span><span class="sxs-lookup"><span data-stu-id="7501c-165">Result</span></span>

<span data-ttu-id="7501c-166">Exchange Online 的 IT 試驗完成且次變更管理材料已開發、 檢閱、 並精簡。</span><span class="sxs-lookup"><span data-stu-id="7501c-166">Your Exchange Online IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.</span></span>

### <a name="step-3-roll-out-to-a-business-group"></a><span data-ttu-id="7501c-167">步驟 3：推行至商務群組</span><span class="sxs-lookup"><span data-stu-id="7501c-167">Step 3: Roll out to a business group</span></span>

<span data-ttu-id="7501c-168">完成後您的 IT 試驗，推出 Exchange Online 商務群組或組織中的部門。</span><span class="sxs-lookup"><span data-stu-id="7501c-168">After completing your IT pilot, roll out Exchange Online to a business group or department in your organization.</span></span> <span data-ttu-id="7501c-169">如果您的組織使用內部部署電子郵件服務，例如 Exchange Server，此導入包含移轉的信箱。</span><span class="sxs-lookup"><span data-stu-id="7501c-169">If your organization is using an on-premises email service such as Exchange Server, this rollout consists of mailbox migration.</span></span> <span data-ttu-id="7501c-170">此導入應包含：</span><span class="sxs-lookup"><span data-stu-id="7501c-170">This rollout should include:</span></span>

- <span data-ttu-id="7501c-171">識別重要商務案例的 Exchange Online 商務群組中。</span><span class="sxs-lookup"><span data-stu-id="7501c-171">Identification of key business scenarios for Exchange Online within the business group.</span></span>
- <span data-ttu-id="7501c-172">用公告活動通知使用者的預期變更和時間表部門及工作或專案小組的 Exchange Online 使用。</span><span class="sxs-lookup"><span data-stu-id="7501c-172">Announcement activities to inform users of the expectations and timelines for Exchange Online usage for departments and work or project teams.</span></span>
- <span data-ttu-id="7501c-173">移轉至 Exchange Online 商務群組成員的內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="7501c-173">Migration of on-premises mailboxes of your business group members to Exchange Online.</span></span>
- <span data-ttu-id="7501c-174">提供在 Exchange Online 或連結的使用者訓練資源介紹 Exchange Online 和如何加以使用。</span><span class="sxs-lookup"><span data-stu-id="7501c-174">Delivering user training on Exchange Online or links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="7501c-175">用意見反應機制 (例如包含商務群組中每個人的中央 Microsoft Teams 小組) 收集商務群組使用者的意見，並針對問題採取行動。</span><span class="sxs-lookup"><span data-stu-id="7501c-175">A feedback mechanism, such as a central Microsoft Teams team containing everyone in the business group, to collect comments and act on issues from users in the business group.</span></span>

<span data-ttu-id="7501c-176">在推行期間，您可以精簡變更管理的材料，為全組織的推行做準備。</span><span class="sxs-lookup"><span data-stu-id="7501c-176">During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.</span></span>

#### <a name="result"></a><span data-ttu-id="7501c-177">結果</span><span class="sxs-lookup"><span data-stu-id="7501c-177">Result</span></span>

<span data-ttu-id="7501c-178">商務群組，且和執行與 Exchange Online 變更管理的材料已測試並精簡。</span><span class="sxs-lookup"><span data-stu-id="7501c-178">A business group is up and running with Exchange Online and the change management materials have been tested and refined.</span></span>

## <a name="phase-3-drive-value"></a><span data-ttu-id="7501c-179">第 3 階段：發揮價值</span><span class="sxs-lookup"><span data-stu-id="7501c-179">Phase 3: Drive value</span></span>

<span data-ttu-id="7501c-180">在這個階段，您完成推出 Exchange Online，並支援您的使用者，以協助他們了解其優點。</span><span class="sxs-lookup"><span data-stu-id="7501c-180">In this phase, you complete the rollout of Exchange Online and support your users to help them realize its benefits.</span></span>

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a><span data-ttu-id="7501c-181">步驟 1： 推行 Exchange Online 組織的其餘部分</span><span class="sxs-lookup"><span data-stu-id="7501c-181">Step 1: Roll out Exchange Online to the rest of your organization</span></span>

<span data-ttu-id="7501c-182">推行至貴組織其餘單位應包含：</span><span class="sxs-lookup"><span data-stu-id="7501c-182">The rollout to the rest of your organization should include:</span></span>

- <span data-ttu-id="7501c-183">識別重要商務案例的 Exchange Online 中的個別商務群組。</span><span class="sxs-lookup"><span data-stu-id="7501c-183">Identification of key business scenarios for Exchange Online within separate business groups.</span></span>
- <span data-ttu-id="7501c-184">使用精簡的變更管理的材料公告活動通知貴組織的預期變更和時間表的 Exchange Online 使用。</span><span class="sxs-lookup"><span data-stu-id="7501c-184">Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Exchange Online usage.</span></span>
- <span data-ttu-id="7501c-185">移轉至 Exchange Online 組織的其餘部分的信箱。</span><span class="sxs-lookup"><span data-stu-id="7501c-185">Migration of the mailboxes for the rest of your organization to Exchange Online.</span></span>
- <span data-ttu-id="7501c-186">提供使用者訓練在 Exchange Online，或提供的資源介紹 Exchange Online，以及如何使用它的連結。</span><span class="sxs-lookup"><span data-stu-id="7501c-186">Delivering user training on Exchange Online or provide links to resources to introduce Exchange Online and how to use it.</span></span>
- <span data-ttu-id="7501c-p112">用意見反應機制 (例如包含每個人的中央小組) 收集組織使用者的意見和問題。如果組織人數小於 2500 人，請使用 Teams 的公用通道。若超過，請使用 Yammer 中的公用群組。</span><span class="sxs-lookup"><span data-stu-id="7501c-p112">A feedback mechanism, such as a central Team containing everyone, to collect comments and issues from organization users. If your organization has less than 2500 individuals, use a public channel in Teams. Otherwise, use a public group in Yammer.</span></span>

#### <a name="result"></a><span data-ttu-id="7501c-190">結果</span><span class="sxs-lookup"><span data-stu-id="7501c-190">Result</span></span>

<span data-ttu-id="7501c-191">您的組織已啟動並執行和變更管理策略已經準備就緒，可以通知、 訓練並讓使用者使用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7501c-191">Your organization is up and running and your change management strategy is in place to inform, train, and enable users to use Exchange Online.</span></span>

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a><span data-ttu-id="7501c-192">步驟 2：評估使用狀況、管理滿意度、推動採用</span><span class="sxs-lookup"><span data-stu-id="7501c-192">Step 2: Measure usage, manage satisfaction, and drive adoption</span></span>

<span data-ttu-id="7501c-193">推行後 Exchange Online 至整個組織，您必須繼續使用變更管理策略：</span><span class="sxs-lookup"><span data-stu-id="7501c-193">After rolling out Exchange Online to your entire organization, you must continue to employ your change management strategy to:</span></span>

- <span data-ttu-id="7501c-194">讓領導者將 Exchange Online 升級為主要工具，進行個別和短暫的通訊和排程。</span><span class="sxs-lookup"><span data-stu-id="7501c-194">Have your leadership promote Exchange Online as the primary tool for individual and short-lived communication and scheduling.</span></span>
- <span data-ttu-id="7501c-195">鼓勵個人將它用於商務群組、 部門、 工作和專案小組的溝通、 行事曆、 和共同作業。</span><span class="sxs-lookup"><span data-stu-id="7501c-195">Encourage individuals to use it for business group, departmental, work, and project team communications, calendaring, and collaboration.</span></span>

<span data-ttu-id="7501c-196">以下是一些建議的活動：</span><span class="sxs-lookup"><span data-stu-id="7501c-196">Here are some suggested activities:</span></span>

- <span data-ttu-id="7501c-197">請參閱 [Office 365 採用指南](https://aka.ms/successfactors)以了解雲端服務採用的一般最佳做法。</span><span class="sxs-lookup"><span data-stu-id="7501c-197">See [Office 365 adoption guidance](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption.</span></span> 
- <span data-ttu-id="7501c-p113">請參閱 [Office 365 系統管理中心的活動報告](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)，以了解整個組織的 Office 365 服務用法。如果貴組織還沒有 Office 365 全域系統管理員，請找將報告讀取權限授與給使用者帳戶的人員，讓您可以存取活動報告。</span><span class="sxs-lookup"><span data-stu-id="7501c-p113">See [Office 365 activity reports](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is a global admin to grant Reports Reader permissions to your user account so you can access activity reports.</span></span>
- <span data-ttu-id="7501c-200">監視您的意見反應場所 （中央 microsoft Teams 小組或 Yammer 中的公用通道） 問題與從他們的經驗與 Exchange Online 相關的個人的意見反應。</span><span class="sxs-lookup"><span data-stu-id="7501c-200">Monitor your feedback venue (a public channel in a central Teams team or Yammer) for issues and feedback from individuals about their experiences with Exchange Online.</span></span> <span data-ttu-id="7501c-201">您可以防止迷惑的個人與示範首度發行的支援，快速解決問題。</span><span class="sxs-lookup"><span data-stu-id="7501c-201">Address questions and issues as quickly as you can to prevent frustrated individuals and demonstrate support for the rollout.</span></span>
- <span data-ttu-id="7501c-202">識別並加強冠軍每個商務群組中的，並反白顯示其成就和使用 Exchange Online 的最佳作法。</span><span class="sxs-lookup"><span data-stu-id="7501c-202">Identify and nurture champions in each business group and highlight their accomplishments and best practices using Exchange Online.</span></span> <span data-ttu-id="7501c-203">反映出其成功至組織，以顯示專案成功和採用率。</span><span class="sxs-lookup"><span data-stu-id="7501c-203">Reflect their successes out to the organization to show project success and adoption.</span></span> <span data-ttu-id="7501c-204">依商務群組內的技術主管適用的背書可以會強大的影響整個負責人及其等項目。</span><span class="sxs-lookup"><span data-stu-id="7501c-204">Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.</span></span>

#### <a name="result"></a><span data-ttu-id="7501c-205">結果</span><span class="sxs-lookup"><span data-stu-id="7501c-205">Result</span></span>

<span data-ttu-id="7501c-206">貴組織已採用 Exchange Online 做為其主要的個別及小型群組短暫的通訊和排程的工具。</span><span class="sxs-lookup"><span data-stu-id="7501c-206">Your organization has adopted Exchange Online as its primary individual and small group short-lived communication and scheduling tool.</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="7501c-207">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="7501c-207">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="7501c-208">一窺 Microsoft 並了解公司如何移轉至 Exchange Online 及使用 Exchange Online Protection 來防範網路攻擊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="7501c-208">To peek inside Microsoft and learn how the company migrated to Exchange Online and is using Exchange Online Protection to protect against cyber attacks, see:</span></span>

- [<span data-ttu-id="7501c-209">Microsoft 會將 150000 個信箱移轉到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7501c-209">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="7501c-210">Microsoft 會使用威脅情報來保護、偵測及回應威脅</span><span class="sxs-lookup"><span data-stu-id="7501c-210">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="7501c-211">Microsoft 會使用 Office 365 來阻撓網路釣魚嘗試</span><span class="sxs-lookup"><span data-stu-id="7501c-211">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a><span data-ttu-id="7501c-212">後續步驟</span><span class="sxs-lookup"><span data-stu-id="7501c-212">Next steps</span></span>

<span data-ttu-id="7501c-213">請參閱 Exchange Online 的持續維護這些資源：</span><span class="sxs-lookup"><span data-stu-id="7501c-213">See these resources for the ongoing maintenance of Exchange Online:</span></span>

- <span data-ttu-id="7501c-214">[Exchange Online 中的 Exchange 系統管理中心](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-214">[Exchange admin center in Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx)</span></span> 
- <span data-ttu-id="7501c-215">[監控、 報告和 Exchange Online 中的郵件追蹤](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-215">[Monitoring, reporting, and message tracing in Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)</span></span>
- <span data-ttu-id="7501c-216">[備份電子郵件在 Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="7501c-216">[Backing up email in Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx)</span></span> 
