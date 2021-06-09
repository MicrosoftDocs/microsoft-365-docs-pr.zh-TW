---
title: 在活動總管中報告的套用標籤動作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活動瀏覽器中可用的標記活動清單。
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532251"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="abf88-103">活動瀏覽器中可用的標記活動</span><span class="sxs-lookup"><span data-stu-id="abf88-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="abf88-104">套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="abf88-104">Sensitivity label applied</span></span>

<span data-ttu-id="abf88-105">此事件會在每次標記未標記的檔或使用敏感度標籤傳送電子郵件時產生。</span><span class="sxs-lookup"><span data-stu-id="abf88-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="abf88-106">它會在儲存時在 Office 原生應用程式和 web 應用程式中捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="abf88-107">它會在 Azure 資訊保護增益集發生時捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="abf88-108">升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。</span><span class="sxs-lookup"><span data-stu-id="abf88-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="abf88-109">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-109">Source</span></span>  |<span data-ttu-id="abf88-110">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-110">Reported in activity explorer</span></span> | <span data-ttu-id="abf88-111">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="abf88-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="abf88-113">是</span><span class="sxs-lookup"><span data-stu-id="abf88-113">yes</span></span> |
|<span data-ttu-id="abf88-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-114">Outlook</span></span>| <span data-ttu-id="abf88-115">是</span><span class="sxs-lookup"><span data-stu-id="abf88-115">yes</span></span> |<span data-ttu-id="abf88-116">從 Win 32</span><span class="sxs-lookup"><span data-stu-id="abf88-116">from Win 32</span></span> |
|<span data-ttu-id="abf88-117">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="abf88-118">是</span><span class="sxs-lookup"><span data-stu-id="abf88-118">yes</span></span> | |
|<span data-ttu-id="abf88-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-119">Exchange</span></span>        |<span data-ttu-id="abf88-120">是</span><span class="sxs-lookup"><span data-stu-id="abf88-120">yes</span></span>         | |
|<span data-ttu-id="abf88-121">Azure 資訊保護 (AIP) 整合用戶端和 AIP 整合掃描程式</span><span class="sxs-lookup"><span data-stu-id="abf88-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="abf88-122">是</span><span class="sxs-lookup"><span data-stu-id="abf88-122">yes</span></span> |<span data-ttu-id="abf88-123">AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*</span><span class="sxs-lookup"><span data-stu-id="abf88-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="abf88-124">Microsoft 資訊保護 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="abf88-125">是</span><span class="sxs-lookup"><span data-stu-id="abf88-125">yes</span></span>|<span data-ttu-id="abf88-126">AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*</span><span class="sxs-lookup"><span data-stu-id="abf88-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="abf88-127">Rights Management Service (RMS) </span><span class="sxs-lookup"><span data-stu-id="abf88-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="abf88-128">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-128">not applicable</span></span>         | |
|<span data-ttu-id="abf88-129">Power BI 桌面和 web</span><span class="sxs-lookup"><span data-stu-id="abf88-129">Power BI desktop and web</span></span>        | <span data-ttu-id="abf88-130">否</span><span class="sxs-lookup"><span data-stu-id="abf88-130">no</span></span>| <span data-ttu-id="abf88-131">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="abf88-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="abf88-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="abf88-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="abf88-133">否</span><span class="sxs-lookup"><span data-stu-id="abf88-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="abf88-134">已變更敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="abf88-134">Sensitivity label changed</span></span>

