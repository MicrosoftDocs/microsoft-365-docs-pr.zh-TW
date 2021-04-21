---
title: 活動 explorer 中所報告的標記動作
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
description: 列出活動瀏覽器中可用的標記動作清單。
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902941"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="d9b0d-103">活動瀏覽器中可用的標記活動</span><span class="sxs-lookup"><span data-stu-id="d9b0d-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="d9b0d-104">套用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d9b0d-104">Sensitivity label applied</span></span>

<span data-ttu-id="d9b0d-105">此事件會在每次標記未標記的檔或以標籤傳送電子郵件時產生。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-105">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span> 

- <span data-ttu-id="d9b0d-106">它會在 Office 原生應用程式和 web 應用程式中儲存時捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="d9b0d-107">它會在 Azure 資訊保護增益集發生時捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="d9b0d-108">升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="d9b0d-109">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-109">Source</span></span>  |<span data-ttu-id="d9b0d-110">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-110">Reported in activity explorer</span></span> | <span data-ttu-id="d9b0d-111">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="d9b0d-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="d9b0d-113">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-113">yes</span></span> |
|<span data-ttu-id="d9b0d-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-114">Outlook</span></span>| <span data-ttu-id="d9b0d-115">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-115">yes</span></span> |<span data-ttu-id="d9b0d-116">從 Win 32</span><span class="sxs-lookup"><span data-stu-id="d9b0d-116">from Win 32</span></span> |
|<span data-ttu-id="d9b0d-117">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="d9b0d-118">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-118">yes</span></span> | |
|<span data-ttu-id="d9b0d-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-119">Exchange</span></span>        |<span data-ttu-id="d9b0d-120">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-120">yes</span></span>         | |
|<span data-ttu-id="d9b0d-121">Azure 資訊保護 (AIP) 整合用戶端和 AIP 整合掃描程式</span><span class="sxs-lookup"><span data-stu-id="d9b0d-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="d9b0d-122">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-122">yes</span></span> |<span data-ttu-id="d9b0d-123">AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*</span><span class="sxs-lookup"><span data-stu-id="d9b0d-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="d9b0d-124">Microsoft 資訊保護 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="d9b0d-125">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-125">yes</span></span>|<span data-ttu-id="d9b0d-126">AIP *new label* action 會對應至在活動瀏覽器中套用的 *標籤*</span><span class="sxs-lookup"><span data-stu-id="d9b0d-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="d9b0d-127">Rights Management Service (RMS) </span><span class="sxs-lookup"><span data-stu-id="d9b0d-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="d9b0d-128">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-128">not applicable</span></span>         | |
|<span data-ttu-id="d9b0d-129">Power BI desktop 和 web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-129">Power BI desktop and web</span></span>        | <span data-ttu-id="d9b0d-130">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-130">no</span></span>| <span data-ttu-id="d9b0d-131">可在 Microsoft 365 審計記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="d9b0d-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="d9b0d-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="d9b0d-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="d9b0d-133">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="d9b0d-134">已變更敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d9b0d-134">Sensitivity label changed</span></span>

<span data-ttu-id="d9b0d-135">每當檔或電子郵件上的標籤更新時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-135">This event is generated each time a label is updated on the document or email.</span></span>

