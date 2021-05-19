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
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="8c148-103">活動瀏覽器中可用的標記活動</span><span class="sxs-lookup"><span data-stu-id="8c148-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="8c148-104">套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="8c148-104">Sensitivity label applied</span></span>

<span data-ttu-id="8c148-105">此事件會在每次標記未標記的檔或使用敏感度標籤傳送電子郵件時產生。</span><span class="sxs-lookup"><span data-stu-id="8c148-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="8c148-106">它會在儲存時在 Office 原生應用程式和 web 應用程式中捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="8c148-107">它會在 Azure 資訊保護增益集發生時捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="8c148-108">升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。</span><span class="sxs-lookup"><span data-stu-id="8c148-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="8c148-109">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-109">Source</span></span>  |<span data-ttu-id="8c148-110">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-110">Reported in activity explorer</span></span> | <span data-ttu-id="8c148-111">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="8c148-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="8c148-113">是</span><span class="sxs-lookup"><span data-stu-id="8c148-113">yes</span></span> |
|<span data-ttu-id="8c148-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-114">Outlook</span></span>| <span data-ttu-id="8c148-115">是</span><span class="sxs-lookup"><span data-stu-id="8c148-115">yes</span></span> |<span data-ttu-id="8c148-116">從 Win 32</span><span class="sxs-lookup"><span data-stu-id="8c148-116">from Win 32</span></span> |
|<span data-ttu-id="8c148-117">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="8c148-118">是</span><span class="sxs-lookup"><span data-stu-id="8c148-118">yes</span></span> | |
|<span data-ttu-id="8c148-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-119">Exchange</span></span>        |<span data-ttu-id="8c148-120">是</span><span class="sxs-lookup"><span data-stu-id="8c148-120">yes</span></span>         | |
|<span data-ttu-id="8c148-121">Azure 資訊保護 (AIP) 整合用戶端和 AIP 整合掃描程式</span><span class="sxs-lookup"><span data-stu-id="8c148-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="8c148-122">是</span><span class="sxs-lookup"><span data-stu-id="8c148-122">yes</span></span> |<span data-ttu-id="8c148-123">AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*</span><span class="sxs-lookup"><span data-stu-id="8c148-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="8c148-124">Microsoft 資訊保護 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="8c148-125">是</span><span class="sxs-lookup"><span data-stu-id="8c148-125">yes</span></span>|<span data-ttu-id="8c148-126">AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*</span><span class="sxs-lookup"><span data-stu-id="8c148-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="8c148-127">Rights Management Service (RMS) </span><span class="sxs-lookup"><span data-stu-id="8c148-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="8c148-128">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-128">not applicable</span></span>         | |
|<span data-ttu-id="8c148-129">Power BI 桌面和 web</span><span class="sxs-lookup"><span data-stu-id="8c148-129">Power BI desktop and web</span></span>        | <span data-ttu-id="8c148-130">否</span><span class="sxs-lookup"><span data-stu-id="8c148-130">no</span></span>| <span data-ttu-id="8c148-131">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="8c148-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="8c148-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="8c148-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="8c148-133">否</span><span class="sxs-lookup"><span data-stu-id="8c148-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="8c148-134">已變更敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="8c148-134">Sensitivity label changed</span></span>