<span data-ttu-id="abf88-135">每當檔或電子郵件上的靈敏度標籤更新時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="abf88-136">針對 AIP 整合用戶端、統一掃描器和 MIP SDK 來源，AIP *升級卷* 標和 *降級標籤* 指令會對應至活動 explorer *標籤已變更*</span><span class="sxs-lookup"><span data-stu-id="abf88-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="abf88-137">它會在儲存的地方 Office 原生應用程式和 web 應用程式中捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="abf88-138">在 Azure 資訊保護統一用戶端增益集與掃描器 enforcements 中發生時，會將它捕獲</span><span class="sxs-lookup"><span data-stu-id="abf88-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="abf88-139">升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。</span><span class="sxs-lookup"><span data-stu-id="abf88-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="abf88-140">除了 SharePoint Online 和 OneDrive 之外，也會捕獲 *調整* 文字。</span><span class="sxs-lookup"><span data-stu-id="abf88-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="abf88-141">在 Outlook Office 原生應用程式中所做的靈敏度標記，會收集在檔案儲存/電子郵件傳送動作之前所產生的最後一個動作。</span><span class="sxs-lookup"><span data-stu-id="abf88-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="abf88-142">例如，如果使用者在傳送之前在電子郵件上變更了標籤，則會在電子郵件傳送時，最後一個標籤會在審計記錄檔中取得，然後在活動 explorer 中報告。</span><span class="sxs-lookup"><span data-stu-id="abf88-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="abf88-143">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-143">Source</span></span>  |<span data-ttu-id="abf88-144">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-144">Reported in activity explorer</span></span>|<span data-ttu-id="abf88-145">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="abf88-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-147">是</span><span class="sxs-lookup"><span data-stu-id="abf88-147">yes</span></span>         |
|<span data-ttu-id="abf88-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-148">Outlook</span></span>         |<span data-ttu-id="abf88-149">是</span><span class="sxs-lookup"><span data-stu-id="abf88-149">yes</span></span>         |<span data-ttu-id="abf88-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="abf88-150">Win 32</span></span>|
|<span data-ttu-id="abf88-151">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-152">是</span><span class="sxs-lookup"><span data-stu-id="abf88-152">yes</span></span>         |
|<span data-ttu-id="abf88-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-153">Exchange</span></span>         |<span data-ttu-id="abf88-154">是</span><span class="sxs-lookup"><span data-stu-id="abf88-154">yes</span></span>         |
|<span data-ttu-id="abf88-155">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-155">AIP unified client</span></span>         |<span data-ttu-id="abf88-156">是</span><span class="sxs-lookup"><span data-stu-id="abf88-156">yes</span></span>         |
|<span data-ttu-id="abf88-157">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-157">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-158">是</span><span class="sxs-lookup"><span data-stu-id="abf88-158">yes</span></span>         |
|<span data-ttu-id="abf88-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-159">MIP SDK</span></span>         |<span data-ttu-id="abf88-160">是</span><span class="sxs-lookup"><span data-stu-id="abf88-160">yes</span></span>         |
|<span data-ttu-id="abf88-161">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-161">RMS service</span></span>         |<span data-ttu-id="abf88-162">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-162">not applicable</span></span>         |
|<span data-ttu-id="abf88-163">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-164">否</span><span class="sxs-lookup"><span data-stu-id="abf88-164">no</span></span>         |<span data-ttu-id="abf88-165">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="abf88-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="abf88-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-166">MCAS</span></span>     |<span data-ttu-id="abf88-167">否</span><span class="sxs-lookup"><span data-stu-id="abf88-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="abf88-168">已移除敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="abf88-168">Sensitivity label removed</span></span>