- <span data-ttu-id="d9b0d-136">針對 AIP 整合用戶端、統一掃描器和 MIP SDK 來源，AIP *升級卷* 標和 *降級標籤* 指令會對應至活動 explorer *標籤已變更*</span><span class="sxs-lookup"><span data-stu-id="d9b0d-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="d9b0d-137">它會在 Office 原生應用程式和 web 應用程式中的儲存點進行捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="d9b0d-138">在 Azure 資訊保護統一用戶端增益集與掃描器 enforcements 中發生時，會將它捕獲</span><span class="sxs-lookup"><span data-stu-id="d9b0d-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="d9b0d-139">升級和降級標籤動作也可以透過 [ *標籤事件種類* ] 欄位及 [篩選] 加以監視。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="d9b0d-140">除了 SharePoint Online 和 OneDrive 之外，也會捕獲 *調整* 文字。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="d9b0d-141">在 Outlook 上的 Office 原生應用程式中完成的敏感度標記，會收集在檔儲存/電子郵件傳送動作之前所產生的最後一個動作。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="d9b0d-142">例如，如果使用者在傳送之前在電子郵件上變更了標籤，則會在電子郵件傳送時，最後一個標籤會在審計記錄檔中取得，然後在活動 explorer 中報告。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="d9b0d-143">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-143">Source</span></span>  |<span data-ttu-id="d9b0d-144">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-144">Reported in activity explorer</span></span>|<span data-ttu-id="d9b0d-145">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="d9b0d-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-147">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-147">yes</span></span>         |
|<span data-ttu-id="d9b0d-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-148">Outlook</span></span>         |<span data-ttu-id="d9b0d-149">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-149">yes</span></span>         |<span data-ttu-id="d9b0d-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="d9b0d-150">Win 32</span></span>|
|<span data-ttu-id="d9b0d-151">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-152">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-152">yes</span></span>         |
|<span data-ttu-id="d9b0d-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-153">Exchange</span></span>         |<span data-ttu-id="d9b0d-154">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-154">yes</span></span>         |
|<span data-ttu-id="d9b0d-155">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-155">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-156">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-156">yes</span></span>         |
|<span data-ttu-id="d9b0d-157">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-157">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-158">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-158">yes</span></span>         |
|<span data-ttu-id="d9b0d-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-159">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-160">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-160">yes</span></span>         |
|<span data-ttu-id="d9b0d-161">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-161">RMS service</span></span>         |<span data-ttu-id="d9b0d-162">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-162">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-163">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-164">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-164">no</span></span>         |<span data-ttu-id="d9b0d-165">可在 Microsoft 365 審計記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="d9b0d-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="d9b0d-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-166">MCAS</span></span>     |<span data-ttu-id="d9b0d-167">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="d9b0d-168">已移除敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d9b0d-168">Sensitivity label removed</span></span>

<span data-ttu-id="d9b0d-169">此事件會在每次從檔案或檔中移除標籤時產生。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-169">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="d9b0d-170">在 Office 原生應用程式和 web 應用程式中儲存時，會捕獲此事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="d9b0d-171">它會在 Azure 資訊保護增益集發生時捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="d9b0d-172">在 Outlook 上，使用 Office native MIP 標籤的敏感度標籤，會收集在儲存檔/電子郵件傳送動作之前所產生的最後一個標記事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="d9b0d-173">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-173">Source</span></span>  |<span data-ttu-id="d9b0d-174">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-174">Reported in activity explorer</span></span> | <span data-ttu-id="d9b0d-175">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="d9b0d-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-177">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-177">yes</span></span>         |
|<span data-ttu-id="d9b0d-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-178">Outlook</span></span>         |<span data-ttu-id="d9b0d-179">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-179">yes</span></span>         |<span data-ttu-id="d9b0d-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="d9b0d-180">Win 32</span></span>|
|<span data-ttu-id="d9b0d-181">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-182">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-182">yes</span></span>         |
|<span data-ttu-id="d9b0d-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-183">Exchange</span></span>         |<span data-ttu-id="d9b0d-184">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-184">yes</span></span>         |
|<span data-ttu-id="d9b0d-185">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-185">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-186">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-186">yes</span></span>         |<span data-ttu-id="d9b0d-187">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="d9b0d-188">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-188">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-189">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-189">yes</span></span>         |<span data-ttu-id="d9b0d-190">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="d9b0d-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-191">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-192">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-192">yes</span></span>         |<span data-ttu-id="d9b0d-193">AIP *移除標籤* 動作會對應至活動 explorer 中 *已移除標籤* 的動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="d9b0d-194">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-194">RMS service</span></span>         |<span data-ttu-id="d9b0d-195">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-195">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-196">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-197">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-197">no</span></span>         |<span data-ttu-id="d9b0d-198">可在 Microsoft 365 審計記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="d9b0d-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="d9b0d-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-199">MCAS</span></span>     |<span data-ttu-id="d9b0d-200">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="d9b0d-201">敏感度標籤檔案讀取</span><span class="sxs-lookup"><span data-stu-id="d9b0d-201">Sensitivity label file read</span></span>

