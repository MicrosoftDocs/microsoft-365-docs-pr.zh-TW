---
title: 開始使用資料外洩防護警示儀表板
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 開始定義及管理資料遺失防護原則的提醒。
ms.openlocfilehash: ad117eb0c5460b90c92c664f0c233b81d1882327
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843863"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a><span data-ttu-id="9921f-103">開始使用資料外洩防護警示儀表板</span><span class="sxs-lookup"><span data-stu-id="9921f-103">Get started with the data loss prevention alert dashboard</span></span>

<span data-ttu-id="9921f-104">資料遺失防護 (DLP) 原則可以採取保護性動作，以避免無意間共用機密專案。</span><span class="sxs-lookup"><span data-stu-id="9921f-104">Data loss prevention (DLP) policies can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="9921f-105">針對敏感專案採取動作時，您可以設定 DLP 的警示來通知您。</span><span class="sxs-lookup"><span data-stu-id="9921f-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="9921f-106">本文說明如何定義與資料遺失防護 (DLP) 原則相關聯的各種警示原則。</span><span class="sxs-lookup"><span data-stu-id="9921f-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="9921f-107">您將會瞭解如何使用[Microsoft 365 規範中心](https://compliance.microsoft.com/)的[DLP 警示管理儀表板](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)來查看警示、事件，以及與 DLP 原則違規相關聯的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="9921f-107">You'll see how to use the [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<span data-ttu-id="9921f-108">如果您是新的 DLP 警示，請參閱 [瞭解資料遺失防護警示儀表板](dlp-alerts-dashboard-learn.md)</span><span class="sxs-lookup"><span data-stu-id="9921f-108">If you are new to DLP alerts, you should review [Learn about the data loss prevention alerts dashboard](dlp-alerts-dashboard-learn.md)</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9921f-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="9921f-109">Before you begin</span></span>

<span data-ttu-id="9921f-110">開始之前，請確定您具備必要的必要條件：</span><span class="sxs-lookup"><span data-stu-id="9921f-110">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="9921f-111">DLP 警示管理儀表板的授權</span><span class="sxs-lookup"><span data-stu-id="9921f-111">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="9921f-112">警示設定選項的授權</span><span class="sxs-lookup"><span data-stu-id="9921f-112">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="9921f-113">角色</span><span class="sxs-lookup"><span data-stu-id="9921f-113">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="9921f-114">DLP 警示管理儀表板的授權</span><span class="sxs-lookup"><span data-stu-id="9921f-114">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="9921f-115">Office 365 dlp 的所有合格租使用者都可以存取 DLP 警示管理儀表板。</span><span class="sxs-lookup"><span data-stu-id="9921f-115">All eligible tenants for Office 365 DLP can access the DLP alert management dashboard.</span></span> <span data-ttu-id="9921f-116">若要開始，您應該具備 Office 365 DLP Exchange Online、SharePoint 線上及商務用 OneDrive 的資格。</span><span class="sxs-lookup"><span data-stu-id="9921f-116">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="9921f-117">如需 Office 365 DLP 之授權需求的詳細資訊，請參閱[哪些授權可為使用者提供從服務受益的許可權？](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。</span><span class="sxs-lookup"><span data-stu-id="9921f-117">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="9921f-118">使用適用于[Teams DLP](dlp-microsoft-teams.md)之[endpoint dlp](endpoint-dlp-learn-about.md)的客戶，將會看到其 endpoint dlp 原則警示，並 Teams dlp 警示管理儀表板中的 dlp 原則警示。</span><span class="sxs-lookup"><span data-stu-id="9921f-118">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

<span data-ttu-id="9921f-119">**內容預覽** 功能僅適用于這些授權：</span><span class="sxs-lookup"><span data-stu-id="9921f-119">The **content preview** feature is available only for these licenses:</span></span>

- <span data-ttu-id="9921f-120">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="9921f-120">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="9921f-121">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="9921f-121">Office 365 (E5)</span></span>
- <span data-ttu-id="9921f-122">高級規範 (E5) 新增</span><span class="sxs-lookup"><span data-stu-id="9921f-122">Advanced Compliance (E5) add on</span></span>
- <span data-ttu-id="9921f-123">Microsoft 365 E5/A5 資訊保護和管理</span><span class="sxs-lookup"><span data-stu-id="9921f-123">Microsoft 365 E5/A5 Information Protection and Governance</span></span>
- <span data-ttu-id="9921f-124">Microsft 365 E5/A5 相容性</span><span class="sxs-lookup"><span data-stu-id="9921f-124">Microsft 365 E5/A5 Compliance</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="9921f-125">警示設定選項的授權</span><span class="sxs-lookup"><span data-stu-id="9921f-125">Licensing for alert configuration options</span></span>

<span data-ttu-id="9921f-126">**單一事件警示** 設定：具有 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱的組織，只會建立在每次發生活動時觸發警示的警示原則。</span><span class="sxs-lookup"><span data-stu-id="9921f-126">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>

<span data-ttu-id="9921f-127">**匯總的警示** 設定：若要根據臨界值來設定匯總警示原則，您必須使用下列其中一種授權設定：</span><span class="sxs-lookup"><span data-stu-id="9921f-127">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must one of these licensing configurations:</span></span>

- <span data-ttu-id="9921f-128">E5 或 G5 訂閱</span><span class="sxs-lookup"><span data-stu-id="9921f-128">An E5 or G5 subscription</span></span>
- <span data-ttu-id="9921f-129">具有下列其中一項功能的 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱：</span><span class="sxs-lookup"><span data-stu-id="9921f-129">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
    - <span data-ttu-id="9921f-130">Office 365 進階威脅防護方案 2</span><span class="sxs-lookup"><span data-stu-id="9921f-130">Office 365 Advanced Threat Protection Plan 2</span></span>
    - <span data-ttu-id="9921f-131">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="9921f-131">Microsoft 365 E5 Compliance</span></span>
    - <span data-ttu-id="9921f-132">Microsoft 365 電子檔探索和審計附加元件授權</span><span class="sxs-lookup"><span data-stu-id="9921f-132">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="9921f-133">角色</span><span class="sxs-lookup"><span data-stu-id="9921f-133">Roles</span></span>


<span data-ttu-id="9921f-134">如果您想要查看 DLP 警示管理儀表板，或編輯 DLP 原則中的警示設定選項，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="9921f-134">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

- <span data-ttu-id="9921f-135">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="9921f-135">Compliance Administrator</span></span>
- <span data-ttu-id="9921f-136">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="9921f-136">Compliance Data Administrator</span></span>
- <span data-ttu-id="9921f-137">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="9921f-137">Security Administrator</span></span>
- <span data-ttu-id="9921f-138">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="9921f-138">Security Operator</span></span>
- <span data-ttu-id="9921f-139">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="9921f-139">Security Reader</span></span>

<span data-ttu-id="9921f-140">若要存取 DLP 警示管理儀表板，您需要：</span><span class="sxs-lookup"><span data-stu-id="9921f-140">To access the DLP alert management dashboard, you need the:</span></span>

- <span data-ttu-id="9921f-141">管理警示</span><span class="sxs-lookup"><span data-stu-id="9921f-141">Manage alerts</span></span>

<span data-ttu-id="9921f-142">下列兩個角色之一：</span><span class="sxs-lookup"><span data-stu-id="9921f-142">and either of these two roles:</span></span>

- <span data-ttu-id="9921f-143">DLP 合規性管理</span><span class="sxs-lookup"><span data-stu-id="9921f-143">DLP Compliance Management</span></span>
- <span data-ttu-id="9921f-144">僅限檢視 DLP 合規性管理</span><span class="sxs-lookup"><span data-stu-id="9921f-144">View-Only DLP Compliance Management</span></span>

<span data-ttu-id="9921f-145">若要存取內容預覽功能以及符合的敏感內容和內容，您必須是下列專案的成員：</span><span class="sxs-lookup"><span data-stu-id="9921f-145">To access the Content preview feature and the Matched sensitive content and context features you must be a member of:</span></span>

- <span data-ttu-id="9921f-146">內容瀏覽器內容檢視器角色群組</span><span class="sxs-lookup"><span data-stu-id="9921f-146">Content Explorer Content Viewer role group</span></span>

<span data-ttu-id="9921f-147">已預先指派「資料分類內容檢視器」角色。</span><span class="sxs-lookup"><span data-stu-id="9921f-147">which has the data classification content viewer role pre-assigned.</span></span>

## <a name="dlp-alert-configuration"></a><span data-ttu-id="9921f-148">DLP 警示設定</span><span class="sxs-lookup"><span data-stu-id="9921f-148">DLP alert configuration</span></span>

<span data-ttu-id="9921f-149">若要瞭解如何在 DLP 原則中設定警示，請參閱 [開始使用資料遺失防護的位置](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)。</span><span class="sxs-lookup"><span data-stu-id="9921f-149">To learn how to configure an alert in your DLP policy, see [Where to start with data loss prevention](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention).</span></span>

### <a name="aggregate-event-alert-configuration"></a><span data-ttu-id="9921f-150">匯總事件警示設定</span><span class="sxs-lookup"><span data-stu-id="9921f-150">Aggregate event alert configuration</span></span>

<span data-ttu-id="9921f-151">如果您的組織授權使用 [匯總的警示設定選項](#licensing-for-alert-configuration-options)，當您建立或編輯 DLP 原則時，您會看到這些選項。</span><span class="sxs-lookup"><span data-stu-id="9921f-151">If your org is licensed for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="螢幕擷取畫面顯示適用于已匯總警示設定選項之使用者的附隨報告選項。" border="false":::

<span data-ttu-id="9921f-153">這項設定可讓您設定原則，以在每次活動符合原則條件時或超過特定臨界值時，根據活動數量或根據挾帶資料量的數量來產生警示。</span><span class="sxs-lookup"><span data-stu-id="9921f-153">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

### <a name="single-event-alert-configuration"></a><span data-ttu-id="9921f-154">單一事件警示設定</span><span class="sxs-lookup"><span data-stu-id="9921f-154">Single event alert configuration</span></span>

<span data-ttu-id="9921f-155">如果您的組織已取得 [單一事件警示設定選項](#licensing-for-alert-configuration-options)的授權，當您建立或編輯 DLP 原則時，您會看到這些選項。</span><span class="sxs-lookup"><span data-stu-id="9921f-155">If your org is licensed for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you'll see these options when you create or edit a DLP policy.</span></span> <span data-ttu-id="9921f-156">使用此選項，可建立每當 DLP 規則相符時，就會引發警示。</span><span class="sxs-lookup"><span data-stu-id="9921f-156">Use this option to create an alert that's raised every time a DLP rule match happens.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="螢幕擷取畫面顯示適用于單一事件警示設定選項的使用者附隨報告選項。" border="false":::

## <a name="investigate-a-dlp-alert"></a><span data-ttu-id="9921f-158">調查 DLP 警示</span><span class="sxs-lookup"><span data-stu-id="9921f-158">Investigate a DLP alert</span></span>

<span data-ttu-id="9921f-159">若要使用 DLP 警示管理儀表板：</span><span class="sxs-lookup"><span data-stu-id="9921f-159">To work with the DLP alert management dashboard:</span></span>

1. <span data-ttu-id="9921f-160">在 [Microsoft 365 規範中心](https://www.compliance.microsoft.com)] 中，移至 [**資料遺失防護**]。</span><span class="sxs-lookup"><span data-stu-id="9921f-160">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>
2. <span data-ttu-id="9921f-161">選取 [ **警示** ] 索引標籤，以查看 [DLP 警示] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="9921f-161">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>
3. <span data-ttu-id="9921f-162">選取警示以查看詳細資料：</span><span class="sxs-lookup"><span data-stu-id="9921f-162">Select an alert to see details:</span></span>

:::image type="content" source="../media/alert-details.png" alt-text="螢幕擷取畫面顯示 DLP 警示管理儀表板上的警示詳細資料。" border="false":::

4. <span data-ttu-id="9921f-164">選取 [ **事件** ] 索引標籤，以查看與警示相關聯的所有事件。</span><span class="sxs-lookup"><span data-stu-id="9921f-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="9921f-165">您可以選擇特定的事件來查看其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9921f-165">You can choose a particular event to view its details.</span></span> <span data-ttu-id="9921f-166">如需部分可用事件詳細資料的清單，請參閱， [瞭解資料遺失防護提醒儀表板](dlp-alerts-dashboard-learn.md)。</span><span class="sxs-lookup"><span data-stu-id="9921f-166">For a list of some of the available event details, see, [Learn about the data loss prevention Alerts dashboard](dlp-alerts-dashboard-learn.md).</span></span>
5. <span data-ttu-id="9921f-167">選取 [ **詳細資料** ] 開啟警示的 [ **一覽表** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="9921f-167">Select **Details** to open the **Overview** page for the alert.</span></span> <span data-ttu-id="9921f-168">[一覽表] 頁面提供摘要：</span><span class="sxs-lookup"><span data-stu-id="9921f-168">The overview page provides a summary:</span></span>
    1. <span data-ttu-id="9921f-169">發生什麼事</span><span class="sxs-lookup"><span data-stu-id="9921f-169">of what happened</span></span>
    1. <span data-ttu-id="9921f-170">誰執行導致原則相符的動作</span><span class="sxs-lookup"><span data-stu-id="9921f-170">who performed the actions that caused the policy match</span></span>
    1. <span data-ttu-id="9921f-171">相符原則的相關資訊，以及其他</span><span class="sxs-lookup"><span data-stu-id="9921f-171">information about the matched policy, and more</span></span> 

6. <span data-ttu-id="9921f-172">選擇 [ **事件** ] 索引標籤，存取：</span><span class="sxs-lookup"><span data-stu-id="9921f-172">Choose the **Events** tab to access the:</span></span>
    1. <span data-ttu-id="9921f-173">相關內容</span><span class="sxs-lookup"><span data-stu-id="9921f-173">content involved</span></span>
    1. <span data-ttu-id="9921f-174">符合的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="9921f-174">sensitive information types matched</span></span>
    1. <span data-ttu-id="9921f-175">元</span><span class="sxs-lookup"><span data-stu-id="9921f-175">metadata</span></span>

7. <span data-ttu-id="9921f-176">選取 [ **敏感資訊類型** ] 索引標籤，以查看內容中偵測到的敏感資訊類型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9921f-176">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="9921f-177">詳細資料包括信賴、計數，以及符合敏感資訊類型的內容。</span><span class="sxs-lookup"><span data-stu-id="9921f-177">Details include confidence, count, and the content that matches the sensitive information type.</span></span>

8. <span data-ttu-id="9921f-178">在調查提醒後，請回到 [ **概述** ] 索引標籤，以供您管理會審及管理提醒的處理及新增批註。</span><span class="sxs-lookup"><span data-stu-id="9921f-178">After you investigate the alert, return to the **Overview** tab where you can manage triage and manage the disposition of the alert and add comments.</span></span>

- <span data-ttu-id="9921f-179">若要查看工作流程管理的史，請選擇 [ **記錄管理**]。</span><span class="sxs-lookup"><span data-stu-id="9921f-179">To see the history of workflow management, choose **Management log**.</span></span>
- <span data-ttu-id="9921f-180">針對警示採取必要的動作後，請將警示的狀態設定為 [ **已解決**]。</span><span class="sxs-lookup"><span data-stu-id="9921f-180">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9921f-181">另請參閱</span><span class="sxs-lookup"><span data-stu-id="9921f-181">See also</span></span>

- [<span data-ttu-id="9921f-182">深入瞭解資料遺失防護警示及警示儀表板</span><span class="sxs-lookup"><span data-stu-id="9921f-182">Learn about data loss prevention alerts and the alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)
- [<span data-ttu-id="9921f-183">建立、測試及調整 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="9921f-183">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)