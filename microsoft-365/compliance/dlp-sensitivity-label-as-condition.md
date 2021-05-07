---
title: 在 DLP 原則中使用敏感度標籤做為條件
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 了解您可以在 DLP 原則中使用敏感度標籤做為條件的服務和項目類型
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876292"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="be157-103">在 DLP 原則中使用敏感度標籤做為條件</span><span class="sxs-lookup"><span data-stu-id="be157-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="be157-104">針對這些位置，您可以在 DLP 原則中使用[敏感度標籤](sensitivity-labels.md)做為條件：</span><span class="sxs-lookup"><span data-stu-id="be157-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="be157-105">Exchange Online 電子郵件</span><span class="sxs-lookup"><span data-stu-id="be157-105">Exchange Online email messages</span></span>
- <span data-ttu-id="be157-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="be157-106">SharePoint Online</span></span>
- <span data-ttu-id="be157-107">商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="be157-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="be157-108">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="be157-108">Windows 10 devices</span></span>

<span data-ttu-id="be157-109">敏感度標籤會顯示為 **內容包含** 清單的選項。</span><span class="sxs-lookup"><span data-stu-id="be157-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="be157-110">![敏感度標籤做為條件](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="be157-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be157-111">若您選取 **Teams 聊天和頻道訊息** 為套用 DLP 原則的位置，將無法以 **敏感度標籤** 做為條件。</span><span class="sxs-lookup"><span data-stu-id="be157-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="be157-112">支援的項目、案例和原則提示</span><span class="sxs-lookup"><span data-stu-id="be157-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="be157-113">您可以針對這些項目使用敏感度標籤做為條件，並在這些案例中使用。</span><span class="sxs-lookup"><span data-stu-id="be157-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="be157-114">不支援的項目</span><span class="sxs-lookup"><span data-stu-id="be157-114">Supported items</span></span>

|<span data-ttu-id="be157-115">服務</span><span class="sxs-lookup"><span data-stu-id="be157-115">Service</span></span>  |<span data-ttu-id="be157-116">項目類型</span><span class="sxs-lookup"><span data-stu-id="be157-116">Item type</span></span>  |<span data-ttu-id="be157-117">可用於原則提示</span><span class="sxs-lookup"><span data-stu-id="be157-117">Available to policy tip</span></span>  |<span data-ttu-id="be157-118">強制</span><span class="sxs-lookup"><span data-stu-id="be157-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="be157-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="be157-119">Exchange</span></span>    |<span data-ttu-id="be157-120">電子郵件</span><span class="sxs-lookup"><span data-stu-id="be157-120">email message</span></span>         |<span data-ttu-id="be157-121">是</span><span class="sxs-lookup"><span data-stu-id="be157-121">yes</span></span>         |<span data-ttu-id="be157-122">是</span><span class="sxs-lookup"><span data-stu-id="be157-122">yes</span></span>         |
|<span data-ttu-id="be157-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="be157-123">Exchange</span></span>    |<span data-ttu-id="be157-124">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="be157-124">email attachment</span></span>         |<span data-ttu-id="be157-125">否 \*</span><span class="sxs-lookup"><span data-stu-id="be157-125">no \*</span></span>         |<span data-ttu-id="be157-126">是 \*</span><span class="sxs-lookup"><span data-stu-id="be157-126">yes \*</span></span>         |
|<span data-ttu-id="be157-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="be157-127">SharePoint Online</span></span>     |<span data-ttu-id="be157-128">SharePoint Online 中的項目</span><span class="sxs-lookup"><span data-stu-id="be157-128">items in SharePoint Online</span></span>         |<span data-ttu-id="be157-129">是</span><span class="sxs-lookup"><span data-stu-id="be157-129">yes</span></span>         |<span data-ttu-id="be157-130">是</span><span class="sxs-lookup"><span data-stu-id="be157-130">yes</span></span>         |
|<span data-ttu-id="be157-131">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="be157-131">OneDrive for Business</span></span>     |<span data-ttu-id="be157-132">項目</span><span class="sxs-lookup"><span data-stu-id="be157-132">items</span></span>         |<span data-ttu-id="be157-133">是</span><span class="sxs-lookup"><span data-stu-id="be157-133">yes</span></span>         |<span data-ttu-id="be157-134">是</span><span class="sxs-lookup"><span data-stu-id="be157-134">yes</span></span>         |
|<span data-ttu-id="be157-135">Teams</span><span class="sxs-lookup"><span data-stu-id="be157-135">Teams</span></span>     |<span data-ttu-id="be157-136">Teams 和頻道訊息</span><span class="sxs-lookup"><span data-stu-id="be157-136">Teams and channel messages</span></span>         |<span data-ttu-id="be157-137">不適用</span><span class="sxs-lookup"><span data-stu-id="be157-137">not applicable</span></span>         |<span data-ttu-id="be157-138">不適用</span><span class="sxs-lookup"><span data-stu-id="be157-138">not applicable</span></span>         |
|<span data-ttu-id="be157-139">Teams</span><span class="sxs-lookup"><span data-stu-id="be157-139">Teams</span></span>     |<span data-ttu-id="be157-140">附件</span><span class="sxs-lookup"><span data-stu-id="be157-140">attachments</span></span>         |<span data-ttu-id="be157-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="be157-141">yes \*\*</span></span>         |<span data-ttu-id="be157-142">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="be157-142">yes \*\*</span></span>         |
|<span data-ttu-id="be157-143">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="be157-143">Windows 10 devices</span></span>     |<span data-ttu-id="be157-144">項目</span><span class="sxs-lookup"><span data-stu-id="be157-144">items</span></span>         |<span data-ttu-id="be157-145">是</span><span class="sxs-lookup"><span data-stu-id="be157-145">yes</span></span>         |<span data-ttu-id="be157-146">是</span><span class="sxs-lookup"><span data-stu-id="be157-146">yes</span></span>         |
|<span data-ttu-id="be157-147">MCAS (預覽)</span><span class="sxs-lookup"><span data-stu-id="be157-147">MCAS (preview)</span></span> |<span data-ttu-id="be157-148">項目</span><span class="sxs-lookup"><span data-stu-id="be157-148">items</span></span>         |<span data-ttu-id="be157-149">是</span><span class="sxs-lookup"><span data-stu-id="be157-149">yes</span></span>         |<span data-ttu-id="be157-150">是</span><span class="sxs-lookup"><span data-stu-id="be157-150">yes</span></span>         |

