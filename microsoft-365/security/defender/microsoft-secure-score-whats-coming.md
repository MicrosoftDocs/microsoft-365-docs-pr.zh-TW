---
title: Microsoft 安全分數
description: 說明 Microsoft 365 security center 中的 Microsoft 安全評分的新變更。
keywords: microsoft 安全分數、安全分數、office 365 安全分數、microsoft security 得分、microsoft 365 安全性中心、改進動作
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 910eb16ad33555ca61875a346b50cea7e63b2220
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338550"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="cbf91-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="cbf91-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cbf91-105">您可以 https://security.microsoft.com/securescore 在「 [Microsoft 365 安全性中心](overview-security-center.md)」找到 Microsoft Secure 得分。</span><span class="sxs-lookup"><span data-stu-id="cbf91-105">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="cbf91-106">建議變更</span><span class="sxs-lookup"><span data-stu-id="cbf91-106">Proposed changes</span></span>

<span data-ttu-id="cbf91-107">我們在近期進行一些變更，讓 [Microsoft 安全評分](microsoft-secure-score.md) 成為安全狀況的更好代表，並提高可用性。</span><span class="sxs-lookup"><span data-stu-id="cbf91-107">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="cbf91-108">您的分數和可能的最大分數可能會有所變更。</span><span class="sxs-lookup"><span data-stu-id="cbf91-108">Your score and the maximum possible score may change.</span></span>

### <a name="july-2021"></a><span data-ttu-id="cbf91-109">2021年7月</span><span class="sxs-lookup"><span data-stu-id="cbf91-109">July 2021</span></span>

#### <a name="add-improvement-action-related-to-microsoft-teams"></a><span data-ttu-id="cbf91-110">新增與 Microsoft Teams 相關的改進動作</span><span class="sxs-lookup"><span data-stu-id="cbf91-110">Add improvement action related to Microsoft Teams</span></span>

- <span data-ttu-id="cbf91-111">限制撥入使用者繞過會議會議廳。</span><span class="sxs-lookup"><span data-stu-id="cbf91-111">Restrict dial-in users from bypassing a meeting lobby.</span></span>
- <span data-ttu-id="cbf91-112">限制外部參與者在 Teams 會議中擁有控制權。</span><span class="sxs-lookup"><span data-stu-id="cbf91-112">Limit external participants from having control in a Teams meeting.</span></span>
- <span data-ttu-id="cbf91-113">限制匿名使用者開始 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="cbf91-113">Restrict anonymous users from starting Teams meetings.</span></span>
- <span data-ttu-id="cbf91-114">需要 Teams 會議中設定大廳。</span><span class="sxs-lookup"><span data-stu-id="cbf91-114">Require lobbies to be set up for Teams meetings.</span></span>
- <span data-ttu-id="cbf91-115">設定允許在 Teams 會議中出現的使用者。</span><span class="sxs-lookup"><span data-stu-id="cbf91-115">Configure which users are allowed to be present in Teams meetings.</span></span>

