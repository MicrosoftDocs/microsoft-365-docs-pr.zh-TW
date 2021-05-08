---
title: 深入了解資料外洩防護
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 瞭解如何使用 Microsoft 365 資料遺失防護原則及工具來保護您的機密資訊，並透過 DLP 生命週期進行導覽。
ms.openlocfilehash: 88cf913f62d28c89bce7054473eb577217de9489
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244609"
---
# <a name="learn-about-data-loss-prevention"></a><span data-ttu-id="3e337-103">深入了解資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="3e337-103">Learn about data loss prevention</span></span>

<span data-ttu-id="3e337-104">組織在其控制之下的敏感資訊，例如財務資料、專有資料、信用卡號碼、健康記錄或社會保險號碼。</span><span class="sxs-lookup"><span data-stu-id="3e337-104">Organizations have sensitive information under their control such as financial data, proprietary data, credit card numbers, health records, or social security numbers.</span></span> <span data-ttu-id="3e337-105">為了協助保護這種敏感性資料，並降低風險，他們需要一種方式，以防止使用者不適當地與未安裝的人員共用。</span><span class="sxs-lookup"><span data-stu-id="3e337-105">To help protect this sensitive data and reduce risk, they need a way to prevent their users from inappropriately sharing it with people who shouldn't have it.</span></span> <span data-ttu-id="3e337-106">這種作法稱為資料遺失防護 (DLP) 。</span><span class="sxs-lookup"><span data-stu-id="3e337-106">This practice is called data loss prevention (DLP).</span></span>

<span data-ttu-id="3e337-107">在 Microsoft 365 中，您可以定義及套用 DLP 原則，以執行資料遺失防護。</span><span class="sxs-lookup"><span data-stu-id="3e337-107">In Microsoft 365, you implement data loss prevention by defining and applying DLP policies.</span></span> <span data-ttu-id="3e337-108">使用 DLP 原則，您可以識別、監視和自動保護不同的敏感專案：</span><span class="sxs-lookup"><span data-stu-id="3e337-108">With a DLP policy, you can identify, monitor, and automatically protect sensitive items across:</span></span>

- <span data-ttu-id="3e337-109">Microsoft 365 服務（如 Teams、Exchange、SharePoint 及 OneDrive）</span><span class="sxs-lookup"><span data-stu-id="3e337-109">Microsoft 365 services such as Teams, Exchange, SharePoint, and OneDrive</span></span>
- <span data-ttu-id="3e337-110">Office 的應用程式，例如 Word、Excel 及 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="3e337-110">Office applications such as Word, Excel, and PowerPoint</span></span>
- <span data-ttu-id="3e337-111">Windows 10 端點</span><span class="sxs-lookup"><span data-stu-id="3e337-111">Windows 10 endpoints</span></span>
- <span data-ttu-id="3e337-112">非 Microsoft cloud app</span><span class="sxs-lookup"><span data-stu-id="3e337-112">non-Microsoft cloud apps</span></span>
- <span data-ttu-id="3e337-113">內部部署檔案共用和內部部署 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="3e337-113">on-premises file shares and on-premises SharePoint.</span></span>

<span data-ttu-id="3e337-114">Microsoft 365 使用深入的內容分析來偵測敏感專案，而不只是簡單的文字掃描。</span><span class="sxs-lookup"><span data-stu-id="3e337-114">Microsoft 365 detects sensitive items by using deep content analysis, not by just a simple text scan.</span></span> <span data-ttu-id="3e337-115">會透過評估正則運算式、內建函式驗證，以及與主要資料比對接近的次要資料比對，來分析主要資料符合關鍵字的內容。</span><span class="sxs-lookup"><span data-stu-id="3e337-115">Content is analyzed for primary data matches to keywords, by the evaluation of regular expressions, by internal function validation, and by secondary data matches that are in proximity to the primary data match.</span></span> <span data-ttu-id="3e337-116">除了該 DLP 之外，還會使用電腦學習演算法和其他方法，偵測符合您 DLP 原則的內容。</span><span class="sxs-lookup"><span data-stu-id="3e337-116">Beyond that DLP also uses machine learning algorithms and other methods to detect content that matches your DLP policies.</span></span>
  
## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a><span data-ttu-id="3e337-117">DLP 是較大 Microsoft 365 規範服務的一部分</span><span class="sxs-lookup"><span data-stu-id="3e337-117">DLP is part of the larger Microsoft 365 Compliance offering</span></span>

<span data-ttu-id="3e337-118">Microsoft 365DLP 只是其中一個 Microsoft 365 規範工具，可讓您在任何居住或旅行時，協助保護您的敏感專案。</span><span class="sxs-lookup"><span data-stu-id="3e337-118">Microsoft 365 DLP is just one of the Microsoft 365 Compliance tools that you will use to help protect your sensitive items wherever they live or travel.</span></span> <span data-ttu-id="3e337-119">您應該瞭解 Microsoft 365 規範工具集合中的其他工具，如何 interrelate，以及如何搭配一起運作。</span><span class="sxs-lookup"><span data-stu-id="3e337-119">You should understand the other tools in the Microsoft 365 Compliance tools set, how they interrelate, and work better together.</span></span>  <span data-ttu-id="3e337-120">請參閱， [Microsoft 365 規範工具](protect-information.md)以深入瞭解資訊保護程式。</span><span class="sxs-lookup"><span data-stu-id="3e337-120">See, [Microsoft 365 compliance tools](protect-information.md) to learn more about the information protection process.</span></span>

