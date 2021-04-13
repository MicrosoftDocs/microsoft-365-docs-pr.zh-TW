---
title: 建立及查看安全性建議的例外狀況-威脅和弱點管理
description: 針對威脅和弱點管理中的安全性建議建立及監視例外狀況。
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
ms.openlocfilehash: 4f37300a742ab8cac32e95863cb706f1fd5f5d66
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689410"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="5b51c-104">建立及查看安全性建議的例外狀況-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="5b51c-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5b51c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5b51c-105">**Applies to:**</span></span>

- [<span data-ttu-id="5b51c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5b51c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5b51c-107">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="5b51c-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5b51c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b51c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="5b51c-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5b51c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5b51c-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5b51c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="5b51c-111">如果目前沒有相關建議，則為修正要求的替代，您可以為建議建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="5b51c-112">如果您的組織有裝置群組，您就可以將例外狀況限定為特定裝置群組。</span><span class="sxs-lookup"><span data-stu-id="5b51c-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="5b51c-113">您可以為選取的裝置群組或所有已過去及呈現的裝置群組建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="5b51c-114">針對建議建立例外狀況時，建議在例外期限結束之前不會作用。</span><span class="sxs-lookup"><span data-stu-id="5b51c-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="5b51c-115">建議狀態會變更為設備群組)  (的 **完整例外** 狀況或 **部分例外** 狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="5b51c-116">權限</span><span class="sxs-lookup"><span data-stu-id="5b51c-116">Permissions</span></span>

<span data-ttu-id="5b51c-117">只有「例外狀況處理」許可權的使用者才能管理例外狀況 (包括建立或取消) 。</span><span class="sxs-lookup"><span data-stu-id="5b51c-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="5b51c-118">[深入瞭解 RBAC 角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="5b51c-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![例外狀況處理許可權的視圖。](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="5b51c-120">建立例外狀況</span><span class="sxs-lookup"><span data-stu-id="5b51c-120">Create an exception</span></span>

<span data-ttu-id="5b51c-121">選取您要為其建立例外狀況的安全性建議，然後選取 [ **例外狀況選項** ] 並填寫表單。</span><span class="sxs-lookup"><span data-stu-id="5b51c-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![顯示「例外選項」按鈕在安全性建議浮出的位置。](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="5b51c-123">依設備群組的例外狀況</span><span class="sxs-lookup"><span data-stu-id="5b51c-123">Exception by device group</span></span>

<span data-ttu-id="5b51c-124">將例外狀況套用至所有目前的裝置群組，或選擇 [特定裝置群組]。</span><span class="sxs-lookup"><span data-stu-id="5b51c-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="5b51c-125">未來的裝置群組不會包含在例外狀況中。</span><span class="sxs-lookup"><span data-stu-id="5b51c-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="5b51c-126">已有例外狀況的裝置群組不會顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="5b51c-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="5b51c-127">如果您只選取特定裝置群組，建議狀態會從「active」變更為「部分例外」。</span><span class="sxs-lookup"><span data-stu-id="5b51c-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="5b51c-128">如果您選取所有的裝置群組，則狀態會變更為「完全例外」。</span><span class="sxs-lookup"><span data-stu-id="5b51c-128">The state will change to “full exception” if you select all the device groups.</span></span>

![顯示裝置群組 dropdown。](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="5b51c-130">篩選的視圖</span><span class="sxs-lookup"><span data-stu-id="5b51c-130">Filtered views</span></span>

<span data-ttu-id="5b51c-131">如果您已在任何威脅和弱點管理頁面上以裝置群組篩選，則只有篩選的裝置群組會顯示為 [選項]。</span><span class="sxs-lookup"><span data-stu-id="5b51c-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="5b51c-132">在任何威脅和弱點管理頁面上，按裝置群組篩選的按鈕：</span><span class="sxs-lookup"><span data-stu-id="5b51c-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![顯示選取的裝置群組篩選器。](images/tvm-selected-device-groups.png)

<span data-ttu-id="5b51c-134">具有篩選裝置群組的例外狀況視圖：</span><span class="sxs-lookup"><span data-stu-id="5b51c-134">Exception view with filtered device groups:</span></span>

![顯示已篩選的裝置群組 dropdown。](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="5b51c-136">大量的裝置群組</span><span class="sxs-lookup"><span data-stu-id="5b51c-136">Large number of device groups</span></span>

<span data-ttu-id="5b51c-137">如果您的組織擁有超過20個裝置群組，請選取 [篩選的裝置群組] 選項旁的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="5b51c-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![顯示如何編輯大量群組。](images/tvm-exception-edit-groups.png)

<span data-ttu-id="5b51c-139">快顯視窗會出現，您可以在其中搜尋及選擇您想要包含的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="5b51c-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="5b51c-140">選取 [搜尋] 下的核取記號圖示，即可勾選/取消全部選取。</span><span class="sxs-lookup"><span data-stu-id="5b51c-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![顯示大型裝置群組飛出。](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="5b51c-142">全域例外狀況</span><span class="sxs-lookup"><span data-stu-id="5b51c-142">Global exceptions</span></span>

<span data-ttu-id="5b51c-143">如果您有全域系統管理員許可權，您就可以建立和取消全域例外狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-143">If you have global administrator permissions, you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="5b51c-144">它會影響組織中的 **所有** 目前和未來裝置群組，且只有具有類似許可權的使用者才能加以變更。</span><span class="sxs-lookup"><span data-stu-id="5b51c-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="5b51c-145">建議狀態會從「active」變更為「完整例外狀況」。</span><span class="sxs-lookup"><span data-stu-id="5b51c-145">The recommendation state will change from “active” to “full exception.”</span></span>

![顯示全域例外狀況選項。](images/tvm-exception-global.png)

<span data-ttu-id="5b51c-147">請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="5b51c-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="5b51c-148">如果建議位於全域例外狀況底下，則新建立的裝置群組例外狀況會暫停，直到全域例外狀況到期或取消為止。</span><span class="sxs-lookup"><span data-stu-id="5b51c-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="5b51c-149">在該點之後，新的裝置群組例外會生效，直到它們到期為止。</span><span class="sxs-lookup"><span data-stu-id="5b51c-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="5b51c-150">如果建議已有特定裝置群組的例外狀況，且已建立全域例外狀況，則裝置群組例外會暫停，直到它到期或全域例外會在到期之前取消。</span><span class="sxs-lookup"><span data-stu-id="5b51c-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="5b51c-151">理由</span><span class="sxs-lookup"><span data-stu-id="5b51c-151">Justification</span></span>

<span data-ttu-id="5b51c-152">選取您需要檔案的例外狀況，而不是修正問題的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="5b51c-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="5b51c-153">填寫對齊內容，然後設定例外期限。</span><span class="sxs-lookup"><span data-stu-id="5b51c-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="5b51c-154">下列清單詳述例外狀況選項背後的合理性論證：</span><span class="sxs-lookup"><span data-stu-id="5b51c-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="5b51c-155">**協力廠商控制** -協力廠商的產品或軟體已經解決此建議-選擇此理由類型會降低您的披露分數，並增加您的安全分數，因為您的風險已降低</span><span class="sxs-lookup"><span data-stu-id="5b51c-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="5b51c-156">**替代的緩解** -內部工具已經解決此建議-選擇此調整類型會降低曝光分數，並增加您的安全分數，因為您的風險已降低</span><span class="sxs-lookup"><span data-stu-id="5b51c-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="5b51c-157">已 **接受風險**-引起低風險和/或實施建議太昂貴</span><span class="sxs-lookup"><span data-stu-id="5b51c-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="5b51c-158">已計畫 **修正 (寬限)** -已計畫，但正等候執行或授權</span><span class="sxs-lookup"><span data-stu-id="5b51c-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="5b51c-159">全部查看例外狀況</span><span class="sxs-lookup"><span data-stu-id="5b51c-159">View all exceptions</span></span>

<span data-ttu-id="5b51c-160">流覽至 [**修正**] 頁面中的 [**例外** 狀況] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5b51c-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="5b51c-161">您可以依論證、類型及狀態進行篩選。</span><span class="sxs-lookup"><span data-stu-id="5b51c-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="5b51c-162">選取 [例外狀況] 開啟具有更多詳細資料的浮出控制項。</span><span class="sxs-lookup"><span data-stu-id="5b51c-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="5b51c-163">每個裝置群組的例外狀況會包含例外狀況涵蓋的每一個裝置群組的清單，您可以將其匯出。</span><span class="sxs-lookup"><span data-stu-id="5b51c-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="5b51c-164">您也可以查看相關的建議或取消例外狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-164">You can also view the related recommendation or cancel the exception.</span></span>

![顯示 [修正] 頁面中的「例外狀況」索引標籤。](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="5b51c-166">如何取消例外狀況</span><span class="sxs-lookup"><span data-stu-id="5b51c-166">How to cancel an exception</span></span>

<span data-ttu-id="5b51c-167">若要取消例外狀況，請流覽至 [**修正**] 頁面中的 [**例外** 狀況] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5b51c-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="5b51c-168">選取例外狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-168">Select the exception.</span></span>

<span data-ttu-id="5b51c-169">若要取消所有裝置群組或全域例外狀況的例外狀況，請選取 [ **所有設備群組的取消例外** 狀況] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5b51c-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="5b51c-170">您將只能取消您具有許可權之裝置群組的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![[取消] 按鈕。](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="5b51c-172">取消特定裝置群組的例外狀況</span><span class="sxs-lookup"><span data-stu-id="5b51c-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="5b51c-173">選取特定裝置群組以取消例外狀況。</span><span class="sxs-lookup"><span data-stu-id="5b51c-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="5b51c-174">裝置群組會顯示快顯視窗，您可以選取 [ **取消例外** 狀況]。</span><span class="sxs-lookup"><span data-stu-id="5b51c-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![顯示如何選取特定的裝置群組。](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="5b51c-176">在套用例外狀況之後查看影響</span><span class="sxs-lookup"><span data-stu-id="5b51c-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="5b51c-177">在 [安全性建議] 頁面中，選取 [**自訂欄位**]，然後在例外狀況) 和 **影響 (例外狀況) 之後**，選取 [已 **公開的裝置 (** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="5b51c-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![顯示 [自訂欄位] 選項。](images/tvm-after-exceptions.png)

<span data-ttu-id="5b51c-179">在例外狀況) 欄 (的公開裝置會顯示在套用例外規則之後，仍然對漏洞公開的剩餘裝置。</span><span class="sxs-lookup"><span data-stu-id="5b51c-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="5b51c-180">影響洩密的例外狀況調整包括「協力廠商控制項」和「替代緩解」。</span><span class="sxs-lookup"><span data-stu-id="5b51c-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="5b51c-181">其他理由不會降低設備的暴露程度，而且仍然會被視為公開。</span><span class="sxs-lookup"><span data-stu-id="5b51c-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="5b51c-182">「例外狀況」) 之後所產生的影響 (會顯示對嚴重性或安全性分數套用例外狀況後的剩餘影響。</span><span class="sxs-lookup"><span data-stu-id="5b51c-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="5b51c-183">影響分數的例外狀況調整包括「協力廠商控制」和「替代緩解」。</span><span class="sxs-lookup"><span data-stu-id="5b51c-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="5b51c-184">其他理由不會降低設備的暴露程度，因此曝光度和安全分數不會變更。</span><span class="sxs-lookup"><span data-stu-id="5b51c-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![顯示表格中的欄。](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="5b51c-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="5b51c-186">Related topics</span></span>

- [<span data-ttu-id="5b51c-187">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="5b51c-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="5b51c-188">修正安全性漏洞</span><span class="sxs-lookup"><span data-stu-id="5b51c-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="5b51c-189">安全性建議</span><span class="sxs-lookup"><span data-stu-id="5b51c-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="5b51c-190">暴險分數</span><span class="sxs-lookup"><span data-stu-id="5b51c-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="5b51c-191">裝置用 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="5b51c-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
