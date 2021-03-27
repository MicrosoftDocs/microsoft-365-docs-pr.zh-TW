---
title: 建立指示器
ms.reviewer: ''
description: 建立檔案雜湊、IP 位址、URLs 或網域的指示器，以定義實體的偵測、預防和排除。
keywords: manage，允許，封鎖，封鎖，clean，惡意，檔案雜湊，ip 位址，url，網域
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 670c6449c1121bc329b1dfb37cd1d9948c99a3f8
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379295"
---
# <a name="create-indicators"></a><span data-ttu-id="ffaf1-104">建立指示器</span><span class="sxs-lookup"><span data-stu-id="ffaf1-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ffaf1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ffaf1-105">**Applies to:**</span></span>
- [<span data-ttu-id="ffaf1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ffaf1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ffaf1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffaf1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="ffaf1-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ffaf1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ffaf1-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="ffaf1-110"> (IoCs) 相符的指示器是每個 endpoint protection 解決方案中的基本功能。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="ffaf1-111">這項功能可讓 SecOps 設定標記清單以進行偵測，以及封鎖封鎖 (防護和回應) 。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="ffaf1-112">建立指示器，以定義實體的偵測、預防和排除。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="ffaf1-113">您可以定義要採取的動作，以及要套用動作的時間和裝置群組的範圍，以及要套用的動作。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="ffaf1-114">目前支援的來源是用於 Defender for Endpoint 的雲端偵測引擎、自動調查和修正引擎，以及 Endpoint 防護引擎 (Microsoft Defender 防病毒) 。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="ffaf1-115">**雲端偵測引擎**</span><span class="sxs-lookup"><span data-stu-id="ffaf1-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="ffaf1-116">Defender for Endpoint 的雲端偵測引擎會定期掃描收集的資料，並嘗試符合您設定的指示器。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="ffaf1-117">當有相符時，會根據您為 IoC 所指定的設定採取動作。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="ffaf1-118">**Endpoint 防護引擎**</span><span class="sxs-lookup"><span data-stu-id="ffaf1-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="ffaf1-119">預防代理程式會接受相同的指示器清單。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="ffaf1-120">也就是說，如果 Microsoft Defender AV 是設定的主要 AV，就會依照設定來處理相符的指示器。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="ffaf1-121">例如，如果動作為 "警示和封鎖"，Microsoft Defender AV 會使檔案執行 (區塊和修正) ，且會引發對應的警示。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="ffaf1-122">另一方面，如果動作設定為 "Allow"，Microsoft Defender AV 將不會偵測到或封鎖檔案執行。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="ffaf1-123">**自動化調查和修正引擎**</span><span class="sxs-lookup"><span data-stu-id="ffaf1-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="ffaf1-124">自動調查和修正行為相同。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="ffaf1-125">如果指示器設定為 "Allow"，則自動調查和修正功能將會忽略對它的「不良」判定。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="ffaf1-126">如果設為 "封鎖"，自動化調查和修正會將其視為「不良」。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="ffaf1-127">目前支援的動作如下：</span><span class="sxs-lookup"><span data-stu-id="ffaf1-127">The current supported actions are:</span></span>
- <span data-ttu-id="ffaf1-128">允許</span><span class="sxs-lookup"><span data-stu-id="ffaf1-128">Allow</span></span>
- <span data-ttu-id="ffaf1-129">僅警示</span><span class="sxs-lookup"><span data-stu-id="ffaf1-129">Alert only</span></span>
- <span data-ttu-id="ffaf1-130">警示和封鎖</span><span class="sxs-lookup"><span data-stu-id="ffaf1-130">Alert and block</span></span>


<span data-ttu-id="ffaf1-131">您可以為下列專案建立指示器：</span><span class="sxs-lookup"><span data-stu-id="ffaf1-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="ffaf1-132">Files</span><span class="sxs-lookup"><span data-stu-id="ffaf1-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="ffaf1-133">IP 位址、URLs/網域</span><span class="sxs-lookup"><span data-stu-id="ffaf1-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="ffaf1-134">憑證</span><span class="sxs-lookup"><span data-stu-id="ffaf1-134">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="ffaf1-135">每個租使用者的指示器限制為15000。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-135">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="ffaf1-136">檔案和憑證指示器不會封鎖 [為 Microsoft Defender 防病毒定義的排除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-136">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="ffaf1-137">Microsoft Defender 防病毒在被動模式時不支援指示器。</span><span class="sxs-lookup"><span data-stu-id="ffaf1-137">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="ffaf1-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="ffaf1-138">Related topics</span></span>

- [<span data-ttu-id="ffaf1-139">建立上下文 IoC</span><span class="sxs-lookup"><span data-stu-id="ffaf1-139">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="ffaf1-140">使用 Microsoft Defender for Endpoint 指示器 API</span><span class="sxs-lookup"><span data-stu-id="ffaf1-140">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="ffaf1-141">使用夥伴整合解決方案</span><span class="sxs-lookup"><span data-stu-id="ffaf1-141">Use partner integrated solutions</span></span>](partner-applications.md)
