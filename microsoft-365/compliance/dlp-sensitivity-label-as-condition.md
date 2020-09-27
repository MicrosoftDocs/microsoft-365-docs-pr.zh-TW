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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235715"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="09ec8-103">使用敏感度標籤作為 DLP 原則中的條件 (預覽)</span><span class="sxs-lookup"><span data-stu-id="09ec8-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="09ec8-104">針對這些位置，您可以在 DLP 原則中使用[敏感度標籤](sensitivity-labels.md)做為條件：</span><span class="sxs-lookup"><span data-stu-id="09ec8-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="09ec8-105">Exchange Online 電子郵件</span><span class="sxs-lookup"><span data-stu-id="09ec8-105">Exchange Online email messages</span></span>
- <span data-ttu-id="09ec8-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="09ec8-106">SharePoint Online</span></span>
- <span data-ttu-id="09ec8-107">商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="09ec8-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="09ec8-108">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="09ec8-108">Windows 10 devices</span></span>

<span data-ttu-id="09ec8-109">敏感度標籤會顯示為**內容包含**清單的選項。</span><span class="sxs-lookup"><span data-stu-id="09ec8-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![敏感度標籤做為條件](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="09ec8-111">支援的項目、案例和原則提示</span><span class="sxs-lookup"><span data-stu-id="09ec8-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="09ec8-112">您可以針對這些項目使用敏感度標籤做為條件，並在這些案例中使用。</span><span class="sxs-lookup"><span data-stu-id="09ec8-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="09ec8-113">不支援的項目</span><span class="sxs-lookup"><span data-stu-id="09ec8-113">Supported items</span></span>

|<span data-ttu-id="09ec8-114">服務</span><span class="sxs-lookup"><span data-stu-id="09ec8-114">service</span></span>  |<span data-ttu-id="09ec8-115">項目類型</span><span class="sxs-lookup"><span data-stu-id="09ec8-115">item type</span></span>  |<span data-ttu-id="09ec8-116">可用於原則提示</span><span class="sxs-lookup"><span data-stu-id="09ec8-116">available to policy tip</span></span>  |<span data-ttu-id="09ec8-117">強制</span><span class="sxs-lookup"><span data-stu-id="09ec8-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="09ec8-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="09ec8-118">Exchange</span></span>    |<span data-ttu-id="09ec8-119">電子郵件</span><span class="sxs-lookup"><span data-stu-id="09ec8-119">email message</span></span>         |<span data-ttu-id="09ec8-120">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-120">yes</span></span>         |<span data-ttu-id="09ec8-121">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-121">yes</span></span>         |
|<span data-ttu-id="09ec8-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="09ec8-122">Exchange</span></span>    |<span data-ttu-id="09ec8-123">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="09ec8-123">email attachment</span></span>         |<span data-ttu-id="09ec8-124">否 \*</span><span class="sxs-lookup"><span data-stu-id="09ec8-124">no \*</span></span>         |<span data-ttu-id="09ec8-125">否 \*</span><span class="sxs-lookup"><span data-stu-id="09ec8-125">no \*</span></span>         |
|<span data-ttu-id="09ec8-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="09ec8-126">SharePoint Online</span></span>     |<span data-ttu-id="09ec8-127">SharePoint Online 中的項目</span><span class="sxs-lookup"><span data-stu-id="09ec8-127">items in SharePoint Online</span></span>         |<span data-ttu-id="09ec8-128">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-128">yes</span></span>         |<span data-ttu-id="09ec8-129">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-129">yes</span></span>         |
|<span data-ttu-id="09ec8-130">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="09ec8-130">OneDrive for Business</span></span>     |<span data-ttu-id="09ec8-131">項目</span><span class="sxs-lookup"><span data-stu-id="09ec8-131">items</span></span>         |<span data-ttu-id="09ec8-132">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-132">yes</span></span>         |<span data-ttu-id="09ec8-133">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-133">yes</span></span>         |
|<span data-ttu-id="09ec8-134">Teams</span><span class="sxs-lookup"><span data-stu-id="09ec8-134">Teams</span></span>     |<span data-ttu-id="09ec8-135">Teams 和頻道訊息</span><span class="sxs-lookup"><span data-stu-id="09ec8-135">Teams and channel messages</span></span>         |<span data-ttu-id="09ec8-136">不適用</span><span class="sxs-lookup"><span data-stu-id="09ec8-136">not applicable</span></span>         |<span data-ttu-id="09ec8-137">不適用</span><span class="sxs-lookup"><span data-stu-id="09ec8-137">not applicable</span></span>         |
|<span data-ttu-id="09ec8-138">Teams</span><span class="sxs-lookup"><span data-stu-id="09ec8-138">Teams</span></span>     |<span data-ttu-id="09ec8-139">附件</span><span class="sxs-lookup"><span data-stu-id="09ec8-139">attachements</span></span>         |<span data-ttu-id="09ec8-140">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="09ec8-140">yes \*\*</span></span>         |<span data-ttu-id="09ec8-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="09ec8-141">yes \*\*</span></span>         |
|<span data-ttu-id="09ec8-142">Windows 10 裝置 (預覽)</span><span class="sxs-lookup"><span data-stu-id="09ec8-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="09ec8-143">項目</span><span class="sxs-lookup"><span data-stu-id="09ec8-143">items</span></span>         |<span data-ttu-id="09ec8-144">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-144">yes</span></span>         |<span data-ttu-id="09ec8-145">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-145">yes</span></span>         |
|<span data-ttu-id="09ec8-146">MCAS (預覽)</span><span class="sxs-lookup"><span data-stu-id="09ec8-146">MCAS (preview)</span></span> |<span data-ttu-id="09ec8-147">項目</span><span class="sxs-lookup"><span data-stu-id="09ec8-147">items</span></span>         |<span data-ttu-id="09ec8-148">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-148">yes</span></span>         |<span data-ttu-id="09ec8-149">是</span><span class="sxs-lookup"><span data-stu-id="09ec8-149">yes</span></span>         |

