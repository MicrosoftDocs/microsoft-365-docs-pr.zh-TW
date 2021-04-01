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
ms.openlocfilehash: 481051b74c1be88ba78bbd44e4fc0c174ed0bdad
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470890"
---
# <a name="create-indicators"></a><span data-ttu-id="e61ad-104">建立指示器</span><span class="sxs-lookup"><span data-stu-id="e61ad-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e61ad-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e61ad-105">**Applies to:**</span></span>
- [<span data-ttu-id="e61ad-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e61ad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e61ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e61ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="e61ad-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e61ad-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e61ad-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e61ad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="e61ad-110"> (IoCs) 相符的指示器是每個 endpoint protection 解決方案中的基本功能。</span><span class="sxs-lookup"><span data-stu-id="e61ad-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="e61ad-111">這項功能可讓 SecOps 設定標記清單以進行偵測，以及封鎖封鎖 (防護和回應) 。</span><span class="sxs-lookup"><span data-stu-id="e61ad-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="e61ad-112">建立指示器，以定義實體的偵測、預防和排除。</span><span class="sxs-lookup"><span data-stu-id="e61ad-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="e61ad-113">您可以定義要採取的動作，以及要套用動作的時間和裝置群組的範圍，以及要套用的動作。</span><span class="sxs-lookup"><span data-stu-id="e61ad-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="e61ad-114">目前支援的來源是用於 Defender for Endpoint 的雲端偵測引擎、自動調查和修正引擎，以及 Endpoint 防護引擎 (Microsoft Defender 防病毒) 。</span><span class="sxs-lookup"><span data-stu-id="e61ad-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="e61ad-115">**雲端偵測引擎**</span><span class="sxs-lookup"><span data-stu-id="e61ad-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="e61ad-116">Defender for Endpoint 的雲端偵測引擎會定期掃描收集的資料，並嘗試符合您設定的指示器。</span><span class="sxs-lookup"><span data-stu-id="e61ad-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="e61ad-117">當有相符時，會根據您為 IoC 所指定的設定採取動作。</span><span class="sxs-lookup"><span data-stu-id="e61ad-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="e61ad-118">**Endpoint 防護引擎**</span><span class="sxs-lookup"><span data-stu-id="e61ad-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="e61ad-119">預防代理程式會接受相同的指示器清單。</span><span class="sxs-lookup"><span data-stu-id="e61ad-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="e61ad-120">也就是說，如果 Microsoft Defender AV 是設定的主要 AV，就會依照設定來處理相符的指示器。</span><span class="sxs-lookup"><span data-stu-id="e61ad-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="e61ad-121">例如，如果動作為 "警示和封鎖"，Microsoft Defender AV 會使檔案執行 (區塊和修正) ，且會引發對應的警示。</span><span class="sxs-lookup"><span data-stu-id="e61ad-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="e61ad-122">另一方面，如果動作設定為 "Allow"，Microsoft Defender AV 將不會偵測到或封鎖檔案執行。</span><span class="sxs-lookup"><span data-stu-id="e61ad-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="e61ad-123">**自動化調查和修正引擎**</span><span class="sxs-lookup"><span data-stu-id="e61ad-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="e61ad-124">自動調查和修正行為相同。</span><span class="sxs-lookup"><span data-stu-id="e61ad-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="e61ad-125">如果指示器設定為 "Allow"，則自動調查和修正功能將會忽略對它的「不良」判定。</span><span class="sxs-lookup"><span data-stu-id="e61ad-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="e61ad-126">如果設為 "封鎖"，自動化調查和修正會將其視為「不良」。</span><span class="sxs-lookup"><span data-stu-id="e61ad-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>

> [!NOTE]
> <span data-ttu-id="e61ad-127">EnableFileHashComputation 設定會在檔掃描期間，計算憑證和檔案 IoC 的檔案雜湊。</span><span class="sxs-lookup"><span data-stu-id="e61ad-127">The EnableFileHashComputation setting computes the file hash for the cert and file IoC during file scans.</span></span> <span data-ttu-id="e61ad-128">它支援對散列和證書的強制執行屬於信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e61ad-128">It supports IoC enforcement of hashes and certs belong to trusted applications.</span></span> <span data-ttu-id="e61ad-129">它會同時使用 allow 或 block file 設定進行啟用與停用。</span><span class="sxs-lookup"><span data-stu-id="e61ad-129">It will be concurrently enabled and disabled with the allow or block file setting.</span></span> <span data-ttu-id="e61ad-130">EnableFileHashComputation 是透過群組原則手動啟用，且預設為停用。</span><span class="sxs-lookup"><span data-stu-id="e61ad-130">EnableFileHashComputation is enabled manually through Group Policy, and is disabled by default.</span></span>


<span data-ttu-id="e61ad-131">目前支援的動作如下：</span><span class="sxs-lookup"><span data-stu-id="e61ad-131">The current supported actions are:</span></span>
- <span data-ttu-id="e61ad-132">允許</span><span class="sxs-lookup"><span data-stu-id="e61ad-132">Allow</span></span>
- <span data-ttu-id="e61ad-133">僅警示</span><span class="sxs-lookup"><span data-stu-id="e61ad-133">Alert only</span></span>
- <span data-ttu-id="e61ad-134">警示和封鎖</span><span class="sxs-lookup"><span data-stu-id="e61ad-134">Alert and block</span></span>


<span data-ttu-id="e61ad-135">您可以為下列專案建立指示器：</span><span class="sxs-lookup"><span data-stu-id="e61ad-135">You can create an indicator for:</span></span>
- [<span data-ttu-id="e61ad-136">Files</span><span class="sxs-lookup"><span data-stu-id="e61ad-136">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="e61ad-137">IP 位址、URLs/網域</span><span class="sxs-lookup"><span data-stu-id="e61ad-137">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="e61ad-138">憑證</span><span class="sxs-lookup"><span data-stu-id="e61ad-138">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="e61ad-139">每個租使用者的指示器限制為15000。</span><span class="sxs-lookup"><span data-stu-id="e61ad-139">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="e61ad-140">檔案和憑證指示器不會封鎖 [為 Microsoft Defender 防病毒定義的排除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="e61ad-140">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="e61ad-141">Microsoft Defender 防病毒在被動模式時不支援指示器。</span><span class="sxs-lookup"><span data-stu-id="e61ad-141">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="e61ad-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="e61ad-142">Related topics</span></span>

- [<span data-ttu-id="e61ad-143">建立上下文 IoC</span><span class="sxs-lookup"><span data-stu-id="e61ad-143">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="e61ad-144">使用 Microsoft Defender for Endpoint 指示器 API</span><span class="sxs-lookup"><span data-stu-id="e61ad-144">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="e61ad-145">使用夥伴整合解決方案</span><span class="sxs-lookup"><span data-stu-id="e61ad-145">Use partner integrated solutions</span></span>](partner-applications.md)