<span data-ttu-id="d9b0d-202">此事件會在每次開啟已標記或受保護的檔時產生。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-202">This event is generated each time a labeled or protected document is opened.</span></span>

|<span data-ttu-id="d9b0d-203">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-203">Source</span></span>  |<span data-ttu-id="d9b0d-204">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-204">Reported in activity explorer</span></span> | <span data-ttu-id="d9b0d-205">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="d9b0d-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-207">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-207">yes</span></span>         |
|<span data-ttu-id="d9b0d-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-208">Outlook</span></span>         |<span data-ttu-id="d9b0d-209">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-209">no</span></span>         |
|<span data-ttu-id="d9b0d-210">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-211">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-211">no</span></span>         |
|<span data-ttu-id="d9b0d-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-212">Exchange</span></span>         |<span data-ttu-id="d9b0d-213">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-213">no</span></span>         |
|<span data-ttu-id="d9b0d-214">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-214">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-215">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-215">yes</span></span>         |<span data-ttu-id="d9b0d-216">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="d9b0d-217">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-217">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-218">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-218">yes</span></span>         |<span data-ttu-id="d9b0d-219">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="d9b0d-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-220">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-221">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-221">yes</span></span>         |<span data-ttu-id="d9b0d-222">AIP *存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="d9b0d-223">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-223">RMS service</span></span>         |<span data-ttu-id="d9b0d-224">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-224">yes</span></span>         |<span data-ttu-id="d9b0d-225">*存取* 動作會對應至活動瀏覽器中的檔案 *讀取* 動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="d9b0d-226">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-227">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-227">no</span></span>         |<span data-ttu-id="d9b0d-228">可在 Microsoft 365 審計記錄檔中存取</span><span class="sxs-lookup"><span data-stu-id="d9b0d-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="d9b0d-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-229">MCAS</span></span>     |<span data-ttu-id="d9b0d-230">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-230">no</span></span>         |         |


## <a name="sensitivity-label-files-discovered"></a><span data-ttu-id="d9b0d-231">已探索敏感度標籤檔案</span><span class="sxs-lookup"><span data-stu-id="d9b0d-231">Sensitivity label files discovered</span></span>

<span data-ttu-id="d9b0d-232">當您每次使用 AIP 掃描程式來掃描不同位置的敏感性資料並尋找檔案時，就會產生這個事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="d9b0d-233">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-233">Source</span></span>  |<span data-ttu-id="d9b0d-234">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-234">Reported in activity explorer</span></span> | <span data-ttu-id="d9b0d-235">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="d9b0d-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-237">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-237">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-238">Outlook</span></span>         |<span data-ttu-id="d9b0d-239">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-239">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-240">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-241">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-241">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-242">Exchange</span></span>         |<span data-ttu-id="d9b0d-243">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-243">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-244">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-244">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-245">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-245">not applicable</span></span>       |
|<span data-ttu-id="d9b0d-246">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-246">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-247">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-247">yes</span></span>         |<span data-ttu-id="d9b0d-248">AIP *探索* 動作會對應至活動瀏覽器中已 *發現的檔* 動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="d9b0d-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-249">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-250">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-250">yes</span></span>         |<span data-ttu-id="d9b0d-251">AIP *探索* 動作會對應至活動瀏覽器中的 [已 *發現的檔* ] 動作</span><span class="sxs-lookup"><span data-stu-id="d9b0d-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="d9b0d-252">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-252">RMS service</span></span>         |<span data-ttu-id="d9b0d-253">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-253">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-254">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-255">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-255">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-256">MCAS</span></span>     |<span data-ttu-id="d9b0d-257">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="d9b0d-258">敏感度標籤檔案名已重新命名</span><span class="sxs-lookup"><span data-stu-id="d9b0d-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="d9b0d-259">此事件會在每次重新命名具有敏感度標籤的檔時產生。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="d9b0d-260">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-260">Source</span></span>  | <span data-ttu-id="d9b0d-261">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-261">Reported in activity explorer</span></span> | <span data-ttu-id="d9b0d-262">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="d9b0d-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-264">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-264">yes</span></span>         |
|<span data-ttu-id="d9b0d-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-265">Outlook</span></span>         |<span data-ttu-id="d9b0d-266">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-266">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-267">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-268">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-268">no</span></span>        |
|<span data-ttu-id="d9b0d-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-269">Exchange</span></span>         |<span data-ttu-id="d9b0d-270">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-270">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-271">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-271">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-272">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-272">no</span></span>         |
|<span data-ttu-id="d9b0d-273">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-273">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-274">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-274">no</span></span>         |
|<span data-ttu-id="d9b0d-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-275">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-276">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-276">no</span></span>         |
|<span data-ttu-id="d9b0d-277">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-277">RMS service</span></span>         |<span data-ttu-id="d9b0d-278">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-278">no</span></span>      |
|<span data-ttu-id="d9b0d-279">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-280">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-280">no</span></span>         |
|<span data-ttu-id="d9b0d-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-281">MCAS</span></span>     |<span data-ttu-id="d9b0d-282">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-282">no</span></span>         |         |