<span data-ttu-id="8c148-135">每當檔或電子郵件上的靈敏度標籤更新時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="8c148-136">針對 AIP 整合用戶端、統一掃描器和 MIP SDK 來源，AIP *升級卷* 標和 *降級標籤* 指令會對應至活動 explorer *標籤已變更*</span><span class="sxs-lookup"><span data-stu-id="8c148-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="8c148-137">它會在儲存的地方 Office 原生應用程式和 web 應用程式中捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="8c148-138">在 Azure 資訊保護統一用戶端增益集與掃描器 enforcements 中發生時，會將它捕獲</span><span class="sxs-lookup"><span data-stu-id="8c148-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="8c148-139">升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。</span><span class="sxs-lookup"><span data-stu-id="8c148-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="8c148-140">除了 SharePoint Online 和 OneDrive 之外，也會捕獲 *調整* 文字。</span><span class="sxs-lookup"><span data-stu-id="8c148-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="8c148-141">在 Outlook Office 原生應用程式中所做的靈敏度標記，會收集在檔案儲存/電子郵件傳送動作之前所產生的最後一個動作。</span><span class="sxs-lookup"><span data-stu-id="8c148-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="8c148-142">例如，如果使用者在傳送之前在電子郵件上變更了標籤，則會在電子郵件傳送時，最後一個標籤會在審計記錄檔中取得，然後在活動 explorer 中報告。</span><span class="sxs-lookup"><span data-stu-id="8c148-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="8c148-143">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-143">Source</span></span>  |<span data-ttu-id="8c148-144">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-144">Reported in activity explorer</span></span>|<span data-ttu-id="8c148-145">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="8c148-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-147">是</span><span class="sxs-lookup"><span data-stu-id="8c148-147">yes</span></span>         |
|<span data-ttu-id="8c148-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-148">Outlook</span></span>         |<span data-ttu-id="8c148-149">是</span><span class="sxs-lookup"><span data-stu-id="8c148-149">yes</span></span>         |<span data-ttu-id="8c148-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="8c148-150">Win 32</span></span>|
|<span data-ttu-id="8c148-151">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-152">是</span><span class="sxs-lookup"><span data-stu-id="8c148-152">yes</span></span>         |
|<span data-ttu-id="8c148-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-153">Exchange</span></span>         |<span data-ttu-id="8c148-154">是</span><span class="sxs-lookup"><span data-stu-id="8c148-154">yes</span></span>         |
|<span data-ttu-id="8c148-155">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-155">AIP unified client</span></span>         |<span data-ttu-id="8c148-156">是</span><span class="sxs-lookup"><span data-stu-id="8c148-156">yes</span></span>         |
|<span data-ttu-id="8c148-157">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-157">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-158">是</span><span class="sxs-lookup"><span data-stu-id="8c148-158">yes</span></span>         |
|<span data-ttu-id="8c148-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-159">MIP SDK</span></span>         |<span data-ttu-id="8c148-160">是</span><span class="sxs-lookup"><span data-stu-id="8c148-160">yes</span></span>         |
|<span data-ttu-id="8c148-161">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-161">RMS service</span></span>         |<span data-ttu-id="8c148-162">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-162">not applicable</span></span>         |
|<span data-ttu-id="8c148-163">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-164">否</span><span class="sxs-lookup"><span data-stu-id="8c148-164">no</span></span>         |<span data-ttu-id="8c148-165">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="8c148-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="8c148-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-166">MCAS</span></span>     |<span data-ttu-id="8c148-167">否</span><span class="sxs-lookup"><span data-stu-id="8c148-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="8c148-168">已移除敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="8c148-168">Sensitivity label removed</span></span>