## <a name="protective-actions-of-dlp-policies"></a><span data-ttu-id="3e337-121">DLP 原則的保護性動作</span><span class="sxs-lookup"><span data-stu-id="3e337-121">Protective actions of DLP policies</span></span>

<span data-ttu-id="3e337-122">Microsoft 365DLP 原則是指如何監控使用者對靜止專案所採取的活動、傳輸中的敏感專案，或使用中的敏感專案，以及採取保護動作。</span><span class="sxs-lookup"><span data-stu-id="3e337-122">Microsoft 365 DLP policies are how you monitor the activities that users take on sensitive items at rest, sensitive items in transit, or sensitive items in use and take protective actions.</span></span> <span data-ttu-id="3e337-123">例如，當使用者嘗試採取禁止的動作時（例如，將敏感專案複製到未核准的位置，或是在原則中所佈置的其他情況下）共用醫學資訊時，DLP 便可：</span><span class="sxs-lookup"><span data-stu-id="3e337-123">For example, when a user attempts to take a prohibited action, like copying a sensitive item to an unapproved location or sharing medical information in an email or other conditions laid out in a policy, DLP can:</span></span>

- <span data-ttu-id="3e337-124">向使用者顯示彈出的原則提示，告知他們可能嘗試以不當的方式共用敏感專案</span><span class="sxs-lookup"><span data-stu-id="3e337-124">show a pop-up policy tip to the user that warns them that they may be trying to share a sensitive item inappropriately</span></span>
- <span data-ttu-id="3e337-125">封鎖共用，並透過原則提示讓使用者覆寫封鎖，並捕獲使用者的合理性論證</span><span class="sxs-lookup"><span data-stu-id="3e337-125">block the sharing and, via a policy tip, allow the user to override the block and capture the users' justification</span></span>
- <span data-ttu-id="3e337-126">封鎖不含覆寫選項的共用</span><span class="sxs-lookup"><span data-stu-id="3e337-126">block the sharing without the override option</span></span>
- <span data-ttu-id="3e337-127">針對靜態的資料，可鎖定敏感專案並將其移至安全的隔離位置</span><span class="sxs-lookup"><span data-stu-id="3e337-127">for data at rest, sensitive items can be locked and moved to a secure quarantine location</span></span>
- <span data-ttu-id="3e337-128">若為 Teams 聊天室，將不會顯示機密資訊。</span><span class="sxs-lookup"><span data-stu-id="3e337-128">for Teams chat, the sensitive information will not be displayed</span></span>

