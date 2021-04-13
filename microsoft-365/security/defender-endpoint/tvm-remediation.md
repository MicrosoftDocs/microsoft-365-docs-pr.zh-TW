---
title: 利用威脅和弱點管理修正弱點
description: 修正透過安全性建議所發現的安全性弱點，視需要在威脅和弱點管理中建立例外狀況。
keywords: microsoft defender for endpoint tvm 修復，mdatp tvm，威脅和弱點管理，威脅 & 漏洞管理，威脅 & 漏洞管理修正，tvm 修正 intune，tvm 修正 sccm
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: be24528c2337c5d2616eb1bf69906f60ae7b4375
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689362"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="51413-104">利用威脅和弱點管理修正弱點</span><span class="sxs-lookup"><span data-stu-id="51413-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="51413-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="51413-105">**Applies to:**</span></span>
- [<span data-ttu-id="51413-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="51413-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="51413-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="51413-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="51413-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51413-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="51413-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="51413-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="51413-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="51413-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="51413-111">要求修正</span><span class="sxs-lookup"><span data-stu-id="51413-111">Request remediation</span></span>

<span data-ttu-id="51413-112">Microsoft Defender for Endpoint 中的威脅和弱點管理功能會透過修正要求工作流程，在安全性與 IT 系統管理員之間取得橋樑。</span><span class="sxs-lookup"><span data-stu-id="51413-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="51413-113">安全性管理員贊您可要求 IT 管理員從 Intune 的 **安全性建議** 頁面修復弱點。</span><span class="sxs-lookup"><span data-stu-id="51413-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="51413-114">啟用 Microsoft Intune 連線</span><span class="sxs-lookup"><span data-stu-id="51413-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="51413-115">若要使用此功能，請啟用您的 Microsoft Intune 連線。</span><span class="sxs-lookup"><span data-stu-id="51413-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="51413-116">在 Microsoft Defender Security Center 中，流覽至 [**設定**]  >  **[一般**  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="51413-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="51413-117">向左下向和尋找 **Microsoft Intune** 連線。</span><span class="sxs-lookup"><span data-stu-id="51413-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="51413-118">預設會關閉切換功能。</span><span class="sxs-lookup"><span data-stu-id="51413-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="51413-119">開啟您 **的** **Microsoft Intune** 連線切換功能。</span><span class="sxs-lookup"><span data-stu-id="51413-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="51413-120">**附注**：如果您已啟用 intune 連線，您可以在建立修復要求時，取得建立 intune 安全性工作的選項。</span><span class="sxs-lookup"><span data-stu-id="51413-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="51413-121">如果未設定 connection，則不會顯示此選項。</span><span class="sxs-lookup"><span data-stu-id="51413-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="51413-122">請參閱 [使用 Intune 修復 Microsoft Defender For Endpoint 所識別的漏洞](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51413-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="51413-123">修正要求步驟</span><span class="sxs-lookup"><span data-stu-id="51413-123">Remediation request steps</span></span>

1. <span data-ttu-id="51413-124">移至 Microsoft Defender Security Center 中的 [威脅與弱點管理] 流覽功能表，然後選取 [ [**安全性建議**](tvm-security-recommendation.md)]。</span><span class="sxs-lookup"><span data-stu-id="51413-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="51413-125">選取您要要求修復的安全性建議，然後選取 [ **修正選項**]。</span><span class="sxs-lookup"><span data-stu-id="51413-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="51413-126">填寫表單，包含您要求修正的專案、適用的裝置群組、優先順序、到期日及選用的附注。</span><span class="sxs-lookup"><span data-stu-id="51413-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="51413-127">如果您選擇「需要注意」修正選項，由於沒有特定動作，所以無法使用選取到期日。</span><span class="sxs-lookup"><span data-stu-id="51413-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="51413-128">選取 [ **提交要求**]。</span><span class="sxs-lookup"><span data-stu-id="51413-128">Select **Submit request**.</span></span> <span data-ttu-id="51413-129">送出修正要求會在威脅和弱點管理中建立修復活動專案，以用於監視此建議的修正進度。</span><span class="sxs-lookup"><span data-stu-id="51413-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="51413-130">這不會觸發修復或將任何變更套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="51413-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="51413-131">通知 IT 管理員有關新要求的資訊，讓他們登入 Intune，以核准或拒絕要求，然後啟動套件部署。</span><span class="sxs-lookup"><span data-stu-id="51413-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="51413-132">移至 [ [**修復**](tvm-remediation.md) ] 頁面，以查看修正要求的狀態。</span><span class="sxs-lookup"><span data-stu-id="51413-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="51413-133">如果您想要檢查票證在 Intune 中的顯示方式，請參閱 [使用 Intune 修復 Microsoft Defender For Endpoint 所識別的漏洞](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="51413-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="51413-134">如果您的要求需要修正超過10000台裝置，我們只能將10000裝置傳送至 Intune 的修正裝置。</span><span class="sxs-lookup"><span data-stu-id="51413-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="51413-135">識別組織的 cybersecurity 弱點並對應至可操作的 [安全性建議](tvm-security-recommendation.md)後，開始建立安全性工作。</span><span class="sxs-lookup"><span data-stu-id="51413-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="51413-136">您可以透過與 Microsoft Intune 整合的方式建立工作，以建立修復票證。</span><span class="sxs-lookup"><span data-stu-id="51413-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="51413-137">降低組織面臨的隱患，並修正安全性建議，以提升安全性設定。</span><span class="sxs-lookup"><span data-stu-id="51413-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="51413-138">查看您的修復活動</span><span class="sxs-lookup"><span data-stu-id="51413-138">View your remediation activities</span></span>

<span data-ttu-id="51413-139">當您從 [安全性建議] 頁面提交修正要求時，它會停用修復活動。</span><span class="sxs-lookup"><span data-stu-id="51413-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="51413-140">建立可在威脅和弱點管理 **修正** 頁面中追蹤的安全性任務，並在 Microsoft Intune 中建立修正憑證。</span><span class="sxs-lookup"><span data-stu-id="51413-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="51413-141">如果您選擇「注意必要」修復選項，則不會有任何進度列、票證狀態或到期日，因為我們沒有任何實際的動作可供監視。</span><span class="sxs-lookup"><span data-stu-id="51413-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="51413-142">在 [修復] 頁面上，選取您要查看的修復活動。</span><span class="sxs-lookup"><span data-stu-id="51413-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="51413-143">您可以依照修復步驟、追蹤進度、查看相關的建議、匯出至 CSV 或標記為完成。</span><span class="sxs-lookup"><span data-stu-id="51413-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="51413-144">![「修復」頁面的範例，其中包含選取的修復活動，以及該活動的快顯視窗，列出描述、IT 服務和裝置管理工具，以及裝置修正進度。](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="51413-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="51413-145">完成修復活動的保留期間為180天。</span><span class="sxs-lookup"><span data-stu-id="51413-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="51413-146">若要讓修正頁面的執行效果優化，修復活動會在完成後6個月內移除。</span><span class="sxs-lookup"><span data-stu-id="51413-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="51413-147">已完成（按欄）</span><span class="sxs-lookup"><span data-stu-id="51413-147">Completed by column</span></span>

<span data-ttu-id="51413-148">在 [修正] 頁面上追蹤「完成者」欄中關閉修復活動的人員。</span><span class="sxs-lookup"><span data-stu-id="51413-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="51413-149">**電子郵件地址**：手動完成工作之人員的電子郵件</span><span class="sxs-lookup"><span data-stu-id="51413-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="51413-150">**系統確認**：任務已自動完成 (所有已修正的裝置) </span><span class="sxs-lookup"><span data-stu-id="51413-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="51413-151">**N/A**：無法使用資訊，因為我們不知道此舊工作的完成方式</span><span class="sxs-lookup"><span data-stu-id="51413-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![由具有兩列的資料行建立及完成。](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="51413-154">儀表板中的主要修復活動</span><span class="sxs-lookup"><span data-stu-id="51413-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="51413-155">在「[威脅與弱點管理」儀表板](tvm-dashboard-insights.md)中查看 **主要修復活動**。</span><span class="sxs-lookup"><span data-stu-id="51413-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="51413-156">選取任何專案，以移至 [ **修復** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="51413-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="51413-157">您可以在 IT 系統管理員小組 remediates 任務之後，將修復活動標示為已完成。</span><span class="sxs-lookup"><span data-stu-id="51413-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![主要修復活動卡的範例，其中會列出由安全性建議所產生之主要活動的表格。](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="51413-159">相關文章</span><span class="sxs-lookup"><span data-stu-id="51413-159">Related articles</span></span>

- [<span data-ttu-id="51413-160">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="51413-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="51413-161">儀表板</span><span class="sxs-lookup"><span data-stu-id="51413-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="51413-162">安全性建議</span><span class="sxs-lookup"><span data-stu-id="51413-162">Security recommendations</span></span>](tvm-security-recommendation.md)