## <a name="sensitivity-label-file-removed"></a><span data-ttu-id="d9b0d-283">已移除敏感度標籤檔案</span><span class="sxs-lookup"><span data-stu-id="d9b0d-283">Sensitivity label file removed</span></span>

<span data-ttu-id="d9b0d-284">此事件會在每次 AIP 掃描程式偵測到先前掃描的檔案已移除時產生。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="d9b0d-285">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-285">Source</span></span>  |<span data-ttu-id="d9b0d-286">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-286">Reported in activity explorer</span></span> | <span data-ttu-id="d9b0d-287">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="d9b0d-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-289">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-289">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-290">Outlook</span></span>         |<span data-ttu-id="d9b0d-291">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-291">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-292">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-293">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-293">not applicable</span></span>           |
|<span data-ttu-id="d9b0d-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-294">Exchange</span></span>         |<span data-ttu-id="d9b0d-295">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-295">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-296">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-296">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-297">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-297">not applicable</span></span>            |
|<span data-ttu-id="d9b0d-298">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-298">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-299">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-299">yes</span></span>         |
|<span data-ttu-id="d9b0d-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-300">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-301">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-301">not applicable</span></span>            |
|<span data-ttu-id="d9b0d-302">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-302">RMS service</span></span>         |<span data-ttu-id="d9b0d-303">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-303">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-304">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-305">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-305">not applicable</span></span>  |
|<span data-ttu-id="d9b0d-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-306">MCAS</span></span>     |<span data-ttu-id="d9b0d-307">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-307">not applicable</span></span>        |         |

### <a name="sensitivity-label-protection-applied"></a><span data-ttu-id="d9b0d-308">套用敏感度標籤保護</span><span class="sxs-lookup"><span data-stu-id="d9b0d-308">Sensitivity label protection applied</span></span>

<span data-ttu-id="d9b0d-309">此事件會產生第一次保護是手動新增至沒有標籤的專案。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="d9b0d-310">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-310">Source</span></span>  |<span data-ttu-id="d9b0d-311">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-311">Reported in activity explorer</span></span> | <span data-ttu-id="d9b0d-312">注意</span><span class="sxs-lookup"><span data-stu-id="d9b0d-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="d9b0d-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-314">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-314">no</span></span>         |
|<span data-ttu-id="d9b0d-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-315">Outlook</span></span>         |<span data-ttu-id="d9b0d-316">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-316">no</span></span>         |
|<span data-ttu-id="d9b0d-317">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-318">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-318">not applicable</span></span>           |
|<span data-ttu-id="d9b0d-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-319">Exchange</span></span>         |<span data-ttu-id="d9b0d-320">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-320">no</span></span>       |
|<span data-ttu-id="d9b0d-321">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-321">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-322">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-322">yes</span></span>            |
|<span data-ttu-id="d9b0d-323">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-323">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-324">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-324">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-325">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-326">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-326">yes</span></span>            |
|<span data-ttu-id="d9b0d-327">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-327">RMS service</span></span>         |<span data-ttu-id="d9b0d-328">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-328">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-329">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-330">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-330">not applicable</span></span>            |
|<span data-ttu-id="d9b0d-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-331">MCAS</span></span>     |<span data-ttu-id="d9b0d-332">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-332">not applicable</span></span>        |         |

