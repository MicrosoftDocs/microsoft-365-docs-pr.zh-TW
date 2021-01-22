---
title: 摘要您的試驗 Microsoft 365 Defender 專案結果
description: 完成計分卡、分析報告結果，並決定如何向前推動，來結束試驗 Microsoft 365 Defender 專案。
keywords: Microsoft 威脅防護試驗，在試驗 Microsoft 威脅防護專案後決定下一步該採取什麼行動、在生產環境中評估 Microsoft 威脅防護後該採取什麼行動、從 Microsoft 威脅防護試驗轉換到部署、網路安全性、進一步持續性威脅、企業安全性、裝置、裝置、身分識別、使用者、資料、應用程式、事件、自動化調查與補救、進一步搜尋
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c8608568301f11a20c940a5ff9f1c205ce6e48f1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930159"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="9e3b0-104">結束並總結您的 Microsoft 365 Defender 試驗</span><span class="sxs-lookup"><span data-stu-id="9e3b0-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9e3b0-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="9e3b0-105">**Applies to:**</span></span>
- <span data-ttu-id="9e3b0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e3b0-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="9e3b0-107">[![規劃](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="9e3b0-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="9e3b0-108">規劃</span><span class="sxs-lookup"><span data-stu-id="9e3b0-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="9e3b0-109">[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="9e3b0-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="9e3b0-110">製備</span><span class="sxs-lookup"><span data-stu-id="9e3b0-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="9e3b0-111">[![類比攻擊](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="9e3b0-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="9e3b0-112">類比攻擊</span><span class="sxs-lookup"><span data-stu-id="9e3b0-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![結束和摘要](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="9e3b0-114">結束和摘要</span><span class="sxs-lookup"><span data-stu-id="9e3b0-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="9e3b0-115">*您目前在這裡！*</span><span class="sxs-lookup"><span data-stu-id="9e3b0-115">*You are here!*</span></span>|


<span data-ttu-id="9e3b0-116">您目前處於結案和摘要階段。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="9e3b0-117">您剛執行進位記憶體指令模擬，在網域控制站上遠端執行程式碼。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="9e3b0-118">您看過 Microsoft Defender for Endpoint 和 Microsoft Defender for Identity 如何偵測並建立惡意活動的警示。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="9e3b0-119">您也會在 Microsoft 365 資訊安全中心入口網站中，看到不同來源的警示與其他關係資訊如何傳遞到單一事件。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="9e3b0-120">遇到這類整合時，SOC 分析師可以進行調查並採取必要動作。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="9e3b0-121">您也建立了進一步搜尋查詢，以識別使用者開啟或儲存附件並依據該查詢建立偵測的內輸入電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="9e3b0-122">所有測試都結束後，程式已經結束。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="9e3b0-123">最後一個輸出結果應為：</span><span class="sxs-lookup"><span data-stu-id="9e3b0-123">The final output should be:</span></span>

- <span data-ttu-id="9e3b0-124">已完成的計分卡</span><span class="sxs-lookup"><span data-stu-id="9e3b0-124">A completed scorecard</span></span>
- <span data-ttu-id="9e3b0-125">試驗結果的詳細報告</span><span class="sxs-lookup"><span data-stu-id="9e3b0-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="9e3b0-126">如何向前移動的決策</span><span class="sxs-lookup"><span data-stu-id="9e3b0-126">A decision on how to move forward</span></span>

<span data-ttu-id="9e3b0-127">將最終輸出結果報告呈現給內部專案關係 (，這是您于) 和 Microsoft[](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval)連絡人在準備階段時所識別的。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="9e3b0-128">如此一來，可確保您有任何意見可用來改善產品與檔。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="9e3b0-129">希望您喜歡這項模擬。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="9e3b0-130">開始在組織中大規模實施您學習到的資訊，以充分使用整合式安全性解決方案。</span><span class="sxs-lookup"><span data-stu-id="9e3b0-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="9e3b0-131">下一步</span><span class="sxs-lookup"><span data-stu-id="9e3b0-131">Next step</span></span>
<span data-ttu-id="9e3b0-132">透過下列互動式指南深入瞭解 Microsoft 365 Defender 基礎：</span><span class="sxs-lookup"><span data-stu-id="9e3b0-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="9e3b0-133">使用 Microsoft Defender for Office 365 保護貴組織</span><span class="sxs-lookup"><span data-stu-id="9e3b0-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="9e3b0-134">使用 Microsoft Defender for Identity 偵測可疑活動和潛在攻擊</span><span class="sxs-lookup"><span data-stu-id="9e3b0-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="9e3b0-135">使用 Microsoft Cloud App 安全性偵測威脅及管理警示</span><span class="sxs-lookup"><span data-stu-id="9e3b0-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="9e3b0-136">使用 Microsoft Defender for Endpoint 調查並補救威脅</span><span class="sxs-lookup"><span data-stu-id="9e3b0-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
