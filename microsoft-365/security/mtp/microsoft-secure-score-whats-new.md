---
title: Microsoft 安全分數的新增功能
description: 說明 Microsoft 365 安全性中心中的 Microsoft 安全分數發生的新變更。
keywords: Microsoft 安全分數， 安全分數， Office 365 安全分數， Microsoft 安全性分數， microsoft 365 資訊安全中心
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 039ec1c3f9b0ba233f950d11b9d58be341b28121
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930591"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="e4928-104">Microsoft 安全分數的新增功能</span><span class="sxs-lookup"><span data-stu-id="e4928-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e4928-105">為了讓 Microsoft Secure Score 更代表您的安全性工作，我們做了一些變更。</span><span class="sxs-lookup"><span data-stu-id="e4928-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="e4928-106">若要瞭解已規劃的變更，請參閱 [Microsoft 安全分數將提供哪些專案？](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="e4928-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

<span data-ttu-id="e4928-107">您可以在 Microsoft https://security.microsoft.com/securescore [365](overview-security-center.md)資訊安全中心找到 Microsoft 安全分數。</span><span class="sxs-lookup"><span data-stu-id="e4928-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="january-2021"></a><span data-ttu-id="e4928-108">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="e4928-108">January 2021</span></span>

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a><span data-ttu-id="e4928-109">新增我們針對 Microsoft Teams 的第一個安全性建議</span><span class="sxs-lookup"><span data-stu-id="e4928-109">Added our first security recommendation for Microsoft Teams</span></span>

<span data-ttu-id="e4928-110">Microsoft Teams 客戶會看到「限制匿名使用者加入會議」，做為安全分數中的新改進動作。</span><span class="sxs-lookup"><span data-stu-id="e4928-110">Microsoft Teams customers will see "Restrict anonymous users from joining meetings" as a new improvement action in Secure Score.</span></span>

## <a name="december-2020"></a><span data-ttu-id="e4928-111">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="e4928-111">December 2020</span></span>

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="e4928-112">針對 Microsoft Defender for Endpoint 新增六個帳戶相關改進動作 (Microsoft Defender ATP) ：</span><span class="sxs-lookup"><span data-stu-id="e4928-112">Added six accounts-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="e4928-113">將密碼長度最小為 14 個字元以上</span><span class="sxs-lookup"><span data-stu-id="e4928-113">Set 'Minimum password length' to '14 or more characters'</span></span>
- <span data-ttu-id="e4928-114">將強制密碼歷程記錄設定為 (24) ></span><span class="sxs-lookup"><span data-stu-id="e4928-114">Set 'Enforce password history' to '24 or more password(s)'</span></span>
- <span data-ttu-id="e4928-115">將密碼年齡上限設定為 60 天以下，但不要設定為 0</span><span class="sxs-lookup"><span data-stu-id="e4928-115">Set 'Maximum password age' to '60 or fewer days, but not 0'</span></span>
- <span data-ttu-id="e4928-116">將 '最低密碼年齡' 設定為 '1 天或 (天) '</span><span class="sxs-lookup"><span data-stu-id="e4928-116">Set 'Minimum password age' to '1 or more day(s)'</span></span>
- <span data-ttu-id="e4928-117">停用內建的系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="e4928-117">Disable the built-in Administrator account</span></span>
- <span data-ttu-id="e4928-118">停用內建的來賓帳戶</span><span class="sxs-lookup"><span data-stu-id="e4928-118">Disable the built-in Guest account</span></span>

## <a name="november-2020"></a><span data-ttu-id="e4928-119">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="e4928-119">November 2020</span></span>

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a><span data-ttu-id="e4928-120">已透過安全分數移除建立 ServiceNow 票證的能力</span><span class="sxs-lookup"><span data-stu-id="e4928-120">Removed the ability to create ServiceNow tickets through Secure Score</span></span> 

<span data-ttu-id="e4928-121">不再提供透過安全分數建立 ServiceNow 票證的能力> **共用服務視窗** 。</span><span class="sxs-lookup"><span data-stu-id="e4928-121">The ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** is no longer available.</span></span> <span data-ttu-id="e4928-122">感謝您的意見和持續支援，我們決定接下來的步驟。</span><span class="sxs-lookup"><span data-stu-id="e4928-122">Thank you for your feedback and continued support while we determine next steps.</span></span>

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="e4928-123">針對 Microsoft Defender for Endpoint (先前是 Microsoft Defender ATP 的三個服務相關改進) ：</span><span class="sxs-lookup"><span data-stu-id="e4928-123">Added three services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="e4928-124">修正未標出之 Windows 服務的服務路徑</span><span class="sxs-lookup"><span data-stu-id="e4928-124">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="e4928-125">將服務可執行路徑變更為一般受保護的位置</span><span class="sxs-lookup"><span data-stu-id="e4928-125">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="e4928-126">變更服務帳戶以避免 Windows 登錄中的緩存密碼</span><span class="sxs-lookup"><span data-stu-id="e4928-126">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="e4928-127">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="e4928-127">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e4928-128">移除與 Microsoft Defender for Endpoint 相關的改進動作</span><span class="sxs-lookup"><span data-stu-id="e4928-128">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="e4928-129">將 Microsoft Defender SmartScreen Windows 市集應用程式內容檢查設為警告</span><span class="sxs-lookup"><span data-stu-id="e4928-129">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="e4928-130">2020年 8月</span><span class="sxs-lookup"><span data-stu-id="e4928-130">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="e4928-131">Azure Active Directory 的更新改進動作</span><span class="sxs-lookup"><span data-stu-id="e4928-131">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="e4928-132">啟用封鎖舊版驗證的策略</span><span class="sxs-lookup"><span data-stu-id="e4928-132">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="e4928-133">與身分識別安全分數和圖形 API 不相容</span><span class="sxs-lookup"><span data-stu-id="e4928-133">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="e4928-134">在最新發佈的 Microsoft 安全分數中，已推出改良的計分模型。</span><span class="sxs-lookup"><span data-stu-id="e4928-134">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="e4928-135">這些變更允許您以更有彈性且更精確的方式查看安全性工作。</span><span class="sxs-lookup"><span data-stu-id="e4928-135">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="e4928-136">不過，這些更新已讓 Microsoft 安全分數暫時與身分識別安全分數和圖形 API 不相容。</span><span class="sxs-lookup"><span data-stu-id="e4928-136">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="e4928-137">身分識別安全分數和圖形 API 會一同採用新的計分模型。</span><span class="sxs-lookup"><span data-stu-id="e4928-137">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="e4928-138">在此之前，客戶會看到 Microsoft 安全分數、身分識別安全分數和圖形 API 報告的成績有差異。</span><span class="sxs-lookup"><span data-stu-id="e4928-138">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="e4928-139">對於造成不便，我們深感抱歉，並且正努力確保未來這些體驗能更相容。</span><span class="sxs-lookup"><span data-stu-id="e4928-139">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="e4928-140">已更新改進動作</span><span class="sxs-lookup"><span data-stu-id="e4928-140">Updated improvement actions</span></span>

- <span data-ttu-id="e4928-141">已新增 Azure Active Directory 改進動作</span><span class="sxs-lookup"><span data-stu-id="e4928-141">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="e4928-142">已針對身分識別改進動作新增 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e4928-142">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="e4928-143">支援 Microsoft Defender 的端點 [威脅&管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全性建議</span><span class="sxs-lookup"><span data-stu-id="e4928-143">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="e4928-144">現在提供由 TVM 提供的所有已發行安全性建議</span><span class="sxs-lookup"><span data-stu-id="e4928-144">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="e4928-145">更新的介面和功能</span><span class="sxs-lookup"><span data-stu-id="e4928-145">Updated interface and functionality</span></span>

* <span data-ttu-id="e4928-146">C們所有新的計量和趨勢視圖，以及潛在客戶層級討論</span><span class="sxs-lookup"><span data-stu-id="e4928-146">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="e4928-147">追蹤和基準分數的新功能</span><span class="sxs-lookup"><span data-stu-id="e4928-147">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="e4928-148">針對分數回歸進行更好的追蹤及理解</span><span class="sxs-lookup"><span data-stu-id="e4928-148">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="e4928-149">篩選、標記、搜尋和分組您的改進動作</span><span class="sxs-lookup"><span data-stu-id="e4928-149">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="e4928-150">使用分數預測和計畫的行動來達成您的未來目標</span><span class="sxs-lookup"><span data-stu-id="e4928-150">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="e4928-151">以及更多功能！</span><span class="sxs-lookup"><span data-stu-id="e4928-151">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="e4928-152">我們想知道您的想法</span><span class="sxs-lookup"><span data-stu-id="e4928-152">We want to hear from you</span></span>

<span data-ttu-id="e4928-153">如有任何問題，請張貼在安全性、隱私權和合規性& [告訴我們](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。</span><span class="sxs-lookup"><span data-stu-id="e4928-153">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="e4928-154">我們正在監控社群，並且會為您提供協助。</span><span class="sxs-lookup"><span data-stu-id="e4928-154">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="e4928-155">相關資源</span><span class="sxs-lookup"><span data-stu-id="e4928-155">Related resources</span></span>

- [<span data-ttu-id="e4928-156">評估您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="e4928-156">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="e4928-157">追蹤您的 Microsoft 安全分數記錄並達成目標</span><span class="sxs-lookup"><span data-stu-id="e4928-157">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="e4928-158">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="e4928-158">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