<span data-ttu-id="8c148-169">每當從檔案或檔中移除靈敏度標籤時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="8c148-170">在儲存時 Office 原生應用程式和 web 應用程式中，會捕獲此事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="8c148-171">它會在 Azure 資訊保護增益集發生時捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="8c148-172">敏感度標記，使用 Office 原生 MIP 標籤，on Outlook 會收集在檔儲存/電子郵件傳送動作之前產生的最後一個標記事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="8c148-173">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-173">Source</span></span>  |<span data-ttu-id="8c148-174">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-174">Reported in activity explorer</span></span> | <span data-ttu-id="8c148-175">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="8c148-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-177">是</span><span class="sxs-lookup"><span data-stu-id="8c148-177">yes</span></span>         |
|<span data-ttu-id="8c148-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-178">Outlook</span></span>         |<span data-ttu-id="8c148-179">是</span><span class="sxs-lookup"><span data-stu-id="8c148-179">yes</span></span>         |<span data-ttu-id="8c148-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="8c148-180">Win 32</span></span>|
|<span data-ttu-id="8c148-181">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-182">是</span><span class="sxs-lookup"><span data-stu-id="8c148-182">yes</span></span>         |
|<span data-ttu-id="8c148-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-183">Exchange</span></span>         |<span data-ttu-id="8c148-184">是</span><span class="sxs-lookup"><span data-stu-id="8c148-184">yes</span></span>         |
|<span data-ttu-id="8c148-185">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-185">AIP unified client</span></span>         |<span data-ttu-id="8c148-186">是</span><span class="sxs-lookup"><span data-stu-id="8c148-186">yes</span></span>         |<span data-ttu-id="8c148-187">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="8c148-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="8c148-188">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-188">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-189">是</span><span class="sxs-lookup"><span data-stu-id="8c148-189">yes</span></span>         |<span data-ttu-id="8c148-190">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="8c148-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="8c148-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-191">MIP SDK</span></span>         |<span data-ttu-id="8c148-192">是</span><span class="sxs-lookup"><span data-stu-id="8c148-192">yes</span></span>         |<span data-ttu-id="8c148-193">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="8c148-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="8c148-194">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-194">RMS service</span></span>         |<span data-ttu-id="8c148-195">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-195">not applicable</span></span>         |
|<span data-ttu-id="8c148-196">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-197">否</span><span class="sxs-lookup"><span data-stu-id="8c148-197">no</span></span>         |<span data-ttu-id="8c148-198">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="8c148-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="8c148-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-199">MCAS</span></span>     |<span data-ttu-id="8c148-200">否</span><span class="sxs-lookup"><span data-stu-id="8c148-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="8c148-201">敏感度標籤檔案讀取</span><span class="sxs-lookup"><span data-stu-id="8c148-201">Sensitivity label file read</span></span>

<span data-ttu-id="8c148-202">此事件會在每次開啟靈敏度標記或受保護的檔時產生。</span><span class="sxs-lookup"><span data-stu-id="8c148-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="8c148-203">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-203">Source</span></span>  |<span data-ttu-id="8c148-204">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-204">Reported in activity explorer</span></span> | <span data-ttu-id="8c148-205">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="8c148-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-207">是</span><span class="sxs-lookup"><span data-stu-id="8c148-207">yes</span></span>         |
|<span data-ttu-id="8c148-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-208">Outlook</span></span>         |<span data-ttu-id="8c148-209">否</span><span class="sxs-lookup"><span data-stu-id="8c148-209">no</span></span>         |
|<span data-ttu-id="8c148-210">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-211">否</span><span class="sxs-lookup"><span data-stu-id="8c148-211">no</span></span>         |
|<span data-ttu-id="8c148-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-212">Exchange</span></span>         |<span data-ttu-id="8c148-213">否</span><span class="sxs-lookup"><span data-stu-id="8c148-213">no</span></span>         |
|<span data-ttu-id="8c148-214">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-214">AIP unified client</span></span>         |<span data-ttu-id="8c148-215">是</span><span class="sxs-lookup"><span data-stu-id="8c148-215">yes</span></span>         |<span data-ttu-id="8c148-216">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="8c148-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="8c148-217">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-217">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-218">是</span><span class="sxs-lookup"><span data-stu-id="8c148-218">yes</span></span>         |<span data-ttu-id="8c148-219">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="8c148-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="8c148-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-220">MIP SDK</span></span>         |<span data-ttu-id="8c148-221">是</span><span class="sxs-lookup"><span data-stu-id="8c148-221">yes</span></span>         |<span data-ttu-id="8c148-222">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="8c148-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="8c148-223">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-223">RMS service</span></span>         |<span data-ttu-id="8c148-224">是</span><span class="sxs-lookup"><span data-stu-id="8c148-224">yes</span></span>         |<span data-ttu-id="8c148-225">*存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="8c148-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="8c148-226">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-227">否</span><span class="sxs-lookup"><span data-stu-id="8c148-227">no</span></span>         |<span data-ttu-id="8c148-228">可在 Microsoft 365 審核記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="8c148-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="8c148-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-229">MCAS</span></span>     |<span data-ttu-id="8c148-230">否</span><span class="sxs-lookup"><span data-stu-id="8c148-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="8c148-231">探索的檔案</span><span class="sxs-lookup"><span data-stu-id="8c148-231">Files discovered</span></span>