<span data-ttu-id="abf88-169">每當從檔案或檔中移除靈敏度標籤時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="abf88-170">在儲存時 Office 原生應用程式和 web 應用程式中，會捕獲此事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="abf88-171">它會在 Azure 資訊保護增益集發生時捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="abf88-172">敏感度標記，使用 Office 原生 MIP 標籤，on Outlook 會收集在檔儲存/電子郵件傳送動作之前產生的最後一個標記事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="abf88-173">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-173">Source</span></span>  |<span data-ttu-id="abf88-174">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-174">Reported in activity explorer</span></span> | <span data-ttu-id="abf88-175">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="abf88-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-177">是</span><span class="sxs-lookup"><span data-stu-id="abf88-177">yes</span></span>         |
|<span data-ttu-id="abf88-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-178">Outlook</span></span>         |<span data-ttu-id="abf88-179">是</span><span class="sxs-lookup"><span data-stu-id="abf88-179">yes</span></span>         |<span data-ttu-id="abf88-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="abf88-180">Win 32</span></span>|
|<span data-ttu-id="abf88-181">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-182">是</span><span class="sxs-lookup"><span data-stu-id="abf88-182">yes</span></span>         |
|<span data-ttu-id="abf88-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-183">Exchange</span></span>         |<span data-ttu-id="abf88-184">是</span><span class="sxs-lookup"><span data-stu-id="abf88-184">yes</span></span>         |
|<span data-ttu-id="abf88-185">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-185">AIP unified client</span></span>         |<span data-ttu-id="abf88-186">是</span><span class="sxs-lookup"><span data-stu-id="abf88-186">yes</span></span>         |<span data-ttu-id="abf88-187">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="abf88-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="abf88-188">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-188">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-189">是</span><span class="sxs-lookup"><span data-stu-id="abf88-189">yes</span></span>         |<span data-ttu-id="abf88-190">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="abf88-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="abf88-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-191">MIP SDK</span></span>         |<span data-ttu-id="abf88-192">是</span><span class="sxs-lookup"><span data-stu-id="abf88-192">yes</span></span>         |<span data-ttu-id="abf88-193">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="abf88-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="abf88-194">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-194">RMS service</span></span>         |<span data-ttu-id="abf88-195">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-195">not applicable</span></span>         |
|<span data-ttu-id="abf88-196">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-197">否</span><span class="sxs-lookup"><span data-stu-id="abf88-197">no</span></span>         |<span data-ttu-id="abf88-198">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="abf88-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="abf88-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-199">MCAS</span></span>     |<span data-ttu-id="abf88-200">否</span><span class="sxs-lookup"><span data-stu-id="abf88-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="abf88-201">敏感度標籤檔案讀取</span><span class="sxs-lookup"><span data-stu-id="abf88-201">Sensitivity label file read</span></span>

<span data-ttu-id="abf88-202">此事件會在每次開啟靈敏度標記或受保護的檔時產生。</span><span class="sxs-lookup"><span data-stu-id="abf88-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="abf88-203">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-203">Source</span></span>  |<span data-ttu-id="abf88-204">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-204">Reported in activity explorer</span></span> | <span data-ttu-id="abf88-205">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="abf88-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-207">是</span><span class="sxs-lookup"><span data-stu-id="abf88-207">yes</span></span>         |
|<span data-ttu-id="abf88-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-208">Outlook</span></span>         |<span data-ttu-id="abf88-209">否</span><span class="sxs-lookup"><span data-stu-id="abf88-209">no</span></span>         |
|<span data-ttu-id="abf88-210">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-211">否</span><span class="sxs-lookup"><span data-stu-id="abf88-211">no</span></span>         |
|<span data-ttu-id="abf88-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-212">Exchange</span></span>         |<span data-ttu-id="abf88-213">否</span><span class="sxs-lookup"><span data-stu-id="abf88-213">no</span></span>         |
|<span data-ttu-id="abf88-214">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-214">AIP unified client</span></span>         |<span data-ttu-id="abf88-215">是</span><span class="sxs-lookup"><span data-stu-id="abf88-215">yes</span></span>         |<span data-ttu-id="abf88-216">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="abf88-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="abf88-217">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-217">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-218">是</span><span class="sxs-lookup"><span data-stu-id="abf88-218">yes</span></span>         |<span data-ttu-id="abf88-219">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="abf88-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="abf88-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-220">MIP SDK</span></span>         |<span data-ttu-id="abf88-221">是</span><span class="sxs-lookup"><span data-stu-id="abf88-221">yes</span></span>         |<span data-ttu-id="abf88-222">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="abf88-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="abf88-223">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-223">RMS service</span></span>         |<span data-ttu-id="abf88-224">是</span><span class="sxs-lookup"><span data-stu-id="abf88-224">yes</span></span>         |<span data-ttu-id="abf88-225">*存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="abf88-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="abf88-226">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-227">否</span><span class="sxs-lookup"><span data-stu-id="abf88-227">no</span></span>         |<span data-ttu-id="abf88-228">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="abf88-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="abf88-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-229">MCAS</span></span>     |<span data-ttu-id="abf88-230">否</span><span class="sxs-lookup"><span data-stu-id="abf88-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="abf88-231">探索的檔案</span><span class="sxs-lookup"><span data-stu-id="abf88-231">Files discovered</span></span>