<span data-ttu-id="09ec8-150">\* 支援電子郵件上敏感度標籤的 DLP 偵測。</span><span class="sxs-lookup"><span data-stu-id="09ec8-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="09ec8-151">不支援標示敏感度電子郵件附件的 DLP 偵測。</span><span class="sxs-lookup"><span data-stu-id="09ec8-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="09ec8-152">\*\* 在 Teams 中透過 1 對 1 聊天或頻道傳送於附件，會自動上傳至商務用 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="09ec8-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="09ec8-153">因此，如果將 SharePoint Online 或商務用 OneDrive 包含在您的 DLP 原則做為位置，則會在此條件的範圍中自動包含於 Teams 傳送、標示的附件。</span><span class="sxs-lookup"><span data-stu-id="09ec8-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="09ec8-154">您不需要在 DLP 原則中選取 Teams 做為位置。</span><span class="sxs-lookup"><span data-stu-id="09ec8-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="09ec8-155">支援的案例</span><span class="sxs-lookup"><span data-stu-id="09ec8-155">Supported scenarios</span></span>

- <span data-ttu-id="09ec8-156">選擇要將一或多個敏感度標籤做為條件時，DLP 系統管理員將看到租用戶中所有敏感度標籤的清單。</span><span class="sxs-lookup"><span data-stu-id="09ec8-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="09ec8-157">如上前述的支援矩陣中所指出，所有工作負載均支援使用敏感度標籤做為條件</span><span class="sxs-lookup"><span data-stu-id="09ec8-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="09ec8-158">針對包含敏感度標籤做為條件的 DLP 原則，DLP 原則提示將持續針對各工作負載 (Outlook Win32 除外) 顯示。</span><span class="sxs-lookup"><span data-stu-id="09ec8-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="09ec8-159">如果比對到使用敏感度標籤做為條件的 DLP 原則，則敏感度標籤也會隨著事件報告電子郵件顯示。</span><span class="sxs-lookup"><span data-stu-id="09ec8-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="09ec8-160">也會在包含敏感度標籤做為條件的符合 DLP 原則比對的 DLP 規則稽核記錄中顯示敏感度標籤詳細資料。</span><span class="sxs-lookup"><span data-stu-id="09ec8-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="09ec8-161">支援原則提示</span><span class="sxs-lookup"><span data-stu-id="09ec8-161">Support policy tips</span></span>


|<span data-ttu-id="09ec8-162">工作負載</span><span class="sxs-lookup"><span data-stu-id="09ec8-162">workload</span></span>  |<span data-ttu-id="09ec8-163">支援/不支援的原則提示</span><span class="sxs-lookup"><span data-stu-id="09ec8-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="09ec8-164">OWA</span><span class="sxs-lookup"><span data-stu-id="09ec8-164">OWA</span></span> |    <span data-ttu-id="09ec8-165">支援</span><span class="sxs-lookup"><span data-stu-id="09ec8-165">supported</span></span>     |
|<span data-ttu-id="09ec8-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="09ec8-166">Outlook Win 32</span></span>    |  <span data-ttu-id="09ec8-167">不支援</span><span class="sxs-lookup"><span data-stu-id="09ec8-167">not supported</span></span>       |
|<span data-ttu-id="09ec8-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="09ec8-168">SharePoint</span></span>   |   <span data-ttu-id="09ec8-169">支援</span><span class="sxs-lookup"><span data-stu-id="09ec8-169">supported</span></span>      |
|<span data-ttu-id="09ec8-170">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="09ec8-170">OneDrive for Business</span></span>    |    <span data-ttu-id="09ec8-171">支援</span><span class="sxs-lookup"><span data-stu-id="09ec8-171">supported</span></span>     |
|<span data-ttu-id="09ec8-172">端點裝置</span><span class="sxs-lookup"><span data-stu-id="09ec8-172">endpoint devices</span></span>   |  <span data-ttu-id="09ec8-173">不支援</span><span class="sxs-lookup"><span data-stu-id="09ec8-173">not supported</span></span>       |