<span data-ttu-id="8c148-232">當您每次使用 AIP 掃描程式來掃描不同位置的敏感性資料並尋找檔案時，就會產生這個事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="8c148-233">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-233">Source</span></span>  |<span data-ttu-id="8c148-234">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-234">Reported in activity explorer</span></span> | <span data-ttu-id="8c148-235">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="8c148-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-237">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-237">not applicable</span></span>         |
|<span data-ttu-id="8c148-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-238">Outlook</span></span>         |<span data-ttu-id="8c148-239">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-239">not applicable</span></span>         |
|<span data-ttu-id="8c148-240">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-241">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-241">not applicable</span></span>         |
|<span data-ttu-id="8c148-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-242">Exchange</span></span>         |<span data-ttu-id="8c148-243">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-243">not applicable</span></span>         |
|<span data-ttu-id="8c148-244">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-244">AIP unified client</span></span>         |<span data-ttu-id="8c148-245">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-245">not applicable</span></span>       |
|<span data-ttu-id="8c148-246">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-246">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-247">是</span><span class="sxs-lookup"><span data-stu-id="8c148-247">yes</span></span>         |<span data-ttu-id="8c148-248">AIP *探索* 動作會對應至活動瀏覽器中已 *發現的檔* 動作</span><span class="sxs-lookup"><span data-stu-id="8c148-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="8c148-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-249">MIP SDK</span></span>         |<span data-ttu-id="8c148-250">是</span><span class="sxs-lookup"><span data-stu-id="8c148-250">yes</span></span>         |<span data-ttu-id="8c148-251">AIP *探索* 動作會對應至活動瀏覽器中的 [已 *發現的檔* ] 動作</span><span class="sxs-lookup"><span data-stu-id="8c148-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="8c148-252">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-252">RMS service</span></span>         |<span data-ttu-id="8c148-253">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-253">not applicable</span></span>         |
|<span data-ttu-id="8c148-254">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-255">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-255">not applicable</span></span>         |
|<span data-ttu-id="8c148-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-256">MCAS</span></span>     |<span data-ttu-id="8c148-257">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="8c148-258">敏感度標籤檔案名已重新命名</span><span class="sxs-lookup"><span data-stu-id="8c148-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="8c148-259">此事件會在每次重新命名具有敏感度標籤的檔時產生。</span><span class="sxs-lookup"><span data-stu-id="8c148-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="8c148-260">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-260">Source</span></span>  | <span data-ttu-id="8c148-261">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-261">Reported in activity explorer</span></span> | <span data-ttu-id="8c148-262">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="8c148-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-264">是</span><span class="sxs-lookup"><span data-stu-id="8c148-264">yes</span></span>         |
|<span data-ttu-id="8c148-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-265">Outlook</span></span>         |<span data-ttu-id="8c148-266">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-266">not applicable</span></span>         |
|<span data-ttu-id="8c148-267">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-268">否</span><span class="sxs-lookup"><span data-stu-id="8c148-268">no</span></span>        |
|<span data-ttu-id="8c148-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-269">Exchange</span></span>         |<span data-ttu-id="8c148-270">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-270">not applicable</span></span>         |
|<span data-ttu-id="8c148-271">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-271">AIP unified client</span></span>         |<span data-ttu-id="8c148-272">否</span><span class="sxs-lookup"><span data-stu-id="8c148-272">no</span></span>         |
|<span data-ttu-id="8c148-273">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-273">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-274">否</span><span class="sxs-lookup"><span data-stu-id="8c148-274">no</span></span>         |
|<span data-ttu-id="8c148-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-275">MIP SDK</span></span>         |<span data-ttu-id="8c148-276">否</span><span class="sxs-lookup"><span data-stu-id="8c148-276">no</span></span>         |
|<span data-ttu-id="8c148-277">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-277">RMS service</span></span>         |<span data-ttu-id="8c148-278">否</span><span class="sxs-lookup"><span data-stu-id="8c148-278">no</span></span>      |
|<span data-ttu-id="8c148-279">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-280">否</span><span class="sxs-lookup"><span data-stu-id="8c148-280">no</span></span>         |
|<span data-ttu-id="8c148-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-281">MCAS</span></span>     |<span data-ttu-id="8c148-282">否</span><span class="sxs-lookup"><span data-stu-id="8c148-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="8c148-283">移除檔案</span><span class="sxs-lookup"><span data-stu-id="8c148-283">File removed</span></span>

