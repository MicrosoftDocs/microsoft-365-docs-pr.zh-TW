---
title: Microsoft 安全分數的新功能
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分發生了哪些新的變更。
keywords: microsoft 安全分數，安全分數，office 365 安全分數，microsoft security 得分，microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: 1933ca86f56524b018c322f3b5560250debd0387
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058572"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="80292-104">Microsoft 安全分數的新功能</span><span class="sxs-lookup"><span data-stu-id="80292-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="80292-105">若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。</span><span class="sxs-lookup"><span data-stu-id="80292-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="80292-106">若要深入瞭解規劃的變更，請參閱 [Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)</span><span class="sxs-lookup"><span data-stu-id="80292-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)</span></span>

<span data-ttu-id="80292-107">Microsoft Secure 得分可在 https://security.microsoft.com/securescore [microsoft 365 的安全性中心](overview-security-center.md)找到。</span><span class="sxs-lookup"><span data-stu-id="80292-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>
    
## <a name="february-2021"></a><span data-ttu-id="80292-108">2021 年 2 月</span><span class="sxs-lookup"><span data-stu-id="80292-108">February 2021</span></span>

### <a name="compatibility-with-graph-api"></a><span data-ttu-id="80292-109">與圖形 API 的相容性</span><span class="sxs-lookup"><span data-stu-id="80292-109">Compatibility with Graph API</span></span>

<span data-ttu-id="80292-110">透過 Graph API 傳遞的 Microsoft 安全分數建議，會與您目前在 Microsoft 365 security center 中看到的建議一樣，具有加權效果。</span><span class="sxs-lookup"><span data-stu-id="80292-110">Microsoft Secure Score recommendations delivered via Graph API will look and be weighted the same as the recommendations you currently see in the Microsoft 365 security center.</span></span>

## <a name="january-2021"></a><span data-ttu-id="80292-111">2021 年 1 月</span><span class="sxs-lookup"><span data-stu-id="80292-111">January 2021</span></span>

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a><span data-ttu-id="80292-112">新增 Microsoft 小組的第一個安全性建議</span><span class="sxs-lookup"><span data-stu-id="80292-112">Added our first security recommendation for Microsoft Teams</span></span>

<span data-ttu-id="80292-113">Microsoft 團隊客戶將會看到「限制匿名使用者加入會議」為安全評分的新改進動作。</span><span class="sxs-lookup"><span data-stu-id="80292-113">Microsoft Teams customers will see "Restrict anonymous users from joining meetings" as a new improvement action in Secure Score.</span></span>

