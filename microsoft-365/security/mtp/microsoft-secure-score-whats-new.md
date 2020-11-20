---
title: Microsoft 安全分數的新功能
description: 說明 microsoft 365 security center 中的 Microsoft Secure 得分發生了哪些新的變更。
keywords: microsoft 安全分數，安全分數，office 365 安全分數，microsoft security 得分，microsoft 365 security center
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6d1358da465bd7e31ca7b234f140aa8e48bb7508
ms.sourcegitcommit: aa8d2de6ffac0157fffd14d0ea7f51ef0c287607
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "49373992"
---
# <a name="whats-new-in-microsoft-secure-score"></a><span data-ttu-id="5c430-104">Microsoft 安全分數的新功能</span><span class="sxs-lookup"><span data-stu-id="5c430-104">What's new in Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5c430-105">若要讓 Microsoft 安全評分為您安全性狀況的更佳代表，我們進行了一些變更。</span><span class="sxs-lookup"><span data-stu-id="5c430-105">To make Microsoft Secure Score a better representative of your security posture, we have made some changes.</span></span> <span data-ttu-id="5c430-106">若要深入瞭解規劃的變更，請參閱 [Microsoft Secure 得分中的內容？](microsoft-secure-score-whats-coming.md)。</span><span class="sxs-lookup"><span data-stu-id="5c430-106">To learn about planned changes, see [What's coming in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).</span></span>