<span data-ttu-id="8c148-284">此事件會在每次 AIP 掃描程式偵測到先前掃描的檔案已移除時產生。</span><span class="sxs-lookup"><span data-stu-id="8c148-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="8c148-285">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-285">Source</span></span>  |<span data-ttu-id="8c148-286">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-286">Reported in activity explorer</span></span> | <span data-ttu-id="8c148-287">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="8c148-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-289">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-289">not applicable</span></span>         |
|<span data-ttu-id="8c148-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-290">Outlook</span></span>         |<span data-ttu-id="8c148-291">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-291">not applicable</span></span>         |
|<span data-ttu-id="8c148-292">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-293">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-293">not applicable</span></span>           |
|<span data-ttu-id="8c148-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-294">Exchange</span></span>         |<span data-ttu-id="8c148-295">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-295">not applicable</span></span>         |
|<span data-ttu-id="8c148-296">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-296">AIP unified client</span></span>         |<span data-ttu-id="8c148-297">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-297">not applicable</span></span>            |
|<span data-ttu-id="8c148-298">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-298">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-299">是</span><span class="sxs-lookup"><span data-stu-id="8c148-299">yes</span></span>         |
|<span data-ttu-id="8c148-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-300">MIP SDK</span></span>         |<span data-ttu-id="8c148-301">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-301">not applicable</span></span>            |
|<span data-ttu-id="8c148-302">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-302">RMS service</span></span>         |<span data-ttu-id="8c148-303">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-303">not applicable</span></span>         |
|<span data-ttu-id="8c148-304">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-305">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-305">not applicable</span></span>  |
|<span data-ttu-id="8c148-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-306">MCAS</span></span>     |<span data-ttu-id="8c148-307">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="8c148-308">套用保護</span><span class="sxs-lookup"><span data-stu-id="8c148-308">Protection applied</span></span>

<span data-ttu-id="8c148-309">此事件會產生第一次保護是手動新增至沒有標籤的專案。</span><span class="sxs-lookup"><span data-stu-id="8c148-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="8c148-310">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-310">Source</span></span>  |<span data-ttu-id="8c148-311">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-311">Reported in activity explorer</span></span> | <span data-ttu-id="8c148-312">注意</span><span class="sxs-lookup"><span data-stu-id="8c148-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="8c148-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-314">否</span><span class="sxs-lookup"><span data-stu-id="8c148-314">no</span></span>         |
|<span data-ttu-id="8c148-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-315">Outlook</span></span>         |<span data-ttu-id="8c148-316">否</span><span class="sxs-lookup"><span data-stu-id="8c148-316">no</span></span>         |
|<span data-ttu-id="8c148-317">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-318">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-318">not applicable</span></span>           |
|<span data-ttu-id="8c148-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-319">Exchange</span></span>         |<span data-ttu-id="8c148-320">否</span><span class="sxs-lookup"><span data-stu-id="8c148-320">no</span></span>       |
|<span data-ttu-id="8c148-321">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-321">AIP unified client</span></span>         |<span data-ttu-id="8c148-322">是</span><span class="sxs-lookup"><span data-stu-id="8c148-322">yes</span></span>            |
|<span data-ttu-id="8c148-323">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-323">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-324">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-324">not applicable</span></span>         |
|<span data-ttu-id="8c148-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-325">MIP SDK</span></span>         |<span data-ttu-id="8c148-326">是</span><span class="sxs-lookup"><span data-stu-id="8c148-326">yes</span></span>            |
|<span data-ttu-id="8c148-327">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-327">RMS service</span></span>         |<span data-ttu-id="8c148-328">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-328">not applicable</span></span>         |
|<span data-ttu-id="8c148-329">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-330">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-330">not applicable</span></span>            |
|<span data-ttu-id="8c148-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-331">MCAS</span></span>     |<span data-ttu-id="8c148-332">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="8c148-333">變更保護</span><span class="sxs-lookup"><span data-stu-id="8c148-333">Protection changed</span></span>