<span data-ttu-id="abf88-232">當您每次使用 AIP 掃描程式來掃描不同位置的敏感性資料並尋找檔案時，就會產生這個事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="abf88-233">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-233">Source</span></span>  |<span data-ttu-id="abf88-234">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-234">Reported in activity explorer</span></span> | <span data-ttu-id="abf88-235">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="abf88-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-237">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-237">not applicable</span></span>         |
|<span data-ttu-id="abf88-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-238">Outlook</span></span>         |<span data-ttu-id="abf88-239">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-239">not applicable</span></span>         |
|<span data-ttu-id="abf88-240">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-241">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-241">not applicable</span></span>         |
|<span data-ttu-id="abf88-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-242">Exchange</span></span>         |<span data-ttu-id="abf88-243">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-243">not applicable</span></span>         |
|<span data-ttu-id="abf88-244">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-244">AIP unified client</span></span>         |<span data-ttu-id="abf88-245">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-245">not applicable</span></span>       |
|<span data-ttu-id="abf88-246">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-246">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-247">是</span><span class="sxs-lookup"><span data-stu-id="abf88-247">yes</span></span>         |<span data-ttu-id="abf88-248">AIP *探索* 動作會對應至活動瀏覽器中已 *發現的檔* 動作</span><span class="sxs-lookup"><span data-stu-id="abf88-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="abf88-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-249">MIP SDK</span></span>         |<span data-ttu-id="abf88-250">是</span><span class="sxs-lookup"><span data-stu-id="abf88-250">yes</span></span>         |<span data-ttu-id="abf88-251">AIP *探索* 動作會對應至活動瀏覽器中的 [已 *發現的檔* ] 動作</span><span class="sxs-lookup"><span data-stu-id="abf88-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="abf88-252">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-252">RMS service</span></span>         |<span data-ttu-id="abf88-253">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-253">not applicable</span></span>         |
|<span data-ttu-id="abf88-254">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-255">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-255">not applicable</span></span>         |
|<span data-ttu-id="abf88-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-256">MCAS</span></span>     |<span data-ttu-id="abf88-257">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="abf88-258">敏感度標籤檔案名已重新命名</span><span class="sxs-lookup"><span data-stu-id="abf88-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="abf88-259">此事件會在每次重新命名具有敏感度標籤的檔時產生。</span><span class="sxs-lookup"><span data-stu-id="abf88-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="abf88-260">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-260">Source</span></span>  | <span data-ttu-id="abf88-261">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-261">Reported in activity explorer</span></span> | <span data-ttu-id="abf88-262">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="abf88-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-264">是</span><span class="sxs-lookup"><span data-stu-id="abf88-264">yes</span></span>         |
|<span data-ttu-id="abf88-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-265">Outlook</span></span>         |<span data-ttu-id="abf88-266">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-266">not applicable</span></span>         |
|<span data-ttu-id="abf88-267">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-268">否</span><span class="sxs-lookup"><span data-stu-id="abf88-268">no</span></span>        |
|<span data-ttu-id="abf88-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-269">Exchange</span></span>         |<span data-ttu-id="abf88-270">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-270">not applicable</span></span>         |
|<span data-ttu-id="abf88-271">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-271">AIP unified client</span></span>         |<span data-ttu-id="abf88-272">否</span><span class="sxs-lookup"><span data-stu-id="abf88-272">no</span></span>         |
|<span data-ttu-id="abf88-273">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-273">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-274">否</span><span class="sxs-lookup"><span data-stu-id="abf88-274">no</span></span>         |
|<span data-ttu-id="abf88-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-275">MIP SDK</span></span>         |<span data-ttu-id="abf88-276">否</span><span class="sxs-lookup"><span data-stu-id="abf88-276">no</span></span>         |
|<span data-ttu-id="abf88-277">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-277">RMS service</span></span>         |<span data-ttu-id="abf88-278">否</span><span class="sxs-lookup"><span data-stu-id="abf88-278">no</span></span>      |
|<span data-ttu-id="abf88-279">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-280">否</span><span class="sxs-lookup"><span data-stu-id="abf88-280">no</span></span>         |
|<span data-ttu-id="abf88-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-281">MCAS</span></span>     |<span data-ttu-id="abf88-282">否</span><span class="sxs-lookup"><span data-stu-id="abf88-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="abf88-283">移除檔案</span><span class="sxs-lookup"><span data-stu-id="abf88-283">File removed</span></span>

