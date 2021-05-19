---
title: 減少零天的漏洞-威脅與弱點管理
description: 瞭解如何透過威脅與弱點管理找出並減少環境中的零天弱點。
keywords: Microsoft Defender for Endpoint tvm day 弱點，tvm，威脅 & 弱點管理，零天，0天，緩解0天的漏洞，易受攻擊的 CVE
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
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538768"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="d537e-104">減少零天的漏洞-威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="d537e-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d537e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d537e-105">**Applies to:**</span></span>

- [<span data-ttu-id="d537e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d537e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d537e-107">威脅及弱點管理</span><span class="sxs-lookup"><span data-stu-id="d537e-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d537e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d537e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d537e-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d537e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d537e-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d537e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="d537e-111">零一天的弱點是公開披露的弱點，尚未發行任何正式的修補程式或安全性更新。</span><span class="sxs-lookup"><span data-stu-id="d537e-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="d537e-112">零天的漏洞通常會有高嚴重性層級，並主動加以利用。</span><span class="sxs-lookup"><span data-stu-id="d537e-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="d537e-113">威脅和弱點管理只會顯示其相關資訊的零天弱點。</span><span class="sxs-lookup"><span data-stu-id="d537e-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="d537e-114">尋找零天弱點的相關資訊</span><span class="sxs-lookup"><span data-stu-id="d537e-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="d537e-115">在找到零天的弱點後，就會透過 Microsoft Defender 資訊安全中心中的下列體驗來傳達相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d537e-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

>[!NOTE]
> <span data-ttu-id="d537e-116">0天功能目前不適用於非 Windows 產品 (Mac，Linux) ;不過，它會在未來新增。</span><span class="sxs-lookup"><span data-stu-id="d537e-116">0-day capability is not currently available for non-Windows products (Mac, Linux); it will, however, be added in the future.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="d537e-117">威脅與弱點管理儀表板</span><span class="sxs-lookup"><span data-stu-id="d537e-117">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="d537e-118">在「最高安全性建議」卡片中尋找含零天標記的建議。</span><span class="sxs-lookup"><span data-stu-id="d537e-118">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![使用零日標記的主要建議。](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="d537e-120">在「有缺陷的軟體」卡片中尋找最主要的軟體（含零天標記）。</span><span class="sxs-lookup"><span data-stu-id="d537e-120">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![具有零日標籤的常見漏洞軟體。](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="d537e-122">弱點頁面</span><span class="sxs-lookup"><span data-stu-id="d537e-122">Weaknesses page</span></span>

<span data-ttu-id="d537e-123">尋找名為零天的弱點，以及描述和詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d537e-123">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="d537e-124">如果此弱點已指派 CVE 識別碼，您會在 CVE 名稱旁看到零天標籤。</span><span class="sxs-lookup"><span data-stu-id="d537e-124">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="d537e-125">如果此弱點未指派 CVE 識別碼，您可以在外觀為 "TVM-XXXX" 的內部暫時名稱下找到該漏洞。</span><span class="sxs-lookup"><span data-stu-id="d537e-125">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="d537e-126">在指派官方 CVE 識別碼後，就會更新此名稱，但先前的內部名稱仍可供搜尋，而且會在側面面板中找到。</span><span class="sxs-lookup"><span data-stu-id="d537e-126">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![CVE-2020-17087 在弱點頁面中的零日範例。](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="d537e-128">軟體庫存頁面</span><span class="sxs-lookup"><span data-stu-id="d537e-128">Software inventory page</span></span>

<span data-ttu-id="d537e-129">尋找含零天標記的軟體。</span><span class="sxs-lookup"><span data-stu-id="d537e-129">Look for software with the zero-day tag.</span></span> <span data-ttu-id="d537e-130">依 "zero day" 標記篩選，只查看含零天漏洞的軟體。</span><span class="sxs-lookup"><span data-stu-id="d537e-130">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![在 [軟體庫存] 頁面中 Windows Server 2016 的零日範例。](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="d537e-132">軟體頁面</span><span class="sxs-lookup"><span data-stu-id="d537e-132">Software page</span></span>

<span data-ttu-id="d537e-133">針對每個受到零天弱點影響的軟體，尋找零天標記。</span><span class="sxs-lookup"><span data-stu-id="d537e-133">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![Windows Server 2016 軟體] 頁面提供零日範例。](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="d537e-135">安全性建議頁面</span><span class="sxs-lookup"><span data-stu-id="d537e-135">Security recommendations page</span></span>

<span data-ttu-id="d537e-136">查看有關修復和緩解選項的明確建議，包括其存在的變通方法。</span><span class="sxs-lookup"><span data-stu-id="d537e-136">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="d537e-137">依 "zero day" 標記篩選，只請參閱解決零天弱點的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="d537e-137">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="d537e-138">如果有軟體有零天弱點，還有其他弱點可解決，您就會對所有的漏洞取得一個建議。</span><span class="sxs-lookup"><span data-stu-id="d537e-138">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![在 [安全性建議] 頁面中 Windows Server 2016 的零日範例。](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="d537e-140">解決零天的漏洞</span><span class="sxs-lookup"><span data-stu-id="d537e-140">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="d537e-141">移至 [安全性建議] 頁面，並選取一個零一天的建議。</span><span class="sxs-lookup"><span data-stu-id="d537e-141">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="d537e-142">快顯視窗將會開啟，其中會顯示零天的資訊以及該軟體的其他弱點。</span><span class="sxs-lookup"><span data-stu-id="d537e-142">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="d537e-143">如果有可供使用的緩解選項和方法，將會有連結。</span><span class="sxs-lookup"><span data-stu-id="d537e-143">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="d537e-144">您可以在部署修補程式或安全性更新之前，避免此零天數弱點帶來的風險。</span><span class="sxs-lookup"><span data-stu-id="d537e-144">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="d537e-145">開啟修復選項，然後選擇 [注意] 類型。</span><span class="sxs-lookup"><span data-stu-id="d537e-145">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="d537e-146">因為尚未發行更新，所以建議使用「注意事項」修復選項，以取得零天的漏洞。</span><span class="sxs-lookup"><span data-stu-id="d537e-146">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="d537e-147">因為沒有要執行的特定動作，所以您無法選取到期日。</span><span class="sxs-lookup"><span data-stu-id="d537e-147">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="d537e-148">如果您想要修正此軟體舊版的漏洞，您可以覆寫「注意必要」修復選項，然後選擇「更新」。</span><span class="sxs-lookup"><span data-stu-id="d537e-148">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![在 [安全性建議] 頁面中 Windows Server 2016 的零天浮出的範例。](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="d537e-150">追蹤零天的修復活動</span><span class="sxs-lookup"><span data-stu-id="d537e-150">Track zero-day remediation activities</span></span>

<span data-ttu-id="d537e-151">移至「威脅與弱點管理[修復](tvm-remediation.md)」頁面，以查看修正活動專案。</span><span class="sxs-lookup"><span data-stu-id="d537e-151">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="d537e-152">如果您選擇「注意必要」修復選項，則不會有任何進度列、票證狀態或到期日，因為我們沒有任何實際的動作可供監視。</span><span class="sxs-lookup"><span data-stu-id="d537e-152">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="d537e-153">您可以依修正類型進行篩選，例如「軟體更新」或「注意事項」，以查看相同類別中的所有活動專案。</span><span class="sxs-lookup"><span data-stu-id="d537e-153">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="d537e-154">修補零天弱點</span><span class="sxs-lookup"><span data-stu-id="d537e-154">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="d537e-155">當您在零天內發行修補程式時，建議會變更為「更新」，並在它旁顯示「新安全性更新天」的藍色標籤。</span><span class="sxs-lookup"><span data-stu-id="d537e-155">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="d537e-156">它將不再視為零一天，將從所有頁面移除零天標記。</span><span class="sxs-lookup"><span data-stu-id="d537e-156">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![「以新的修補程式標籤更新 Microsoft Windows 10」的建議。](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="d537e-158">相關文章</span><span class="sxs-lookup"><span data-stu-id="d537e-158">Related articles</span></span>

- [<span data-ttu-id="d537e-159">威脅與弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="d537e-159">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="d537e-160">儀表板</span><span class="sxs-lookup"><span data-stu-id="d537e-160">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="d537e-161">安全性建議</span><span class="sxs-lookup"><span data-stu-id="d537e-161">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="d537e-162">軟體庫存</span><span class="sxs-lookup"><span data-stu-id="d537e-162">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="d537e-163">我組織中的弱點</span><span class="sxs-lookup"><span data-stu-id="d537e-163">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