## <a name="sensitivity-label-protection-changed"></a><span data-ttu-id="d9b0d-333">已變更敏感度標籤保護</span><span class="sxs-lookup"><span data-stu-id="d9b0d-333">Sensitivity label protection changed</span></span>

<span data-ttu-id="d9b0d-334">每當以手動方式變更未標記檔的保護時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="d9b0d-335">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-335">Source</span></span>  |<span data-ttu-id="d9b0d-336">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="d9b0d-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-338">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-338">no</span></span>         |
|<span data-ttu-id="d9b0d-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-339">Outlook</span></span>         |<span data-ttu-id="d9b0d-340">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-340">no</span></span>         |
|<span data-ttu-id="d9b0d-341">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-342">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-342">not applicable</span></span>           |
|<span data-ttu-id="d9b0d-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-343">Exchange</span></span>         |<span data-ttu-id="d9b0d-344">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-344">no</span></span>       |
|<span data-ttu-id="d9b0d-345">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-345">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-346">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-346">yes</span></span>            |
|<span data-ttu-id="d9b0d-347">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-347">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-348">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-348">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-349">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-350">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-350">yes</span></span>            |
|<span data-ttu-id="d9b0d-351">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-351">RMS service</span></span>         |<span data-ttu-id="d9b0d-352">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-352">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-353">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-354">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-354">not applicable</span></span>            |
|<span data-ttu-id="d9b0d-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-355">MCAS</span></span>     |<span data-ttu-id="d9b0d-356">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-356">not applicable</span></span>        |

## <a name="sensitivity-label-protection-removed"></a><span data-ttu-id="d9b0d-357">已移除敏感度標籤保護</span><span class="sxs-lookup"><span data-stu-id="d9b0d-357">Sensitivity label protection removed</span></span>

<span data-ttu-id="d9b0d-358">每當以手動方式變更未標記檔的保護時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="d9b0d-359">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-359">Source</span></span>  |<span data-ttu-id="d9b0d-360">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="d9b0d-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d9b0d-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="d9b0d-362">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-362">no</span></span>         |
|<span data-ttu-id="d9b0d-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="d9b0d-363">Outlook</span></span>         |<span data-ttu-id="d9b0d-364">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-364">no</span></span>         |
|<span data-ttu-id="d9b0d-365">線上 SharePoint OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="d9b0d-366">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-366">not applicable</span></span>           |
|<span data-ttu-id="d9b0d-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-367">Exchange</span></span>         |<span data-ttu-id="d9b0d-368">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-368">no</span></span>       |
|<span data-ttu-id="d9b0d-369">AIP 整合用戶端</span><span class="sxs-lookup"><span data-stu-id="d9b0d-369">AIP unified client</span></span>         |<span data-ttu-id="d9b0d-370">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-370">yes</span></span>            |
|<span data-ttu-id="d9b0d-371">AIP 整合掃描器</span><span class="sxs-lookup"><span data-stu-id="d9b0d-371">AIP unified scanner</span></span>         |<span data-ttu-id="d9b0d-372">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-372">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="d9b0d-373">MIP SDK</span></span>         |<span data-ttu-id="d9b0d-374">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-374">yes</span></span>            |
|<span data-ttu-id="d9b0d-375">RMS 服務</span><span class="sxs-lookup"><span data-stu-id="d9b0d-375">RMS service</span></span>         |<span data-ttu-id="d9b0d-376">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-376">not applicable</span></span>         |
|<span data-ttu-id="d9b0d-377">Power BI desktop 和 Web</span><span class="sxs-lookup"><span data-stu-id="d9b0d-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="d9b0d-378">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-378">not applicable</span></span>            |
|<span data-ttu-id="d9b0d-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-379">MCAS</span></span>     |<span data-ttu-id="d9b0d-380">不適用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-380">not applicable</span></span>        |