<span data-ttu-id="abf88-284">此事件會在每次 AIP 掃描程式偵測到先前掃描的檔案已移除時產生。</span><span class="sxs-lookup"><span data-stu-id="abf88-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="abf88-285">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-285">Source</span></span>  |<span data-ttu-id="abf88-286">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-286">Reported in activity explorer</span></span> | <span data-ttu-id="abf88-287">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="abf88-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-289">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-289">not applicable</span></span>         |
|<span data-ttu-id="abf88-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-290">Outlook</span></span>         |<span data-ttu-id="abf88-291">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-291">not applicable</span></span>         |
|<span data-ttu-id="abf88-292">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-293">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-293">not applicable</span></span>           |
|<span data-ttu-id="abf88-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-294">Exchange</span></span>         |<span data-ttu-id="abf88-295">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-295">not applicable</span></span>         |
|<span data-ttu-id="abf88-296">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-296">AIP unified client</span></span>         |<span data-ttu-id="abf88-297">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-297">not applicable</span></span>            |
|<span data-ttu-id="abf88-298">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-298">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-299">是</span><span class="sxs-lookup"><span data-stu-id="abf88-299">yes</span></span>         |
|<span data-ttu-id="abf88-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-300">MIP SDK</span></span>         |<span data-ttu-id="abf88-301">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-301">not applicable</span></span>            |
|<span data-ttu-id="abf88-302">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-302">RMS service</span></span>         |<span data-ttu-id="abf88-303">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-303">not applicable</span></span>         |
|<span data-ttu-id="abf88-304">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-305">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-305">not applicable</span></span>  |
|<span data-ttu-id="abf88-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-306">MCAS</span></span>     |<span data-ttu-id="abf88-307">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="abf88-308">套用保護</span><span class="sxs-lookup"><span data-stu-id="abf88-308">Protection applied</span></span>

<span data-ttu-id="abf88-309">此事件會產生第一次保護是手動新增至沒有標籤的專案。</span><span class="sxs-lookup"><span data-stu-id="abf88-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="abf88-310">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-310">Source</span></span>  |<span data-ttu-id="abf88-311">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-311">Reported in activity explorer</span></span> | <span data-ttu-id="abf88-312">注意</span><span class="sxs-lookup"><span data-stu-id="abf88-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="abf88-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-314">否</span><span class="sxs-lookup"><span data-stu-id="abf88-314">no</span></span>         |
|<span data-ttu-id="abf88-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-315">Outlook</span></span>         |<span data-ttu-id="abf88-316">否</span><span class="sxs-lookup"><span data-stu-id="abf88-316">no</span></span>         |
|<span data-ttu-id="abf88-317">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-318">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-318">not applicable</span></span>           |
|<span data-ttu-id="abf88-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-319">Exchange</span></span>         |<span data-ttu-id="abf88-320">否</span><span class="sxs-lookup"><span data-stu-id="abf88-320">no</span></span>       |
|<span data-ttu-id="abf88-321">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-321">AIP unified client</span></span>         |<span data-ttu-id="abf88-322">是</span><span class="sxs-lookup"><span data-stu-id="abf88-322">yes</span></span>            |
|<span data-ttu-id="abf88-323">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-323">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-324">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-324">not applicable</span></span>         |
|<span data-ttu-id="abf88-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-325">MIP SDK</span></span>         |<span data-ttu-id="abf88-326">是</span><span class="sxs-lookup"><span data-stu-id="abf88-326">yes</span></span>            |
|<span data-ttu-id="abf88-327">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-327">RMS service</span></span>         |<span data-ttu-id="abf88-328">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-328">not applicable</span></span>         |
|<span data-ttu-id="abf88-329">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-330">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-330">not applicable</span></span>            |
|<span data-ttu-id="abf88-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-331">MCAS</span></span>     |<span data-ttu-id="abf88-332">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="abf88-333">變更保護</span><span class="sxs-lookup"><span data-stu-id="abf88-333">Protection changed</span></span>