<span data-ttu-id="5c430-107">Microsoft Secure 得分可在 https://security.microsoft.com/securescore [microsoft 365 的安全性中心](overview-security-center.md)找到。</span><span class="sxs-lookup"><span data-stu-id="5c430-107">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="november-2020"></a><span data-ttu-id="5c430-108">2020年11月</span><span class="sxs-lookup"><span data-stu-id="5c430-108">November 2020</span></span>

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a><span data-ttu-id="5c430-109">在先前的 Microsoft Defender ATP) 中，為 Microsoft Defender for Endpoint (新增3個與服務相關的改進動作：</span><span class="sxs-lookup"><span data-stu-id="5c430-109">Added 3 services-related improvement actions for Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

- <span data-ttu-id="5c430-110">修正 Windows 服務的未加引號服務路徑</span><span class="sxs-lookup"><span data-stu-id="5c430-110">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="5c430-111">將服務可執行路徑變更為一般受保護的位置</span><span class="sxs-lookup"><span data-stu-id="5c430-111">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="5c430-112">變更服務帳戶以避免在 windows 登錄中快取密碼</span><span class="sxs-lookup"><span data-stu-id="5c430-112">Change service account to avoid cached password in windows registry</span></span>

## <a name="october-2020"></a><span data-ttu-id="5c430-113">2020 年 10 月</span><span class="sxs-lookup"><span data-stu-id="5c430-113">October 2020</span></span>

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="5c430-114">移除與 Microsoft Defender for Endpoint 相關的改進動作</span><span class="sxs-lookup"><span data-stu-id="5c430-114">Remove improvement action related to Microsoft Defender for Endpoint</span></span>

- <span data-ttu-id="5c430-115">設定 Microsoft Defender SmartScreen Windows 應用程式 web 內容檢查以警告</span><span class="sxs-lookup"><span data-stu-id="5c430-115">Set Microsoft Defender SmartScreen Windows Store app web content checking to warn</span></span>

## <a name="august-2020"></a><span data-ttu-id="5c430-116">2020年 8月</span><span class="sxs-lookup"><span data-stu-id="5c430-116">August 2020</span></span>

### <a name="updated-improvement-action-for-azure-active-directory"></a><span data-ttu-id="5c430-117">Azure Active Directory 的更新改進動作</span><span class="sxs-lookup"><span data-stu-id="5c430-117">Updated improvement action for Azure Active Directory</span></span>

- <span data-ttu-id="5c430-118">啟用原則以封鎖舊版驗證</span><span class="sxs-lookup"><span data-stu-id="5c430-118">Enable policy to block legacy authentication</span></span>

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a><span data-ttu-id="5c430-119">不相容身分識別安全分數與圖形 API</span><span class="sxs-lookup"><span data-stu-id="5c430-119">Incompatibility with Identity Secure Score and Graph API</span></span>

<span data-ttu-id="5c430-120">在最近發行的 Microsoft Secure 得分中，已發佈一個已改進的計分模型。</span><span class="sxs-lookup"><span data-stu-id="5c430-120">In the recent release of Microsoft Secure Score, an improved scoring model has been released.</span></span> <span data-ttu-id="5c430-121">這些變更可讓您更靈活且準確的安全性狀況的觀點。</span><span class="sxs-lookup"><span data-stu-id="5c430-121">These changes allow for a more flexible and accurate view of your security posture.</span></span> <span data-ttu-id="5c430-122">不過，這些更新已讓 Microsoft 安全分數暫時不相容身分識別安全分數和圖形 API。</span><span class="sxs-lookup"><span data-stu-id="5c430-122">However, these updates have made Microsoft Secure Score temporarily incompatible with Identity Secure Score and the Graph API.</span></span>

<span data-ttu-id="5c430-123">在時間內，身分識別安全分數和圖形 API 將採用新的計分模型。</span><span class="sxs-lookup"><span data-stu-id="5c430-123">In time, Identity Secure Score and the Graph API will adopt the new scoring model.</span></span> <span data-ttu-id="5c430-124">在此之前，客戶會看到 Microsoft 安全評分、身分識別安全分數及圖形 API 所報告的分數差異。</span><span class="sxs-lookup"><span data-stu-id="5c430-124">Until then, customers will see differences in the scores reported by Microsoft Secure Score, Identity Secure Score, and the Graph API.</span></span> <span data-ttu-id="5c430-125">我們對這項不便的任何不便深表歉意，而且正在運作，以確保未來的體驗更具相容性。</span><span class="sxs-lookup"><span data-stu-id="5c430-125">We apologize for any inconvenience this causes, and are working to ensure these experiences are more compatible in the future.</span></span>

## <a name="updated-improvement-actions"></a><span data-ttu-id="5c430-126">更新的改進動作</span><span class="sxs-lookup"><span data-stu-id="5c430-126">Updated improvement actions</span></span>

- <span data-ttu-id="5c430-127">新增 Azure Active Directory 改進動作</span><span class="sxs-lookup"><span data-stu-id="5c430-127">Added Azure Active Directory improvement actions</span></span>
- <span data-ttu-id="5c430-128">新增 Microsoft Defender 以進行身分識別改進動作</span><span class="sxs-lookup"><span data-stu-id="5c430-128">Added Microsoft Defender for Identity improvement actions</span></span>
- <span data-ttu-id="5c430-129">支援 Microsoft Defender for Endpoint [威脅 & 弱點管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 安全性建議</span><span class="sxs-lookup"><span data-stu-id="5c430-129">Support for Microsoft Defender for Endpoint [Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) security recommendations</span></span>
    - <span data-ttu-id="5c430-130">現在提供 TVM 提供的所有發行安全性建議</span><span class="sxs-lookup"><span data-stu-id="5c430-130">All released security recommendations supplied by TVM are now available</span></span>

## <a name="updated-interface-and-functionality"></a><span data-ttu-id="5c430-131">更新的介面及功能</span><span class="sxs-lookup"><span data-stu-id="5c430-131">Updated interface and functionality</span></span>

* <span data-ttu-id="5c430-132">CISO 和潛在客戶層級討論的所有新的計量和趨勢視圖</span><span class="sxs-lookup"><span data-stu-id="5c430-132">All new metrics and trends views for CISO and lead level discussions</span></span>
* <span data-ttu-id="5c430-133">追蹤和基準成績的新方法</span><span class="sxs-lookup"><span data-stu-id="5c430-133">New ways to track and benchmark your score</span></span>
* <span data-ttu-id="5c430-134">更好地追蹤和瞭解分數回歸</span><span class="sxs-lookup"><span data-stu-id="5c430-134">Better tracking and understanding for score regressions</span></span>
* <span data-ttu-id="5c430-135">篩選、標記、搜尋及群組您的改善動作</span><span class="sxs-lookup"><span data-stu-id="5c430-135">Filter, tag, search, and group your improvement actions</span></span>
* <span data-ttu-id="5c430-136">使用分數預測和規劃的動作來管理您的未來目標</span><span class="sxs-lookup"><span data-stu-id="5c430-136">Manage towards your future goals using score projections and planned actions</span></span>
* <span data-ttu-id="5c430-137">還有更多！</span><span class="sxs-lookup"><span data-stu-id="5c430-137">And more!</span></span>

## <a name="we-want-to-hear-from-you"></a><span data-ttu-id="5c430-138">我們想要聽到您的來信</span><span class="sxs-lookup"><span data-stu-id="5c430-138">We want to hear from you</span></span>

<span data-ttu-id="5c430-139">如果您有任何問題，請在 [安全性、隱私權 & 合規性](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 社區中發佈以告知我們。</span><span class="sxs-lookup"><span data-stu-id="5c430-139">If you have any issues, let us know by posting in the [Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) community.</span></span> <span data-ttu-id="5c430-140">我們正在監視社區，並會提供協助。</span><span class="sxs-lookup"><span data-stu-id="5c430-140">We're monitoring the community and will provide help.</span></span>

## <a name="related-resources"></a><span data-ttu-id="5c430-141">相關資源</span><span class="sxs-lookup"><span data-stu-id="5c430-141">Related resources</span></span>

- [<span data-ttu-id="5c430-142">評估您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="5c430-142">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="5c430-143">追蹤您的 Microsoft 安全分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="5c430-143">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="5c430-144">即將推出的功能</span><span class="sxs-lookup"><span data-stu-id="5c430-144">What's coming</span></span>](microsoft-secure-score-whats-coming.md)