## <a name="sensitivity-label-dlp-policy-matched"></a><span data-ttu-id="d9b0d-381">敏感度標籤 DLP 原則符合</span><span class="sxs-lookup"><span data-stu-id="d9b0d-381">Sensitivity label DLP policy matched</span></span>

<span data-ttu-id="d9b0d-382">每當符合 DLP 原則時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-382">This event is generated each time a DLP policy is matched.</span></span>

|<span data-ttu-id="d9b0d-383">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-383">Source</span></span>  |<span data-ttu-id="d9b0d-384">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="d9b0d-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-385">Exchange</span></span>         |<span data-ttu-id="d9b0d-386">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-386">yes</span></span>       |
|<span data-ttu-id="d9b0d-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9b0d-387">SharePoint Online</span></span>|<span data-ttu-id="d9b0d-388">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-388">yes</span></span>          |
|<span data-ttu-id="d9b0d-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-389">OneDrive</span></span> |<span data-ttu-id="d9b0d-390">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-390">yes</span></span>|
|<span data-ttu-id="d9b0d-391">Teams</span><span class="sxs-lookup"><span data-stu-id="d9b0d-391">Teams</span></span> |<span data-ttu-id="d9b0d-392">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-392">yes</span></span>   |
|<span data-ttu-id="d9b0d-393">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="d9b0d-393">Windows 10 devices</span></span>         |<span data-ttu-id="d9b0d-394">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-394">yes</span></span> |
|<span data-ttu-id="d9b0d-395">Mac</span><span class="sxs-lookup"><span data-stu-id="d9b0d-395">MAC</span></span>         |<span data-ttu-id="d9b0d-396">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-396">no</span></span>     |
|<span data-ttu-id="d9b0d-397">內部部署</span><span class="sxs-lookup"><span data-stu-id="d9b0d-397">on-premises</span></span>         |<span data-ttu-id="d9b0d-398">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-398">no</span></span>|
|<span data-ttu-id="d9b0d-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="d9b0d-399">MCAS</span></span>     |<span data-ttu-id="d9b0d-400">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-400">no</span></span>        | 

<span data-ttu-id="d9b0d-401">Windows 10 裝置的事件 (端點 DLP) 如下：</span><span class="sxs-lookup"><span data-stu-id="d9b0d-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="d9b0d-402">已刪除檔案</span><span class="sxs-lookup"><span data-stu-id="d9b0d-402">file deleted</span></span>
- <span data-ttu-id="d9b0d-403">已建立檔</span><span class="sxs-lookup"><span data-stu-id="d9b0d-403">file created</span></span>
- <span data-ttu-id="d9b0d-404">檔案已複製到剪貼簿</span><span class="sxs-lookup"><span data-stu-id="d9b0d-404">file copied to clipboard</span></span>
- <span data-ttu-id="d9b0d-405">修改檔案</span><span class="sxs-lookup"><span data-stu-id="d9b0d-405">file modified</span></span>
- <span data-ttu-id="d9b0d-406">檔案讀取</span><span class="sxs-lookup"><span data-stu-id="d9b0d-406">file read</span></span>
- <span data-ttu-id="d9b0d-407">已列印檔案</span><span class="sxs-lookup"><span data-stu-id="d9b0d-407">file printed</span></span>
- <span data-ttu-id="d9b0d-408">重新命名的檔案名</span><span class="sxs-lookup"><span data-stu-id="d9b0d-408">file renamed</span></span>
- <span data-ttu-id="d9b0d-409">檔案已複製到網路共用</span><span class="sxs-lookup"><span data-stu-id="d9b0d-409">file copied to network share</span></span>
- <span data-ttu-id="d9b0d-410">unallowed 應用程式所存取的檔案</span><span class="sxs-lookup"><span data-stu-id="d9b0d-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="d9b0d-411">套用保留標籤</span><span class="sxs-lookup"><span data-stu-id="d9b0d-411">Retention label applied</span></span> 