<span data-ttu-id="abf88-334">每當以手動方式變更未標記檔的保護時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="abf88-335">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-335">Source</span></span>  |<span data-ttu-id="abf88-336">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="abf88-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-338">否</span><span class="sxs-lookup"><span data-stu-id="abf88-338">no</span></span>         |
|<span data-ttu-id="abf88-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-339">Outlook</span></span>         |<span data-ttu-id="abf88-340">否</span><span class="sxs-lookup"><span data-stu-id="abf88-340">no</span></span>         |
|<span data-ttu-id="abf88-341">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-342">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-342">not applicable</span></span>           |
|<span data-ttu-id="abf88-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-343">Exchange</span></span>         |<span data-ttu-id="abf88-344">否</span><span class="sxs-lookup"><span data-stu-id="abf88-344">no</span></span>       |
|<span data-ttu-id="abf88-345">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-345">AIP unified client</span></span>         |<span data-ttu-id="abf88-346">是</span><span class="sxs-lookup"><span data-stu-id="abf88-346">yes</span></span>            |
|<span data-ttu-id="abf88-347">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-347">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-348">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-348">not applicable</span></span>         |
|<span data-ttu-id="abf88-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-349">MIP SDK</span></span>         |<span data-ttu-id="abf88-350">是</span><span class="sxs-lookup"><span data-stu-id="abf88-350">yes</span></span>            |
|<span data-ttu-id="abf88-351">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-351">RMS service</span></span>         |<span data-ttu-id="abf88-352">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-352">not applicable</span></span>         |
|<span data-ttu-id="abf88-353">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-354">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-354">not applicable</span></span>            |
|<span data-ttu-id="abf88-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-355">MCAS</span></span>     |<span data-ttu-id="abf88-356">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="abf88-357">已移除保護</span><span class="sxs-lookup"><span data-stu-id="abf88-357">Protection removed</span></span>

<span data-ttu-id="abf88-358">每當以手動方式變更未標記檔的保護時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="abf88-359">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-359">Source</span></span>  |<span data-ttu-id="abf88-360">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="abf88-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="abf88-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="abf88-362">否</span><span class="sxs-lookup"><span data-stu-id="abf88-362">no</span></span>         |
|<span data-ttu-id="abf88-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="abf88-363">Outlook</span></span>         |<span data-ttu-id="abf88-364">否</span><span class="sxs-lookup"><span data-stu-id="abf88-364">no</span></span>         |
|<span data-ttu-id="abf88-365">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="abf88-366">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-366">not applicable</span></span>           |
|<span data-ttu-id="abf88-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-367">Exchange</span></span>         |<span data-ttu-id="abf88-368">否</span><span class="sxs-lookup"><span data-stu-id="abf88-368">no</span></span>       |
|<span data-ttu-id="abf88-369">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="abf88-369">AIP unified client</span></span>         |<span data-ttu-id="abf88-370">是</span><span class="sxs-lookup"><span data-stu-id="abf88-370">yes</span></span>            |
|<span data-ttu-id="abf88-371">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="abf88-371">AIP unified scanner</span></span>         |<span data-ttu-id="abf88-372">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-372">not applicable</span></span>         |
|<span data-ttu-id="abf88-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="abf88-373">MIP SDK</span></span>         |<span data-ttu-id="abf88-374">是</span><span class="sxs-lookup"><span data-stu-id="abf88-374">yes</span></span>            |
|<span data-ttu-id="abf88-375">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="abf88-375">RMS service</span></span>         |<span data-ttu-id="abf88-376">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-376">not applicable</span></span>         |
|<span data-ttu-id="abf88-377">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="abf88-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="abf88-378">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-378">not applicable</span></span>            |
|<span data-ttu-id="abf88-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-379">MCAS</span></span>     |<span data-ttu-id="abf88-380">不適用</span><span class="sxs-lookup"><span data-stu-id="abf88-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="abf88-381">符合的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="abf88-381">DLP policy matched</span></span>