#### <a name="add-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="cbf91-116">新增與 Microsoft Defender for Endpoint 相關的改進動作</span><span class="sxs-lookup"><span data-stu-id="cbf91-116">Add improvement action related to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="cbf91-117">修正 Microsoft Defender for macOS 的端點感應器資料收集</span><span class="sxs-lookup"><span data-stu-id="cbf91-117">Fix Microsoft Defender for Endpoint sensor data collection for macOS</span></span>
- <span data-ttu-id="cbf91-118">修正 Microsoft Defender 對 macOS 的 Endpoint 受損通訊</span><span class="sxs-lookup"><span data-stu-id="cbf91-118">Fix Microsoft Defender for Endpoint impaired communications for macOS</span></span>
- <span data-ttu-id="cbf91-119">設定 macOS 中的最小密碼長度為15或以上的字元</span><span class="sxs-lookup"><span data-stu-id="cbf91-119">Set minimum password length to 15 or more characters in macOS</span></span>
- <span data-ttu-id="cbf91-120">在 macOS 中將「強制密碼史 ' 設定為「24或以上的密碼 (s) 」</span><span class="sxs-lookup"><span data-stu-id="cbf91-120">Set 'Enforce password history' to '24 or more password(s)' in macOS</span></span>
- <span data-ttu-id="cbf91-121">將「密碼最長存留期 ' 設定為 ' 90 或更少的天數，但在 macOS 中不是 0 '</span><span class="sxs-lookup"><span data-stu-id="cbf91-121">Set 'Maximum password age' to '90 or fewer days, but not 0' in macOS</span></span>
- <span data-ttu-id="cbf91-122">將帳戶鎖定閥值設定為5或更低的 macOS</span><span class="sxs-lookup"><span data-stu-id="cbf91-122">Set account lockout threshold to 5 or lower in macOS</span></span>
- <span data-ttu-id="cbf91-123">開啟 macOS 上的防火牆</span><span class="sxs-lookup"><span data-stu-id="cbf91-123">Turn on Firewall on macOS</span></span>
- <span data-ttu-id="cbf91-124">啟用閘道管理員</span><span class="sxs-lookup"><span data-stu-id="cbf91-124">Enable Gatekeeper</span></span>
- <span data-ttu-id="cbf91-125">啟用系統完整性保護 (SIP) </span><span class="sxs-lookup"><span data-stu-id="cbf91-125">Enable System Integrity Protection (SIP)</span></span>
- <span data-ttu-id="cbf91-126">啟用 FileVault 磁片加密</span><span class="sxs-lookup"><span data-stu-id="cbf91-126">Enable FileVault Disk Encryption</span></span>
- <span data-ttu-id="cbf91-127">將畫面設定為在 macOS 中的屏保程式開始時鎖定</span><span class="sxs-lookup"><span data-stu-id="cbf91-127">Set screen to lock when screensaver starts in macOS</span></span>
- <span data-ttu-id="cbf91-128">確定屏保程式已設定為在 macOS 20 分鐘以內開始</span><span class="sxs-lookup"><span data-stu-id="cbf91-128">Ensure screensaver is set to start in 20 minutes or less in macOS</span></span>
- <span data-ttu-id="cbf91-129">安全主資料夾</span><span class="sxs-lookup"><span data-stu-id="cbf91-129">Secure Home Folders</span></span>
- <span data-ttu-id="cbf91-130">開啟 macOS 的 Microsoft Defender 防毒軟體即時保護</span><span class="sxs-lookup"><span data-stu-id="cbf91-130">Turn on Microsoft Defender Antivirus real-time protection for macOS</span></span>
- <span data-ttu-id="cbf91-131">在封鎖模式中開啟 macOS 的 Microsoft Defender 防毒軟體 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="cbf91-131">Turn on Microsoft Defender Antivirus PUA protection in block mode for macOS</span></span>
- <span data-ttu-id="cbf91-132">為 macOS 啟用 Microsoft Defender 防毒軟體雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="cbf91-132">Enable Microsoft Defender Antivirus cloud-delivered protection for macOS</span></span>
- <span data-ttu-id="cbf91-133">更新 macOS 的 Microsoft Defender 防毒軟體定義</span><span class="sxs-lookup"><span data-stu-id="cbf91-133">Update Microsoft Defender Antivirus definitions for macOS</span></span>
- <span data-ttu-id="cbf91-134">修正 Microsoft Defender for Linux 的 Endpoint 感應器資料收集</span><span class="sxs-lookup"><span data-stu-id="cbf91-134">Fix Microsoft Defender for Endpoint sensor data collection for Linux</span></span>
- <span data-ttu-id="cbf91-135">修正 Microsoft Defender 以取得 Linux 的 Endpoint 受損通訊</span><span class="sxs-lookup"><span data-stu-id="cbf91-135">Fix Microsoft Defender for Endpoint impaired communications for Linux</span></span>
- <span data-ttu-id="cbf91-136">無限制存取帳戶</span><span class="sxs-lookup"><span data-stu-id="cbf91-136">Unrestricted Access Accounts</span></span>
- <span data-ttu-id="cbf91-137">開啟對 Linux Microsoft Defender 防毒軟體即時保護</span><span class="sxs-lookup"><span data-stu-id="cbf91-137">Turn on Microsoft Defender Antivirus real-time protection for Linux</span></span>
- <span data-ttu-id="cbf91-138">開啟 Linux 的封鎖模式中的 Microsoft Defender 防毒軟體 PUA 保護</span><span class="sxs-lookup"><span data-stu-id="cbf91-138">Turn on Microsoft Defender Antivirus PUA protection in block mode for Linux</span></span>
- <span data-ttu-id="cbf91-139">為 Linux 啟用 Microsoft Defender 防毒軟體雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="cbf91-139">Enable Microsoft Defender Antivirus cloud-delivered protection for Linux</span></span>
- <span data-ttu-id="cbf91-140">更新 Linux 的 Microsoft Defender 防毒軟體定義</span><span class="sxs-lookup"><span data-stu-id="cbf91-140">Update Microsoft Defender Antivirus definitions for Linux</span></span>



## <a name="related-resources"></a><span data-ttu-id="cbf91-141">相關資源</span><span class="sxs-lookup"><span data-stu-id="cbf91-141">Related resources</span></span>

- [<span data-ttu-id="cbf91-142">Microsoft 安全評分概述</span><span class="sxs-lookup"><span data-stu-id="cbf91-142">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="cbf91-143">評估您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="cbf91-143">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="cbf91-144">追蹤您的 Microsoft 安全分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="cbf91-144">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="cbf91-145">新功能</span><span class="sxs-lookup"><span data-stu-id="cbf91-145">What's new</span></span>](microsoft-secure-score-whats-new.md)
