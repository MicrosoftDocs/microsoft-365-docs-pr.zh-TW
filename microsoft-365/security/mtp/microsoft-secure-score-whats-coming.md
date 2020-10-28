---
title: Microsoft 安全分數
description: 說明 Microsoft 365 security center 中的 Microsoft 安全評分的新變更。
keywords: microsoft 安全分數、安全分數、office 365 安全分數、microsoft security 得分、microsoft 365 安全性中心、改進動作
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779245"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="521a2-104">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="521a2-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="521a2-105">我們在近期進行一些變更，讓 [Microsoft 安全評分](microsoft-secure-score.md) 成為安全狀況的更好代表，並提高可用性。</span><span class="sxs-lookup"><span data-stu-id="521a2-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="521a2-106">您的分數和可能的最大分數可能會有所變更。</span><span class="sxs-lookup"><span data-stu-id="521a2-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="521a2-107">建議變更</span><span class="sxs-lookup"><span data-stu-id="521a2-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="521a2-108">2020年11月</span><span class="sxs-lookup"><span data-stu-id="521a2-108">November 2020</span></span>

<span data-ttu-id="521a2-109">移到 **> ServiceNow** 中，移除透過安全分數建立 ServiceNow 入場券的功能。</span><span class="sxs-lookup"><span data-stu-id="521a2-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="521a2-110">ServiceNow 連接器的預覽期間結束。</span><span class="sxs-lookup"><span data-stu-id="521a2-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="521a2-111">2020的結尾將不再提供這項功能。</span><span class="sxs-lookup"><span data-stu-id="521a2-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="521a2-112">感謝您的意見反應，並在我們決定接下來的步驟時繼續支援。</span><span class="sxs-lookup"><span data-stu-id="521a2-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="521a2-113">在先前的 Microsoft Defender ATP) 中，新增與 Microsoft Defender for Endpoint (相關的18個改進動作：</span><span class="sxs-lookup"><span data-stu-id="521a2-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="521a2-114">攻擊面減少 (ASR) 相關建議：</span><span class="sxs-lookup"><span data-stu-id="521a2-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="521a2-115">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="521a2-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="521a2-116">封鎖所有 Office 應用程式以建立子流程</span><span class="sxs-lookup"><span data-stu-id="521a2-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="521a2-117">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="521a2-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="521a2-118">封鎖 Office 應用程式將程式碼注入其他程式</span><span class="sxs-lookup"><span data-stu-id="521a2-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="521a2-119">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="521a2-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="521a2-120">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="521a2-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="521a2-121">封鎖 Office 宏的 WIN32 API 呼叫</span><span class="sxs-lookup"><span data-stu-id="521a2-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="521a2-122">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="521a2-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="521a2-123">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="521a2-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="521a2-124">封鎖從 Windows local security 機關子系統進行的認證竊取 ( # A0) </span><span class="sxs-lookup"><span data-stu-id="521a2-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="521a2-125">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="521a2-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="521a2-126">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="521a2-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="521a2-127">封鎖 Office communication application 建立子流程</span><span class="sxs-lookup"><span data-stu-id="521a2-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="521a2-128">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="521a2-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="521a2-129">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="521a2-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="521a2-130">服務相關建議：</span><span class="sxs-lookup"><span data-stu-id="521a2-130">Services related recommendations:</span></span>
- <span data-ttu-id="521a2-131">修正 Windows 服務的未加引號服務路徑</span><span class="sxs-lookup"><span data-stu-id="521a2-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="521a2-132">將服務可執行路徑變更為一般受保護的位置</span><span class="sxs-lookup"><span data-stu-id="521a2-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="521a2-133">變更服務帳戶以避免在 windows 登錄中快取密碼</span><span class="sxs-lookup"><span data-stu-id="521a2-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="521a2-134">相關資源</span><span class="sxs-lookup"><span data-stu-id="521a2-134">Related resources</span></span>

- [<span data-ttu-id="521a2-135">Microsoft 安全評分概述</span><span class="sxs-lookup"><span data-stu-id="521a2-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="521a2-136">評估您的安全性狀態</span><span class="sxs-lookup"><span data-stu-id="521a2-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="521a2-137">追蹤您的 Microsoft 安全分數記錄並符合目標</span><span class="sxs-lookup"><span data-stu-id="521a2-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="521a2-138">新功能</span><span class="sxs-lookup"><span data-stu-id="521a2-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