<span data-ttu-id="abf88-382">每當在檔或電子郵件上符合 DLP 原則時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="abf88-383">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-383">Source</span></span>  |<span data-ttu-id="abf88-384">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="abf88-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-385">Exchange</span></span>         |<span data-ttu-id="abf88-386">是</span><span class="sxs-lookup"><span data-stu-id="abf88-386">yes</span></span>       |
|<span data-ttu-id="abf88-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abf88-387">SharePoint Online</span></span>|<span data-ttu-id="abf88-388">是</span><span class="sxs-lookup"><span data-stu-id="abf88-388">yes</span></span>          |
|<span data-ttu-id="abf88-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-389">OneDrive</span></span> |<span data-ttu-id="abf88-390">是</span><span class="sxs-lookup"><span data-stu-id="abf88-390">yes</span></span>|
|<span data-ttu-id="abf88-391">Teams</span><span class="sxs-lookup"><span data-stu-id="abf88-391">Teams</span></span> |<span data-ttu-id="abf88-392">是</span><span class="sxs-lookup"><span data-stu-id="abf88-392">yes</span></span>   |
|<span data-ttu-id="abf88-393">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="abf88-393">Windows 10 devices</span></span>         |<span data-ttu-id="abf88-394">是</span><span class="sxs-lookup"><span data-stu-id="abf88-394">yes</span></span> |
|<span data-ttu-id="abf88-395">Mac</span><span class="sxs-lookup"><span data-stu-id="abf88-395">MAC</span></span>         |<span data-ttu-id="abf88-396">否</span><span class="sxs-lookup"><span data-stu-id="abf88-396">no</span></span>     |
|<span data-ttu-id="abf88-397">內部部署</span><span class="sxs-lookup"><span data-stu-id="abf88-397">on-premises</span></span>         |<span data-ttu-id="abf88-398">否</span><span class="sxs-lookup"><span data-stu-id="abf88-398">no</span></span>|
|<span data-ttu-id="abf88-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="abf88-399">MCAS</span></span>     |<span data-ttu-id="abf88-400">否</span><span class="sxs-lookup"><span data-stu-id="abf88-400">no</span></span>        | 

<span data-ttu-id="abf88-401">Windows 10 裝置的事件 (Endpoint DLP) 為：</span><span class="sxs-lookup"><span data-stu-id="abf88-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="abf88-402">已刪除檔案</span><span class="sxs-lookup"><span data-stu-id="abf88-402">file deleted</span></span>
- <span data-ttu-id="abf88-403">已建立檔</span><span class="sxs-lookup"><span data-stu-id="abf88-403">file created</span></span>
- <span data-ttu-id="abf88-404">檔案已複製到剪貼簿</span><span class="sxs-lookup"><span data-stu-id="abf88-404">file copied to clipboard</span></span>
- <span data-ttu-id="abf88-405">修改檔案</span><span class="sxs-lookup"><span data-stu-id="abf88-405">file modified</span></span>
- <span data-ttu-id="abf88-406">檔案讀取</span><span class="sxs-lookup"><span data-stu-id="abf88-406">file read</span></span>
- <span data-ttu-id="abf88-407">已列印檔案</span><span class="sxs-lookup"><span data-stu-id="abf88-407">file printed</span></span>
- <span data-ttu-id="abf88-408">重新命名的檔案名</span><span class="sxs-lookup"><span data-stu-id="abf88-408">file renamed</span></span>
- <span data-ttu-id="abf88-409">檔案已複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="abf88-409">file copied to network share</span></span>
- <span data-ttu-id="abf88-410">unallowed 應用程式所存取的檔案</span><span class="sxs-lookup"><span data-stu-id="abf88-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="abf88-411">套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="abf88-411">Retention label applied</span></span> 