<span data-ttu-id="be157-151">\* 在傳輸中支援電子郵件和附件上的 DLP 偵測和敏感度標籤之強制執行。</span><span class="sxs-lookup"><span data-stu-id="be157-151">\* DLP detection and enforcement of sensitivity labels on emails and attachments are supported in-transit.</span></span> <span data-ttu-id="be157-152">不支援已標記敏感度標籤之電子郵件附件的 DLP 偵測。</span><span class="sxs-lookup"><span data-stu-id="be157-152">DLP policy tips of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="be157-153">\*\* 在 Teams 中透過 1 對 1 聊天或頻道傳送的附件，會自動上傳至 [商務用 OneDrive] 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="be157-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="be157-154">因此，如果將 SharePoint Online 或 [商務用 OneDrive] 包含在您的 DLP 原則做為位置，則會在此條件的範圍中會自動包含於 Teams 中傳送的已標示附件。</span><span class="sxs-lookup"><span data-stu-id="be157-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="be157-155">您不需要在 DLP 原則中選取 Teams 做為位置。</span><span class="sxs-lookup"><span data-stu-id="be157-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="be157-156">支援的案例</span><span class="sxs-lookup"><span data-stu-id="be157-156">Supported scenarios</span></span>

- <span data-ttu-id="be157-157">選擇要將一或多個敏感度標籤做為條件時，DLP 系統管理員將看到租用戶中所有敏感度標籤的清單。</span><span class="sxs-lookup"><span data-stu-id="be157-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="be157-158">如上前述的支援矩陣中所指出，所有工作負載均支援使用敏感度標籤做為條件。</span><span class="sxs-lookup"><span data-stu-id="be157-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="be157-159">針對包含敏感度標籤做為條件的 DLP 原則，DLP 原則提示將持續針對各工作負載 (Outlook Win32 除外) 顯示。</span><span class="sxs-lookup"><span data-stu-id="be157-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="be157-160">如果比對到使用敏感度標籤做為條件的 DLP 原則，則敏感度標籤也會隨著事件報告電子郵件顯示。</span><span class="sxs-lookup"><span data-stu-id="be157-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="be157-161">也會在包含敏感度標籤做為條件的符合 DLP 原則比對的 DLP 規則稽核記錄中顯示敏感度標籤詳細資料。</span><span class="sxs-lookup"><span data-stu-id="be157-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="be157-162">支援原則提示</span><span class="sxs-lookup"><span data-stu-id="be157-162">Support policy tips</span></span>


|<span data-ttu-id="be157-163">工作負載</span><span class="sxs-lookup"><span data-stu-id="be157-163">Workload</span></span>  |<span data-ttu-id="be157-164">支援/不支援的原則提示</span><span class="sxs-lookup"><span data-stu-id="be157-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="be157-165">OWA</span><span class="sxs-lookup"><span data-stu-id="be157-165">OWA</span></span> |    <span data-ttu-id="be157-166">支援</span><span class="sxs-lookup"><span data-stu-id="be157-166">supported</span></span>     |
|<span data-ttu-id="be157-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="be157-167">Outlook Win 32</span></span>    |  <span data-ttu-id="be157-168">不支援</span><span class="sxs-lookup"><span data-stu-id="be157-168">not supported</span></span>       |
|<span data-ttu-id="be157-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="be157-169">SharePoint</span></span>   |   <span data-ttu-id="be157-170">支援</span><span class="sxs-lookup"><span data-stu-id="be157-170">supported</span></span>      |
|<span data-ttu-id="be157-171">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="be157-171">OneDrive for Business</span></span>    |    <span data-ttu-id="be157-172">支援</span><span class="sxs-lookup"><span data-stu-id="be157-172">supported</span></span>     |
|<span data-ttu-id="be157-173">端點裝置</span><span class="sxs-lookup"><span data-stu-id="be157-173">endpoint devices</span></span>   |  <span data-ttu-id="be157-174">不支援</span><span class="sxs-lookup"><span data-stu-id="be157-174">not supported</span></span>       |
