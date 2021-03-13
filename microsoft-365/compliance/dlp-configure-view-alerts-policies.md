---
title: 設定和檢視 DLP 原則的警示 (預覽)
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
description: 瞭解如何定義及管理 DLP 原則的警示。
ms.openlocfilehash: 7bc9d9b59c0424792f995be42591548b758c99ec
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766418"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a><span data-ttu-id="604a3-103">設定及查看 DLP 原則的警示 (預覽) </span><span class="sxs-lookup"><span data-stu-id="604a3-103">Configure and view alerts for DLP polices (preview)</span></span>

<span data-ttu-id="604a3-104">本文說明如何定義與資料遺失防護 (DLP) 原則相關聯的各種警示原則。</span><span class="sxs-lookup"><span data-stu-id="604a3-104">This article shows you how to define rich alert policies that are linked to your data loss prevention (DLP) policies.</span></span> <span data-ttu-id="604a3-105">您將會瞭解如何使用 [Microsoft 365 相容性中心](https://compliance.microsoft.com/) 的新 DLP 警示管理儀表板來查看警示、事件，以及與 DLP 原則違規相關聯的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="604a3-105">You'll see how to use the new DLP alert management dashboard in the [Microsoft 365 compliance center](https://compliance.microsoft.com/) to view alerts, events, and associated metadata for DLP policy violations.</span></span>

## <a name="features"></a><span data-ttu-id="604a3-106">功能</span><span class="sxs-lookup"><span data-stu-id="604a3-106">Features</span></span>

<span data-ttu-id="604a3-107">以下是此預覽的一部分功能：</span><span class="sxs-lookup"><span data-stu-id="604a3-107">The following features are part of this preview:</span></span>

-   <span data-ttu-id="604a3-108">**DLP 警示管理儀表板**：在 [Microsoft 365 規範中心](https://compliance.microsoft.com/)內，此儀表板會顯示在下列工作負載中強制執行之 DLP 原則的警示：</span><span class="sxs-lookup"><span data-stu-id="604a3-108">**DLP alert management dashboard**: In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), this dashboard shows alerts for DLP policies that are enforced on the following workloads:</span></span>

    -   <span data-ttu-id="604a3-109">Exchange</span><span class="sxs-lookup"><span data-stu-id="604a3-109">Exchange</span></span>
    -   <span data-ttu-id="604a3-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="604a3-110">SharePoint</span></span>
    -   <span data-ttu-id="604a3-111">OneDrive</span><span class="sxs-lookup"><span data-stu-id="604a3-111">OneDrive</span></span>
    -   <span data-ttu-id="604a3-112">Teams</span><span class="sxs-lookup"><span data-stu-id="604a3-112">Teams</span></span>
    -   <span data-ttu-id="604a3-113">裝置</span><span class="sxs-lookup"><span data-stu-id="604a3-113">Devices</span></span>
-   <span data-ttu-id="604a3-114">**高級警示設定選項**：這些選項是 DLP 原則撰寫流程的一部分。</span><span class="sxs-lookup"><span data-stu-id="604a3-114">**Advanced alert configuration options**: These options are part of the DLP policy authoring flow.</span></span> <span data-ttu-id="604a3-115">使用它們來建立豐富的警示設定。</span><span class="sxs-lookup"><span data-stu-id="604a3-115">Use them to create rich alert configurations.</span></span> <span data-ttu-id="604a3-116">您可以根據事件數目或洩漏的資料大小，來建立單一事件警示或匯總警示。</span><span class="sxs-lookup"><span data-stu-id="604a3-116">You can create a single-event alert or an aggregated alert, based on the number of events or the size of the leaked data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="604a3-117">事前準備</span><span class="sxs-lookup"><span data-stu-id="604a3-117">Before you begin</span></span>

<span data-ttu-id="604a3-118">開始之前，請確定您具備必要的必要條件：</span><span class="sxs-lookup"><span data-stu-id="604a3-118">Before you begin, make sure you have the necessary prerequisites:</span></span>

-   <span data-ttu-id="604a3-119">DLP 警示管理儀表板的授權</span><span class="sxs-lookup"><span data-stu-id="604a3-119">Licensing for the DLP alerts management dashboard</span></span>
-   <span data-ttu-id="604a3-120">警示設定選項的授權</span><span class="sxs-lookup"><span data-stu-id="604a3-120">Licensing for alert configuration options</span></span>
-   <span data-ttu-id="604a3-121">角色</span><span class="sxs-lookup"><span data-stu-id="604a3-121">Roles</span></span>

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a><span data-ttu-id="604a3-122">DLP 警示管理儀表板的授權</span><span class="sxs-lookup"><span data-stu-id="604a3-122">Licensing for the DLP alert management dashboard</span></span>

<span data-ttu-id="604a3-123">Office 365 DLP 所有合格租使用者皆可存取新的 DLP 警示管理儀表板。</span><span class="sxs-lookup"><span data-stu-id="604a3-123">All eligible tenants for Office 365 DLP can access the new DLP alert management dashboard.</span></span> <span data-ttu-id="604a3-124">若要開始，您應該具備適用于 Exchange Online、SharePoint 線上和商務 OneDrive 的 Office 365 DLP。</span><span class="sxs-lookup"><span data-stu-id="604a3-124">To get started, you should be eligible for Office 365 DLP for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="604a3-125">如需有關 Office 365 DLP 授權需求的詳細資訊，請參閱 [哪些授權可為使用者提供從服務受益的許可權？](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。</span><span class="sxs-lookup"><span data-stu-id="604a3-125">For more information about the licensing requirements for Office 365 DLP, see [Which licenses provide the rights for a user to benefit from the service?](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16).</span></span>

<span data-ttu-id="604a3-126">參與 [端點 dlp](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) 公開預覽或具備 [團隊 dlp](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) 資格之使用者的客戶，將會看到其 Endpoint Dlp 原則警示和團隊 dlp 警示管理儀表板中的「dlp 原則警示」。</span><span class="sxs-lookup"><span data-stu-id="604a3-126">Customers who participate in the [Endpoint DLP](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide) public preview or who are eligible for [Teams DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.</span></span>

### <a name="licensing-for-alert-configuration-options"></a><span data-ttu-id="604a3-127">警示設定選項的授權</span><span class="sxs-lookup"><span data-stu-id="604a3-127">Licensing for alert configuration options</span></span>

-   <span data-ttu-id="604a3-128">**單一事件警示** 設定：具有 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱的組織，只會建立在每次發生活動時觸發警示的警示原則。</span><span class="sxs-lookup"><span data-stu-id="604a3-128">**Single-event alert configuration**: Organizations that have an E1, F1, or G1 subscription or an E3 or G3 subscription can create alert policies only where an alert is triggered every time an activity occurs.</span></span>
-   <span data-ttu-id="604a3-129">**匯總的警示** 設定：若要根據臨界值來設定匯總警示原則，您必須具有下列任一設定：</span><span class="sxs-lookup"><span data-stu-id="604a3-129">**Aggregated alert configuration**: To configure aggregate alert policies based on a threshold, you must have either of the following configurations:</span></span>
    -   <span data-ttu-id="604a3-130">E5 或 G5 訂閱</span><span class="sxs-lookup"><span data-stu-id="604a3-130">An E5 or G5 subscription</span></span>
    -   <span data-ttu-id="604a3-131">具有下列其中一項功能的 E1、F1 或 G1 訂閱或 E3 或 G3 訂閱：</span><span class="sxs-lookup"><span data-stu-id="604a3-131">An E1, F1, or G1 subscription or an E3 or G3 subscription that includes one of the following features:</span></span>
        -   <span data-ttu-id="604a3-132">Office 365 進階威脅防護方案 2</span><span class="sxs-lookup"><span data-stu-id="604a3-132">Office 365 Advanced Threat Protection Plan 2</span></span>
        -   <span data-ttu-id="604a3-133">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="604a3-133">Microsoft 365 E5 Compliance</span></span>
        -   <span data-ttu-id="604a3-134">Microsoft 365 電子檔探索和審核附加元件授權</span><span class="sxs-lookup"><span data-stu-id="604a3-134">Microsoft 365 eDiscovery and Audit add-on license</span></span>

### <a name="roles"></a><span data-ttu-id="604a3-135">角色</span><span class="sxs-lookup"><span data-stu-id="604a3-135">Roles</span></span>

<span data-ttu-id="604a3-136">如果您想要查看 DLP 警示管理儀表板，或編輯 DLP 原則中的警示設定選項，您必須是下列其中一個角色群組的成員：</span><span class="sxs-lookup"><span data-stu-id="604a3-136">If you want to view the DLP alert management dashboard or to edit the alert configuration options in a DLP policy, you must be a member of one of these role groups:</span></span>

-   <span data-ttu-id="604a3-137">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="604a3-137">Compliance Administrator</span></span>
-   <span data-ttu-id="604a3-138">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="604a3-138">Compliance Data Administrator</span></span>
-   <span data-ttu-id="604a3-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="604a3-139">Security Administrator</span></span>
-   <span data-ttu-id="604a3-140">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="604a3-140">Security Operator</span></span>
-   <span data-ttu-id="604a3-141">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="604a3-141">Security Reader</span></span>

<span data-ttu-id="604a3-142">若要存取 DLP 警示管理儀表板，您需要「管理警示」角色及下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="604a3-142">To access the DLP alert management dashboard, you need the Manage alerts role and either of the following roles:</span></span>

-   <span data-ttu-id="604a3-143">DLP 合規性管理</span><span class="sxs-lookup"><span data-stu-id="604a3-143">DLP Compliance Management</span></span>
-   <span data-ttu-id="604a3-144">僅限檢視 DLP 合規性管理</span><span class="sxs-lookup"><span data-stu-id="604a3-144">View-Only DLP Compliance Management</span></span>

## <a name="alert-configuration-experience"></a><span data-ttu-id="604a3-145">警示設定經驗</span><span class="sxs-lookup"><span data-stu-id="604a3-145">Alert configuration experience</span></span>

<span data-ttu-id="604a3-146">如果您符合匯總的 [警示設定選項](#licensing-for-alert-configuration-options)，您可以在 DLP 原則製作體驗中看到下列內嵌選項。</span><span class="sxs-lookup"><span data-stu-id="604a3-146">If you're eligible for [aggregated alert configuration options](#licensing-for-alert-configuration-options), then you see the following options inline in the DLP policy authoring experience.</span></span>

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="螢幕擷取畫面顯示適用于已匯總警示設定選項之使用者的附隨報告選項。" border="false":::

<span data-ttu-id="604a3-148">您可以使用這些警示設定選項，設定定義在觸發警示之前可以進行 DLP 規則相符的頻率。</span><span class="sxs-lookup"><span data-stu-id="604a3-148">You can use these alert configuration options to configure a setting that defines how often a DLP rule match can occur before an alert is triggered.</span></span> <span data-ttu-id="604a3-149">這項設定可讓您設定原則，以在每次活動符合原則條件時或超過特定臨界值時，根據活動數量或根據挾帶資料量的數量來產生警示。</span><span class="sxs-lookup"><span data-stu-id="604a3-149">This configuration allows you to set up a policy to generate an alert every time an activity matches the policy conditions or when a certain threshold is exceeded, based on the number of activities or based on the volume of exfiltrated data.</span></span>

<span data-ttu-id="604a3-150">如果您符合 [單一事件警示設定選項](#licensing-for-alert-configuration-options)，則會在 DLP 原則製作體驗中看到下列警示設定選項。</span><span class="sxs-lookup"><span data-stu-id="604a3-150">If you're eligible for [single-event alert configuration options](#licensing-for-alert-configuration-options), then you see the following alert configuration option in the DLP policy authoring experience.</span></span> <span data-ttu-id="604a3-151">使用此選項，可建立每當 DLP 規則比對使用者活動發生時，每次都會引發的警示。</span><span class="sxs-lookup"><span data-stu-id="604a3-151">Use this option to create an alert that's raised every time a DLP rule match happens because of a user activity.</span></span>

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="螢幕擷取畫面顯示適用于單一事件警示設定選項的使用者附隨報告選項。" border="false":::

## <a name="dlp-alert-management-dashboard"></a><span data-ttu-id="604a3-153">DLP 警示管理儀表板</span><span class="sxs-lookup"><span data-stu-id="604a3-153">DLP alert management dashboard</span></span>

<span data-ttu-id="604a3-154">若要使用 DLP 警示管理儀表板：</span><span class="sxs-lookup"><span data-stu-id="604a3-154">To work with the DLP alert management dashboard:</span></span>

1.  <span data-ttu-id="604a3-155">在 [Microsoft 365 規範中心](https://www.compliance.microsoft.com)內，移至 [ **資料遺失防護**]。</span><span class="sxs-lookup"><span data-stu-id="604a3-155">In the [Microsoft 365 compliance center](https://www.compliance.microsoft.com), go to **Data Loss Prevention**.</span></span>

2.  <span data-ttu-id="604a3-156">選取 [ **警示** ] 索引標籤，以查看 [DLP 警示] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="604a3-156">Select the **Alerts** tab to view the DLP alerts dashboard.</span></span>

    -   <span data-ttu-id="604a3-157">選擇 [篩選] 以精煉警示清單。</span><span class="sxs-lookup"><span data-stu-id="604a3-157">Choose filters to refine the list of alerts.</span></span> <span data-ttu-id="604a3-158">選擇 [ **自訂欄位** ]，列出您要查看的屬性。</span><span class="sxs-lookup"><span data-stu-id="604a3-158">Choose **Customize columns** to list the properties you want to see.</span></span> <span data-ttu-id="604a3-159">您也可以選擇在任何欄中，以遞增或遞減順序排序警示。</span><span class="sxs-lookup"><span data-stu-id="604a3-159">You can also choose to sort the alerts in ascending or descending order in any column.</span></span>
    -   <span data-ttu-id="604a3-160">選取警示以查看詳細資料：</span><span class="sxs-lookup"><span data-stu-id="604a3-160">Select an alert to see details:</span></span>

        :::image type="content" source="../media/alert-details.png" alt-text="螢幕擷取畫面顯示 DLP 警示管理儀表板上的警示詳細資料。" border="false":::

1.  <span data-ttu-id="604a3-162">選取 [ **事件** ] 索引標籤，以查看與警示相關聯的所有事件。</span><span class="sxs-lookup"><span data-stu-id="604a3-162">Select the **Events** tab to view all of the events associated with the alert.</span></span> <span data-ttu-id="604a3-163">您可以選擇特定的事件來查看其詳細資料。</span><span class="sxs-lookup"><span data-stu-id="604a3-163">You can choose a particular event to view its details.</span></span>
    <span data-ttu-id="604a3-164">下表顯示一些事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="604a3-164">The following table shows some of the event details.</span></span>
    
    | <span data-ttu-id="604a3-165">類別</span><span class="sxs-lookup"><span data-stu-id="604a3-165">Category</span></span>          | <span data-ttu-id="604a3-166">屬性名稱</span><span class="sxs-lookup"><span data-stu-id="604a3-166">Property name</span></span>                 | <span data-ttu-id="604a3-167">描述</span><span class="sxs-lookup"><span data-stu-id="604a3-167">Description</span></span>                                                                | <span data-ttu-id="604a3-168">適用的事件種類</span><span class="sxs-lookup"><span data-stu-id="604a3-168">Applicable event types</span></span>                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |<span data-ttu-id="604a3-169">*事件詳細資料*</span><span class="sxs-lookup"><span data-stu-id="604a3-169">*Event details*</span></span>||
    |      | <span data-ttu-id="604a3-170">識別碼</span><span class="sxs-lookup"><span data-stu-id="604a3-170">Id</span></span>                            | <span data-ttu-id="604a3-171">與事件相關聯的唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="604a3-171">Unique ID associated with the event</span></span>                                        | <span data-ttu-id="604a3-172">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-172">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-173">位置</span><span class="sxs-lookup"><span data-stu-id="604a3-173">Location</span></span>                      | <span data-ttu-id="604a3-174">偵測到事件的工作負載</span><span class="sxs-lookup"><span data-stu-id="604a3-174">Workload where the event was detected</span></span>                                      | <span data-ttu-id="604a3-175">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-175">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-176">啟用時間</span><span class="sxs-lookup"><span data-stu-id="604a3-176">Time of activity</span></span>              | <span data-ttu-id="604a3-177">導致 DLP 違規之使用者活動的時間</span><span class="sxs-lookup"><span data-stu-id="604a3-177">Time of the user activity that caused the DLP violation</span></span>                    | <span data-ttu-id="604a3-178">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-178">All events</span></span>                               |
    |<span data-ttu-id="604a3-179">*受影響實體*</span><span class="sxs-lookup"><span data-stu-id="604a3-179">*Impacted entities*</span></span>||
    |  | <span data-ttu-id="604a3-180">使用者</span><span class="sxs-lookup"><span data-stu-id="604a3-180">User</span></span>                          | <span data-ttu-id="604a3-181">導致 DLP 違規的使用者</span><span class="sxs-lookup"><span data-stu-id="604a3-181">User who caused the DLP violation</span></span>                                          | <span data-ttu-id="604a3-182">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-182">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-183">主機名稱</span><span class="sxs-lookup"><span data-stu-id="604a3-183">Hostname</span></span>                      | <span data-ttu-id="604a3-184">偵測到 DLP 侵犯之機器的主機名稱</span><span class="sxs-lookup"><span data-stu-id="604a3-184">Host name of the machine where the DLP violation was detected</span></span>              | <span data-ttu-id="604a3-185">裝置事件</span><span class="sxs-lookup"><span data-stu-id="604a3-185">Devices events</span></span>                           |
    |                   | <span data-ttu-id="604a3-186">IP 位址</span><span class="sxs-lookup"><span data-stu-id="604a3-186">IP address</span></span>                    | <span data-ttu-id="604a3-187">電腦的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="604a3-187">IP address of the machine</span></span>                                                  | <span data-ttu-id="604a3-188">裝置事件</span><span class="sxs-lookup"><span data-stu-id="604a3-188">Devices events</span></span>                           |
    |                   | <span data-ttu-id="604a3-189">檔案路徑</span><span class="sxs-lookup"><span data-stu-id="604a3-189">File path</span></span>                     | <span data-ttu-id="604a3-190">與非法相關之檔案的絕對路徑</span><span class="sxs-lookup"><span data-stu-id="604a3-190">Absolute path of the file involved in the violation</span></span>                        | <span data-ttu-id="604a3-191">SharePoint、OneDrive 和裝置事件</span><span class="sxs-lookup"><span data-stu-id="604a3-191">SharePoint, OneDrive, and Devices events</span></span> |
    |                   | <span data-ttu-id="604a3-192">電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="604a3-192">Email recipients</span></span>              | <span data-ttu-id="604a3-193">違反 DLP 原則的電子郵件收件者</span><span class="sxs-lookup"><span data-stu-id="604a3-193">Recipients of the email that violated the DLP policy</span></span>                       | <span data-ttu-id="604a3-194">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-194">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="604a3-195">電子郵件主旨</span><span class="sxs-lookup"><span data-stu-id="604a3-195">Email subject</span></span>                 | <span data-ttu-id="604a3-196">違反 DLP 原則的電子郵件主題</span><span class="sxs-lookup"><span data-stu-id="604a3-196">Subject of the email that violated the DLP policy</span></span>                          | <span data-ttu-id="604a3-197">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-197">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="604a3-198">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="604a3-198">Email attachments</span></span>             | <span data-ttu-id="604a3-199">違反 DLP 原則之電子郵件中的附件名稱</span><span class="sxs-lookup"><span data-stu-id="604a3-199">Names of the attachments in the email that violated the DLP policy</span></span>         | <span data-ttu-id="604a3-200">Exchange 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-200">Exchange events</span></span>                          |
    |                   | <span data-ttu-id="604a3-201">網站擁有人</span><span class="sxs-lookup"><span data-stu-id="604a3-201">Site owner</span></span>                    | <span data-ttu-id="604a3-202">網站擁有者的名稱</span><span class="sxs-lookup"><span data-stu-id="604a3-202">Name of the site owner</span></span>                                                     | <span data-ttu-id="604a3-203">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-203">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="604a3-204">網站 URL</span><span class="sxs-lookup"><span data-stu-id="604a3-204">Site URL</span></span>                      | <span data-ttu-id="604a3-205">SharePoint 或 OneDrive 網站的完整 URL</span><span class="sxs-lookup"><span data-stu-id="604a3-205">Full URL of the SharePoint or OneDrive site</span></span>                                | <span data-ttu-id="604a3-206">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-206">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="604a3-207">已建立檔案</span><span class="sxs-lookup"><span data-stu-id="604a3-207">File created</span></span>                  | <span data-ttu-id="604a3-208">檔建立時間</span><span class="sxs-lookup"><span data-stu-id="604a3-208">Time of file creation</span></span>                                                      | <span data-ttu-id="604a3-209">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-209">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="604a3-210">上次修改的檔案</span><span class="sxs-lookup"><span data-stu-id="604a3-210">File last modified</span></span>            | <span data-ttu-id="604a3-211">上次修改檔案的時間</span><span class="sxs-lookup"><span data-stu-id="604a3-211">Time of the last modification of the file</span></span>                                  | <span data-ttu-id="604a3-212">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-212">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="604a3-213">檔案大小</span><span class="sxs-lookup"><span data-stu-id="604a3-213">File size</span></span>                     | <span data-ttu-id="604a3-214">檔案大小</span><span class="sxs-lookup"><span data-stu-id="604a3-214">Size of the file</span></span>                                                           | <span data-ttu-id="604a3-215">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-215">SharePoint and OneDrive events</span></span>           |
    |                   | <span data-ttu-id="604a3-216">檔案擁有者</span><span class="sxs-lookup"><span data-stu-id="604a3-216">File owner</span></span>                    | <span data-ttu-id="604a3-217">檔案擁有者</span><span class="sxs-lookup"><span data-stu-id="604a3-217">Owner of the file</span></span>                                                          | <span data-ttu-id="604a3-218">SharePoint 和 OneDrive 事件</span><span class="sxs-lookup"><span data-stu-id="604a3-218">SharePoint and OneDrive events</span></span>           |
    |<span data-ttu-id="604a3-219">*原則詳細資料*</span><span class="sxs-lookup"><span data-stu-id="604a3-219">*Policy details*</span></span>||
    |     | <span data-ttu-id="604a3-220">符合的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="604a3-220">DLP policy matched</span></span>            | <span data-ttu-id="604a3-221">符合的 DLP 原則名稱</span><span class="sxs-lookup"><span data-stu-id="604a3-221">Name of the DLP policy that was matched</span></span>                                    | <span data-ttu-id="604a3-222">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-222">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-223">符合規則</span><span class="sxs-lookup"><span data-stu-id="604a3-223">Rule matched</span></span>                  | <span data-ttu-id="604a3-224">已符合之 DLP 原則中的 DLP 規則名稱</span><span class="sxs-lookup"><span data-stu-id="604a3-224">Name of the DLP rule in the DLP policy that was matched</span></span>                    | <span data-ttu-id="604a3-225">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-225">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-226">偵測到敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="604a3-226">Sensitive info types detected</span></span> | <span data-ttu-id="604a3-227">以 DLP 原則的一部分偵測到的敏感資訊類型</span><span class="sxs-lookup"><span data-stu-id="604a3-227">Sensitive information types that were detected as a part of the DLP policy</span></span> | <span data-ttu-id="604a3-228">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-228">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-229">採取的動作</span><span class="sxs-lookup"><span data-stu-id="604a3-229">Actions taken</span></span>                 | <span data-ttu-id="604a3-230">做為符合的 DLP 原則的一部分採取的動作</span><span class="sxs-lookup"><span data-stu-id="604a3-230">Actions taken as a part of the matched DLP policy</span></span>                          | <span data-ttu-id="604a3-231">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-231">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-232">使用者 overrode 原則</span><span class="sxs-lookup"><span data-stu-id="604a3-232">User overrode policy</span></span>          | <span data-ttu-id="604a3-233">使用者是否透過原則提示來 overrode 原則</span><span class="sxs-lookup"><span data-stu-id="604a3-233">Whether the user overrode the policy through the policy tip</span></span>                | <span data-ttu-id="604a3-234">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-234">All events</span></span>                               |
    |                   | <span data-ttu-id="604a3-235">覆寫對齊文字</span><span class="sxs-lookup"><span data-stu-id="604a3-235">Override justification text</span></span>   | <span data-ttu-id="604a3-236">提供以覆寫原則提示的理由</span><span class="sxs-lookup"><span data-stu-id="604a3-236">Justification provided to override the policy tip</span></span>                          | <span data-ttu-id="604a3-237">所有事件</span><span class="sxs-lookup"><span data-stu-id="604a3-237">All events</span></span>                               |
    
1.  <span data-ttu-id="604a3-238">選取 [ **敏感資訊類型** ] 索引標籤，以查看內容中偵測到的敏感資訊類型的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="604a3-238">Select the **Sensitive Info Types** tab to view details about the sensitive information types detected in the content.</span></span> <span data-ttu-id="604a3-239">詳細資料包括自信和計數。</span><span class="sxs-lookup"><span data-stu-id="604a3-239">Details include confidence and count.</span></span>

2.  <span data-ttu-id="604a3-240">調查警示之後，請選擇 [ **管理警示** **]，以變更狀態 (使用** 中、 **調查**、 **消除** 或 **解決**) 。</span><span class="sxs-lookup"><span data-stu-id="604a3-240">After you investigate the alert, choose **Manage alert** to change the status (**Active**, **Investigating**, **Dismissed**, or **Resolved**).</span></span> <span data-ttu-id="604a3-241">您也可以新增批註，並將提醒指派給組織中的某人。</span><span class="sxs-lookup"><span data-stu-id="604a3-241">You can also add comments and assign the alert to someone in your organization.</span></span>

    -   <span data-ttu-id="604a3-242">若要查看工作流程管理的史，請選擇 [ **記錄管理**]。</span><span class="sxs-lookup"><span data-stu-id="604a3-242">To see the history of workflow management, choose **Management log**.</span></span>
    -   <span data-ttu-id="604a3-243">針對警示採取必要的動作後，請將警示的狀態設定為 [ **已解決**]。</span><span class="sxs-lookup"><span data-stu-id="604a3-243">After you take the required action for the alert, set the status of the alert to **Resolved**.</span></span>