<span data-ttu-id="3e337-129">所有 DLP 監控的活動預設都會記錄到[Microsoft 365 的審計記錄](search-the-audit-log-in-security-and-compliance.md)，並路由傳送至[活動瀏覽器](data-classification-activity-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="3e337-129">All DLP monitored activities are recorded to the [Microsoft 365 Audit log](search-the-audit-log-in-security-and-compliance.md) by default and routed to [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="3e337-130">當使用者執行符合 DLP 原則條件的動作，並已設定警示時，DLP 會在 [dlp 警示管理儀表板](dlp-configure-view-alerts-policies.md)中提供警示。</span><span class="sxs-lookup"><span data-stu-id="3e337-130">When a user performs an action that meets the criteria of a DLP policy, and you have alerts configured, DLP provides alerts in the [DLP alert management dashboard](dlp-configure-view-alerts-policies.md).</span></span>

## <a name="dlp-lifecycle"></a><span data-ttu-id="3e337-131">DLP 生命週期</span><span class="sxs-lookup"><span data-stu-id="3e337-131">DLP lifecycle</span></span>

<span data-ttu-id="3e337-132">DLP 實施通常會遵循這些主要階段。</span><span class="sxs-lookup"><span data-stu-id="3e337-132">A DLP implementation typically follows these major phases.</span></span>

- [<span data-ttu-id="3e337-133">規劃 DLP</span><span class="sxs-lookup"><span data-stu-id="3e337-133">Plan for DLP</span></span>](#plan-for-dlp)
- [<span data-ttu-id="3e337-134">準備 DLP</span><span class="sxs-lookup"><span data-stu-id="3e337-134">Prepare for DLP</span></span>](#prepare-for-dlp)
- [<span data-ttu-id="3e337-135">在生產環境中部署原則</span><span class="sxs-lookup"><span data-stu-id="3e337-135">Deploy your policies in production</span></span>](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a><span data-ttu-id="3e337-136">規劃 DLP</span><span class="sxs-lookup"><span data-stu-id="3e337-136">Plan for DLP</span></span>

<span data-ttu-id="3e337-137">Microsoft 365DLP 監控和保護是使用者每天使用之應用程式的原生。</span><span class="sxs-lookup"><span data-stu-id="3e337-137">Microsoft 365 DLP monitoring and protection are native to the applications that users use every day.</span></span> <span data-ttu-id="3e337-138">這有助於保護組織的敏感專案免受危險的活動，即使您的使用者 unaccustomed 到資料遺失防護思考和作法也是一樣。</span><span class="sxs-lookup"><span data-stu-id="3e337-138">This helps to protect your organizations' sensitive items from risky activities even if your users are unaccustomed to data loss prevention thinking and practices.</span></span> <span data-ttu-id="3e337-139">如果您的組織和使用者是資料遺失防護做法的新資料，則 DLP 採用可能需要變更您的商務程式，而且將為您的使用者提供文化的轉變。</span><span class="sxs-lookup"><span data-stu-id="3e337-139">If your organization and your users are new to data loss prevention practices, the adoption of DLP may require a change to your business processes and there will be a culture shift for your users.</span></span> <span data-ttu-id="3e337-140">不過，使用適當的規劃、測試及調整，您的 DLP 原則會保護您的機密專案，同時將任何潛在的業務程式中斷降到最低。</span><span class="sxs-lookup"><span data-stu-id="3e337-140">But, with proper planning, testing and tuning, your DLP policies will protect your sensitive items while minimizing any potential business process disruptions.</span></span>

<span data-ttu-id="3e337-141">**DLP 的技術規劃**</span><span class="sxs-lookup"><span data-stu-id="3e337-141">**Technology planning for DLP**</span></span>

<span data-ttu-id="3e337-142">請記住，DLP 為技術可以監視和保護靜態資料、使用中的資料，以及在 Microsoft 365 服務、Windows 10 裝置、內部部署檔案共用和內部部署 SharePoint 中的動作中的資料。</span><span class="sxs-lookup"><span data-stu-id="3e337-142">Keep in mind that DLP as a technology can monitor and protect your data at rest, data in use and data in motion across Microsoft 365 services, Windows 10 devices, on-premises file shares, and on-premises SharePoint.</span></span> <span data-ttu-id="3e337-143">針對不同的位置、您想要監視和保護的資料類型，以及當原則相符時所採取的動作，都有一定的計畫含義。</span><span class="sxs-lookup"><span data-stu-id="3e337-143">There are planning implications for the different locations, the type of data you want to monitor and protect, and the actions to be taken when a policy match occurs.</span></span>  

<span data-ttu-id="3e337-144">**規劃 DLP 的商務程式**</span><span class="sxs-lookup"><span data-stu-id="3e337-144">**Business processes planning for DLP**</span></span>

<span data-ttu-id="3e337-145">DLP 原則可以封鎖禁止的活動，例如透過電子郵件不適當的敏感資訊共用。</span><span class="sxs-lookup"><span data-stu-id="3e337-145">DLP policies can block prohibited activities, like inappropriate sharing of sensitive information via email.</span></span> <span data-ttu-id="3e337-146">當您規劃 DLP 原則時，您必須識別觸及機密專案的商務程式。</span><span class="sxs-lookup"><span data-stu-id="3e337-146">As you plan your DLP policies, you must identify the business processes that touch your sensitive items.</span></span> <span data-ttu-id="3e337-147">業務程式擁有人可協助您識別應允許的適當使用者行為，以及應保護的使用者行為不當。</span><span class="sxs-lookup"><span data-stu-id="3e337-147">The business process owners can help you identify appropriate user behaviors that should be allowed and inappropriate user behaviors that should be protected against.</span></span> <span data-ttu-id="3e337-148">您應該規劃您的原則，並以測試模式進行部署，並先評估其對 [活動瀏覽器](data-classification-activity-explorer.md) 的影響，再將其套用至更嚴格的模式。</span><span class="sxs-lookup"><span data-stu-id="3e337-148">You should plan your policies and deploy them in test mode, and evaluate their impact via [activity explorer](data-classification-activity-explorer.md) first, before applying them in more restrictive modes.</span></span>

<span data-ttu-id="3e337-149">**DLP 的組織文化環境規劃**</span><span class="sxs-lookup"><span data-stu-id="3e337-149">**Organizational culture planning for DLP**</span></span>

<span data-ttu-id="3e337-150">成功的 DLP 執行相當於讓您的使用者訓練有素並 acclimated 資料遺失防護做法，因為這是一項完善的規劃和調整原則。</span><span class="sxs-lookup"><span data-stu-id="3e337-150">A successful DLP implementation is as much dependent on getting your users trained and acclimated to data loss prevention practices as it is on well planned and tuned policies.</span></span> <span data-ttu-id="3e337-151">由於您的使用者非常介入，因此請務必規劃訓練。</span><span class="sxs-lookup"><span data-stu-id="3e337-151">Since your users are heavily involved, be sure to plan for training for them too.</span></span> <span data-ttu-id="3e337-152">您可以在將原則強制從測試模式變更為限制性更高的模式之前，以策略性方式使用原則提示來提升使用者的知名度。</span><span class="sxs-lookup"><span data-stu-id="3e337-152">You can strategically use policy tips to raise awareness with your users before changing the policy enforcement from test mode to more restrictive modes.</span></span>

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a><span data-ttu-id="3e337-153">準備 DLP</span><span class="sxs-lookup"><span data-stu-id="3e337-153">Prepare for DLP</span></span>

<span data-ttu-id="3e337-154">您可以將 DLP 原則套用到靜態資料、使用中的資料，以及位置中的動作資料，例如：</span><span class="sxs-lookup"><span data-stu-id="3e337-154">You can apply DLP policies to data at rest, data in use, and data in motion in locations, such as:</span></span>

- <span data-ttu-id="3e337-155">Exchange Online 電子郵件</span><span class="sxs-lookup"><span data-stu-id="3e337-155">Exchange Online email</span></span>
- <span data-ttu-id="3e337-156">SharePoint Online 網站</span><span class="sxs-lookup"><span data-stu-id="3e337-156">SharePoint Online sites</span></span>
- <span data-ttu-id="3e337-157">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="3e337-157">OneDrive accounts</span></span>
- <span data-ttu-id="3e337-158">Teams 聊天和頻道訊息</span><span class="sxs-lookup"><span data-stu-id="3e337-158">Teams chat and channel messages</span></span>
- <span data-ttu-id="3e337-159">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="3e337-159">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="3e337-160">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="3e337-160">Windows 10 devices</span></span>
- <span data-ttu-id="3e337-161">內部部署存放庫</span><span class="sxs-lookup"><span data-stu-id="3e337-161">On-premises repositories</span></span>

<span data-ttu-id="3e337-162">每個必備項都有不同的必要條件。</span><span class="sxs-lookup"><span data-stu-id="3e337-162">Each one has different pre-requisites.</span></span> <span data-ttu-id="3e337-163">某些位置的機密專案（例如 Exchange 線上）可以透過在 DLP 傘底下進行，只需設定套用至這些專案的原則。</span><span class="sxs-lookup"><span data-stu-id="3e337-163">Sensitive items in some locations, like Exchange online, can be brought under the DLP umbrella by just configuring a policy that applies to them.</span></span> <span data-ttu-id="3e337-164">其他如內部部署檔案存放庫需要部署 Azure 資訊保護 (AIP) 掃描器。</span><span class="sxs-lookup"><span data-stu-id="3e337-164">Others, such as on-premises file repositories require a deployment of Azure Information Protection (AIP) scanner.</span></span> <span data-ttu-id="3e337-165">在啟動任何封鎖動作之前，您需要準備您的環境、程式碼草稿原則，並加以徹底測試。</span><span class="sxs-lookup"><span data-stu-id="3e337-165">You'll need to prepare your environment, code draft policies, and test them thoroughly before activating any blocking actions.</span></span>

### <a name="deploy-your-policies-in-production"></a><span data-ttu-id="3e337-166">在生產環境中部署原則</span><span class="sxs-lookup"><span data-stu-id="3e337-166">Deploy your policies in production</span></span>

#### <a name="design-your-policies"></a><span data-ttu-id="3e337-167">設計您的原則</span><span class="sxs-lookup"><span data-stu-id="3e337-167">Design your policies</span></span>

<span data-ttu-id="3e337-168">請先定義您的控制目標，以及它們如何套用各個不同的工作負載。</span><span class="sxs-lookup"><span data-stu-id="3e337-168">Start by defining your control objectives, and how they apply across each respective workload.</span></span> <span data-ttu-id="3e337-169">起草包含您目標的原則。</span><span class="sxs-lookup"><span data-stu-id="3e337-169">Draft a policy that embodies your objectives.</span></span> <span data-ttu-id="3e337-170">您可以隨時從一個工作負載開始，也可以跨所有工作負載開始-尚無影響。</span><span class="sxs-lookup"><span data-stu-id="3e337-170">Feel free to start with one workload at a time, or across all workloads - there's no impact yet.</span></span>

#### <a name="implement-policy-in-test-mode"></a><span data-ttu-id="3e337-171">在測試模式中實施原則</span><span class="sxs-lookup"><span data-stu-id="3e337-171">Implement policy in test mode</span></span>

<span data-ttu-id="3e337-172">在測試模式中以 DLP 原則實施，以評估控制措施的影響。</span><span class="sxs-lookup"><span data-stu-id="3e337-172">Evaluate the impact of the controls by implementing them with a DLP policy in test mode.</span></span> <span data-ttu-id="3e337-173">[！注意事項] 您可以將原則套用至測試模式中的所有工作負載，這樣您就可以取得完整的結果，但是您可以在需要時從一個工作負載開始。</span><span class="sxs-lookup"><span data-stu-id="3e337-173">It's ok to apply the policy to all workloads in test mode, so that you can get the full breadth of results, but you can start with one workload if you need to.</span></span>

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a><span data-ttu-id="3e337-174">監視結果和微調原則</span><span class="sxs-lookup"><span data-stu-id="3e337-174">Monitor outcomes and fine-tune the policy</span></span>

<span data-ttu-id="3e337-175">在測試模式中，監控原則的結果並微調它，使其符合您的控制目標，同時確保您不會對有效的使用者工作流程和生產力造成不良或不慎影響。</span><span class="sxs-lookup"><span data-stu-id="3e337-175">While in test mode, monitor the outcomes of the policy and fine-tune it so that it meets your control objectives while ensuring you aren't adversely or inadvertently impacting valid user workflows and productivity.</span></span> <span data-ttu-id="3e337-176">以下是一些需要微調的範例：</span><span class="sxs-lookup"><span data-stu-id="3e337-176">Here are some examples of things to fine-tune:</span></span>

- <span data-ttu-id="3e337-177">調整範圍內或範圍之外的位置和人員/位置</span><span class="sxs-lookup"><span data-stu-id="3e337-177">adjusting the locations and people/places that are in or out of scope</span></span>
- <span data-ttu-id="3e337-178">調整用於判斷專案及其執行專案與原則相符時所用的條件和例外狀況</span><span class="sxs-lookup"><span data-stu-id="3e337-178">tune the conditions and exceptions that are used to determine if an item and what is being done with it matches the policy</span></span>
- <span data-ttu-id="3e337-179">敏感資訊定義/秒</span><span class="sxs-lookup"><span data-stu-id="3e337-179">the sensitive information definition/s</span></span>
- <span data-ttu-id="3e337-180">的動作</span><span class="sxs-lookup"><span data-stu-id="3e337-180">the actions</span></span>
- <span data-ttu-id="3e337-181">限制層級</span><span class="sxs-lookup"><span data-stu-id="3e337-181">the level of restrictions</span></span>
- <span data-ttu-id="3e337-182">新增控制項</span><span class="sxs-lookup"><span data-stu-id="3e337-182">add new controls</span></span>
- <span data-ttu-id="3e337-183">新增人員</span><span class="sxs-lookup"><span data-stu-id="3e337-183">add new people</span></span>
- <span data-ttu-id="3e337-184">新增受限制的應用程式</span><span class="sxs-lookup"><span data-stu-id="3e337-184">add new restricted apps</span></span>
- <span data-ttu-id="3e337-185">新增受限制的網站</span><span class="sxs-lookup"><span data-stu-id="3e337-185">add new restricted sites</span></span>

#### <a name="enable-the-control-and-tune-your-policies"></a><span data-ttu-id="3e337-186">啟用控制項並調整原則</span><span class="sxs-lookup"><span data-stu-id="3e337-186">Enable the control and tune your policies</span></span>

<span data-ttu-id="3e337-187">一旦原則符合您的所有目標，請將其開啟。</span><span class="sxs-lookup"><span data-stu-id="3e337-187">Once the policy meets all your objectives, turn it on.</span></span> <span data-ttu-id="3e337-188">繼續監視原則應用程式的結果，並視需要調整。</span><span class="sxs-lookup"><span data-stu-id="3e337-188">Continue to monitor the outcomes of the policy application and tune as needed.</span></span> <span data-ttu-id="3e337-189">一般來說，原則會在開啟後的一小時內生效。</span><span class="sxs-lookup"><span data-stu-id="3e337-189">In general, policies take effect about an hour after being turned on.</span></span> <span data-ttu-id="3e337-190"><!--請參閱，連結至位置特定詳細資料的 Sla 相關主題--></span><span class="sxs-lookup"><span data-stu-id="3e337-190"><!--See, LINK TO topic for SLAs for location specific  details-- ></span></span>

## <a name="dlp-policy-configuration-overview"></a><span data-ttu-id="3e337-191">DLP 原則設定概述</span><span class="sxs-lookup"><span data-stu-id="3e337-191">DLP policy configuration overview</span></span>

<span data-ttu-id="3e337-192">您在建立和設定 DLP 原則方面具有彈性。</span><span class="sxs-lookup"><span data-stu-id="3e337-192">You have flexibility in how you create and configure your DLP policies.</span></span> <span data-ttu-id="3e337-193">您可以從預先定義的範本開始，只需稍按幾下即可建立原則，或自行設計。</span><span class="sxs-lookup"><span data-stu-id="3e337-193">You can start from a predefined template and create a policy in just a few clicks or you can design your own from the ground up.</span></span> <span data-ttu-id="3e337-194">不論選擇哪一個，所有 DLP 原則都需要您所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="3e337-194">No matter which you choose, all DLP policies require the same information from you.</span></span>

1. <span data-ttu-id="3e337-195">**選擇您要監視** 的專案 Microsoft 365 隨附許多預先定義的原則範本，以協助您開始使用，也可以建立自訂原則。</span><span class="sxs-lookup"><span data-stu-id="3e337-195">**Choose what you want to monitor** - Microsoft 365 comes with many predefined policy templates to help you get started or you can create a custom policy.</span></span>
    - <span data-ttu-id="3e337-196">預先定義的原則範本：金融資料、醫療和健康情況資料、各種國家和地區的隱私權資料。</span><span class="sxs-lookup"><span data-stu-id="3e337-196">A predefined policy template: Financial data, Medical and health data, Privacy data all for various countries and regions.</span></span>
    - <span data-ttu-id="3e337-197">使用可用的敏感資訊類型、保留標籤和敏感度標籤的自訂原則。</span><span class="sxs-lookup"><span data-stu-id="3e337-197">A custom policy that uses the available sensitive information types, retention labels, and sensitivity labels.</span></span>
2. <span data-ttu-id="3e337-198">**選擇您要監視的位置** -您可以選擇一個或多個您想要 DLP 監控機密資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="3e337-198">**Choose where you want to monitor** - You pick one or more locations that you want DLP to monitor for sensitive information.</span></span> <span data-ttu-id="3e337-199">您可以監視：</span><span class="sxs-lookup"><span data-stu-id="3e337-199">You can monitor:</span></span>
    
<span data-ttu-id="3e337-200">位置</span><span class="sxs-lookup"><span data-stu-id="3e337-200">location</span></span> | <span data-ttu-id="3e337-201">包含/排除依據</span><span class="sxs-lookup"><span data-stu-id="3e337-201">include/exclude by</span></span>|
|---------|---------|
|<span data-ttu-id="3e337-202">Exchange 電子郵件</span><span class="sxs-lookup"><span data-stu-id="3e337-202">Exchange email</span></span>| <span data-ttu-id="3e337-203">通訊群組</span><span class="sxs-lookup"><span data-stu-id="3e337-203">distribution groups</span></span>|
|<span data-ttu-id="3e337-204">SharePoint 網站</span><span class="sxs-lookup"><span data-stu-id="3e337-204">SharePoint sites</span></span> |<span data-ttu-id="3e337-205">網站</span><span class="sxs-lookup"><span data-stu-id="3e337-205">sites</span></span> |
|<span data-ttu-id="3e337-206">OneDrive 帳戶</span><span class="sxs-lookup"><span data-stu-id="3e337-206">OneDrive accounts</span></span> |<span data-ttu-id="3e337-207">帳戶或通訊群組</span><span class="sxs-lookup"><span data-stu-id="3e337-207">accounts or distribution groups</span></span> |
|<span data-ttu-id="3e337-208">Teams 聊天和頻道訊息</span><span class="sxs-lookup"><span data-stu-id="3e337-208">Teams chat and channel messages</span></span> |<span data-ttu-id="3e337-209">帳戶</span><span class="sxs-lookup"><span data-stu-id="3e337-209">accounts</span></span> |
|<span data-ttu-id="3e337-210">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="3e337-210">Windows 10 devices</span></span> |<span data-ttu-id="3e337-211">使用者或群組</span><span class="sxs-lookup"><span data-stu-id="3e337-211">user or group</span></span> |
|<span data-ttu-id="3e337-212">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3e337-212">Microsoft Cloud App Security</span></span> |<span data-ttu-id="3e337-213">執行個體</span><span class="sxs-lookup"><span data-stu-id="3e337-213">instance</span></span> |
|<span data-ttu-id="3e337-214">內部部署存放庫</span><span class="sxs-lookup"><span data-stu-id="3e337-214">On-premises repositories</span></span>| <span data-ttu-id="3e337-215">存放庫檔路徑</span><span class="sxs-lookup"><span data-stu-id="3e337-215">repository file path</span></span>|

3. <span data-ttu-id="3e337-216">**選擇要套用至專案的原則必須符合的條件** -您可以接受預先設定的條件或定義自訂條件。</span><span class="sxs-lookup"><span data-stu-id="3e337-216">**Choose the conditions that must be matched for a policy to be applied to an item** - you can accept pre-configured conditions or define custom conditions.</span></span> <span data-ttu-id="3e337-217">部分範例如下：</span><span class="sxs-lookup"><span data-stu-id="3e337-217">Some examples are:</span></span>

- <span data-ttu-id="3e337-218">專案包含在特定內容中所使用的機密資訊的指定類型。</span><span class="sxs-lookup"><span data-stu-id="3e337-218">item contains a specified kind of sensitive information that is being used in a certain context.</span></span> <span data-ttu-id="3e337-219">例如，95社會保險號碼會以電子郵件傳送給組織外部的收件者。</span><span class="sxs-lookup"><span data-stu-id="3e337-219">For example, 95 social security numbers being emailed to recipient outside your org.</span></span>
- <span data-ttu-id="3e337-220">專案具有指定的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3e337-220">item has a specified sensitivity label</span></span>
- <span data-ttu-id="3e337-221">具有敏感資訊的專案會在內部或外部共用</span><span class="sxs-lookup"><span data-stu-id="3e337-221">item with sensitive information is shared either internally or externally</span></span>

4. <span data-ttu-id="3e337-222">**選擇符合原則條件時要採取的動作** -動作取決於發生活動的位置。</span><span class="sxs-lookup"><span data-stu-id="3e337-222">**Choose the action to take when the policy conditions are met** - The actions depend on the location where the activity is happening.</span></span>  <span data-ttu-id="3e337-223">部分範例如下：</span><span class="sxs-lookup"><span data-stu-id="3e337-223">Some examples are:</span></span>

- <span data-ttu-id="3e337-224">SharePoint/Exchange/OneDrive：封鎖位於組織表單以外存取內容的人員。</span><span class="sxs-lookup"><span data-stu-id="3e337-224">SharePoint/Exchange/OneDrive: Block people who are outside your organization form accessing the content.</span></span> <span data-ttu-id="3e337-225">向使用者顯示提示，並傳送電子郵件通知，告知他們採取的是 DLP 原則所禁止的動作。</span><span class="sxs-lookup"><span data-stu-id="3e337-225">Show the user a tip and send them an email notification that they are taking an action that is prohibited by the DLP policy.</span></span>
- <span data-ttu-id="3e337-226">Teams聊天室及通道：封鎖在聊天或頻道中共用的敏感資訊</span><span class="sxs-lookup"><span data-stu-id="3e337-226">Teams Chat and Channel: Block sensitive information from being shared in the chat or channel</span></span>
- <span data-ttu-id="3e337-227">Windows 10裝置：審核或限制將敏感專案複製到可拆卸的 USB 裝置</span><span class="sxs-lookup"><span data-stu-id="3e337-227">Windows 10 Devices: Audit or restrict copying a sensitive item to a removeable USB device</span></span> 
- <span data-ttu-id="3e337-228">Office應用程式：顯示快顯視窗，通知使用者他們正在進入危險的行為和封鎖或封鎖，但允許覆寫。</span><span class="sxs-lookup"><span data-stu-id="3e337-228">Office Apps: Show a popup notifying the user that they are engaging in a risky behavior and block or block but allow override.</span></span>
- <span data-ttu-id="3e337-229">內部部署檔案共用：將檔案從儲存位置移至隔離資料夾</span><span class="sxs-lookup"><span data-stu-id="3e337-229">On-premises file shares: move the file from where it is stored to a quarantine folder</span></span>

> [!NOTE]
> <span data-ttu-id="3e337-230">條件和要採取的動作是定義在稱為規則的物件中。</span><span class="sxs-lookup"><span data-stu-id="3e337-230">The conditions and the actions to take are defined in an object called a Rule.</span></span>

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

<span data-ttu-id="3e337-231">在規範中心建立 DLP 原則之後，它會儲存在中央原則存放區中，然後再同步處理至各種內容來源，包括：</span><span class="sxs-lookup"><span data-stu-id="3e337-231">After you create a DLP policy in the Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="3e337-232">Exchange Online，再從這裡到 Outlook 網頁版和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="3e337-232">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
- <span data-ttu-id="3e337-233">商務用 OneDrive 網站。</span><span class="sxs-lookup"><span data-stu-id="3e337-233">OneDrive for Business sites.</span></span>
- <span data-ttu-id="3e337-234">SharePoint Online 網站。</span><span class="sxs-lookup"><span data-stu-id="3e337-234">SharePoint Online sites.</span></span>
- <span data-ttu-id="3e337-235">Office 桌上型電腦程式 (Excel、PowerPoint 及 Word)。</span><span class="sxs-lookup"><span data-stu-id="3e337-235">Office desktop programs (Excel, PowerPoint, and Word).</span></span>
- <span data-ttu-id="3e337-236">Microsoft Teams 頻道和聊天訊息。</span><span class="sxs-lookup"><span data-stu-id="3e337-236">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="3e337-237">原則同步處理至正確的位置之後，會開始評估內容並強制執行動作。</span><span class="sxs-lookup"><span data-stu-id="3e337-237">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>

## <a name="viewing-policy-application-results"></a><span data-ttu-id="3e337-238">查看原則應用程式結果</span><span class="sxs-lookup"><span data-stu-id="3e337-238">Viewing policy application results</span></span>

<span data-ttu-id="3e337-239">DLP 會將大量資訊從監控、原則比對和動作和使用者活動報告 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3e337-239">DLP reports a vast amount of information into Microsoft 365 from monitoring, policy matches and actions, and user activities.</span></span> <span data-ttu-id="3e337-240">您必須使用該資訊並採取行動，以調整對機密專案所採取的原則及會審動作。</span><span class="sxs-lookup"><span data-stu-id="3e337-240">You'll need to consume and act on that information to tune your policies and triage actions taken on sensitive items.</span></span> <span data-ttu-id="3e337-241">遙測會先處理[Microsoft 365 規範中心審核記錄](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center)檔，並將其方式用於不同的報表工具。</span><span class="sxs-lookup"><span data-stu-id="3e337-241">The telemetry goes into the [Microsoft 365 Compliance center Audit Logs](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) first, is processed, and makes its way to different reporting tools.</span></span> <span data-ttu-id="3e337-242">每個報告工具都有不同的用途。</span><span class="sxs-lookup"><span data-stu-id="3e337-242">Each reporting tool has a different purpose.</span></span>  

### <a name="dlp-alerts-dashboard"></a><span data-ttu-id="3e337-243">DLP 警示儀表板</span><span class="sxs-lookup"><span data-stu-id="3e337-243">DLP Alerts Dashboard</span></span>

<span data-ttu-id="3e337-244">當 DLP 對機密專案採取動作時，您可以透過可設定的警示通知該動作。</span><span class="sxs-lookup"><span data-stu-id="3e337-244">When DLP takes an action on a sensitive item, you can be notified of that action via a configurable alert.</span></span> <span data-ttu-id="3e337-245">「規範中心」可讓 [您在信箱](dlp-configure-view-alerts-policies.md)中進行鎖定，而不是讓您在信箱中進行這些警示。</span><span class="sxs-lookup"><span data-stu-id="3e337-245">Rather than having these alerts pile up in a mailbox for you to sift through, the Compliance center makes them available in the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span> <span data-ttu-id="3e337-246">使用 [DLP 警示] 儀表板來設定警示、進行審閱、會審及追蹤 DLP 警示的解決方法。</span><span class="sxs-lookup"><span data-stu-id="3e337-246">Use the DLP Alerts dashboard to configure alerts, review them, triage them and track resolution of DLP Alerts.</span></span> <span data-ttu-id="3e337-247">以下是從 Windows 10 裝置中的原則相符和活動所產生之警示的範例。</span><span class="sxs-lookup"><span data-stu-id="3e337-247">Here's an example of alerts generated by policy matches and activities from Windows 10 devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3e337-248">![警示資訊](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="3e337-248">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="3e337-249">您還可以在同一個儀表板中檢視具有豐富中繼資料的關聯事件的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3e337-249">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3e337-250">![事件資訊](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="3e337-250">![event info](../media/Event-info-1.png)</span></span>

### <a name="reports"></a><span data-ttu-id="3e337-251">報告</span><span class="sxs-lookup"><span data-stu-id="3e337-251">Reports</span></span>

<span data-ttu-id="3e337-252">[DLP 報告](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention)會顯示隨時間的廣泛趨勢，並提供下列專案的特定見解：</span><span class="sxs-lookup"><span data-stu-id="3e337-252">The [DLP reports](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) show broad trends over time and give specific insights into:</span></span>

- <span data-ttu-id="3e337-253">**DLP 原則符合** 時間，並依日期範圍、位置、原則或動作進行篩選</span><span class="sxs-lookup"><span data-stu-id="3e337-253">**DLP Policy Matches** over time and filter by date range, location, policy, or action</span></span>
- <span data-ttu-id="3e337-254">**DLP 事件** 比對會隨著時間而顯示相符專案，但會在專案上轉動，而不是原則規則。</span><span class="sxs-lookup"><span data-stu-id="3e337-254">**DLP incident matches** also shows matches over time, but pivots on the items rather than the policy rules.</span></span>
- <span data-ttu-id="3e337-255">**DLP false 正值和 overrides** 會顯示誤報計數，以及設定後的使用者覆寫（如果已設定）和使用者的理由。</span><span class="sxs-lookup"><span data-stu-id="3e337-255">**DLP false positives and overrides** shows the count of false positives and, if configured, user-overrides along with the user justification.</span></span>

### <a name="dlp-activity-explorer"></a><span data-ttu-id="3e337-256">DLP 活動瀏覽器</span><span class="sxs-lookup"><span data-stu-id="3e337-256">DLP Activity Explorer</span></span>

<span data-ttu-id="3e337-257">DLP 頁面上的 [活動流覽] 索引標籤會將 *活動* 篩選器預先設定為 *DLPRuleMatch*。</span><span class="sxs-lookup"><span data-stu-id="3e337-257">The Activity explorer tab on the DLP page has the *Activity* filter preset to *DLPRuleMatch*.</span></span> <span data-ttu-id="3e337-258">使用此工具可查看與包含機密資訊或已套用標籤之內容相關的活動，例如變更的標籤、檔已修改，以及符合規則。</span><span class="sxs-lookup"><span data-stu-id="3e337-258">Use this tool to review activity related to content that contains sensitive info or has labels applied, such as what labels were changed, files were modified, and matched a rule.</span></span>

![<span data-ttu-id="3e337-259">DLPRuleMatch 範圍的活動瀏覽器的螢幕擷取畫面</span><span class="sxs-lookup"><span data-stu-id="3e337-259">screenshot of the DLPRuleMatch scoped activity explorer</span></span> ](../media/dlp-activity-explorer.png)

<span data-ttu-id="3e337-260">如需詳細資訊，請參閱 [活動瀏覽器快速入門](data-classification-activity-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="3e337-260">For more information, see [Get started with activity explorer](data-classification-activity-explorer.md)</span></span>

<span data-ttu-id="3e337-261">若要深入瞭解 Microsoft 365 DLP，請參閱：</span><span class="sxs-lookup"><span data-stu-id="3e337-261">To learn more about Microsoft 365 DLP, see:</span></span>

- [<span data-ttu-id="3e337-262">深入瞭解 Microsoft 365 端點資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="3e337-262">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="3e337-263">了解 Microsoft Teams 中的預設資料外洩防護原則 (預覽)</span><span class="sxs-lookup"><span data-stu-id="3e337-263">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>](dlp-teams-default-policy.md)
- [<span data-ttu-id="3e337-264">深入了解 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)</span><span class="sxs-lookup"><span data-stu-id="3e337-264">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="3e337-265">了解 Microsoft 合規性擴充功能 (預覽)</span><span class="sxs-lookup"><span data-stu-id="3e337-265">Learn about the Microsoft Compliance Extension (preview)</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="3e337-266">了解資料外洩防護警示儀表板</span><span class="sxs-lookup"><span data-stu-id="3e337-266">Learn about the data loss prevention Alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)

<span data-ttu-id="3e337-267">若要瞭解如何使用資料遺失防護來遵守資料隱私權規定，請參閱使用 Microsoft 365 (aka.ms/m365dataprivacy) [部署資料隱私權法規的資訊保護](../solutions/information-protection-deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="3e337-267">To learn how to use data loss prevention to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>