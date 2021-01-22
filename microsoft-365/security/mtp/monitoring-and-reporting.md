---
title: 監控和查看報告 - 資訊安全中心
description: 說明 Microsoft 365 資訊安全中心如何提供一目了然的保護和安全性狀態摘要。
keywords: Security， malware， Microsoft 365， M365， security center， monitor， report， status
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
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930399"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="9d553-104">在 Microsoft 365 資訊安全中心監控和查看報告</span><span class="sxs-lookup"><span data-stu-id="9d553-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="9d553-105">想要體驗 Microsoft 365 Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="9d553-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9d553-106">您可以在實驗室 [環境中進行評估，](https://aka.ms/mtp-trial-lab) 或在生產 [環境中執行試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="9d553-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="9d553-107">Microsoft 365 安全性中心提供您整個 Microsoft 365 環境的保護和安全性狀態摘要。</span><span class="sxs-lookup"><span data-stu-id="9d553-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="9d553-108">資訊安全中心包含一 **個** 報告區段，其功能包含數張涵蓋數個地區的卡片。</span><span class="sxs-lookup"><span data-stu-id="9d553-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="9d553-109">安全性分析師和系統管理員可以在日常作業中追蹤卡片。</span><span class="sxs-lookup"><span data-stu-id="9d553-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="9d553-110">在向下切入時，卡片會提供詳細的報告，在某些情況下還有管理選項。</span><span class="sxs-lookup"><span data-stu-id="9d553-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="9d553-111">自訂視圖</span><span class="sxs-lookup"><span data-stu-id="9d553-111">Customize views</span></span>

<span data-ttu-id="9d553-112">根據預設，卡片會分組為以下類別：</span><span class="sxs-lookup"><span data-stu-id="9d553-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="9d553-113">[身分證](monitor-and-report-identities.md) - 使用者帳戶和認證</span><span class="sxs-lookup"><span data-stu-id="9d553-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="9d553-114">[資料](monitor-data.md) - 電子郵件和檔內容</span><span class="sxs-lookup"><span data-stu-id="9d553-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="9d553-115">[裝置](monitor-devices.md) - 電腦、行動電話及其他裝置</span><span class="sxs-lookup"><span data-stu-id="9d553-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="9d553-116">[應用程式](monitor-apps.md) - 程式和附加的線上服務</span><span class="sxs-lookup"><span data-stu-id="9d553-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="9d553-117">切換至 **按主題分組**，以重新排列卡片，並分組為下列主題：</span><span class="sxs-lookup"><span data-stu-id="9d553-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="9d553-118">**風險** - 卡片可突顯可能風險的實體，例如帳戶和裝置。</span><span class="sxs-lookup"><span data-stu-id="9d553-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="9d553-119">這些卡片也會突顯可能的風險來源，例如新的威脅行銷活動和特殊許可權的雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="9d553-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="9d553-120">**偵測趨勢** - 卡片可強調新的威脅偵測、威脅和違反政策</span><span class="sxs-lookup"><span data-stu-id="9d553-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="9d553-121">**組配置及健康** 狀態 - 涵蓋安全性控制措施的組配置和部署的卡片，包括到管理服務的裝置上設置狀態</span><span class="sxs-lookup"><span data-stu-id="9d553-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="9d553-122">**其他** - 所有其他卡片未分類到其他主題</span><span class="sxs-lookup"><span data-stu-id="9d553-122">**Other** - all other cards not categorized under other topics</span></span>
