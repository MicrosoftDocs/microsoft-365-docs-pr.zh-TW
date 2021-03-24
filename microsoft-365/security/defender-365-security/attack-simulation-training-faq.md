---
title: 攻擊模擬訓練部署考慮和常見問題
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以深入瞭解 Microsoft 365 E5 或 Microsoft Defender for Office 365 Plan 2 組織中有關攻擊模擬和訓練的部署考慮和常見問題。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059027"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a><span data-ttu-id="135e1-103">攻擊模擬訓練部署考慮和常見問題</span><span class="sxs-lookup"><span data-stu-id="135e1-103">Attack simulation training deployment considerations and FAQ</span></span>

<span data-ttu-id="135e1-104">現已 [提供](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291)攻擊模擬訓練。</span><span class="sxs-lookup"><span data-stu-id="135e1-104">Attack simulation training is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291).</span></span> <span data-ttu-id="135e1-105">攻擊模擬訓練可讓 Microsoft 365 E5 或 Microsoft Defender for Office 365 Plan 2 組織，可讓您建立及管理以實際執行 weaponized 網路釣魚詐騙為供電的網路釣魚模擬模擬，以衡量及管理社交工程風險。</span><span class="sxs-lookup"><span data-stu-id="135e1-105">Attack simulation training enables Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2 organizations to measure and manage social engineering risk by allowing the creation and management of phishing simulations that are powered by real-world, de-weaponized phishing payloads.</span></span> <span data-ttu-id="135e1-106">在合作與 Terranova 安全性中提供的超目標訓練，可協助改善知識並變更員工行為。</span><span class="sxs-lookup"><span data-stu-id="135e1-106">Hyper-targeted training, delivered in partnership with Terranova security, helps improve knowledge and change employee behavior.</span></span>

<span data-ttu-id="135e1-107">如需如何開始使用攻擊模擬訓練的詳細資訊，請參閱 [開始使用攻擊模擬訓練](attack-simulation-training-get-started.md)。</span><span class="sxs-lookup"><span data-stu-id="135e1-107">For more information about getting started with Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="135e1-108">當整個類比建立及排程體驗設計為自由流動和 frictionless 時，在企業規模中執行模擬通常需要規劃。</span><span class="sxs-lookup"><span data-stu-id="135e1-108">While the whole simulation creation and scheduling experience has been designed to be free-flowing and frictionless, running simulations at an enterprise scale often requires planning.</span></span> <span data-ttu-id="135e1-109">本文可協助解決客戶在自己的環境中執行模擬時所看到的特定難題。</span><span class="sxs-lookup"><span data-stu-id="135e1-109">This article helps address specific challenges that we see as our customers run simulations in their own environments.</span></span>

## <a name="issues-with-end-user-experiences"></a><span data-ttu-id="135e1-110">使用者體驗方面的問題</span><span class="sxs-lookup"><span data-stu-id="135e1-110">Issues with end user experiences</span></span>

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a><span data-ttu-id="135e1-111">Google Safe 流覽封鎖 URLs 網路釣魚類比</span><span class="sxs-lookup"><span data-stu-id="135e1-111">Phishing simulation URLs blocked by Google Safe Browsing</span></span>

<span data-ttu-id="135e1-112">URL 信譽服務可能會識別攻擊模擬訓練所使用的一或多個 URLs 為不安全。</span><span class="sxs-lookup"><span data-stu-id="135e1-112">A URL reputation service might identify one or more of the URLs that are used by Attack simulation training as unsafe.</span></span> <span data-ttu-id="135e1-113">Google Chrome 中的 google Safe 流覽會封鎖某些模擬的網路釣魚 URLs 與 **欺騙性網站** 一起使用的郵件。</span><span class="sxs-lookup"><span data-stu-id="135e1-113">Google Safe Browsing in Google Chrome blocks some of the simulated phishing URLs with a **Deceptive site ahead** message.</span></span> <span data-ttu-id="135e1-114">當我們與許多 URL 信譽廠商合作，以無條件允許類比 URLs，我們不一定會有完整的覆蓋範圍。</span><span class="sxs-lookup"><span data-stu-id="135e1-114">While we work with many URL reputation vendors to always allow our simulation URLs, we don't always have full coverage.</span></span>

