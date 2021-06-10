---
title: 管理 Microsoft Defender for Endpoint 警示
description: 變更警示的狀態、建立抑制規則，以隱藏提醒、提交批註，以及使用「管理警示」功能表查看個別警示的變更歷程記錄。
keywords: 管理提醒、管理、警示、狀態、新、進行中、已解決、解決警告、抑制、supression、規則、內容、記錄、批註、變更
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
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186998"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="e9c00-104">管理 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="e9c00-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e9c00-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e9c00-105">**Applies to:**</span></span>
- [<span data-ttu-id="e9c00-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e9c00-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e9c00-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9c00-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="e9c00-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e9c00-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e9c00-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e9c00-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="e9c00-110">Defender for Endpoint 會透過提醒通知您可能的惡意事件、屬性和內容資訊。</span><span class="sxs-lookup"><span data-stu-id="e9c00-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="e9c00-111">[ **安全性作業] 儀表板** 會顯示新警示的摘要，您可以在 [ **警示] 佇列** 中存取所有警示。</span><span class="sxs-lookup"><span data-stu-id="e9c00-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="e9c00-112">您可以在 [ **警示] 佇列** 中選取警示，或個別裝置之 [裝置] 頁面的 [ **警示** ] 索引標籤，以管理提醒。</span><span class="sxs-lookup"><span data-stu-id="e9c00-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="e9c00-113">在其中一個位置選取警示會顯示 **警示管理窗格**。</span><span class="sxs-lookup"><span data-stu-id="e9c00-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![警示管理窗格和警示佇列的影像](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="e9c00-115">連結至另一個事件</span><span class="sxs-lookup"><span data-stu-id="e9c00-115">Link to another incident</span></span>
<span data-ttu-id="e9c00-116">您可以從警示中建立新的事件，或從現有的事件連結。</span><span class="sxs-lookup"><span data-stu-id="e9c00-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="e9c00-117">指派提醒</span><span class="sxs-lookup"><span data-stu-id="e9c00-117">Assign alerts</span></span>
<span data-ttu-id="e9c00-118">若尚未指派警示，您可以選取 [ **指派給我** ] 指派提醒給您自己。</span><span class="sxs-lookup"><span data-stu-id="e9c00-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="e9c00-119">抑制提醒</span><span class="sxs-lookup"><span data-stu-id="e9c00-119">Suppress alerts</span></span>
<span data-ttu-id="e9c00-120">在某些情況下，您可能需要抑制警告，使其不會出現在 Microsoft Defender 資訊安全中心中。</span><span class="sxs-lookup"><span data-stu-id="e9c00-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="e9c00-121">Defender for Endpoint 可讓您針對已知的特殊警示（如組織中的已知工具或處理常式），建立抑制規則。</span><span class="sxs-lookup"><span data-stu-id="e9c00-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="e9c00-122">抑制規則可以從現有的警示建立。</span><span class="sxs-lookup"><span data-stu-id="e9c00-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="e9c00-123">您可以視需要停用或重新啟用。</span><span class="sxs-lookup"><span data-stu-id="e9c00-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="e9c00-124">在建立抑制規則時，它會從建立規則的點生效。</span><span class="sxs-lookup"><span data-stu-id="e9c00-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="e9c00-125">在建立規則之前，規則不會影響佇列中已存在的警示。</span><span class="sxs-lookup"><span data-stu-id="e9c00-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="e9c00-126">規則只會在建立規則之後，于符合條件設定的警示上套用。</span><span class="sxs-lookup"><span data-stu-id="e9c00-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="e9c00-127">抑制規則有兩個內容可供您選擇：</span><span class="sxs-lookup"><span data-stu-id="e9c00-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="e9c00-128">**抑制此裝置上的警示**</span><span class="sxs-lookup"><span data-stu-id="e9c00-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="e9c00-129">**抑制組織中的警示**</span><span class="sxs-lookup"><span data-stu-id="e9c00-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="e9c00-130">規則的內容可讓您定制入口網站中所呈現的內容，並確保只會將實際的安全性警示放入入口網站中。</span><span class="sxs-lookup"><span data-stu-id="e9c00-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="e9c00-131">您可以使用下表中的範例，協助您選擇抑制規則的內容：</span><span class="sxs-lookup"><span data-stu-id="e9c00-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="e9c00-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="e9c00-132">**Context**</span></span>                           | <span data-ttu-id="e9c00-133">**定義**</span><span class="sxs-lookup"><span data-stu-id="e9c00-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="e9c00-134">**範例案例**</span><span class="sxs-lookup"><span data-stu-id="e9c00-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="e9c00-135">**抑制此裝置上的警示**</span><span class="sxs-lookup"><span data-stu-id="e9c00-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="e9c00-136">只有在該特定裝置上具有相同警示標題及的警示，才會遭到抑制。</span><span class="sxs-lookup"><span data-stu-id="e9c00-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="e9c00-137">將不會抑制該裝置上的所有其他警示。</span><span class="sxs-lookup"><span data-stu-id="e9c00-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="e9c00-138">安全性研究人員正在調查已用來攻擊組織中其他裝置的惡意腳本。</span><span class="sxs-lookup"><span data-stu-id="e9c00-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="e9c00-139">開發人員定期為小組建立 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="e9c00-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="e9c00-140">**抑制組織中的警示**</span><span class="sxs-lookup"><span data-stu-id="e9c00-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="e9c00-141">任何裝置上具有相同警示標題的警示都會遭到抑制。</span><span class="sxs-lookup"><span data-stu-id="e9c00-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="e9c00-142">您組織中的每個人都會使用良性系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="e9c00-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="e9c00-143">抑制警示並建立新的抑制規則：</span><span class="sxs-lookup"><span data-stu-id="e9c00-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="e9c00-144">建立自訂規則，以控制何時抑制或解決警告。</span><span class="sxs-lookup"><span data-stu-id="e9c00-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="e9c00-145">您可以指定警示標題、安全指示器及條件，以控制抑制警示的上下文。</span><span class="sxs-lookup"><span data-stu-id="e9c00-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="e9c00-146">在指定內容之後，您可以設定警示的動作和範圍。</span><span class="sxs-lookup"><span data-stu-id="e9c00-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="e9c00-147">選取您想要隱藏的警示。</span><span class="sxs-lookup"><span data-stu-id="e9c00-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="e9c00-148">這會顯示 **警示管理** 窗格。</span><span class="sxs-lookup"><span data-stu-id="e9c00-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="e9c00-149">選取 [ **建立抑制規則**]。</span><span class="sxs-lookup"><span data-stu-id="e9c00-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="e9c00-150">您可以使用這些屬性建立抑制條件。</span><span class="sxs-lookup"><span data-stu-id="e9c00-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="e9c00-151">每個條件間都會套用一個 AND 運算子，所以只有在符合所有條件時，才會發生抑制。</span><span class="sxs-lookup"><span data-stu-id="e9c00-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="e9c00-152">檔 SHA1</span><span class="sxs-lookup"><span data-stu-id="e9c00-152">File SHA1</span></span>
    * <span data-ttu-id="e9c00-153">檔案名-支援萬用字元</span><span class="sxs-lookup"><span data-stu-id="e9c00-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="e9c00-154">資料夾路徑-支援萬用字元</span><span class="sxs-lookup"><span data-stu-id="e9c00-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="e9c00-155">IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9c00-155">IP address</span></span>
    * <span data-ttu-id="e9c00-156">URL-支援萬用字元</span><span class="sxs-lookup"><span data-stu-id="e9c00-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="e9c00-157">命令列-支援萬用字元</span><span class="sxs-lookup"><span data-stu-id="e9c00-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="e9c00-158">選取 **觸發 IOC**。</span><span class="sxs-lookup"><span data-stu-id="e9c00-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="e9c00-159">指定警示的動作和範圍。</span><span class="sxs-lookup"><span data-stu-id="e9c00-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="e9c00-160">您可以自動解決或隱藏來自入口網站的警示。</span><span class="sxs-lookup"><span data-stu-id="e9c00-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="e9c00-161">自動解決的警示將會出現在 [警示佇列]、[警示] 頁面及裝置時程表的 [已解析] 區段中，且會在每個 Defender for Endpoint APIs 中顯示為 [已解決]。</span><span class="sxs-lookup"><span data-stu-id="e9c00-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="e9c00-162">標記為隱藏的警示會從整個系統中抑制，這兩者位於裝置相關聯的警示上，以及來自于儀表板，而且不會在每個 Defender 進行端點 APIs 之間流動。</span><span class="sxs-lookup"><span data-stu-id="e9c00-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="e9c00-163">輸入規則名稱和批註。</span><span class="sxs-lookup"><span data-stu-id="e9c00-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="e9c00-164">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="e9c00-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="e9c00-165">查看隱藏規則清單</span><span class="sxs-lookup"><span data-stu-id="e9c00-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="e9c00-166">在功能窗格中，選取 [**設定**  >  **警示抑制**]。</span><span class="sxs-lookup"><span data-stu-id="e9c00-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="e9c00-167">抑制規則清單會顯示組織中使用者所建立的所有規則。</span><span class="sxs-lookup"><span data-stu-id="e9c00-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="e9c00-168">如需管理抑制規則的相關資訊，請參閱 [Manage 抑制規則](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="e9c00-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="e9c00-169">變更警示的狀態</span><span class="sxs-lookup"><span data-stu-id="e9c00-169">Change the status of an alert</span></span>

<span data-ttu-id="e9c00-170">您可以在調查的進展中變更其狀態，將警示分類 (為 **新** 的、 **進行中** 或 **解決** 的) 。</span><span class="sxs-lookup"><span data-stu-id="e9c00-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="e9c00-171">這可協助您組織和管理您的小組可以回應提醒的方式。</span><span class="sxs-lookup"><span data-stu-id="e9c00-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="e9c00-172">例如，小組主持人可以查看所有 **新** 的警示，並決定將其指派給 **進行中** 的佇列以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="e9c00-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="e9c00-173">或者，小組主持人可能會將警示指派給 **已解析** 的佇列，如果他們知道警示是良性的，來自不 (相關的裝置，例如屬於安全性管理員的裝置) ，或是透過先前的警示來處理。</span><span class="sxs-lookup"><span data-stu-id="e9c00-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="e9c00-174">警示分類</span><span class="sxs-lookup"><span data-stu-id="e9c00-174">Alert classification</span></span>
<span data-ttu-id="e9c00-175">您可以選擇不設定分類，或指定警示為 true 警示或 false 警示。</span><span class="sxs-lookup"><span data-stu-id="e9c00-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="e9c00-176">務必提供 true 正/假正值的分類。</span><span class="sxs-lookup"><span data-stu-id="e9c00-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="e9c00-177">這種分類是用來監視警示品質，並使提醒更準確。</span><span class="sxs-lookup"><span data-stu-id="e9c00-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="e9c00-178">「判斷」欄位會定義 "true 正值" 分類的額外逼真度。</span><span class="sxs-lookup"><span data-stu-id="e9c00-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="e9c00-179">新增批註並查看警示的記錄</span><span class="sxs-lookup"><span data-stu-id="e9c00-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="e9c00-180">您可以新增批註及查看有關警示的歷史事件，以查看先前對警示所做的變更。</span><span class="sxs-lookup"><span data-stu-id="e9c00-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="e9c00-181">每當對警示進行變更或批註時，就會將它記錄在 [ **批註和記錄** ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="e9c00-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="e9c00-182">新增的註解會立即顯示在窗格中。</span><span class="sxs-lookup"><span data-stu-id="e9c00-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="e9c00-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="e9c00-183">Related topics</span></span>
- [<span data-ttu-id="e9c00-184">管理歸併規則</span><span class="sxs-lookup"><span data-stu-id="e9c00-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="e9c00-185">查看和組織 Microsoft Defender for Endpoint 警示佇列</span><span class="sxs-lookup"><span data-stu-id="e9c00-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="e9c00-186">調查 Microsoft Defender for Endpoint 警示</span><span class="sxs-lookup"><span data-stu-id="e9c00-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="e9c00-187">調查與 Microsoft Defender for Endpoint alert 相關聯的檔案</span><span class="sxs-lookup"><span data-stu-id="e9c00-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="e9c00-188">調查 Microsoft Defender for Endpoint Devices 清單中的裝置</span><span class="sxs-lookup"><span data-stu-id="e9c00-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="e9c00-189">調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9c00-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="e9c00-190">調查與 Microsoft Defender for Endpoint alert 相關聯的網域</span><span class="sxs-lookup"><span data-stu-id="e9c00-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="e9c00-191">調查 Microsoft Defender for Endpoint 中的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="e9c00-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
