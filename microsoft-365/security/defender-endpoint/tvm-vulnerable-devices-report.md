---
title: 易受攻擊的裝置報告-威脅與弱點管理
description: 顯示受影響裝置趨勢和目前統計資料的報告。 目標是讓您瞭解裝置洩密的 breath 和範圍。
keywords: Microsoft Defender for Endpoint tvm 易受攻擊的裝置、Microsoft Defender for Endpoint、tvm、降低威脅 & 弱點洩密、減少威脅和弱點，監視安全性設定
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245477"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="056b6-105">易受攻擊的裝置報告-威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="056b6-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="056b6-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="056b6-106">**Applies to:**</span></span>

- [<span data-ttu-id="056b6-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="056b6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="056b6-108">威脅及弱點管理</span><span class="sxs-lookup"><span data-stu-id="056b6-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="056b6-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="056b6-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="056b6-110">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="056b6-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="056b6-111">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="056b6-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="056b6-112">報告會顯示圖表和橫條圖，包含易受影響的裝置趨勢和目前的統計資料。</span><span class="sxs-lookup"><span data-stu-id="056b6-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="056b6-113">目標是讓您瞭解裝置洩密的 breath 和範圍。</span><span class="sxs-lookup"><span data-stu-id="056b6-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="056b6-114">前往 **報告 > 易受攻擊的裝置**，以存取 Microsoft Defender 資訊安全中心中的報告</span><span class="sxs-lookup"><span data-stu-id="056b6-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="056b6-115">有兩個欄：</span><span class="sxs-lookup"><span data-stu-id="056b6-115">There are two columns:</span></span>

- <span data-ttu-id="056b6-116">隨時間)  (趨勢。</span><span class="sxs-lookup"><span data-stu-id="056b6-116">Trends (over time).</span></span> <span data-ttu-id="056b6-117">可顯示過去30天、3個月、6個月或自訂的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="056b6-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="056b6-118">今天 (目前的資訊) </span><span class="sxs-lookup"><span data-stu-id="056b6-118">Today (current information)</span></span>

<span data-ttu-id="056b6-119">**篩選**：您可以依弱點嚴重性層級、利用可用性、弱點年齡、作業系統平臺、Windows 10 版本或裝置群組篩選資料。</span><span class="sxs-lookup"><span data-stu-id="056b6-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="056b6-120">**深入** 查看：如果您想要進一步探索，請選取相關的橫條圖，以在 [設備庫存] 頁面中查看已篩選的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="056b6-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="056b6-121">您可以從這裡匯出清單。</span><span class="sxs-lookup"><span data-stu-id="056b6-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="056b6-122">嚴重性層級圖形</span><span class="sxs-lookup"><span data-stu-id="056b6-122">Severity level graphs</span></span>

<span data-ttu-id="056b6-123">每個裝置會根據該裝置上最嚴重的弱點，只計算一次。</span><span class="sxs-lookup"><span data-stu-id="056b6-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![目前裝置弱點嚴重性層級的一個圖形，以及一個顯示一段時間的層級的圖形。](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="056b6-125">利用可用性圖表</span><span class="sxs-lookup"><span data-stu-id="056b6-125">Exploit availability graphs</span></span>

<span data-ttu-id="056b6-126">每個裝置只會根據最上層的已知利用方式，計算一次。</span><span class="sxs-lookup"><span data-stu-id="056b6-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![目前裝置侵入可用性的一個圖形，以及一個顯示一段時間可用性的圖形。](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="056b6-128">弱點時期圖表</span><span class="sxs-lookup"><span data-stu-id="056b6-128">Vulnerability age graphs</span></span>

<span data-ttu-id="056b6-129">每個裝置只會在最舊的弱點發布日期下計算一次。</span><span class="sxs-lookup"><span data-stu-id="056b6-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="056b6-130">較舊的漏洞可能會受到攻擊的可能性較高。</span><span class="sxs-lookup"><span data-stu-id="056b6-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![目前裝置弱點壽命的一個圖形，以及一個顯示一段時間的時期的圖形。](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="056b6-132">受作業系統平臺圖影響的裝置</span><span class="sxs-lookup"><span data-stu-id="056b6-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="056b6-133">每個作業系統上因軟體弱點而公開的裝置數目。</span><span class="sxs-lookup"><span data-stu-id="056b6-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![由作業系統平臺所組成的目前易受攻擊裝置的一個圖形，以及一段時間後作業系統平臺顯示有漏洞裝置的圖形。](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="056b6-135">Windows 10 版本圖形的裝置受到攻擊</span><span class="sxs-lookup"><span data-stu-id="056b6-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="056b6-136">每個 Windows 10 版本上由於易受攻擊的應用程式或作業系統而公開的裝置數目。</span><span class="sxs-lookup"><span data-stu-id="056b6-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Windows 10 版本的目前有漏洞裝置的一個圖形，以及一段時間內 Windows 10 版本顯示有缺陷裝置的圖形。](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="056b6-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="056b6-138">Related topics</span></span>

- [<span data-ttu-id="056b6-139">威脅與弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="056b6-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="056b6-140">安全性建議</span><span class="sxs-lookup"><span data-stu-id="056b6-140">Security recommendations</span></span>](tvm-security-recommendation.md)