![Google Chrome 中的欺騙性網站先行警告](../../media/attack-sim-chrome-deceptive-site-message.png)

<span data-ttu-id="135e1-116">請注意，此問題不會影響 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="135e1-116">Note that this issue does not affect Microsoft Edge.</span></span>

<span data-ttu-id="135e1-117">在規劃階段中，請務必先檢查支援的網頁瀏覽器中的 URL 可用性，再使用網路釣魚活動中的 URL。</span><span class="sxs-lookup"><span data-stu-id="135e1-117">As part of the planning phase, be sure to check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="135e1-118">如果 URLs 被 Google 安全流覽封鎖，請遵循 Google 的 [指導](https://support.google.com/chrome/a/answer/7532419) 以允許存取 URLs。</span><span class="sxs-lookup"><span data-stu-id="135e1-118">If the URLs are blocked by Google Safe Browsing, [follow this guidance](https://support.google.com/chrome/a/answer/7532419) from Google to allow access to the URLs.</span></span>

<span data-ttu-id="135e1-119">請參閱如何 [開始使用攻擊模擬訓練](attack-simulation-training-get-started.md) ，以取得受攻擊模擬訓練的目前使用 URLs 清單。</span><span class="sxs-lookup"><span data-stu-id="135e1-119">Refer to [Get started using Attack simulation training](attack-simulation-training-get-started.md) for the list of URLs that are currently used by Attack simulation training.</span></span>

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a><span data-ttu-id="135e1-120">網路 proxy 解決方案及篩選器驅動程式封鎖網路釣魚類比和系統管理員 URLs</span><span class="sxs-lookup"><span data-stu-id="135e1-120">Phishing simulation and admin URLs blocked by network proxy solutions and filter drivers</span></span>

<span data-ttu-id="135e1-121">網路釣魚模擬 URLs 和系統管理 URLs 可能會被您的中間安全性裝置或篩選器封鎖或丟棄。</span><span class="sxs-lookup"><span data-stu-id="135e1-121">Both phishing simulation URLs and admin URLs might be blocked or dropped by your intermediate security devices or filters.</span></span> <span data-ttu-id="135e1-122">例如：</span><span class="sxs-lookup"><span data-stu-id="135e1-122">For example:</span></span>

- <span data-ttu-id="135e1-123">防火牆</span><span class="sxs-lookup"><span data-stu-id="135e1-123">Firewalls</span></span>
- <span data-ttu-id="135e1-124">WAF) 解決方案的 Web 應用程式防火牆 (</span><span class="sxs-lookup"><span data-stu-id="135e1-124">Web Application Firewall (WAF) solutions</span></span>
- <span data-ttu-id="135e1-125">協力廠商篩選器驅動程式 (例如，核心模式篩選) </span><span class="sxs-lookup"><span data-stu-id="135e1-125">Third-party filter drivers (for example, kernel mode filters)</span></span>

<span data-ttu-id="135e1-126">當我們看到少數客戶在此階層遭到封鎖時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="135e1-126">While we have seen few customers being blocked at this layer, it does happen.</span></span> <span data-ttu-id="135e1-127">如果您遇到問題，請考慮設定下列 URLs，以略過您的安全性裝置或篩選器（如有必要）：</span><span class="sxs-lookup"><span data-stu-id="135e1-127">If you encounter problems, consider configuring the following URLs to bypass scanning by your security devices or filters as required:</span></span>

- <span data-ttu-id="135e1-128">模擬網路釣魚 URLs，如 [開始使用進攻類比訓練](attack-simulation-training-get-started.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="135e1-128">The simulated phishing URLs as described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a><span data-ttu-id="135e1-129">類比訊息未傳遞給所有目標使用者</span><span class="sxs-lookup"><span data-stu-id="135e1-129">Simulation messages not delivered to all targeted users</span></span>

<span data-ttu-id="135e1-130">實際接收模擬電子郵件的使用者人數可能會小於類比所針對的使用者數目的數目。</span><span class="sxs-lookup"><span data-stu-id="135e1-130">It's possible that the number of users who actually receive the simulation email messages is less than the number of users who were targeted by the simulation.</span></span> <span data-ttu-id="135e1-131">下列類型的使用者將會排除為目標驗證的一部分：</span><span class="sxs-lookup"><span data-stu-id="135e1-131">The following types of users will be excluded as part of target validation:</span></span>

- <span data-ttu-id="135e1-132">不正確收件者電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="135e1-132">Invalid recipient email addresses.</span></span>
- <span data-ttu-id="135e1-133">來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="135e1-133">Guest users.</span></span>
- <span data-ttu-id="135e1-134">在 Azure Active Directory (Azure AD) 中不再使用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="135e1-134">Users that are no longer active in Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="135e1-135">模擬中只會包含有效的非來賓使用者，具有有效的信箱。</span><span class="sxs-lookup"><span data-stu-id="135e1-135">Only valid, non-guest users with a valid mailbox will be included in simulations.</span></span> <span data-ttu-id="135e1-136">如果您使用通訊群組或擁有郵件功能的安全性群組來為使用者設定目標，您可以使用[Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中的[Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) Cmdlet，以查看和驗證通訊群組成員。</span><span class="sxs-lookup"><span data-stu-id="135e1-136">If you use distribution groups or mail-enabled security groups to target users, you can use the [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) cmdlet in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) to view and validate distribution group members.</span></span>

## <a name="issues-with-attack-simulation-training-reporting"></a><span data-ttu-id="135e1-137">攻擊模擬的訓練報告問題</span><span class="sxs-lookup"><span data-stu-id="135e1-137">Issues with Attack simulation training reporting</span></span>

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a><span data-ttu-id="135e1-138">攻擊模擬訓練報告不含任何活動詳細資料</span><span class="sxs-lookup"><span data-stu-id="135e1-138">Attack simulation training reports do not contain any activity details</span></span>

<span data-ttu-id="135e1-139">攻擊模擬訓練包含豐富的可操作性見解，可讓您獲悉員工的威脅準備進度。</span><span class="sxs-lookup"><span data-stu-id="135e1-139">Attack simulation training comes with rich, actionable insights that keep you informed of the threat readiness progress of your employees.</span></span> <span data-ttu-id="135e1-140">如果攻擊模擬訓練報告未填入資料，請確認已在組織中開啟「審計記錄搜尋」 () 預設為開啟。</span><span class="sxs-lookup"><span data-stu-id="135e1-140">If Attack simulation training reports are not populated with data, verify that audit log search is turned on in your organization (it's on by default).</span></span>

<span data-ttu-id="135e1-141">攻擊模擬訓練會要求進行審計記錄搜尋，讓事件可以捕獲、記錄和回讀。</span><span class="sxs-lookup"><span data-stu-id="135e1-141">Audit log search is required by Attack simulation training so events can be captured, recorded, and read back.</span></span> <span data-ttu-id="135e1-142">關閉「審計記錄檔搜尋」時，攻擊模擬訓練會產生下列後果：</span><span class="sxs-lookup"><span data-stu-id="135e1-142">Turning off audit log search has the following consequences for Attack simulation training:</span></span>

- <span data-ttu-id="135e1-143">報告資料無法在所有報告中使用。</span><span class="sxs-lookup"><span data-stu-id="135e1-143">Reporting data is not available across all reports.</span></span> <span data-ttu-id="135e1-144">報告會顯示空白。</span><span class="sxs-lookup"><span data-stu-id="135e1-144">The reports will appear empty.</span></span>
- <span data-ttu-id="135e1-145">因為無法使用資料，所以訓練指派遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="135e1-145">Training assignments are blocked, because data is not available.</span></span>

<span data-ttu-id="135e1-146">若要開啟審計記錄搜尋，請參閱 [開啟或關閉審計記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="135e1-146">To turn on audit log search, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

> [!NOTE]
> <span data-ttu-id="135e1-147">不會將任何 E5 授權指派給使用者，也可能會造成空白的活動詳細資料。</span><span class="sxs-lookup"><span data-stu-id="135e1-147">Empty activity details can also be caused by no E5 licenses being assigned to users.</span></span> <span data-ttu-id="135e1-148">請確認至少有一個 E5 授權指派給作用中的使用者，以確保捕獲和記錄報告事件。</span><span class="sxs-lookup"><span data-stu-id="135e1-148">Verify at least one E5 license is assigned to an active user to ensure that reporting events are captured and recorded.</span></span>

### <a name="simulation-reports-are-not-updated-immediately"></a><span data-ttu-id="135e1-149">不會立即更新類比報告</span><span class="sxs-lookup"><span data-stu-id="135e1-149">Simulation reports are not updated immediately</span></span>

<span data-ttu-id="135e1-150">在您啟動市場活動之後，就不會立即更新詳細的類比報告。</span><span class="sxs-lookup"><span data-stu-id="135e1-150">Detailed simulation reports are not updated immediately after you launch a campaign.</span></span> <span data-ttu-id="135e1-151">別擔心;這是預期行為。</span><span class="sxs-lookup"><span data-stu-id="135e1-151">Don't worry; this behavior is expected.</span></span>

<span data-ttu-id="135e1-152">每個類比活動都有生命週期。</span><span class="sxs-lookup"><span data-stu-id="135e1-152">Every simulation campaign has a lifecycle.</span></span> <span data-ttu-id="135e1-153">第一次建立時，類比即為 **排程** 狀態。</span><span class="sxs-lookup"><span data-stu-id="135e1-153">When first created, the simulation is in the **Scheduled** state.</span></span> <span data-ttu-id="135e1-154">當類比開始時，它會轉變為 **進行中** 狀態。</span><span class="sxs-lookup"><span data-stu-id="135e1-154">When the simulation starts, it transitions to the **In progress** state.</span></span> <span data-ttu-id="135e1-155">完成時，類比會轉換成 **已完成** 的狀態。</span><span class="sxs-lookup"><span data-stu-id="135e1-155">When completed, the simulation transitions to the **Completed** state.</span></span>

<span data-ttu-id="135e1-156">當類比處於 **排程** 狀態時，類比報告基本上會是空的。</span><span class="sxs-lookup"><span data-stu-id="135e1-156">While a simulation is in the **Scheduled** state, the simulation reports will be mostly empty.</span></span> <span data-ttu-id="135e1-157">在此階段中，模擬引擎正在解析目標使用者電子郵件地址、展開通訊群組、從清單中移除來賓使用者等等：</span><span class="sxs-lookup"><span data-stu-id="135e1-157">During this stage, the simulation engine is resolving the target user email addresses, expanding distribution groups, removing guest users from the list, etc.:</span></span>

![排程狀態中的報告](../../media/attack-sim-empty-reporting.png)

<span data-ttu-id="135e1-159">類比進入 **進行中** 階段後，您會注意到資訊開始細流到報告：</span><span class="sxs-lookup"><span data-stu-id="135e1-159">Once the simulation enters the **In progress** stage, you will notice information starting to trickle into the reporting:</span></span>

![在進行中的狀態報表](../../media/attack-sim-in-progress.png)

<span data-ttu-id="135e1-161">您最多可能需要30分鐘的時間，才能將個別的類比報告更新為 [ **進行中** ] 狀態。</span><span class="sxs-lookup"><span data-stu-id="135e1-161">It can take up to 30 minutes for the individual simulation reports to update after the transition to the **In progress** state.</span></span> <span data-ttu-id="135e1-162">報告資料會繼續建立，直到類比達到 **完成** 狀態為止。</span><span class="sxs-lookup"><span data-stu-id="135e1-162">The report data continues to build until the simulation reaches the **Completed** state.</span></span> <span data-ttu-id="135e1-163">報告更新的執行間隔如下：</span><span class="sxs-lookup"><span data-stu-id="135e1-163">Reporting updates occur at the following intervals:</span></span>

- <span data-ttu-id="135e1-164">在前60分鐘內，每10分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="135e1-164">Every 10 minutes for the first 60 minutes.</span></span>
- <span data-ttu-id="135e1-165">60分鐘之後每隔15分鐘直到2天。</span><span class="sxs-lookup"><span data-stu-id="135e1-165">Every 15 minutes after 60 minutes until 2 days.</span></span>
- <span data-ttu-id="135e1-166">在2天之後的30分鐘之後，直到7天。</span><span class="sxs-lookup"><span data-stu-id="135e1-166">Every 30 minutes after 2 days until 7 days.</span></span>
- <span data-ttu-id="135e1-167">7天后，每隔60分鐘。</span><span class="sxs-lookup"><span data-stu-id="135e1-167">Every 60 minutes after 7 days.</span></span>

<span data-ttu-id="135e1-168">[ **一覽** ] 頁面上的小元件可提供組織隨時間的類比基礎安全性狀況快速快照。</span><span class="sxs-lookup"><span data-stu-id="135e1-168">Widgets on the **Overview** page provide a quick snapshot of your organization's simulation-based security posture over time.</span></span> <span data-ttu-id="135e1-169">因為這些小小程式會反映您的整體安全性狀況和旅程，所以在完成每個類比活動之後，就會更新。</span><span class="sxs-lookup"><span data-stu-id="135e1-169">Because these widgets reflect your overall security posture and journey over time, they're updated after each simulation campaign is completed.</span></span>

> [!NOTE]
> <span data-ttu-id="135e1-170">您可以在各種報告頁面上使用 [ **匯出** ] 選項，以提取資料。</span><span class="sxs-lookup"><span data-stu-id="135e1-170">You can use the **Export** option on the various reporting pages to extract data.</span></span>

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a><span data-ttu-id="135e1-171">使用者報告為網路釣魚的郵件未出現在類比報告中</span><span class="sxs-lookup"><span data-stu-id="135e1-171">Messages reported as phishing by users aren't appearing in simulation reports</span></span>

<span data-ttu-id="135e1-172">攻擊模擬器訓練中的類比報告可提供使用者活動的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="135e1-172">Simulation reports in Attack simulator training provide details on user activity.</span></span> <span data-ttu-id="135e1-173">例如：</span><span class="sxs-lookup"><span data-stu-id="135e1-173">For example:</span></span>

- <span data-ttu-id="135e1-174">在郵件中按一下連結的使用者。</span><span class="sxs-lookup"><span data-stu-id="135e1-174">Users who clicked on the link in the message.</span></span>
- <span data-ttu-id="135e1-175">提供其認證的使用者。</span><span class="sxs-lookup"><span data-stu-id="135e1-175">Users who gave up their credentials.</span></span>
- <span data-ttu-id="135e1-176">將郵件報告為網路釣魚的使用者。</span><span class="sxs-lookup"><span data-stu-id="135e1-176">Users who reported the message as phishing.</span></span>

<span data-ttu-id="135e1-177">如果使用者報告為網路釣魚的郵件不會在攻擊模擬訓練類比報告中取得，則可能會有 Exchange 郵件流程規則 (也稱為傳輸規則) 會封鎖所報告的郵件傳遞至 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="135e1-177">If messages that users reported as phishing aren't captured in Attack simulation training simulation reports, there might be an Exchange mail flow rule (also known as a transport rule) that's blocking the delivery of the reported messages to Microsoft.</span></span> <span data-ttu-id="135e1-178">確認任何郵件流程規則不會封鎖傳遞至下列電子郵件地址：</span><span class="sxs-lookup"><span data-stu-id="135e1-178">Verify that any mail flow rules aren't blocking delivery to the following email addresses:</span></span>

- <span data-ttu-id="135e1-179">junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="135e1-179">junk@office365.microsoft.com</span></span>
- <span data-ttu-id="135e1-180">abuse@messaging.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="135e1-180">abuse@messaging.microsoft.com</span></span>
- <span data-ttu-id="135e1-181">phish@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="135e1-181">phish@office365.microsoft.com</span></span>
- <span data-ttu-id="135e1-182">非 \_ junk@office365.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="135e1-182">not\_junk@office365.microsoft.com</span></span>

## <a name="other-frequently-asked-questions"></a><span data-ttu-id="135e1-183">其他常見問題</span><span class="sxs-lookup"><span data-stu-id="135e1-183">Other frequently asked questions</span></span>

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a><span data-ttu-id="135e1-184">問：針對類比活動的使用者，建議使用哪種方法？</span><span class="sxs-lookup"><span data-stu-id="135e1-184">Q: What is the recommended method to target users for simulation campaigns?</span></span>

<span data-ttu-id="135e1-185">A：目標使用者可以使用數種選項：</span><span class="sxs-lookup"><span data-stu-id="135e1-185">A: Several options are available to target users:</span></span>

- <span data-ttu-id="135e1-186">包含目前可供低於40000使用者之組織使用的所有使用者 () 。</span><span class="sxs-lookup"><span data-stu-id="135e1-186">Include all users (currently available to organizations with less than 40,000 users).</span></span>
- <span data-ttu-id="135e1-187">選擇 [特定使用者]。</span><span class="sxs-lookup"><span data-stu-id="135e1-187">Choose specific users.</span></span>
- <span data-ttu-id="135e1-188">從 CSV 檔案中選取 [使用者]。</span><span class="sxs-lookup"><span data-stu-id="135e1-188">Select users from a CSV file.</span></span>
- <span data-ttu-id="135e1-189">Azure AD 群組為基礎的目標。</span><span class="sxs-lookup"><span data-stu-id="135e1-189">Azure AD group-based targeting.</span></span>

<span data-ttu-id="135e1-190">我們發現市場活動中，Azure AD 群組識別目標使用者通常會比較容易管理。</span><span class="sxs-lookup"><span data-stu-id="135e1-190">We've found that campaigns where the targeted users are identified by Azure AD groups are generally easier to manage.</span></span>

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a><span data-ttu-id="135e1-191">問：從 CSV 或新增使用者進行匯入時，是否要針對使用者提供任何限制？</span><span class="sxs-lookup"><span data-stu-id="135e1-191">Q: Are there any limits in targeting users while importing from a CSV or adding users?</span></span>

<span data-ttu-id="135e1-192">A：從 CSV 檔案匯入收件者或將個別收件者新增至類比的限制是40000。</span><span class="sxs-lookup"><span data-stu-id="135e1-192">A: The limit for importing recipients from a CSV file or adding individual recipients to a simulation is 40,000.</span></span>

<span data-ttu-id="135e1-193">收件者可以是個別的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="135e1-193">A recipient can be an individual user or a group.</span></span> <span data-ttu-id="135e1-194">群組可能包含成百上千個收件者，因此實際的限制不會放在個別使用者的數量上。</span><span class="sxs-lookup"><span data-stu-id="135e1-194">A group might contain hundreds or thousands of recipients, so an actual limit isn't placed on the number of individual users.</span></span>

<span data-ttu-id="135e1-195">管理大型 CSV 檔案或新增許多個人的收件者可能會很麻煩。</span><span class="sxs-lookup"><span data-stu-id="135e1-195">Managing a large CSV file or adding many individual recipients can be cumbersome.</span></span> <span data-ttu-id="135e1-196">使用 Azure AD 群組可簡化類比的整體管理。</span><span class="sxs-lookup"><span data-stu-id="135e1-196">Using Azure AD groups will simplify the overall management of the simulation.</span></span>

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a><span data-ttu-id="135e1-197">問： Microsoft 是否提供其他語言的負載？</span><span class="sxs-lookup"><span data-stu-id="135e1-197">Q: Does Microsoft provide payloads in other languages?</span></span>

<span data-ttu-id="135e1-198">A：目前有5個當地語系化的負載可用。</span><span class="sxs-lookup"><span data-stu-id="135e1-198">A: Currently, there are 5 localized payloads available.</span></span> <span data-ttu-id="135e1-199">已注意到，現有負載的任何直接或機器翻譯翻譯為其他語言的通知，會導致不准確並降低相關性。</span><span class="sxs-lookup"><span data-stu-id="135e1-199">We've noticed than any direct or machine translations of existing payloads to other languages will lead to inaccuracies and decreased relevance.</span></span>

<span data-ttu-id="135e1-200">也就是說，您可以使用自訂的負載製作體驗，以您選擇的語言來建立您自己的負載。</span><span class="sxs-lookup"><span data-stu-id="135e1-200">That being said, you can create your own payload in the language of your choice using the custom payload authoring experience.</span></span> <span data-ttu-id="135e1-201">我們也強烈建議您收集用來將特定地理位置的使用者作為目標的現有負載。</span><span class="sxs-lookup"><span data-stu-id="135e1-201">We also strongly recommend that you harvest existing payloads that were used to target users in a specific geography.</span></span> <span data-ttu-id="135e1-202">換句話說，讓攻擊者為您當地語系化內容。</span><span class="sxs-lookup"><span data-stu-id="135e1-202">In other words, let the attackers localize the content for you.</span></span>

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a><span data-ttu-id="135e1-203">問：我該如何切換其他語言以取得系統管理員入口網站及訓練體驗？</span><span class="sxs-lookup"><span data-stu-id="135e1-203">Q: How can I switch to other languages for my admin portal and training experience?</span></span>

<span data-ttu-id="135e1-204">A：在 Microsoft 365 或 Office 365 中，語言設定為每個使用者帳戶的特定及集中式。</span><span class="sxs-lookup"><span data-stu-id="135e1-204">A: In Microsoft 365 or Office 365, language configuration is specific and centralized for each user account.</span></span> <span data-ttu-id="135e1-205">如需如何變更語言設定的指示，請參閱 [在 Microsoft 365 For Business 中變更您的顯示語言和](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)時區。</span><span class="sxs-lookup"><span data-stu-id="135e1-205">For instructions on how to change your language setting, see [Change your display language and time zone in Microsoft 365 for Business](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b).</span></span>

<span data-ttu-id="135e1-206">請注意，設定變更可能需要30分鐘的時間，才能同步處理所有服務。</span><span class="sxs-lookup"><span data-stu-id="135e1-206">Note that the configuration change might take up to 30 minutes to synchronize across all services.</span></span>

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a><span data-ttu-id="135e1-207">問：我是否可以觸發測試模擬，以瞭解在啟動完整的活動之前所要看到的功能？</span><span class="sxs-lookup"><span data-stu-id="135e1-207">Q: Can I trigger a test simulation to understand what it looks like prior to launching a full-fledged campaign?</span></span>

<span data-ttu-id="135e1-208">A：可以是。</span><span class="sxs-lookup"><span data-stu-id="135e1-208">A: Yes you can!</span></span> <span data-ttu-id="135e1-209">在嚮導中 [最近一次的 **檢查類比** ] 頁面上，建立新的類比，有一個選項可以 **傳送測試**。</span><span class="sxs-lookup"><span data-stu-id="135e1-209">On the very last **Review Simulation** page in the wizard to create a new simulation, there's an option to **Send a test**.</span></span> <span data-ttu-id="135e1-210">此選項會將範例網路釣魚模擬郵件傳送給目前登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="135e1-210">This option will send a sample phishing simulation message to the currently logged in user.</span></span> <span data-ttu-id="135e1-211">在您在 [收件匣] 中驗證網路釣魚郵件之後，您可以提交模擬。</span><span class="sxs-lookup"><span data-stu-id="135e1-211">After you validate the phishing message in your Inbox, you can submit the simulation.</span></span>

![在 [檢查類比] 頁面上傳送測試按鈕](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a><span data-ttu-id="135e1-213">問：我是否可以將屬於其他租使用者的使用者設定為相同類比活動的一部分？</span><span class="sxs-lookup"><span data-stu-id="135e1-213">Q: Can I target users that belong to a different tenant as part of the same simulation campaign?</span></span>

<span data-ttu-id="135e1-214">答：否。</span><span class="sxs-lookup"><span data-stu-id="135e1-214">A: No.</span></span> <span data-ttu-id="135e1-215">目前不支援跨租使用者模擬。</span><span class="sxs-lookup"><span data-stu-id="135e1-215">Currently, cross-tenant simulations are not supported.</span></span> <span data-ttu-id="135e1-216">確認您的所有目標使用者都位於相同的承租人。</span><span class="sxs-lookup"><span data-stu-id="135e1-216">Verify that all of your targeted users are in the same tenant.</span></span> <span data-ttu-id="135e1-217">任何跨承租人使用者或來賓使用者將會從類比活動中排除。</span><span class="sxs-lookup"><span data-stu-id="135e1-217">Any cross-tenant users or guest users will be excluded from the simulation campaign.</span></span>

### <a name="q-how-does-region-aware-delivery-work"></a><span data-ttu-id="135e1-218">問：地區識別傳遞的運作方式如何？</span><span class="sxs-lookup"><span data-stu-id="135e1-218">Q: How does region aware delivery work?</span></span>

<span data-ttu-id="135e1-219">A：地區感知傳遞使用目標使用者信箱的 TimeZone 屬性和「非 before」邏輯來決定何時傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="135e1-219">A: Region aware delivery uses the TimeZone attribute of the targeted user's mailbox and 'not before' logic to determine when to deliver the message.</span></span> <span data-ttu-id="135e1-220">例如，請考量下列情境：</span><span class="sxs-lookup"><span data-stu-id="135e1-220">For example, consider the following scenario:</span></span>

- <span data-ttu-id="135e1-221">在太平洋時區中的 7:00 AM (UTC-8) ，系統管理員會建立和排程市場活動，以在同一天的 9:00 AM 開始。</span><span class="sxs-lookup"><span data-stu-id="135e1-221">At 7:00 AM in the Pacific time zone (UTC-8), an admin creates and schedules a campaign to start at 9:00 AM on the same day.</span></span>
- <span data-ttu-id="135e1-222">UserA 位於東部時區 (UTC-5) 。</span><span class="sxs-lookup"><span data-stu-id="135e1-222">UserA is in the Eastern time zone (UTC-5).</span></span>
- <span data-ttu-id="135e1-223">UserB 也位於太平洋時區。</span><span class="sxs-lookup"><span data-stu-id="135e1-223">UserB is also in the Pacific time zone.</span></span>

<span data-ttu-id="135e1-224">在同一天的 9:00 AM，類比郵件會傳送至 UserB。</span><span class="sxs-lookup"><span data-stu-id="135e1-224">At 9:00 AM on the same day, the simulation message is sent to UserB.</span></span> <span data-ttu-id="135e1-225">透過地區感知傳遞，郵件不會在同一天傳送至 UserA，因為 9:00 AM 太平洋時間是東部時間 12:00 PM。</span><span class="sxs-lookup"><span data-stu-id="135e1-225">With region-aware delivery, the message is not sent to UserA on the same day, because 9:00 AM Pacific time is 12:00 PM Eastern time.</span></span> <span data-ttu-id="135e1-226">相反地，郵件會在下一天的 9:00 AM 東部時間傳送至 UserA。</span><span class="sxs-lookup"><span data-stu-id="135e1-226">Instead, the message is sent to UserA at 9:00 AM Eastern time on the following day.</span></span>

<span data-ttu-id="135e1-227">因此，在初次執行具有地區感知傳遞功能的活動時，可能會出現類比訊息只傳送給特定時區中的使用者。</span><span class="sxs-lookup"><span data-stu-id="135e1-227">So, on the initial run of a campaign with region aware delivery enabled, it might appear that the simulation message was sent only to users in a specific time zone.</span></span> <span data-ttu-id="135e1-228">不過，隨著時間傳遞和更多使用者進入範圍中，目標使用者將會增加。</span><span class="sxs-lookup"><span data-stu-id="135e1-228">But, as time passes and more users come into scope, the targeted users will increase.</span></span>