<span data-ttu-id="d9b0d-412">此事件會在每次標記未標記的檔或以標籤傳送電子郵件時產生。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-412">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span>

- <span data-ttu-id="d9b0d-413">它會在 Office 原生應用程式和 web 應用程式中儲存時捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-413">It is captured at the time of save in Office native applications and web applications.</span></span>

|<span data-ttu-id="d9b0d-414">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-414">Source</span></span>  |<span data-ttu-id="d9b0d-415">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="d9b0d-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-416">Exchange</span></span>         |<span data-ttu-id="d9b0d-417">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-417">no</span></span>       |
|<span data-ttu-id="d9b0d-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9b0d-418">SharePoint Online</span></span>|<span data-ttu-id="d9b0d-419">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-419">yes</span></span>          |
|<span data-ttu-id="d9b0d-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-420">OneDrive</span></span> |<span data-ttu-id="d9b0d-421">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="d9b0d-422">已變更保留標籤</span><span class="sxs-lookup"><span data-stu-id="d9b0d-422">Retention label changed</span></span>

<span data-ttu-id="d9b0d-423">每當檔或電子郵件上的標籤更新時，就會產生此事件。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="d9b0d-424">它會在儲存時被捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-424">It is captured at the time of save.</span></span>

|<span data-ttu-id="d9b0d-425">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-425">Source</span></span>  |<span data-ttu-id="d9b0d-426">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="d9b0d-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-427">Exchange</span></span>         |<span data-ttu-id="d9b0d-428">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-428">no</span></span>       |
|<span data-ttu-id="d9b0d-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9b0d-429">SharePoint Online</span></span>|<span data-ttu-id="d9b0d-430">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-430">yes</span></span>          |
|<span data-ttu-id="d9b0d-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-431">OneDrive</span></span> |<span data-ttu-id="d9b0d-432">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="d9b0d-433">已移除保留標籤</span><span class="sxs-lookup"><span data-stu-id="d9b0d-433">Retention label removed</span></span>

<span data-ttu-id="d9b0d-434">此事件會在每次從檔案或檔中移除標籤時產生。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="d9b0d-435">它會在儲存時被捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-435">It is captured at the time of save.</span></span>

|<span data-ttu-id="d9b0d-436">來源</span><span class="sxs-lookup"><span data-stu-id="d9b0d-436">Source</span></span>  |<span data-ttu-id="d9b0d-437">活動 explorer 中報告</span><span class="sxs-lookup"><span data-stu-id="d9b0d-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="d9b0d-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="d9b0d-438">Exchange</span></span>         |<span data-ttu-id="d9b0d-439">否</span><span class="sxs-lookup"><span data-stu-id="d9b0d-439">no</span></span>       |
|<span data-ttu-id="d9b0d-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d9b0d-440">SharePoint Online</span></span>|<span data-ttu-id="d9b0d-441">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-441">yes</span></span>          |
|<span data-ttu-id="d9b0d-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d9b0d-442">OneDrive</span></span> |<span data-ttu-id="d9b0d-443">是</span><span class="sxs-lookup"><span data-stu-id="d9b0d-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="d9b0d-444">已知問題</span><span class="sxs-lookup"><span data-stu-id="d9b0d-444">Known issues</span></span>
  
- <span data-ttu-id="d9b0d-445">向使用者顯示建議的標籤工具提示時，不會將其捕獲。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="d9b0d-446">不過，如果使用者選擇套用建議的標籤，標籤會顯示在 *建議* 的 *套用欄位底下*。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="d9b0d-447">敏感度標籤上目前無法使用對齊文字，請從 Sharepoint 和 OneDrive 降級。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="d9b0d-448">機密資訊類型目前不適用於來自 Word、Excel、PowerPoint 和 Outlook 的 autolabeling 活動，以及 SharePoint 線上及 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="d9b0d-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
