---
title: 摘要示範 Microsoft 365 Defender 專案結果
description: 完成您的試驗 Microsoft 365 Defender 專案，方法是完成計分卡、分析報表結果，以及決定如何向前移動。
keywords: Microsoft 365 Defender 試驗，決定在試驗 Microsoft 365 Defender 專案之後要執行的工作、在生產中評估 Microsoft 365 Defender 後要執行的工作、從 Microsoft 365 Defender 試驗轉換為部署、網路安全性、高級持續性威脅、企業安全性、裝置、裝置、自動調查和修正，以及高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 64cdb37b64780a651b2689e68e21c5a385df5ba9
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457956"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="f57b9-104">關閉及摘要您的 Microsoft 365 Defender 試驗</span><span class="sxs-lookup"><span data-stu-id="f57b9-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f57b9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f57b9-105">**Applies to:**</span></span>
- <span data-ttu-id="f57b9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f57b9-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="f57b9-107">[![規劃](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="f57b9-107">[![Planning](../../media/phase-diagrams/1-planning.png)](m365d-pilot-plan.md)</span></span><br/>[<span data-ttu-id="f57b9-108">規劃</span><span class="sxs-lookup"><span data-stu-id="f57b9-108">Planning</span></span>](m365d-pilot-plan.md) |<span data-ttu-id="f57b9-109">[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="f57b9-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="f57b9-110">製備</span><span class="sxs-lookup"><span data-stu-id="f57b9-110">Preparation</span></span>](prepare-m365d-eval.md) | <span data-ttu-id="f57b9-111">[![類比攻擊](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="f57b9-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](m365d-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="f57b9-112">類比攻擊</span><span class="sxs-lookup"><span data-stu-id="f57b9-112">Simulate attack</span></span>](m365d-pilot-simulate.md) | ![結束和摘要](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="f57b9-114">結束和摘要</span><span class="sxs-lookup"><span data-stu-id="f57b9-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="f57b9-115">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="f57b9-115">*You are here!*</span></span>|


<span data-ttu-id="f57b9-116">您目前正在結束和摘要階段。</span><span class="sxs-lookup"><span data-stu-id="f57b9-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="f57b9-117">您已執行的是僅限記憶體的高級攻擊模擬，可在網域控制站上遠端執行程式碼。</span><span class="sxs-lookup"><span data-stu-id="f57b9-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="f57b9-118">您已瞭解 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 偵測，以及如何在 stealthy 惡意活動上建立警示。</span><span class="sxs-lookup"><span data-stu-id="f57b9-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="f57b9-119">您也瞭解如何將不同來源的警示，與其他上下文資訊一起傳遞到 Microsoft 365 安全性中心入口網站中的單一事件。</span><span class="sxs-lookup"><span data-stu-id="f57b9-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="f57b9-120">遇到這類整合，可讓 SOC 分析員調查並採取必要的動作。</span><span class="sxs-lookup"><span data-stu-id="f57b9-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="f57b9-121">您也已經建立高級搜尋查詢，識別輸入電子郵件，使用者已開啟或儲存附件，並根據該查詢建立偵測。</span><span class="sxs-lookup"><span data-stu-id="f57b9-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="f57b9-122">所有測試結束之後，您已到達程式的結束。</span><span class="sxs-lookup"><span data-stu-id="f57b9-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="f57b9-123">最後一個輸出應該是：</span><span class="sxs-lookup"><span data-stu-id="f57b9-123">The final output should be:</span></span>

- <span data-ttu-id="f57b9-124">完成計分卡</span><span class="sxs-lookup"><span data-stu-id="f57b9-124">A completed scorecard</span></span>
- <span data-ttu-id="f57b9-125">試驗結果的詳細報告</span><span class="sxs-lookup"><span data-stu-id="f57b9-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="f57b9-126">如何繼續進行決策</span><span class="sxs-lookup"><span data-stu-id="f57b9-126">A decision on how to move forward</span></span>

<span data-ttu-id="f57b9-127">從您的最後一個輸出中，向內部的專案關係人呈現報表，以供您在 [準備](./prepare-m365d-eval.md) 階段) 和 Microsoft 連絡人中識別 (。</span><span class="sxs-lookup"><span data-stu-id="f57b9-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](./prepare-m365d-eval.md) phase) and Microsoft contacts.</span></span> <span data-ttu-id="f57b9-128">這類工作可確保任何意見反應都可以用來改善產品及檔。</span><span class="sxs-lookup"><span data-stu-id="f57b9-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="f57b9-129">我們希望您可以享受這種模擬。</span><span class="sxs-lookup"><span data-stu-id="f57b9-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="f57b9-130">開始執行您在組織中較大規模所學的專案，以充分利用整合安全性解決方案。</span><span class="sxs-lookup"><span data-stu-id="f57b9-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="f57b9-131">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f57b9-131">Next step</span></span>
<span data-ttu-id="f57b9-132">透過下列互動式指南深入瞭解 Microsoft 365 Defender 的支柱：</span><span class="sxs-lookup"><span data-stu-id="f57b9-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="f57b9-133">使用 Microsoft Defender Office 365 來保護您的組織</span><span class="sxs-lookup"><span data-stu-id="f57b9-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="f57b9-134">使用適用於身分識別的 Microsoft Defender 偵測可疑活動和潛在攻擊</span><span class="sxs-lookup"><span data-stu-id="f57b9-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="f57b9-135">偵測威脅並使用 Microsoft Cloud App Security 管理提醒</span><span class="sxs-lookup"><span data-stu-id="f57b9-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="f57b9-136">使用 Microsoft Defender for Endpoint 調查和修正威脅</span><span class="sxs-lookup"><span data-stu-id="f57b9-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)