<span data-ttu-id="8c148-334">每當以手動方式變更未標記檔的保護時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="8c148-335">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-335">Source</span></span>  |<span data-ttu-id="8c148-336">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="8c148-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-338">否</span><span class="sxs-lookup"><span data-stu-id="8c148-338">no</span></span>         |
|<span data-ttu-id="8c148-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-339">Outlook</span></span>         |<span data-ttu-id="8c148-340">否</span><span class="sxs-lookup"><span data-stu-id="8c148-340">no</span></span>         |
|<span data-ttu-id="8c148-341">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-342">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-342">not applicable</span></span>           |
|<span data-ttu-id="8c148-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-343">Exchange</span></span>         |<span data-ttu-id="8c148-344">否</span><span class="sxs-lookup"><span data-stu-id="8c148-344">no</span></span>       |
|<span data-ttu-id="8c148-345">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-345">AIP unified client</span></span>         |<span data-ttu-id="8c148-346">是</span><span class="sxs-lookup"><span data-stu-id="8c148-346">yes</span></span>            |
|<span data-ttu-id="8c148-347">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-347">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-348">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-348">not applicable</span></span>         |
|<span data-ttu-id="8c148-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-349">MIP SDK</span></span>         |<span data-ttu-id="8c148-350">是</span><span class="sxs-lookup"><span data-stu-id="8c148-350">yes</span></span>            |
|<span data-ttu-id="8c148-351">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-351">RMS service</span></span>         |<span data-ttu-id="8c148-352">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-352">not applicable</span></span>         |
|<span data-ttu-id="8c148-353">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-354">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-354">not applicable</span></span>            |
|<span data-ttu-id="8c148-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-355">MCAS</span></span>     |<span data-ttu-id="8c148-356">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="8c148-357">已移除保護</span><span class="sxs-lookup"><span data-stu-id="8c148-357">Protection removed</span></span>

<span data-ttu-id="8c148-358">每當以手動方式變更未標記檔的保護時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="8c148-359">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-359">Source</span></span>  |<span data-ttu-id="8c148-360">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="8c148-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c148-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="8c148-362">否</span><span class="sxs-lookup"><span data-stu-id="8c148-362">no</span></span>         |
|<span data-ttu-id="8c148-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="8c148-363">Outlook</span></span>         |<span data-ttu-id="8c148-364">否</span><span class="sxs-lookup"><span data-stu-id="8c148-364">no</span></span>         |
|<span data-ttu-id="8c148-365">SharePoint線上，OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="8c148-366">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-366">not applicable</span></span>           |
|<span data-ttu-id="8c148-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-367">Exchange</span></span>         |<span data-ttu-id="8c148-368">否</span><span class="sxs-lookup"><span data-stu-id="8c148-368">no</span></span>       |
|<span data-ttu-id="8c148-369">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="8c148-369">AIP unified client</span></span>         |<span data-ttu-id="8c148-370">是</span><span class="sxs-lookup"><span data-stu-id="8c148-370">yes</span></span>            |
|<span data-ttu-id="8c148-371">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="8c148-371">AIP unified scanner</span></span>         |<span data-ttu-id="8c148-372">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-372">not applicable</span></span>         |
|<span data-ttu-id="8c148-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="8c148-373">MIP SDK</span></span>         |<span data-ttu-id="8c148-374">是</span><span class="sxs-lookup"><span data-stu-id="8c148-374">yes</span></span>            |
|<span data-ttu-id="8c148-375">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="8c148-375">RMS service</span></span>         |<span data-ttu-id="8c148-376">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-376">not applicable</span></span>         |
|<span data-ttu-id="8c148-377">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="8c148-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="8c148-378">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-378">not applicable</span></span>            |
|<span data-ttu-id="8c148-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-379">MCAS</span></span>     |<span data-ttu-id="8c148-380">不適用</span><span class="sxs-lookup"><span data-stu-id="8c148-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="8c148-381">符合的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="8c148-381">DLP policy matched</span></span>

