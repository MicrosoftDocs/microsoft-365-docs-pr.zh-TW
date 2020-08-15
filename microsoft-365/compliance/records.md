---
title: 了解記錄
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解可協助您在 Microsoft 365 中實施記錄管理解決方案的記錄。
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685439"
---
# <a name="learn-about-records"></a><span data-ttu-id="44cfb-103">了解記錄</span><span class="sxs-lookup"><span data-stu-id="44cfb-103">Learn about records</span></span>

><span data-ttu-id="44cfb-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="44cfb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="44cfb-105">在 Microsoft 365 中管理記錄可協助組織遵守公司政策、法律或法規義務，同時降低風險和法律責任。</span><span class="sxs-lookup"><span data-stu-id="44cfb-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="44cfb-106">當內容標示為記錄時：</span><span class="sxs-lookup"><span data-stu-id="44cfb-106">When content is marked as a record:</span></span>

- <span data-ttu-id="44cfb-107">根據[允許或封鎖的動作](#compare-restrictions-for-what-actions-are-allowed-or-blocked)，對項目施加限制。</span><span class="sxs-lookup"><span data-stu-id="44cfb-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="44cfb-108">關於項目的其他活動會予以記錄。</span><span class="sxs-lookup"><span data-stu-id="44cfb-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="44cfb-109">在項目保留期結束時將其刪除時，您會有處置證明。</span><span class="sxs-lookup"><span data-stu-id="44cfb-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="44cfb-110">使用[保留標籤](retention.md#retention-labels)將內容標記為記錄。</span><span class="sxs-lookup"><span data-stu-id="44cfb-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="44cfb-111">您可以發佈這些標籤，讓使用者和系統管理員手動將這些標籤套用至內容，或自動將這些標籤套用到您想要標記為記錄的內容。</span><span class="sxs-lookup"><span data-stu-id="44cfb-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="44cfb-112">透過使用保留標籤來將內容標記為記錄，您可以在 Microsoft 365 環境中實作單一且一致的管理記錄策略。</span><span class="sxs-lookup"><span data-stu-id="44cfb-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="44cfb-113">比較允許或封鎖動作的限制</span><span class="sxs-lookup"><span data-stu-id="44cfb-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="44cfb-114">使用下表來找出由於套用標準保留標籤，對內容施加的限制，以及將內容標示為記錄的保留標籤。</span><span class="sxs-lookup"><span data-stu-id="44cfb-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="44cfb-115">標準保留標籤的設定可保留資料，而不會將內容標示為記錄。</span><span class="sxs-lookup"><span data-stu-id="44cfb-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="44cfb-116">為了完整起見，表格包含鎖定和解除鎖定記錄的欄，這適用於 SharePoint 和 OneDrive，但不適用 Exchange。</span><span class="sxs-lookup"><span data-stu-id="44cfb-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="44cfb-117">鎖定和解除鎖定記錄的功能會使用[記錄版本設定](record-versioning.md)，其不支援 Exchange 項目。</span><span class="sxs-lookup"><span data-stu-id="44cfb-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="44cfb-118">因此，針對標示為記錄的所有 Exchange 項目，行為會對應到**記錄 - 鎖定**欄，而**記錄 - 解除鎖定**則不相關。</span><span class="sxs-lookup"><span data-stu-id="44cfb-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="44cfb-119">動作</span><span class="sxs-lookup"><span data-stu-id="44cfb-119">Action</span></span>| <span data-ttu-id="44cfb-120">保留標籤</span><span class="sxs-lookup"><span data-stu-id="44cfb-120">Retention label</span></span> |<span data-ttu-id="44cfb-121">記錄 - 鎖定</span><span class="sxs-lookup"><span data-stu-id="44cfb-121">Record - locked</span></span>| <span data-ttu-id="44cfb-122">記錄 - 解除鎖定</span><span class="sxs-lookup"><span data-stu-id="44cfb-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44cfb-123">編輯內容</span><span class="sxs-lookup"><span data-stu-id="44cfb-123">Edit contents</span></span>|<span data-ttu-id="44cfb-124">允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-124">Allowed</span></span> | <span data-ttu-id="44cfb-125">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="44cfb-125">**Blocked**</span></span> | <span data-ttu-id="44cfb-126">允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-126">Allowed</span></span>|
|<span data-ttu-id="44cfb-127">編輯內容，包括重新命名</span><span class="sxs-lookup"><span data-stu-id="44cfb-127">Edit properties, including rename</span></span>|<span data-ttu-id="44cfb-128">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-128">Allowed</span></span> |<span data-ttu-id="44cfb-129">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-129">Allowed</span></span> | <span data-ttu-id="44cfb-130">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-130">Allowed</span></span>|
|<span data-ttu-id="44cfb-131">刪除</span><span class="sxs-lookup"><span data-stu-id="44cfb-131">Delete</span></span>|<span data-ttu-id="44cfb-132">允許 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="44cfb-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="44cfb-133">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="44cfb-133">**Blocked**</span></span> | <span data-ttu-id="44cfb-134">**封鎖**</span><span class="sxs-lookup"><span data-stu-id="44cfb-134">**Blocked**</span></span>|
|<span data-ttu-id="44cfb-135">複製</span><span class="sxs-lookup"><span data-stu-id="44cfb-135">Copy</span></span>|<span data-ttu-id="44cfb-136">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-136">Allowed</span></span> |<span data-ttu-id="44cfb-137">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-137">Allowed</span></span> | <span data-ttu-id="44cfb-138">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-138">Allowed</span></span>|
|<span data-ttu-id="44cfb-139">在容器內移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="44cfb-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="44cfb-140">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-140">Allowed</span></span> |<span data-ttu-id="44cfb-141">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-141">Allowed</span></span> | <span data-ttu-id="44cfb-142">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-142">Allowed</span></span>|
|<span data-ttu-id="44cfb-143">在容器間移動 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="44cfb-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="44cfb-144">允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-144">Allowed</span></span> |<span data-ttu-id="44cfb-145">如果從未解除鎖定則允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-145">Allowed if never unlocked</span></span> | <span data-ttu-id="44cfb-146">允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-146">Allowed</span></span>|
|<span data-ttu-id="44cfb-147">開啟/讀取</span><span class="sxs-lookup"><span data-stu-id="44cfb-147">Open/Read</span></span>|<span data-ttu-id="44cfb-148">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-148">Allowed</span></span> |<span data-ttu-id="44cfb-149">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-149">Allowed</span></span> | <span data-ttu-id="44cfb-150">已允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-150">Allowed</span></span>|
|<span data-ttu-id="44cfb-151">變更標籤</span><span class="sxs-lookup"><span data-stu-id="44cfb-151">Change label</span></span>|<span data-ttu-id="44cfb-152">允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-152">Allowed</span></span> |<span data-ttu-id="44cfb-153">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="44cfb-153">Allowed - container admin only</span></span> | <span data-ttu-id="44cfb-154">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="44cfb-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="44cfb-155">移除標籤</span><span class="sxs-lookup"><span data-stu-id="44cfb-155">Remove label</span></span>|<span data-ttu-id="44cfb-156">允許</span><span class="sxs-lookup"><span data-stu-id="44cfb-156">Allowed</span></span> |<span data-ttu-id="44cfb-157">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="44cfb-157">Allowed - container admin only</span></span> | <span data-ttu-id="44cfb-158">允許 - 僅限容器系統管理員</span><span class="sxs-lookup"><span data-stu-id="44cfb-158">Allowed - container admin only</span></span>|

<span data-ttu-id="44cfb-159">註腳：</span><span class="sxs-lookup"><span data-stu-id="44cfb-159">Footnotes:</span></span>

<span data-ttu-id="44cfb-160"><sup>1</sup> OneDrive 和 Exchange 透過將複本保留在安全的位置但由 SharePoint 鎖定而支援。</span><span class="sxs-lookup"><span data-stu-id="44cfb-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="44cfb-161">使用者嘗試刪除 SharePoint 中的加標籤文件時會看見的訊息：</span><span class="sxs-lookup"><span data-stu-id="44cfb-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![無法從 SharePoint 中刪除項目的訊息](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="44cfb-163"><sup>2</sup> 容器包括 SharePoint 文件庫和 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="44cfb-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44cfb-164">後續步驟</span><span class="sxs-lookup"><span data-stu-id="44cfb-164">Next steps</span></span>

<span data-ttu-id="44cfb-165">如果您還未有保留標籤可用以記錄管理，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="44cfb-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="44cfb-166">若要將內容標示為記錄，請參閱 [使用保留標籤宣告記錄](declare-records.md)。</span><span class="sxs-lookup"><span data-stu-id="44cfb-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
