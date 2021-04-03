---
title: 減少零天的漏洞-威脅和弱點管理
description: 瞭解如何透過威脅和弱點管理，找出並減少環境中的零天弱點。
keywords: mdatp tvm zero 弱點，tvm，威脅 & 漏洞管理，零天，0天，緩解0天的漏洞，易攻擊的 CVE
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
ms.openlocfilehash: 941e4989dcb91ff9240131f5980d0e1eced2b21d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501230"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a><span data-ttu-id="66231-104">減少零天的漏洞-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="66231-104">Mitigate zero-day vulnerabilities - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="66231-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="66231-105">**Applies to:**</span></span>

- [<span data-ttu-id="66231-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="66231-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="66231-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="66231-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="66231-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66231-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="66231-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="66231-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="66231-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="66231-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="66231-111">零一天的弱點是公開披露的弱點，尚未發行任何正式的修補程式或安全性更新。</span><span class="sxs-lookup"><span data-stu-id="66231-111">A zero-day vulnerability is a publicly disclosed vulnerability for which no official patches or security updates have been released.</span></span> <span data-ttu-id="66231-112">零天的漏洞通常會有高嚴重性層級，並主動加以利用。</span><span class="sxs-lookup"><span data-stu-id="66231-112">Zero-day vulnerabilities often have high severity levels and are actively exploited.</span></span>

<span data-ttu-id="66231-113">威脅和弱點管理只會顯示零天其相關資訊的漏洞。</span><span class="sxs-lookup"><span data-stu-id="66231-113">Threat and vulnerability management will only display zero-day vulnerabilities it has information about.</span></span>

## <a name="find-information-about-zero-day-vulnerabilities"></a><span data-ttu-id="66231-114">尋找零天弱點的相關資訊</span><span class="sxs-lookup"><span data-stu-id="66231-114">Find information about zero-day vulnerabilities</span></span>

<span data-ttu-id="66231-115">一旦找到零天弱點，就會透過 Microsoft Defender Security Center 中的下列體驗來傳達相關資訊。</span><span class="sxs-lookup"><span data-stu-id="66231-115">Once a zero-day vulnerability has been found, information about it will be conveyed through the following experiences in the Microsoft Defender Security Center.</span></span>

### <a name="threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="66231-116">威脅與弱點管理儀表板</span><span class="sxs-lookup"><span data-stu-id="66231-116">Threat and vulnerability management dashboard</span></span>

<span data-ttu-id="66231-117">在「最高安全性建議」卡片中尋找含零天標記的建議。</span><span class="sxs-lookup"><span data-stu-id="66231-117">Look for recommendations with a zero-day tag in the “Top security recommendations” card.</span></span>

![使用零日標記的主要建議。](images/tvm-zero-day-top-security-recommendations.png)

<span data-ttu-id="66231-119">在「有缺陷的軟體」卡片中尋找最主要的軟體（含零天標記）。</span><span class="sxs-lookup"><span data-stu-id="66231-119">Find top software with the zero-day tag in the "Top vulnerable software" card.</span></span>

![具有零日標籤的常見漏洞軟體。](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a><span data-ttu-id="66231-121">弱點頁面</span><span class="sxs-lookup"><span data-stu-id="66231-121">Weaknesses page</span></span>

<span data-ttu-id="66231-122">尋找名為零天的弱點，以及描述和詳細資料。</span><span class="sxs-lookup"><span data-stu-id="66231-122">Look for the named zero-day vulnerability along with a description and details.</span></span>

- <span data-ttu-id="66231-123">如果此弱點已指派 CVE 識別碼，您會在 CVE 名稱旁看到零天標籤。</span><span class="sxs-lookup"><span data-stu-id="66231-123">If this vulnerability has a CVE-ID assigned, you’ll see the zero-day label next to the CVE name.</span></span>

- <span data-ttu-id="66231-124">如果此弱點未指派 CVE 識別碼，您可以在外觀為 "TVM-XXXX" 的內部暫時名稱下找到該漏洞。</span><span class="sxs-lookup"><span data-stu-id="66231-124">If this vulnerability has no CVE-ID assigned, you'll find it under an internal, temporary name that looks like “TVM-XXXX-XXXX”.</span></span> <span data-ttu-id="66231-125">在指派官方 CVE 識別碼後，就會更新此名稱，但先前的內部名稱仍可供搜尋，而且會在側面面板中找到。</span><span class="sxs-lookup"><span data-stu-id="66231-125">The name will be updated once an official CVE-ID has been assigned, but the previous internal name will still be searchable and found in the side-panel.</span></span>

![CVE-2020-17087 在弱點頁面中的零日範例。](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a><span data-ttu-id="66231-127">軟體庫存頁面</span><span class="sxs-lookup"><span data-stu-id="66231-127">Software inventory page</span></span>

<span data-ttu-id="66231-128">尋找含零天標記的軟體。</span><span class="sxs-lookup"><span data-stu-id="66231-128">Look for software with the zero-day tag.</span></span> <span data-ttu-id="66231-129">依 "zero day" 標記篩選，只查看含零天漏洞的軟體。</span><span class="sxs-lookup"><span data-stu-id="66231-129">Filter by the "zero day" tag to only see software with zero-day vulnerabilities.</span></span>

![在 [軟體庫存] 頁面中，Windows Server 2016 的零第一天範例。](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a><span data-ttu-id="66231-131">軟體頁面</span><span class="sxs-lookup"><span data-stu-id="66231-131">Software page</span></span>

<span data-ttu-id="66231-132">針對每個受到零天弱點影響的軟體，尋找零天標記。</span><span class="sxs-lookup"><span data-stu-id="66231-132">Look for a zero-day tag for each software that has been affected by the zero–day vulnerability.</span></span>

![[Windows Server 2016 軟體] 頁面的 [零天範例] 頁面。](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a><span data-ttu-id="66231-134">安全性建議頁面</span><span class="sxs-lookup"><span data-stu-id="66231-134">Security recommendations page</span></span>

<span data-ttu-id="66231-135">查看有關修復和緩解選項的明確建議，包括其存在的變通方法。</span><span class="sxs-lookup"><span data-stu-id="66231-135">View clear suggestions about remediation and mitigation options, including workarounds if they exist.</span></span> <span data-ttu-id="66231-136">依 "zero day" 標記篩選，只請參閱解決零天弱點的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="66231-136">Filter by the "zero day" tag to only see security recommendations addressing zero-day vulnerabilities.</span></span>

<span data-ttu-id="66231-137">如果有軟體有零天弱點，還有其他弱點可解決，您就會對所有的漏洞取得一個建議。</span><span class="sxs-lookup"><span data-stu-id="66231-137">If there's software with a zero-day vulnerability and additional vulnerabilities to address, you'll get one recommendation about all vulnerabilities.</span></span>

![在 [安全性建議] 頁面中，Windows Server 2016 的零第一天範例。](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a><span data-ttu-id="66231-139">解決零天的漏洞</span><span class="sxs-lookup"><span data-stu-id="66231-139">Addressing zero-day vulnerabilities</span></span>

<span data-ttu-id="66231-140">移至 [安全性建議] 頁面，並選取一個零一天的建議。</span><span class="sxs-lookup"><span data-stu-id="66231-140">Go to the security recommendation page and select a recommendation with a zero-day.</span></span> <span data-ttu-id="66231-141">快顯視窗將會開啟，其中會顯示零天的資訊以及該軟體的其他弱點。</span><span class="sxs-lookup"><span data-stu-id="66231-141">A flyout will open with information about the zero-day and other vulnerabilities for that software.</span></span>

<span data-ttu-id="66231-142">如果有可供使用的緩解選項和方法，將會有連結。</span><span class="sxs-lookup"><span data-stu-id="66231-142">There will be a link to mitigation options and workarounds if they are available.</span></span> <span data-ttu-id="66231-143">您可以在部署修補程式或安全性更新之前，避免此零天數弱點帶來的風險。</span><span class="sxs-lookup"><span data-stu-id="66231-143">Workarounds may help reduce the risk posed by this zero-day vulnerability until a patch or security update can be deployed.</span></span>

<span data-ttu-id="66231-144">開啟修復選項，然後選擇 [注意] 類型。</span><span class="sxs-lookup"><span data-stu-id="66231-144">Open remediation options and choose the attention type.</span></span> <span data-ttu-id="66231-145">因為尚未發行更新，所以建議使用「注意事項」修復選項，以取得零天的漏洞。</span><span class="sxs-lookup"><span data-stu-id="66231-145">An "attention required" remediation option is recommended for the zero-day vulnerabilities, since an update hasn't been released yet.</span></span> <span data-ttu-id="66231-146">因為沒有要執行的特定動作，所以您無法選取到期日。</span><span class="sxs-lookup"><span data-stu-id="66231-146">You won't be able to select a due date, since there's no specific action to perform.</span></span> <span data-ttu-id="66231-147">如果您想要修正此軟體舊版的漏洞，您可以覆寫「注意必要」修復選項，然後選擇「更新」。</span><span class="sxs-lookup"><span data-stu-id="66231-147">If there are older vulnerabilities for this software you wish to remediation, you can override the "attention required" remediation option and choose “update.”</span></span>

![在 [安全性建議] 頁面中的「零天飛出 Windows Server 2016」範例。](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a><span data-ttu-id="66231-149">追蹤零天的修復活動</span><span class="sxs-lookup"><span data-stu-id="66231-149">Track zero-day remediation activities</span></span>

<span data-ttu-id="66231-150">移至 [威脅與弱點管理 [修正](tvm-remediation.md) ] 頁面，以查看修正活動專案。</span><span class="sxs-lookup"><span data-stu-id="66231-150">Go to the threat and vulnerability management [Remediation](tvm-remediation.md) page to view the remediation activity item.</span></span> <span data-ttu-id="66231-151">如果您選擇「注意必要」修復選項，則不會有任何進度列、票證狀態或到期日，因為我們沒有任何實際的動作可供監視。</span><span class="sxs-lookup"><span data-stu-id="66231-151">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there's no actual action we can monitor.</span></span> <span data-ttu-id="66231-152">您可以依修正類型進行篩選，例如「軟體更新」或「注意事項」，以查看相同類別中的所有活動專案。</span><span class="sxs-lookup"><span data-stu-id="66231-152">You can filter by remediation type, such as "software update" or "attention required," to see all activity items in the same category.</span></span>

## <a name="patching-zero-day-vulnerabilities"></a><span data-ttu-id="66231-153">修補零天弱點</span><span class="sxs-lookup"><span data-stu-id="66231-153">Patching zero-day vulnerabilities</span></span>

<span data-ttu-id="66231-154">當您在零天內發行修補程式時，建議會變更為「更新」，並在它旁顯示「新安全性更新天」的藍色標籤。</span><span class="sxs-lookup"><span data-stu-id="66231-154">When a patch is released for the zero-day, the recommendation will be changed to “Update” and a blue label next to it that says “New security update for zero day.”</span></span> <span data-ttu-id="66231-155">它將不再視為零一天，將從所有頁面移除零天標記。</span><span class="sxs-lookup"><span data-stu-id="66231-155">It will no longer consider as a zero-day, the zero-day tag will be removed from all pages.</span></span>

![「以新的修補程式標籤更新 Microsoft Windows 10」的建議。](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a><span data-ttu-id="66231-157">相關文章</span><span class="sxs-lookup"><span data-stu-id="66231-157">Related articles</span></span>

- [<span data-ttu-id="66231-158">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="66231-158">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="66231-159">儀表板</span><span class="sxs-lookup"><span data-stu-id="66231-159">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="66231-160">安全性建議</span><span class="sxs-lookup"><span data-stu-id="66231-160">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="66231-161">軟體庫存</span><span class="sxs-lookup"><span data-stu-id="66231-161">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="66231-162">我組織中的弱點</span><span class="sxs-lookup"><span data-stu-id="66231-162">Vulnerabilities in my organization</span></span>](tvm-weaknesses.md)