<span data-ttu-id="8c148-382">每當在檔或電子郵件上符合 DLP 原則時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="8c148-383">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-383">Source</span></span>  |<span data-ttu-id="8c148-384">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="8c148-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-385">Exchange</span></span>         |<span data-ttu-id="8c148-386">是</span><span class="sxs-lookup"><span data-stu-id="8c148-386">yes</span></span>       |
|<span data-ttu-id="8c148-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8c148-387">SharePoint Online</span></span>|<span data-ttu-id="8c148-388">是</span><span class="sxs-lookup"><span data-stu-id="8c148-388">yes</span></span>          |
|<span data-ttu-id="8c148-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-389">OneDrive</span></span> |<span data-ttu-id="8c148-390">是</span><span class="sxs-lookup"><span data-stu-id="8c148-390">yes</span></span>|
|<span data-ttu-id="8c148-391">Teams</span><span class="sxs-lookup"><span data-stu-id="8c148-391">Teams</span></span> |<span data-ttu-id="8c148-392">是</span><span class="sxs-lookup"><span data-stu-id="8c148-392">yes</span></span>   |
|<span data-ttu-id="8c148-393">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="8c148-393">Windows 10 devices</span></span>         |<span data-ttu-id="8c148-394">是</span><span class="sxs-lookup"><span data-stu-id="8c148-394">yes</span></span> |
|<span data-ttu-id="8c148-395">Mac</span><span class="sxs-lookup"><span data-stu-id="8c148-395">MAC</span></span>         |<span data-ttu-id="8c148-396">否</span><span class="sxs-lookup"><span data-stu-id="8c148-396">no</span></span>     |
|<span data-ttu-id="8c148-397">內部部署</span><span class="sxs-lookup"><span data-stu-id="8c148-397">on-premises</span></span>         |<span data-ttu-id="8c148-398">否</span><span class="sxs-lookup"><span data-stu-id="8c148-398">no</span></span>|
|<span data-ttu-id="8c148-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="8c148-399">MCAS</span></span>     |<span data-ttu-id="8c148-400">否</span><span class="sxs-lookup"><span data-stu-id="8c148-400">no</span></span>        | 

<span data-ttu-id="8c148-401">Windows 10 裝置的事件 (Endpoint DLP) 為：</span><span class="sxs-lookup"><span data-stu-id="8c148-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="8c148-402">已刪除檔案</span><span class="sxs-lookup"><span data-stu-id="8c148-402">file deleted</span></span>
- <span data-ttu-id="8c148-403">已建立檔</span><span class="sxs-lookup"><span data-stu-id="8c148-403">file created</span></span>
- <span data-ttu-id="8c148-404">檔案已複製到剪貼簿</span><span class="sxs-lookup"><span data-stu-id="8c148-404">file copied to clipboard</span></span>
- <span data-ttu-id="8c148-405">修改檔案</span><span class="sxs-lookup"><span data-stu-id="8c148-405">file modified</span></span>
- <span data-ttu-id="8c148-406">檔案讀取</span><span class="sxs-lookup"><span data-stu-id="8c148-406">file read</span></span>
- <span data-ttu-id="8c148-407">已列印檔案</span><span class="sxs-lookup"><span data-stu-id="8c148-407">file printed</span></span>
- <span data-ttu-id="8c148-408">重新命名的檔案名</span><span class="sxs-lookup"><span data-stu-id="8c148-408">file renamed</span></span>
- <span data-ttu-id="8c148-409">檔案已複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="8c148-409">file copied to network share</span></span>
- <span data-ttu-id="8c148-410">unallowed 應用程式所存取的檔案</span><span class="sxs-lookup"><span data-stu-id="8c148-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="8c148-411">套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c148-411">Retention label applied</span></span> 