<span data-ttu-id="abf88-412">此事件會在每次標記未標記的檔或以保留標籤傳送電子郵件時產生。</span><span class="sxs-lookup"><span data-stu-id="abf88-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="abf88-413">它會在儲存檔時和傳送電子郵件的時間內捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="abf88-414">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-414">Source</span></span>  |<span data-ttu-id="abf88-415">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="abf88-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-416">Exchange</span></span>         |<span data-ttu-id="abf88-417">否</span><span class="sxs-lookup"><span data-stu-id="abf88-417">no</span></span>       |
|<span data-ttu-id="abf88-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abf88-418">SharePoint Online</span></span>|<span data-ttu-id="abf88-419">是</span><span class="sxs-lookup"><span data-stu-id="abf88-419">yes</span></span>          |
|<span data-ttu-id="abf88-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-420">OneDrive</span></span> |<span data-ttu-id="abf88-421">是</span><span class="sxs-lookup"><span data-stu-id="abf88-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="abf88-422">已變更保留標籤</span><span class="sxs-lookup"><span data-stu-id="abf88-422">Retention label changed</span></span>

<span data-ttu-id="abf88-423">每當檔或電子郵件上的標籤更新時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="abf88-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="abf88-424">它會在儲存檔時和傳送電子郵件的時間內捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="abf88-425">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-425">Source</span></span>  |<span data-ttu-id="abf88-426">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="abf88-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-427">Exchange</span></span>         |<span data-ttu-id="abf88-428">否</span><span class="sxs-lookup"><span data-stu-id="abf88-428">no</span></span>       |
|<span data-ttu-id="abf88-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abf88-429">SharePoint Online</span></span>|<span data-ttu-id="abf88-430">是</span><span class="sxs-lookup"><span data-stu-id="abf88-430">yes</span></span>          |
|<span data-ttu-id="abf88-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-431">OneDrive</span></span> |<span data-ttu-id="abf88-432">是</span><span class="sxs-lookup"><span data-stu-id="abf88-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="abf88-433">已移除保留標籤</span><span class="sxs-lookup"><span data-stu-id="abf88-433">Retention label removed</span></span>

<span data-ttu-id="abf88-434">此事件會在每次從檔案或檔中移除標籤時產生。</span><span class="sxs-lookup"><span data-stu-id="abf88-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="abf88-435">它會在儲存檔時和傳送電子郵件的時間內捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="abf88-436">來源</span><span class="sxs-lookup"><span data-stu-id="abf88-436">Source</span></span>  |<span data-ttu-id="abf88-437">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="abf88-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="abf88-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="abf88-438">Exchange</span></span>         |<span data-ttu-id="abf88-439">否</span><span class="sxs-lookup"><span data-stu-id="abf88-439">no</span></span>       |
|<span data-ttu-id="abf88-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="abf88-440">SharePoint Online</span></span>|<span data-ttu-id="abf88-441">是</span><span class="sxs-lookup"><span data-stu-id="abf88-441">yes</span></span>          |
|<span data-ttu-id="abf88-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="abf88-442">OneDrive</span></span> |<span data-ttu-id="abf88-443">是</span><span class="sxs-lookup"><span data-stu-id="abf88-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="abf88-444">已知問題</span><span class="sxs-lookup"><span data-stu-id="abf88-444">Known issues</span></span>
  
- <span data-ttu-id="abf88-445">向使用者顯示建議的標籤工具提示時，不會將其捕獲。</span><span class="sxs-lookup"><span data-stu-id="abf88-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="abf88-446">不過，如果使用者選擇套用建議的標籤，標籤會顯示在 *建議* 的 *套用欄位底下*。</span><span class="sxs-lookup"><span data-stu-id="abf88-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="abf88-447">敏感度標籤上目前無法使用對齊文字，請從 Sharepoint 和 OneDrive 降級。</span><span class="sxs-lookup"><span data-stu-id="abf88-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="abf88-448">機密資訊類型目前不適用於來自 Word 的 autolabeling 活動、Excel、PowerPoint 和 Outlook，以及 SharePoint 線上及 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="abf88-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
