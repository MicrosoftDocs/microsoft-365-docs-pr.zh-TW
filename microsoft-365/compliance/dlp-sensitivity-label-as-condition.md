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
ms.openlocfilehash: 2f8eb30e23d722a5e8faf7d0ddaca6b9a94e279b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649632"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="de808-103">使用敏感度標籤作為 DLP 原則中的條件 (預覽)</span><span class="sxs-lookup"><span data-stu-id="de808-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="de808-104">針對這些位置，您可以在 DLP 原則中使用[敏感度標籤](sensitivity-labels.md)做為條件：</span><span class="sxs-lookup"><span data-stu-id="de808-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="de808-105">Exchange Online 電子郵件</span><span class="sxs-lookup"><span data-stu-id="de808-105">Exchange Online email messages</span></span>
- <span data-ttu-id="de808-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="de808-106">SharePoint Online</span></span>
- <span data-ttu-id="de808-107">商務用 OneDrive 網站</span><span class="sxs-lookup"><span data-stu-id="de808-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="de808-108">Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="de808-108">Windows 10 devices</span></span>

<span data-ttu-id="de808-109">敏感度標籤會顯示為**內容包含**清單的選項。</span><span class="sxs-lookup"><span data-stu-id="de808-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="de808-110">![敏感度標籤做為條件](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="de808-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de808-111">若您選取 **Teams 聊天和頻道訊息** 為套用 DLP 原則的位置，將無法以 **敏感度標籤** 做為條件。</span><span class="sxs-lookup"><span data-stu-id="de808-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="de808-112">支援的項目、案例和原則提示</span><span class="sxs-lookup"><span data-stu-id="de808-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="de808-113">您可以針對這些項目使用敏感度標籤做為條件，並在這些案例中使用。</span><span class="sxs-lookup"><span data-stu-id="de808-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="de808-114">不支援的項目</span><span class="sxs-lookup"><span data-stu-id="de808-114">Supported items</span></span>

|<span data-ttu-id="de808-115">服務</span><span class="sxs-lookup"><span data-stu-id="de808-115">Service</span></span>  |<span data-ttu-id="de808-116">項目類型</span><span class="sxs-lookup"><span data-stu-id="de808-116">Item type</span></span>  |<span data-ttu-id="de808-117">可用於原則提示</span><span class="sxs-lookup"><span data-stu-id="de808-117">Available to policy tip</span></span>  |<span data-ttu-id="de808-118">強制</span><span class="sxs-lookup"><span data-stu-id="de808-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="de808-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="de808-119">Exchange</span></span>    |<span data-ttu-id="de808-120">電子郵件</span><span class="sxs-lookup"><span data-stu-id="de808-120">email message</span></span>         |<span data-ttu-id="de808-121">是</span><span class="sxs-lookup"><span data-stu-id="de808-121">yes</span></span>         |<span data-ttu-id="de808-122">是</span><span class="sxs-lookup"><span data-stu-id="de808-122">yes</span></span>         |
|<span data-ttu-id="de808-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="de808-123">Exchange</span></span>    |<span data-ttu-id="de808-124">電子郵件附件</span><span class="sxs-lookup"><span data-stu-id="de808-124">email attachment</span></span>         |<span data-ttu-id="de808-125">否 \*</span><span class="sxs-lookup"><span data-stu-id="de808-125">no \*</span></span>         |<span data-ttu-id="de808-126">否 \*</span><span class="sxs-lookup"><span data-stu-id="de808-126">no \*</span></span>         |
|<span data-ttu-id="de808-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="de808-127">SharePoint Online</span></span>     |<span data-ttu-id="de808-128">SharePoint Online 中的項目</span><span class="sxs-lookup"><span data-stu-id="de808-128">items in SharePoint Online</span></span>         |<span data-ttu-id="de808-129">是</span><span class="sxs-lookup"><span data-stu-id="de808-129">yes</span></span>         |<span data-ttu-id="de808-130">是</span><span class="sxs-lookup"><span data-stu-id="de808-130">yes</span></span>         |
|<span data-ttu-id="de808-131">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="de808-131">OneDrive for Business</span></span>     |<span data-ttu-id="de808-132">項目</span><span class="sxs-lookup"><span data-stu-id="de808-132">items</span></span>         |<span data-ttu-id="de808-133">是</span><span class="sxs-lookup"><span data-stu-id="de808-133">yes</span></span>         |<span data-ttu-id="de808-134">是</span><span class="sxs-lookup"><span data-stu-id="de808-134">yes</span></span>         |
|<span data-ttu-id="de808-135">Teams</span><span class="sxs-lookup"><span data-stu-id="de808-135">Teams</span></span>     |<span data-ttu-id="de808-136">Teams 和頻道訊息</span><span class="sxs-lookup"><span data-stu-id="de808-136">Teams and channel messages</span></span>         |<span data-ttu-id="de808-137">不適用</span><span class="sxs-lookup"><span data-stu-id="de808-137">not applicable</span></span>         |<span data-ttu-id="de808-138">不適用</span><span class="sxs-lookup"><span data-stu-id="de808-138">not applicable</span></span>         |
|<span data-ttu-id="de808-139">Teams</span><span class="sxs-lookup"><span data-stu-id="de808-139">Teams</span></span>     |<span data-ttu-id="de808-140">附件</span><span class="sxs-lookup"><span data-stu-id="de808-140">attachments</span></span>         |<span data-ttu-id="de808-141">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="de808-141">yes \*\*</span></span>         |<span data-ttu-id="de808-142">是 \*\*</span><span class="sxs-lookup"><span data-stu-id="de808-142">yes \*\*</span></span>         |
|<span data-ttu-id="de808-143">Windows 10 裝置 (預覽)</span><span class="sxs-lookup"><span data-stu-id="de808-143">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="de808-144">項目</span><span class="sxs-lookup"><span data-stu-id="de808-144">items</span></span>         |<span data-ttu-id="de808-145">是</span><span class="sxs-lookup"><span data-stu-id="de808-145">yes</span></span>         |<span data-ttu-id="de808-146">是</span><span class="sxs-lookup"><span data-stu-id="de808-146">yes</span></span>         |
|<span data-ttu-id="de808-147">MCAS (預覽)</span><span class="sxs-lookup"><span data-stu-id="de808-147">MCAS (preview)</span></span> |<span data-ttu-id="de808-148">項目</span><span class="sxs-lookup"><span data-stu-id="de808-148">items</span></span>         |<span data-ttu-id="de808-149">是</span><span class="sxs-lookup"><span data-stu-id="de808-149">yes</span></span>         |<span data-ttu-id="de808-150">是</span><span class="sxs-lookup"><span data-stu-id="de808-150">yes</span></span>         |

