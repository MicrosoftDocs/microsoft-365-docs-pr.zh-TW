---
title: 使用敏感度標籤作為 DLP 原則中的條件 (預覽)
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
ms.openlocfilehash: 561a6cbd7b8aeb9082862319c5cc6419fd79c896
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321108"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="f6b2f-103">使用敏感度標籤作為 DLP 原則中的條件 (預覽)</span><span class="sxs-lookup"><span data-stu-id="f6b2f-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="f6b2f-104">針對這些位置，您可以在 DLP 原則中使用[敏感度標籤](sensitivity-labels.md)做為條件：</span><span class="sxs-lookup"><span data-stu-id="f6b2f-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="f6b2f-105">Exchange Online 電子郵件</span><span class="sxs-lookup"><span data-stu-id="f6b2f-105">Exchange Online email messages</span></span>
- <span data-ttu-id="f6b2f-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f6b2f-106">SharePoint Online</span></span>
- <span data-ttu-id="f6b2f-107">商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="f6b2f-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="f6b2f-108">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="f6b2f-108">Windows 10 devices</span></span>

<span data-ttu-id="f6b2f-109">敏感度標籤會顯示為**內容包含**清單的選項。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![敏感度標籤做為條件](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="f6b2f-111">支援的項目、案例和原則提示</span><span class="sxs-lookup"><span data-stu-id="f6b2f-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="f6b2f-112">您可以針對這些項目使用敏感度標籤做為條件，並在這些案例中使用。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="f6b2f-113">不支援的項目</span><span class="sxs-lookup"><span data-stu-id="f6b2f-113">Supported items</span></span>

|<span data-ttu-id="f6b2f-114">服務</span><span class="sxs-lookup"><span data-stu-id="f6b2f-114">service</span></span>  |<span data-ttu-id="f6b2f-115">項目類型</span><span class="sxs-lookup"><span data-stu-id="f6b2f-115">item type</span></span>  |<span data-ttu-id="f6b2f-116">可用於原則提示</span><span class="sxs-lookup"><span data-stu-id="f6b2f-116">available to policy tip</span></span>  |<span data-ttu-id="f6b2f-117">強制</span><span class="sxs-lookup"><span data-stu-id="f6b2f-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="f6b2f-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="f6b2f-118">Exchange</span></span>    |<span data-ttu-id="f6b2f-119">電子郵件</span><span class="sxs-lookup"><span data-stu-id="f6b2f-119">email message</span></span>         |<span data-ttu-id="f6b2f-120">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-120">yes</span></span>         |<span data-ttu-id="f6b2f-121">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-121">yes</span></span>         |
|<span data-ttu-id="f6b2f-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="f6b2f-122">Exchange</span></span>    |<span data-ttu-id="f6b2f-123">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="f6b2f-123">email attachment</span></span>         |<span data-ttu-id="f6b2f-124">否 \*</span><span class="sxs-lookup"><span data-stu-id="f6b2f-124">no \*</span></span>         |<span data-ttu-id="f6b2f-125">否 \*</span><span class="sxs-lookup"><span data-stu-id="f6b2f-125">no \*</span></span>         |
|<span data-ttu-id="f6b2f-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f6b2f-126">SharePoint Online</span></span>     |<span data-ttu-id="f6b2f-127">SharePoint Online 中的項目</span><span class="sxs-lookup"><span data-stu-id="f6b2f-127">items in SharePoint Online</span></span>         |<span data-ttu-id="f6b2f-128">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-128">yes</span></span>         |<span data-ttu-id="f6b2f-129">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-129">yes</span></span>         |
|<span data-ttu-id="f6b2f-130">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f6b2f-130">OneDrive for Business</span></span>     |<span data-ttu-id="f6b2f-131">項目</span><span class="sxs-lookup"><span data-stu-id="f6b2f-131">items</span></span>         |<span data-ttu-id="f6b2f-132">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-132">yes</span></span>         |<span data-ttu-id="f6b2f-133">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-133">yes</span></span>         |
|<span data-ttu-id="f6b2f-134">Teams</span><span class="sxs-lookup"><span data-stu-id="f6b2f-134">Teams</span></span>     |<span data-ttu-id="f6b2f-135">Teams 和頻道訊息</span><span class="sxs-lookup"><span data-stu-id="f6b2f-135">Teams and channel messages</span></span>         |<span data-ttu-id="f6b2f-136">不適用</span><span class="sxs-lookup"><span data-stu-id="f6b2f-136">not applicable</span></span>         |<span data-ttu-id="f6b2f-137">不適用</span><span class="sxs-lookup"><span data-stu-id="f6b2f-137">not applicable</span></span>         |
|<span data-ttu-id="f6b2f-138">Teams</span><span class="sxs-lookup"><span data-stu-id="f6b2f-138">Teams</span></span>     |<span data-ttu-id="f6b2f-139">附件</span><span class="sxs-lookup"><span data-stu-id="f6b2f-139">attachments</span></span>         |<span data-ttu-id="f6b2f-140">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="f6b2f-140">yes \*\*</span></span>         |<span data-ttu-id="f6b2f-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="f6b2f-141">yes \*\*</span></span>         |
|<span data-ttu-id="f6b2f-142">Windows 10 裝置 (預覽)</span><span class="sxs-lookup"><span data-stu-id="f6b2f-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="f6b2f-143">項目</span><span class="sxs-lookup"><span data-stu-id="f6b2f-143">items</span></span>         |<span data-ttu-id="f6b2f-144">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-144">yes</span></span>         |<span data-ttu-id="f6b2f-145">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-145">yes</span></span>         |
|<span data-ttu-id="f6b2f-146">MCAS (預覽)</span><span class="sxs-lookup"><span data-stu-id="f6b2f-146">MCAS (preview)</span></span> |<span data-ttu-id="f6b2f-147">項目</span><span class="sxs-lookup"><span data-stu-id="f6b2f-147">items</span></span>         |<span data-ttu-id="f6b2f-148">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-148">yes</span></span>         |<span data-ttu-id="f6b2f-149">是</span><span class="sxs-lookup"><span data-stu-id="f6b2f-149">yes</span></span>         |

<span data-ttu-id="f6b2f-150">\* 支援電子郵件上敏感度標籤的 DLP 偵測。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="f6b2f-151">不支援標示敏感度電子郵件附件的 DLP 偵測。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="f6b2f-152">\*\* 在 Teams 中透過 1 對 1 聊天或頻道傳送的附件，會自動上傳至 [商務用 OneDrive] 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="f6b2f-153">因此，如果將 SharePoint Online 或 [商務用 OneDrive] 包含在您的 DLP 原則做為位置，則會在此條件的範圍中會自動包含於 Teams 中傳送的已標示附件。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="f6b2f-154">您不需要在 DLP 原則中選取 Teams 做為位置。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="f6b2f-155">支援的案例</span><span class="sxs-lookup"><span data-stu-id="f6b2f-155">Supported scenarios</span></span>

- <span data-ttu-id="f6b2f-156">選擇要將一或多個敏感度標籤做為條件時，DLP 系統管理員將看到租用戶中所有敏感度標籤的清單。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="f6b2f-157">如上前述的支援矩陣中所指出，所有工作負載均支援使用敏感度標籤做為條件</span><span class="sxs-lookup"><span data-stu-id="f6b2f-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="f6b2f-158">針對包含敏感度標籤做為條件的 DLP 原則，DLP 原則提示將持續針對各工作負載 (Outlook Win32 除外) 顯示。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="f6b2f-159">如果比對到使用敏感度標籤做為條件的 DLP 原則，則敏感度標籤也會隨著事件報告電子郵件顯示。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="f6b2f-160">也會在包含敏感度標籤做為條件的符合 DLP 原則比對的 DLP 規則稽核記錄中顯示敏感度標籤詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f6b2f-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="f6b2f-161">支援原則提示</span><span class="sxs-lookup"><span data-stu-id="f6b2f-161">Support policy tips</span></span>


|<span data-ttu-id="f6b2f-162">工作負載</span><span class="sxs-lookup"><span data-stu-id="f6b2f-162">workload</span></span>  |<span data-ttu-id="f6b2f-163">支援/不支援的原則提示</span><span class="sxs-lookup"><span data-stu-id="f6b2f-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="f6b2f-164">OWA</span><span class="sxs-lookup"><span data-stu-id="f6b2f-164">OWA</span></span> |    <span data-ttu-id="f6b2f-165">支援</span><span class="sxs-lookup"><span data-stu-id="f6b2f-165">supported</span></span>     |
|<span data-ttu-id="f6b2f-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="f6b2f-166">Outlook Win 32</span></span>    |  <span data-ttu-id="f6b2f-167">不支援</span><span class="sxs-lookup"><span data-stu-id="f6b2f-167">not supported</span></span>       |
|<span data-ttu-id="f6b2f-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6b2f-168">SharePoint</span></span>   |   <span data-ttu-id="f6b2f-169">支援</span><span class="sxs-lookup"><span data-stu-id="f6b2f-169">supported</span></span>      |
|<span data-ttu-id="f6b2f-170">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="f6b2f-170">OneDrive for Business</span></span>    |    <span data-ttu-id="f6b2f-171">支援</span><span class="sxs-lookup"><span data-stu-id="f6b2f-171">supported</span></span>     |
|<span data-ttu-id="f6b2f-172">端點裝置</span><span class="sxs-lookup"><span data-stu-id="f6b2f-172">endpoint devices</span></span>   |  <span data-ttu-id="f6b2f-173">不支援</span><span class="sxs-lookup"><span data-stu-id="f6b2f-173">not supported</span></span>       |
