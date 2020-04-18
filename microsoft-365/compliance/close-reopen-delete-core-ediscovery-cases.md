---
title: 關閉、重新開啟和刪除核心 eDiscovery 案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明如何管理核心 eDiscovery 案例。 這包括關閉案例、開啟關閉的案例，以及刪除案例。
ms.openlocfilehash: 41ba622a58b0abb5ce668e6d94d89b1694a328c9
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551388"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="fb1ff-104">關閉、重新開啟和刪除核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="fb1ff-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="fb1ff-105">本文說明如何關閉、重新開啟和刪除 Microsoft 365 中的核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="fb1ff-106">關閉案例</span><span class="sxs-lookup"><span data-stu-id="fb1ff-106">Close a case</span></span>

<span data-ttu-id="fb1ff-107">當核心 eDiscovery 案例支援的法律案例或調查完成後，您就可以關閉案例。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="fb1ff-108">以下是關閉案例時會發生的情況：</span><span class="sxs-lookup"><span data-stu-id="fb1ff-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="fb1ff-109">若案例包含 eDiscovery 保留中的任何內容位置，將會關閉那些保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="fb1ff-110">這可能會導致內容被使用者或自動化程式（如刪除原則）永久刪除或清除。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-110">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="fb1ff-111">關閉案例只會關閉與該案例相關聯的保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-111">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="fb1ff-112">如果其他保留放在內容位置（例如訴訟暫止、保留原則或不同核心 eDiscovery 案例的保留）上，則仍會保留這些保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-112">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="fb1ff-113">此案例仍列在 Microsoft 365 規範中心的核心 eDiscovery 頁面上。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-113">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb1ff-114">已關閉案例的詳細資料、保留、搜尋及成員都會保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-114">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="fb1ff-115">您可以在關閉案例後進行編輯。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-115">You can edit a case after it's closed.</span></span> <span data-ttu-id="fb1ff-116">例如，您可以新增或移除成員、建立搜尋並匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-116">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="fb1ff-117">主動和封閉式案例之間的主要差異是關閉案例時，會關閉 eDiscovery 保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-117">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="fb1ff-118">若要關閉案例：</span><span class="sxs-lookup"><span data-stu-id="fb1ff-118">To close a case:</span></span>
  
1. <span data-ttu-id="fb1ff-119">在 [Microsoft 365 合規性] enter 中，按一下 [ **eDiscovery** > **Core** ] 以顯示您組織中的核心 eDiscovery 案例清單。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-119">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="fb1ff-120">按一下您要關閉之案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-120">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="fb1ff-121">[**管理此案例**飛出] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-121">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="fb1ff-122">在 [**管理案例狀態**] 底下，按一下 [**關閉案例**]。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-122">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="fb1ff-123">會顯示警告，指出與案例相關聯的保留會關閉。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-123">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="fb1ff-124">按一下 **[是]** 以關閉案例。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-124">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="fb1ff-125">[**管理此案例**] 飛入頁面上的狀態會**從 [** 使用中] 改為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-125">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="fb1ff-126">關閉 [**管理此案例**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-126">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="fb1ff-127">在 [**核心 eDiscovery** ] 頁面上 **，按一下 [** 重新整理] 以更新封閉式案例的狀態。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-127">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="fb1ff-128">完成關閉程式可能需要長達60分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-128">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="fb1ff-129">當程式完成時，**核心 eDiscovery**頁面上的案例狀態會變更為 [**已關閉**]。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-129">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="fb1ff-130">再次按一下案例的名稱，以顯示 [**管理此案例**飛出] 頁面，該頁面包含案例已關閉及關閉者的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-130">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="fb1ff-131">重新開啟已關閉的案例</span><span class="sxs-lookup"><span data-stu-id="fb1ff-131">Reopen a closed case</span></span>

<span data-ttu-id="fb1ff-132">當您重新開啟案例時，關閉案例時所使用的任何 eDiscovery 保留都不會自動復原。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="fb1ff-133">在重新開啟案例之後，您必須移至 [**保留**] 頁面並開啟先前保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="fb1ff-134">若要開啟保留，請選取它以顯示飛入頁面，然後將**狀態**切換設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="fb1ff-135">在 [Microsoft 365 合規性] enter 中，按一下 [ **eDiscovery** > **Core** ] 以顯示您組織中的核心 eDiscovery 案例清單。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-135">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="fb1ff-136">按一下您要重新開啟之案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-136">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="fb1ff-137">[**管理此案例**飛出] 頁面隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-137">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="fb1ff-138">在 [**管理案例狀態**] 底下，按一下 [**重新開啟案例**]。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-138">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="fb1ff-139">會顯示警告，指出在關閉此案例時，其所關聯的保留不會自動開啟。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="fb1ff-140">按一下 **[是]** 重新開啟案例。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="fb1ff-141">「**管理此案例**」彈出頁面上的狀態會從 [**已關閉**] 變更為 [**使用中]。**</span><span class="sxs-lookup"><span data-stu-id="fb1ff-141">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="fb1ff-142">關閉 [**管理此案例**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-142">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="fb1ff-143">在**核心 eDiscovery**頁面上 **，按一下 [** 重新整理] 以更新重新開啟之案例的狀態。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-143">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="fb1ff-144">最多可能需要60分鐘的時間，重新開啟程式才會完成。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-144">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="fb1ff-145">當程式完成時，**核心 eDiscovery**頁面上的案例狀態會變更為 [**作用中]** 。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-145">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="fb1ff-146">刪除案例</span><span class="sxs-lookup"><span data-stu-id="fb1ff-146">Delete a case</span></span>

<span data-ttu-id="fb1ff-147">您也可以刪除主動及封閉式核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="fb1ff-148">當您刪除案例時，案例中的所有搜尋和匯出都會被刪除，而且案例會從 Microsoft 365 規範中心的**核心 eDiscovery**頁面上的案例清單中移除。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="fb1ff-149">您無法重新開啟已刪除的案例。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="fb1ff-150">您必須先刪除*所有*與案例相關聯的 eDiscovery 保留，才可刪除案例（不論是作用中或已關閉）。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="fb1ff-151">這包括刪除狀態為**Off**的保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="fb1ff-152">若要刪除 eDiscovery 保留：</span><span class="sxs-lookup"><span data-stu-id="fb1ff-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="fb1ff-153">移至 [**保留**] 索引標籤中您要刪除的情況。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="fb1ff-154">按一下您要刪除的保留。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-154">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="fb1ff-155">在飛入頁面上，按一下 [**刪除保留**]。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-155">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="fb1ff-156">若要刪除案例：</span><span class="sxs-lookup"><span data-stu-id="fb1ff-156">To delete a case:</span></span>

1. <span data-ttu-id="fb1ff-157">在 [Microsoft 365 合規性] enter 中，按一下 [ **eDiscovery** > **Core** ] 以顯示您組織中的核心 eDiscovery 案例清單。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-157">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="fb1ff-158">按一下您要刪除之案例的名稱。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-158">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="fb1ff-159">在 [飛入] 頁面上，按一下 [**管理案例狀態**] 底下的 [**刪除案例**]。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-159">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="fb1ff-160">如果您嘗試刪除的案例仍包含 eDiscovery 保留，您會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-160">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="fb1ff-161">您必須刪除所有與案例相關聯的保留，然後再試一次，以刪除案例。</span><span class="sxs-lookup"><span data-stu-id="fb1ff-161">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
