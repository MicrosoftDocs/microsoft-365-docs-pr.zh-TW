---
title: 設定及查看資料遺失防護原則的警示
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
description: 瞭解如何定義及管理資料遺失防護原則的警示。
ms.openlocfilehash: ee04f6080edcde86dc39c7f4aa43130223fee8bf
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750035"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a><span data-ttu-id="96031-103">設定及查看資料遺失防護策略的警示</span><span class="sxs-lookup"><span data-stu-id="96031-103">Configure and view alerts for data loss prevention polices</span></span>

<span data-ttu-id="96031-104">資料遺失防護 (DLP) 原則可以採取保護性動作，以防止意外共用機密專案。</span><span class="sxs-lookup"><span data-stu-id="96031-104">Data loss prevention (DLP) polices can take protective actions to prevent unintentional sharing of sensitive items.</span></span> <span data-ttu-id="96031-105">針對敏感專案採取動作時，您可以設定 DLP 的警示來通知您。</span><span class="sxs-lookup"><span data-stu-id="96031-105">When an action is taken on a sensitive item, you can be notified by configuring alerts for DLP.</span></span> <span data-ttu-id="96031-106">本文說明如何定義與資料遺失防護 (DLP) 原則相關聯的各種警示原則。</span><span class="sxs-lookup"><span data-stu-id="96031-106">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="96031-107">您將會瞭解如何使用[Microsoft 365 規範中心](https://compliance.microsoft.com/)內的新 DLP 警示管理儀表板，來查看警示、事件，以及與 DLP 原則違規相關聯的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="96031-107">You'll see how to use the new DLP alert management dashboard in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

<!-- LEFT OFF HERE-->

## <a name="features"></a><span data-ttu-id="96031-108">功能</span><span class="sxs-lookup"><span data-stu-id="96031-108">Features</span></span>

<span data-ttu-id="96031-109">下列功能屬於這種情況：</span><span class="sxs-lookup"><span data-stu-id="96031-109">The following features are part of this:</span></span>

-   <span data-ttu-id="96031-110">**DLP 警示管理儀表板**：在 [Microsoft 365 規範中心](https://compliance.microsoft.com/)，此儀表板會顯示在下列工作負載上強制執行之 DLP 原則的警示：</span><span class="sxs-lookup"><span data-stu-id="96031-110">**DLP alert management dashboard**: In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), this dashboard shows alerts for DLP policies that are enforced on the following workloads:</span></span>

    -   <span data-ttu-id="96031-111">Exchange</span><span class="sxs-lookup"><span data-stu-id="96031-111">Exchange</span></span>
    -   <span data-ttu-id="96031-112">SharePoint</span><span class="sxs-lookup"><span data-stu-id="96031-112">SharePoint</span></span>
    -   <span data-ttu-id="96031-113">OneDrive</span><span class="sxs-lookup"><span data-stu-id="96031-113">OneDrive</span></span>
    -   <span data-ttu-id="96031-114">Teams</span><span class="sxs-lookup"><span data-stu-id="96031-114">Teams</span></span>
    -   <span data-ttu-id="96031-115">裝置</span><span class="sxs-lookup"><span data-stu-id="96031-115">Devices</span></span>
-   <span data-ttu-id="96031-116">**高級警示設定選項**：這些選項是 DLP 原則撰寫流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="96031-116">**Advanced alert configuration options**: These options are part of the DLP policy authoring flow.</span></span> <span data-ttu-id="96031-117">使用它們來建立豐富的警示設定。</span><span class="sxs-lookup"><span data-stu-id="96031-117">Use them to create rich alert configurations.</span></span> <span data-ttu-id="96031-118">您可以根據事件數目或洩漏的資料大小，來建立單一事件警示或匯總警示。</span><span class="sxs-lookup"><span data-stu-id="96031-118">You can create a single-event alert or an aggregated alert, based on the number of events or the size of the leaked data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="96031-119">開始之前</span><span class="sxs-lookup"><span data-stu-id="96031-119">Before you begin</span></span>

<span data-ttu-id="96031-120">開始之前，請確定您具備必要的必要條件：</span><span class="sxs-lookup"><span data-stu-id="96031-120">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="96031-121">DLP 警示管理儀表板的授權</span><span class="sxs-lookup"><span data-stu-id="96031-121">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="96031-122">警示設定選項的授權</span><span class="sxs-lookup"><span data-stu-id="96031-122">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="96031-123">角色</span><span class="sxs-lookup"><span data-stu-id="96031-123">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="96031-124">DLP 警示管理儀表板的授權</span><span class="sxs-lookup"><span data-stu-id="96031-124">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="96031-125">Office 365 DLP 的所有合格租使用者皆可存取新的 DLP 警示管理儀表板。</span><span class="sxs-lookup"><span data-stu-id="96031-125">All eligible tenants for Office 365 DLP can access the new DLP alert management dashboard.</span></span> <span data-ttu-id="96031-126">若要開始，您應該具備 Office 365 DLP Exchange Online、SharePoint 線上及商務用 OneDrive 的資格。</span><span class="sxs-lookup"><span data-stu-id="96031-126">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="96031-127">如需 Office 365 DLP 之授權需求的詳細資訊，請參閱[哪些授權可為使用者提供從服務受益的許可權？](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。</span><span class="sxs-lookup"><span data-stu-id="96031-127">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="96031-128">使用適用于[Teams DLP](dlp-microsoft-teams.md)之[endpoint dlp](endpoint-dlp-learn-about.md)的客戶，將會看到其 endpoint dlp 原則警示，並 Teams dlp 警示管理儀表板中的 dlp 原則警示。</span><span class="sxs-lookup"><span data-stu-id="96031-128">Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="96031-129">警示設定選項的授權</span><span class="sxs-lookup"><span data-stu-id="96031-129">Licensing for alert configuration options</span></span>

-   <span data-ttu-id="96031-130">**單一事件警示** 設定：具有 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱的組織，只會建立在每次發生活動時觸發警示的警示原則。</span><span class="sxs-lookup"><span data-stu-id="96031-130">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>
-   <span data-ttu-id="96031-131">**匯總的警示** 設定：若要根據臨界值來設定匯總警示原則，您必須具有下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="96031-131">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must have either of the following configurations:</span></span>
    -   <span data-ttu-id="96031-132">E5 或 G5 訂閱</span><span class="sxs-lookup"><span data-stu-id="96031-132">An E5 or G5 subscription</span></span>
    -   <span data-ttu-id="96031-133">具有下列其中一項功能的 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱：</span><span class="sxs-lookup"><span data-stu-id="96031-133">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
        -   <span data-ttu-id="96031-134">Office 365 進階威脅防護方案 2</span><span class="sxs-lookup"><span data-stu-id="96031-134">Office 365 Advanced Threat Protection Plan 2</span></span>
        -   <span data-ttu-id="96031-135">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="96031-135">Microsoft 365 E5 Compliance</span></span>
        -   <span data-ttu-id="96031-136">Microsoft 365 電子檔探索和審計附加元件授權</span><span class="sxs-lookup"><span data-stu-id="96031-136">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="96031-137">角色</span><span class="sxs-lookup"><span data-stu-id="96031-137">Roles</span></span>

<span data-ttu-id="96031-138">如果您想要查看 DLP 警示管理儀表板，或編輯 DLP 原則中的警示設定選項，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="96031-138">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

-   <span data-ttu-id="96031-139">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="96031-139">Compliance Administrator</span></span>
-   <span data-ttu-id="96031-140">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="96031-140">Compliance Data Administrator</span></span>
-   <span data-ttu-id="96031-141">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="96031-141">Security Administrator</span></span>
-   <span data-ttu-id="96031-142">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="96031-142">Security Operator</span></span>
-   <span data-ttu-id="96031-143">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="96031-143">Security Reader</span></span>

<span data-ttu-id="96031-144">若要存取 DLP 警示管理儀表板，您需要「管理警示」角色及下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="96031-144">To access the DLP alert management dashboard, you need the Manage alerts role and either of the following roles:</span></span>

-   <span data-ttu-id="96031-145">DLP 合規性管理</span><span class="sxs-lookup"><span data-stu-id="96031-145">DLP Compliance Management</span></span>
-   <span data-ttu-id="96031-146">僅限檢視 DLP 合規性管理</span><span class="sxs-lookup"><span data-stu-id="96031-146">View-Only DLP Compliance Management</span></span>

## <a name="alert-configuration-experience"></a><span data-ttu-id="96031-147">警示設定經驗</span><span class="sxs-lookup"><span data-stu-id="96031-147">Alert configuration experience</span></span>

<span data-ttu-id="96031-148">如果您符合匯總的 [警示設定選項](#licensing-for-alert-configuration-options)，您可以在 DLP 原則製作體驗中看到下列內嵌選項。</span><span class="sxs-lookup"><span data-stu-id="96031-148">If you're eligible for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you see the following options inline in the DLP policy authoring experience.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="螢幕擷取畫面顯示適用于已匯總警示設定選項之使用者的附隨報告選項。" border="false":::

<span data-ttu-id="96031-150">您可以使用這些警示設定選項，設定定義在觸發警示之前可以進行 DLP 規則相符的頻率。</span><span class="sxs-lookup"><span data-stu-id="96031-150">You can use these alert configuration options to configure a setting that defines how often a DLP rule match can occur before an alert is triggered.</span></span> <span data-ttu-id="96031-151">這項設定可讓您設定原則，以在每次活動符合原則條件時或超過特定臨界值時，根據活動數量或根據挾帶資料量的數量來產生警示。</span><span class="sxs-lookup"><span data-stu-id="96031-151">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

<span data-ttu-id="96031-152">如果您符合 [單一事件警示設定選項](#licensing-for-alert-configuration-options)，則會在 DLP 原則製作體驗中看到下列警示設定選項。</span><span class="sxs-lookup"><span data-stu-id="96031-152">If you're eligible for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you see the following alert configuration option in the DLP policy authoring experience.</span></span> <span data-ttu-id="96031-153">使用此選項，可建立每當 DLP 規則比對使用者活動發生時，每次都會引發的警示。</span><span class="sxs-lookup"><span data-stu-id="96031-153">Use this option to create an alert that's raised every time a DLP rule match happens because of a user activity.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="螢幕擷取畫面顯示適用于單一事件警示設定選項的使用者附隨報告選項。" border="false":::

## <a name="dlp-alert-management-dashboard"></a><span data-ttu-id="96031-155">DLP 警示管理儀表板</span><span class="sxs-lookup"><span data-stu-id="96031-155">DLP alert management dashboard</span></span>

<span data-ttu-id="96031-156">若要使用 DLP 警示管理儀表板：</span><span class="sxs-lookup"><span data-stu-id="96031-156">To work with the DLP alert management dashboard:</span></span>

1.  <span data-ttu-id="96031-157">在 [Microsoft 365 規範中心](https://www.compliance.microsoft.com)] 中，移至 [**資料遺失防護**]。</span><span class="sxs-lookup"><span data-stu-id="96031-157">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>

2.  <span data-ttu-id="96031-158">選取 [ **警示** ] 索引標籤，以查看 [DLP 警示] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="96031-158">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>

    -   <span data-ttu-id="96031-159">選擇 [篩選] 以精煉警示清單。</span><span class="sxs-lookup"><span data-stu-id="96031-159">Choose filters to refine the list of alerts.</span></span> <span data-ttu-id="96031-160">選擇 [ **自訂欄位** ]，列出您要查看的屬性。</span><span class="sxs-lookup"><span data-stu-id="96031-160">Choose **Customize columns** to list the properties you want to see.</span></span> <span data-ttu-id="96031-161">您也可以選擇在任何欄中，以遞增或遞減順序排序警示。</span><span class="sxs-lookup"><span data-stu-id="96031-161">You can also choose to sort the alerts in ascending or descending order in any column.</span></span>
    -   <span data-ttu-id="96031-162">選取警示以查看詳細資料：</span><span class="sxs-lookup"><span data-stu-id="96031-162">Select an alert to see details:</span></span>

        :::image type="content" source="../media/alert-details.png" alt-text="螢幕擷取畫面顯示 DLP 警示管理儀表板上的警示詳細資料。" border="false":::

1.  <span data-ttu-id="96031-164">選取 [ **事件** ] 索引標籤，以查看與警示相關聯的所有事件。</span><span class="sxs-lookup"><span data-stu-id="96031-164">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="96031-165">您可以選擇特定的事件來查看其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="96031-165">You can choose a particular event to view its details.</span></span>
    <span data-ttu-id="96031-166">下表顯示一些事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="96031-166">The following table shows some of the event details.</span></span>
    
    | <span data-ttu-id="96031-167">類別</span><span class="sxs-lookup"><span data-stu-id="96031-167">Category</span></span>          | <span data-ttu-id="96031-168">屬性名稱</span><span class="sxs-lookup"><span data-stu-id="96031-168">Property name</span></span>                 | <span data-ttu-id="96031-169">描述</span><span class="sxs-lookup"><span data-stu-id="96031-169">Description</span></span>                                                                | <span data-ttu-id="96031-170">適用的事件種類</span><span class="sxs-lookup"><span data-stu-id="96031-170">Applicable event types</span></span>                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |<span data-ttu-id="96031-171">*事件詳細資料*</span><span class="sxs-lookup"><span data-stu-id="96031-171">*Event details*</span></span>||
    |      | <span data-ttu-id="96031-172">識別碼</span><span class="sxs-lookup"><span data-stu-id="96031-172">Id</span></span>                            | <span data-ttu-id="96031-173">與事件相關聯的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="96031-173">Unique ID associated with the event</span></span>                                        | <span data-ttu-id="96031-174">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-174">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-175">位置</span><span class="sxs-lookup"><span data-stu-id="96031-175">Location</span></span>                      | <span data-ttu-id="96031-176">偵測到事件的工作負載</span><span class="sxs-lookup"><span data-stu-id="96031-176">Workload where the event was detected</span></span>                                      | <span data-ttu-id="96031-177">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-177">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-178">啟用時間</span><span class="sxs-lookup"><span data-stu-id="96031-178">Time of activity</span></span>              | <span data-ttu-id="96031-179">導致 DLP 違規之使用者活動的時間</span><span class="sxs-lookup"><span data-stu-id="96031-179">Time of the user activity that caused the DLP violation</span></span>                    | <span data-ttu-id="96031-180">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-180">All events</span></span>                               |
    |<span data-ttu-id="96031-181">*受影響實體*</span><span class="sxs-lookup"><span data-stu-id="96031-181">*Impacted entities*</span></span>||
    |  | <span data-ttu-id="96031-182">使用者</span><span class="sxs-lookup"><span data-stu-id="96031-182">User</span></span>                          | <span data-ttu-id="96031-183">導致 DLP 違規的使用者</span><span class="sxs-lookup"><span data-stu-id="96031-183">User who caused the DLP violation</span></span>                                          | <span data-ttu-id="96031-184">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-184">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-185">主機名稱</span><span class="sxs-lookup"><span data-stu-id="96031-185">Hostname</span></span>                      | <span data-ttu-id="96031-186">偵測到 DLP 侵犯之機器的主機名稱</span><span class="sxs-lookup"><span data-stu-id="96031-186">Host name of the machine where the DLP violation was detected</span></span>              | <span data-ttu-id="96031-187">裝置事件</span><span class="sxs-lookup"><span data-stu-id="96031-187">Devices events</span></span>                           |
    |                   | <span data-ttu-id="96031-188">IP 位址</span><span class="sxs-lookup"><span data-stu-id="96031-188">IP address</span></span>                    | <span data-ttu-id="96031-189">電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="96031-189">IP address of the machine</span></span>                                                  | <span data-ttu-id="96031-190">裝置事件</span><span class="sxs-lookup"><span data-stu-id="96031-190">Devices events</span></span>                           |
    |                   | <span data-ttu-id="96031-191">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="96031-191">File path</span></span>                     | <span data-ttu-id="96031-192">與非法相關之檔案的絕對路徑</span><span class="sxs-lookup"><span data-stu-id="96031-192">Absolute path of the file involved in the violation</span></span>                        | <span data-ttu-id="96031-193">SharePoint、OneDrive 和裝置事件</span><span class="sxs-lookup"><span data-stu-id="96031-193">SharePoint, OneDrive, and Devices events</span></span> |
    |                   | <span data-ttu-id="96031-194">電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="96031-194">Email recipients</span></span>              | <span data-ttu-id="96031-195">違反 DLP 原則的電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="96031-195">Recipients of the email that violated the DLP policy</span></span>                       | <span data-ttu-id="96031-196">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="96031-196">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="96031-197">電子郵件主旨</span><span class="sxs-lookup"><span data-stu-id="96031-197">Email subject</span></span>                 | <span data-ttu-id="96031-198">違反 DLP 原則的電子郵件主題</span><span class="sxs-lookup"><span data-stu-id="96031-198">Subject of the email that violated the DLP policy</span></span>                          | <span data-ttu-id="96031-199">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="96031-199">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="96031-200">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="96031-200">Email attachments</span></span>             | <span data-ttu-id="96031-201">違反 DLP 原則之電子郵件中的附件名稱</span><span class="sxs-lookup"><span data-stu-id="96031-201">Names of the attachments in the email that violated the DLP policy</span></span>         | <span data-ttu-id="96031-202">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="96031-202">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="96031-203">網站擁有人</span><span class="sxs-lookup"><span data-stu-id="96031-203">Site owner</span></span>                    | <span data-ttu-id="96031-204">網站擁有者的名稱</span><span class="sxs-lookup"><span data-stu-id="96031-204">Name of the site owner</span></span>                                                     | <span data-ttu-id="96031-205">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="96031-205">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="96031-206">網站 URL</span><span class="sxs-lookup"><span data-stu-id="96031-206">Site URL</span></span>                      | <span data-ttu-id="96031-207">SharePoint 或 OneDrive 網站的完整 URL</span><span class="sxs-lookup"><span data-stu-id="96031-207">Full URL of the SharePoint or OneDrive site</span></span>                                | <span data-ttu-id="96031-208">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="96031-208">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="96031-209">已建立檔案</span><span class="sxs-lookup"><span data-stu-id="96031-209">File created</span></span>                  | <span data-ttu-id="96031-210">檔建立時間</span><span class="sxs-lookup"><span data-stu-id="96031-210">Time of file creation</span></span>                                                      | <span data-ttu-id="96031-211">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="96031-211">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="96031-212">上次修改的檔案</span><span class="sxs-lookup"><span data-stu-id="96031-212">File last modified</span></span>            | <span data-ttu-id="96031-213">上次修改檔案的時間</span><span class="sxs-lookup"><span data-stu-id="96031-213">Time of the last modification of the file</span></span>                                  | <span data-ttu-id="96031-214">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="96031-214">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="96031-215">檔案大小</span><span class="sxs-lookup"><span data-stu-id="96031-215">File size</span></span>                     | <span data-ttu-id="96031-216">檔案大小</span><span class="sxs-lookup"><span data-stu-id="96031-216">Size of the file</span></span>                                                           | <span data-ttu-id="96031-217">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="96031-217">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="96031-218">檔案擁有者</span><span class="sxs-lookup"><span data-stu-id="96031-218">File owner</span></span>                    | <span data-ttu-id="96031-219">檔案擁有者</span><span class="sxs-lookup"><span data-stu-id="96031-219">Owner of the file</span></span>                                                          | <span data-ttu-id="96031-220">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="96031-220">SharePoint and OneDrive events</span></span>           |
    |<span data-ttu-id="96031-221">*原則詳細資料*</span><span class="sxs-lookup"><span data-stu-id="96031-221">*Policy details*</span></span>||
    |     | <span data-ttu-id="96031-222">符合的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="96031-222">DLP policy matched</span></span>            | <span data-ttu-id="96031-223">符合的 DLP 原則名稱</span><span class="sxs-lookup"><span data-stu-id="96031-223">Name of the DLP policy that was matched</span></span>                                    | <span data-ttu-id="96031-224">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-224">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-225">符合規則</span><span class="sxs-lookup"><span data-stu-id="96031-225">Rule matched</span></span>                  | <span data-ttu-id="96031-226">已符合之 DLP 原則中的 DLP 規則名稱</span><span class="sxs-lookup"><span data-stu-id="96031-226">Name of the DLP rule in the DLP policy that was matched</span></span>                    | <span data-ttu-id="96031-227">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-227">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-228">偵測到敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="96031-228">Sensitive info types detected</span></span> | <span data-ttu-id="96031-229">以 DLP 原則的一部分偵測到的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="96031-229">Sensitive information types that were detected as a part of the DLP policy</span></span> | <span data-ttu-id="96031-230">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-230">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-231">採取的動作</span><span class="sxs-lookup"><span data-stu-id="96031-231">Actions taken</span></span>                 | <span data-ttu-id="96031-232">做為符合的 DLP 原則的一部分採取的動作</span><span class="sxs-lookup"><span data-stu-id="96031-232">Actions taken as a part of the matched DLP policy</span></span>                          | <span data-ttu-id="96031-233">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-233">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-234">使用者 overrode 原則</span><span class="sxs-lookup"><span data-stu-id="96031-234">User overrode policy</span></span>          | <span data-ttu-id="96031-235">使用者是否透過原則提示來 overrode 原則</span><span class="sxs-lookup"><span data-stu-id="96031-235">Whether the user overrode the policy through the policy tip</span></span>                | <span data-ttu-id="96031-236">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-236">All events</span></span>                               |
    |                   | <span data-ttu-id="96031-237">覆寫對齊文字</span><span class="sxs-lookup"><span data-stu-id="96031-237">Override justification text</span></span>   | <span data-ttu-id="96031-238">提供以覆寫原則提示的理由</span><span class="sxs-lookup"><span data-stu-id="96031-238">Justification provided to override the policy tip</span></span>                          | <span data-ttu-id="96031-239">所有事件</span><span class="sxs-lookup"><span data-stu-id="96031-239">All events</span></span>                               |
    
1.  <span data-ttu-id="96031-240">選取 [ **敏感資訊類型** ] 索引標籤，以查看內容中偵測到的敏感資訊類型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="96031-240">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="96031-241">詳細資料包括自信和計數。</span><span class="sxs-lookup"><span data-stu-id="96031-241">Details include confidence and count.</span></span>

2.  <span data-ttu-id="96031-242">調查警示之後，請選擇 [ **管理警示** **]，以變更狀態 (使用** 中、 **調查**、 **消除** 或 **解決**) 。</span><span class="sxs-lookup"><span data-stu-id="96031-242">After you investigate the alert, choose **Manage alert** to change the status (**Active**, **Investigating**, **Dismissed**, or **Resolved**).</span></span> <span data-ttu-id="96031-243">您也可以新增批註，並將提醒指派給組織中的某人。</span><span class="sxs-lookup"><span data-stu-id="96031-243">You can also add comments and assign the alert to someone in your organization.</span></span>

    -   <span data-ttu-id="96031-244">若要查看工作流程管理的史，請選擇 [ **記錄管理**]。</span><span class="sxs-lookup"><span data-stu-id="96031-244">To see the history of workflow management, choose **Management log**.</span></span>
    -   <span data-ttu-id="96031-245">針對警示採取必要的動作後，請將警示的狀態設定為 [ **已解決**]。</span><span class="sxs-lookup"><span data-stu-id="96031-245">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>