<span data-ttu-id="de808-151">\* 支援電子郵件上敏感度標籤的 DLP 偵測。</span><span class="sxs-lookup"><span data-stu-id="de808-151">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="de808-152">不支援標示敏感度電子郵件附件的 DLP 偵測。</span><span class="sxs-lookup"><span data-stu-id="de808-152">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="de808-153">\*\* 在 Teams 中透過 1 對 1 聊天或頻道傳送的附件，會自動上傳至 [商務用 OneDrive] 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="de808-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="de808-154">因此，如果將 SharePoint Online 或 [商務用 OneDrive] 包含在您的 DLP 原則做為位置，則會在此條件的範圍中會自動包含於 Teams 中傳送的已標示附件。</span><span class="sxs-lookup"><span data-stu-id="de808-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="de808-155">您不需要在 DLP 原則中選取 Teams 做為位置。</span><span class="sxs-lookup"><span data-stu-id="de808-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="de808-156">支援的案例</span><span class="sxs-lookup"><span data-stu-id="de808-156">Supported scenarios</span></span>

- <span data-ttu-id="de808-157">選擇要將一或多個敏感度標籤做為條件時，DLP 系統管理員將看到租用戶中所有敏感度標籤的清單。</span><span class="sxs-lookup"><span data-stu-id="de808-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="de808-158">如上前述的支援矩陣中所指出，所有工作負載均支援使用敏感度標籤做為條件。</span><span class="sxs-lookup"><span data-stu-id="de808-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="de808-159">針對包含敏感度標籤做為條件的 DLP 原則，DLP 原則提示將持續針對各工作負載 (Outlook Win32 除外) 顯示。</span><span class="sxs-lookup"><span data-stu-id="de808-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="de808-160">如果比對到使用敏感度標籤做為條件的 DLP 原則，則敏感度標籤也會隨著事件報告電子郵件顯示。</span><span class="sxs-lookup"><span data-stu-id="de808-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="de808-161">也會在包含敏感度標籤做為條件的符合 DLP 原則比對的 DLP 規則稽核記錄中顯示敏感度標籤詳細資料。</span><span class="sxs-lookup"><span data-stu-id="de808-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="de808-162">支援原則提示</span><span class="sxs-lookup"><span data-stu-id="de808-162">Support policy tips</span></span>


|<span data-ttu-id="de808-163">工作負載</span><span class="sxs-lookup"><span data-stu-id="de808-163">Workload</span></span>  |<span data-ttu-id="de808-164">支援/不支援的原則提示</span><span class="sxs-lookup"><span data-stu-id="de808-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="de808-165">OWA</span><span class="sxs-lookup"><span data-stu-id="de808-165">OWA</span></span> |    <span data-ttu-id="de808-166">支援</span><span class="sxs-lookup"><span data-stu-id="de808-166">supported</span></span>     |
|<span data-ttu-id="de808-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="de808-167">Outlook Win 32</span></span>    |  <span data-ttu-id="de808-168">不支援</span><span class="sxs-lookup"><span data-stu-id="de808-168">not supported</span></span>       |
|<span data-ttu-id="de808-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="de808-169">SharePoint</span></span>   |   <span data-ttu-id="de808-170">支援</span><span class="sxs-lookup"><span data-stu-id="de808-170">supported</span></span>      |
|<span data-ttu-id="de808-171">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="de808-171">OneDrive for Business</span></span>    |    <span data-ttu-id="de808-172">支援</span><span class="sxs-lookup"><span data-stu-id="de808-172">supported</span></span>     |
|<span data-ttu-id="de808-173">端點裝置</span><span class="sxs-lookup"><span data-stu-id="de808-173">endpoint devices</span></span>   |  <span data-ttu-id="de808-174">不支援</span><span class="sxs-lookup"><span data-stu-id="de808-174">not supported</span></span>       |