<span data-ttu-id="8c148-412">此事件會在每次標記未標記的檔或以保留標籤傳送電子郵件時產生。</span><span class="sxs-lookup"><span data-stu-id="8c148-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="8c148-413">它會在儲存檔時和傳送電子郵件的時間內捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="8c148-414">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-414">Source</span></span>  |<span data-ttu-id="8c148-415">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="8c148-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-416">Exchange</span></span>         |<span data-ttu-id="8c148-417">否</span><span class="sxs-lookup"><span data-stu-id="8c148-417">no</span></span>       |
|<span data-ttu-id="8c148-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8c148-418">SharePoint Online</span></span>|<span data-ttu-id="8c148-419">是</span><span class="sxs-lookup"><span data-stu-id="8c148-419">yes</span></span>          |
|<span data-ttu-id="8c148-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-420">OneDrive</span></span> |<span data-ttu-id="8c148-421">是</span><span class="sxs-lookup"><span data-stu-id="8c148-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="8c148-422">已變更保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c148-422">Retention label changed</span></span>

<span data-ttu-id="8c148-423">每當檔或電子郵件上的標籤更新時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="8c148-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="8c148-424">它會在儲存檔時和傳送電子郵件的時間內捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="8c148-425">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-425">Source</span></span>  |<span data-ttu-id="8c148-426">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="8c148-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-427">Exchange</span></span>         |<span data-ttu-id="8c148-428">否</span><span class="sxs-lookup"><span data-stu-id="8c148-428">no</span></span>       |
|<span data-ttu-id="8c148-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8c148-429">SharePoint Online</span></span>|<span data-ttu-id="8c148-430">是</span><span class="sxs-lookup"><span data-stu-id="8c148-430">yes</span></span>          |
|<span data-ttu-id="8c148-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-431">OneDrive</span></span> |<span data-ttu-id="8c148-432">是</span><span class="sxs-lookup"><span data-stu-id="8c148-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="8c148-433">已移除保留標籤</span><span class="sxs-lookup"><span data-stu-id="8c148-433">Retention label removed</span></span>

<span data-ttu-id="8c148-434">此事件會在每次從檔案或檔中移除標籤時產生。</span><span class="sxs-lookup"><span data-stu-id="8c148-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="8c148-435">它會在儲存檔時和傳送電子郵件的時間內捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="8c148-436">來源</span><span class="sxs-lookup"><span data-stu-id="8c148-436">Source</span></span>  |<span data-ttu-id="8c148-437">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="8c148-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="8c148-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="8c148-438">Exchange</span></span>         |<span data-ttu-id="8c148-439">否</span><span class="sxs-lookup"><span data-stu-id="8c148-439">no</span></span>       |
|<span data-ttu-id="8c148-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8c148-440">SharePoint Online</span></span>|<span data-ttu-id="8c148-441">是</span><span class="sxs-lookup"><span data-stu-id="8c148-441">yes</span></span>          |
|<span data-ttu-id="8c148-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c148-442">OneDrive</span></span> |<span data-ttu-id="8c148-443">是</span><span class="sxs-lookup"><span data-stu-id="8c148-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="8c148-444">已知問題</span><span class="sxs-lookup"><span data-stu-id="8c148-444">Known issues</span></span>
  
- <span data-ttu-id="8c148-445">向使用者顯示建議的標籤工具提示時，不會將其捕獲。</span><span class="sxs-lookup"><span data-stu-id="8c148-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="8c148-446">不過，如果使用者選擇套用建議的標籤，標籤會顯示在 *建議* 的 *套用欄位底下*。</span><span class="sxs-lookup"><span data-stu-id="8c148-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="8c148-447">敏感度標籤上目前無法使用對齊文字，請從 Sharepoint 和 OneDrive 降級。</span><span class="sxs-lookup"><span data-stu-id="8c148-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="8c148-448">機密資訊類型目前不適用於來自 Word 的 autolabeling 活動、Excel、PowerPoint 和 Outlook，以及 SharePoint 線上及 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="8c148-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