## <a name="december-2020"></a><span data-ttu-id="80292-114">2020 年 12 月</span><span class="sxs-lookup"><span data-stu-id="80292-114">December 2020</span></span>

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="80292-115">針對先前的 Microsoft Defender ATP) ，新增了 Microsoft Defender for Endpoint (的六個帳戶相關改進動作：</span><span class="sxs-lookup"><span data-stu-id="80292-115">Added six accounts-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="80292-116">將 ' 密碼長度下限 ' 設定為 ' 14 或以上的字元」</span><span class="sxs-lookup"><span data-stu-id="80292-116">Set 'Minimum password length' to '14 or more characters'</span></span>
- <span data-ttu-id="80292-117">將 ' 強制密碼歷程記錄 ' 設定為 ' 24 或以上的密碼 (s) '</span><span class="sxs-lookup"><span data-stu-id="80292-117">Set 'Enforce password history' to '24 or more password(s)'</span></span>
- <span data-ttu-id="80292-118">將 ' 密碼最長存留期 ' 設定為 ' 60 或更少的天數，但不是 0 '</span><span class="sxs-lookup"><span data-stu-id="80292-118">Set 'Maximum password age' to '60 or fewer days, but not 0'</span></span>
- <span data-ttu-id="80292-119">將 ' 密碼最短保留天數 ' 設定為 ' 1 或以上的 (s) '</span><span class="sxs-lookup"><span data-stu-id="80292-119">Set 'Minimum password age' to '1 or more day(s)'</span></span>
- <span data-ttu-id="80292-120">停用內建管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="80292-120">Disable the built-in Administrator account</span></span>
- <span data-ttu-id="80292-121">停用內建來賓帳戶</span><span class="sxs-lookup"><span data-stu-id="80292-121">Disable the built-in Guest account</span></span>

## <a name="november-2020"></a><span data-ttu-id="80292-122">2020 年 11 月</span><span class="sxs-lookup"><span data-stu-id="80292-122">November 2020</span></span>

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a><span data-ttu-id="80292-123">移除透過安全分數建立 ServiceNow 票證的能力</span><span class="sxs-lookup"><span data-stu-id="80292-123">Removed the ability to create ServiceNow tickets through Secure Score</span></span> 

<span data-ttu-id="80292-124">無法再使用 **> ServiceNow** ，透過安全的分數建立 ServiceNow 入場券的功能。</span><span class="sxs-lookup"><span data-stu-id="80292-124">The ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** is no longer available.</span></span> <span data-ttu-id="80292-125">感謝您的意見反應，並在我們決定接下來的步驟時繼續支援。</span><span class="sxs-lookup"><span data-stu-id="80292-125">Thank you for your feedback and continued support while we determine next steps.</span></span>

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="80292-126">在先前的 Microsoft Defender ATP) 中，新增三項 Microsoft Defender for Endpoint (的服務相關改進動作：</span><span class="sxs-lookup"><span data-stu-id="80292-126">Added three services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="80292-127">修正 Windows 服務的未加引號服務路徑</span><span class="sxs-lookup"><span data-stu-id="80292-127">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="80292-128">將服務可執行路徑變更為一般受保護的位置</span><span class="sxs-lookup"><span data-stu-id="80292-128">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="80292-129">變更服務帳戶以避免在 windows 登錄中快取密碼</span><span class="sxs-lookup"><span data-stu-id="80292-129">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="80292-130">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="80292-130">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="80292-131">移除與 Microsoft Defender for Endpoint 相關的改進動作</span><span class="sxs-lookup"><span data-stu-id="80292-131">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="80292-132">設定 Microsoft Defender SmartScreen Windows 應用程式 web 內容檢查以警告</span><span class="sxs-lookup"><span data-stu-id="80292-132">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="80292-133">2020年 8月</span><span class="sxs-lookup"><span data-stu-id="80292-133">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="80292-134">Azure Active Directory 的更新改進動作</span><span class="sxs-lookup"><span data-stu-id="80292-134">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="80292-135">啟用原則以封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="80292-135">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score"></a><span data-ttu-id="80292-136">不相容身分識別安全分數</span><span class="sxs-lookup"><span data-stu-id="80292-136">Incompatibility with Identity Secure Score</span></span>

<span data-ttu-id="80292-137">在最近發行的 Microsoft Secure 得分中，已發佈一個已改進的計分模型。</span><span class="sxs-lookup"><span data-stu-id="80292-137">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="80292-138">這些變更可讓您更靈活且準確的安全性狀況的觀點。</span><span class="sxs-lookup"><span data-stu-id="80292-138">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="80292-139">不過，這些更新已使 Microsoft 安全分數暫時不相容身分識別安全分數。</span><span class="sxs-lookup"><span data-stu-id="80292-139">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score.</span></span>

<span data-ttu-id="80292-140">在時間內，身分識別安全分數將採用新的計分模型。</span><span class="sxs-lookup"><span data-stu-id="80292-140">In time, Identity Secure Score will adopt the new scoring model.</span></span> <span data-ttu-id="80292-141">在此之前，客戶會看到 Microsoft 安全分數和身分識別安全分數所報告的分數差異。</span><span class="sxs-lookup"><span data-stu-id="80292-141">Until then, customers will see differences in the scores reported by Microsoft Secure Score and the Identity Secure Score.</span></span> <span data-ttu-id="80292-142">我們對這項不便的任何不便深表歉意，而且正在運作，以確保未來的體驗更具相容性。</span><span class="sxs-lookup"><span data-stu-id="80292-142">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="80292-143">更新的改進動作</span><span class="sxs-lookup"><span data-stu-id="80292-143">Updated improvement actions</span></span>

- <span data-ttu-id="80292-144">新增 Azure Active Directory 改進動作</span><span class="sxs-lookup"><span data-stu-id="80292-144">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="80292-145">新增 Microsoft Defender 以進行身分識別改進動作</span><span class="sxs-lookup"><span data-stu-id="80292-145">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="80292-146">支援 Microsoft Defender for Endpoint [威脅 & 弱點管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全性建議</span><span class="sxs-lookup"><span data-stu-id="80292-146">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="80292-147">現在提供 TVM 提供的所有發行安全性建議</span><span class="sxs-lookup"><span data-stu-id="80292-147">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="80292-148">更新的介面及功能</span><span class="sxs-lookup"><span data-stu-id="80292-148">Updated interface and functionality</span></span>

* <span data-ttu-id="80292-149">CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖</span><span class="sxs-lookup"><span data-stu-id="80292-149">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="80292-150">追蹤和基準成績的新方法</span><span class="sxs-lookup"><span data-stu-id="80292-150">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="80292-151">更好地追蹤和瞭解分數回歸</span><span class="sxs-lookup"><span data-stu-id="80292-151">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="80292-152">篩選、標記、搜尋及群組您的改善動作</span><span class="sxs-lookup"><span data-stu-id="80292-152">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="80292-153">使用分數預測和規劃的動作來管理您的未來目標</span><span class="sxs-lookup"><span data-stu-id="80292-153">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="80292-154">還有更多！</span><span class="sxs-lookup"><span data-stu-id="80292-154">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="80292-155">我們想知道您的想法</span><span class="sxs-lookup"><span data-stu-id="80292-155">We want to hear from you</span></span>

<span data-ttu-id="80292-156">如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。</span><span class="sxs-lookup"><span data-stu-id="80292-156">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="80292-157">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="80292-157">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="80292-158">相關資源</span><span class="sxs-lookup"><span data-stu-id="80292-158">Related resources</span></span>

- [<span data-ttu-id="80292-159">評估您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="80292-159">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="80292-160">追蹤您的 Microsoft 安全分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="80292-160">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="80292-161">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="80292-161">What's coming</span></span>](microsoft-secure-score-whats-coming.md)