---
title: 無限制封存概觀
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: 深入瞭解自動擴充封存，為 Exchange Online 信箱提供無限制的封存儲存。
ms.openlocfilehash: 5481fd14f281c132475613228c835c72592d2f59
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370421"
---
# <a name="overview-of-unlimited-archiving"></a><span data-ttu-id="a8857-103">無限制封存概觀</span><span class="sxs-lookup"><span data-stu-id="a8857-103">Overview of unlimited archiving</span></span>

<span data-ttu-id="a8857-104">在 Office 365 中，封存信箱可為使用者提供額外的信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="a8857-105">啟用使用者的封存信箱之後，最多可有 100 GB 的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="a8857-106">過去，當達到 100 GB 的儲存配額時，組織必須與 Microsoft 聯繫以要求封存信箱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="a8857-107">不再是這樣。</span><span class="sxs-lookup"><span data-stu-id="a8857-107">That's no longer the case.</span></span>

<span data-ttu-id="a8857-108">Microsoft 365 (中的「無限封存」功能稱為「 *自動展開* 封存」) 會在封存信箱中提供額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-108">The unlimited archiving feature in Microsoft 365 (called *auto-expanding archiving*) provides additional storage in archive mailboxes.</span></span> <span data-ttu-id="a8857-109">當封存信箱中的儲存配額達到時，Microsoft 365 會自動增加封存的大小，這表示使用者將不會耗盡信箱儲存空間，而且系統管理員不需要針對封存信箱要求額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-109">When the storage quota in the archive mailbox is reached, Microsoft 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="a8857-110">如需開啟自動展開封存的逐步指示，請參閱 [啟用無限期](enable-unlimited-archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a8857-111">自動展開封存也支援共用信箱。</span><span class="sxs-lookup"><span data-stu-id="a8857-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="a8857-112">若要啟用共用信箱的封存，則需要 exchange Online Plan 2 授權或 Exchange online Plan 1 授權與 Exchange Online 封存授權。</span><span class="sxs-lookup"><span data-stu-id="a8857-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="a8857-113">自動展開封存的運作方式</span><span class="sxs-lookup"><span data-stu-id="a8857-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="a8857-114">如先前所述，在啟用使用者的封存信箱時，會建立額外的信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="a8857-115">啟用自動展開封存時，Microsoft 365 會定期檢查封存信箱的大小。</span><span class="sxs-lookup"><span data-stu-id="a8857-115">When auto-expanding archiving is enabled, Microsoft 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="a8857-116">封存信箱接近其儲存限制時，Microsoft 365 會自動為封存建立額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-116">When an archive mailbox gets close to its storage limit, Microsoft 365 automatically creates additional storage space for the archive.</span></span> <span data-ttu-id="a8857-117">如果使用者已耗盡此額外的儲存空間，則 Microsoft 365 會為使用者的封存增加更多儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-117">If the user runs out of this additional storage space, Microsoft 365 adds more storage space to the user's archive.</span></span> <span data-ttu-id="a8857-118">此程式會自動進行，這表示系統管理員不需要要求額外的封存儲存或管理自動展開的封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-118">This process happens automatically, which means administrators don't have to request additional archive storage or manage auto-expanding archiving.</span></span>

<span data-ttu-id="a8857-119">以下是程式的快速綜述。</span><span class="sxs-lookup"><span data-stu-id="a8857-119">Here's a quick overview of the process.</span></span>

![自動展開的封存處理常式概述](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="a8857-121">啟用使用者信箱或共用信箱的封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-121">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="a8857-122">會建立具有 100 GB 儲存空間的封存信箱，並將封存信箱的警告配額設定為 90 GB。</span><span class="sxs-lookup"><span data-stu-id="a8857-122">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="a8857-123">管理員啟用信箱的自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-123">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="a8857-124">當封存信箱 (包含 [可復原的專案] 資料夾) 達到 90 GB 時，它會轉換成自動展開的封存，而 Microsoft 365 會將儲存空間新增至封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-124">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Microsoft 365 adds storage space to the archive.</span></span> <span data-ttu-id="a8857-125">最多可能需要30天的時間，才能布建額外的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-125">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8857-126">如果信箱處於暫止狀態或指派給保留原則，當自動擴充封存啟用時，封存信箱的儲存配額會提升為 110 GB。</span><span class="sxs-lookup"><span data-stu-id="a8857-126">If a mailbox is placed on hold or assigned to a retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="a8857-127">同樣地，封存警告配額增加為 100 GB。</span><span class="sxs-lookup"><span data-stu-id="a8857-127">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="a8857-128">Microsoft 365 會在必要時自動新增更多儲存空間。</span><span class="sxs-lookup"><span data-stu-id="a8857-128">Microsoft 365 automatically adds more storage space when necessary.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8857-129">只支援針對個別使用者使用的信箱 (或共用信箱) ，其成長率不會超過每日 1 GB。</span><span class="sxs-lookup"><span data-stu-id="a8857-129">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="a8857-130">使用者的封存信箱僅供該使用者使用。</span><span class="sxs-lookup"><span data-stu-id="a8857-130">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="a8857-131">不允許使用日誌記錄、傳輸規則或自動轉寄規則，將郵件複製到封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a8857-131">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="a8857-132">Microsoft 保留在使用者的封存信箱用來儲存其他使用者的封存資料或其他不適當用途的情況下，拒絕無限封存的權利。</span><span class="sxs-lookup"><span data-stu-id="a8857-132">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users or in other cases of the inappropriate use.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="a8857-133">哪些專案會移至其他封存儲存空間？</span><span class="sxs-lookup"><span data-stu-id="a8857-133">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="a8857-134">若要有效使用自動展開的封存儲存區，資料夾可能會移動。</span><span class="sxs-lookup"><span data-stu-id="a8857-134">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="a8857-135">Microsoft 365 會決定當其他儲存區新增至封存時，哪些資料夾會移動。</span><span class="sxs-lookup"><span data-stu-id="a8857-135">Microsoft 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="a8857-136">有時移動資料夾時，會自動建立一個或多個子資料夾，而且原始檔案夾中的專案會發佈到這些資料夾，以協助移動程式。</span><span class="sxs-lookup"><span data-stu-id="a8857-136">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="a8857-137">當您在 Outlook 中查看資料夾清單的封存部分時，這些子資料夾會顯示在原始檔案夾底下。</span><span class="sxs-lookup"><span data-stu-id="a8857-137">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="a8857-138">Microsoft 365 用來命名這些子資料夾的命名慣例，是\*\* \<folder name\> 在 mmm dd，yyyy h_mm) 上建立 _yyyy (\*\*，其中：</span><span class="sxs-lookup"><span data-stu-id="a8857-138">The naming convention that Microsoft 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="a8857-139">**yyyy** 是一年接收資料夾中的郵件。</span><span class="sxs-lookup"><span data-stu-id="a8857-139">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="a8857-140">**mmm dd yyyy h_m** 是由 Office 365 建立子資料夾的日期和時間，以 UTC 格式，根據使用者的時區及 Outlook 中的區域設定而定。</span><span class="sxs-lookup"><span data-stu-id="a8857-140">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="a8857-141">下列螢幕擷取畫面顯示將郵件移至自動展開的封存之前和之後的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="a8857-141">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="a8857-142">**新增額外的儲存體之前**</span><span class="sxs-lookup"><span data-stu-id="a8857-142">**Before additional storage is added**</span></span>

![已布建自動擴充封存之前，封存信箱的資料夾清單](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="a8857-144">**新增額外的儲存空間之後**</span><span class="sxs-lookup"><span data-stu-id="a8857-144">**After additional storage is added**</span></span>

![已布建自動展開封存後的封存信箱的資料夾清單](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="a8857-146">如先前所述，Microsoft 365 會將專案移至子資料夾 (，並使用上述) 所述的命名慣例加以命名，以協助將內容散佈至輔助封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-146">As previously described, Microsoft 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="a8857-147">但是將專案移至子資料夾可能不一定是這樣。</span><span class="sxs-lookup"><span data-stu-id="a8857-147">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="a8857-148">有時候整個資料夾可能會移至輔助封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-148">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="a8857-149">在此情況下，資料夾將保留其原始名稱。</span><span class="sxs-lookup"><span data-stu-id="a8857-149">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="a8857-150">在 Outlook 的資料夾清單中，資料夾已經移至輔助封存，它並不明顯。</span><span class="sxs-lookup"><span data-stu-id="a8857-150">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="a8857-151">在自動展開的封存中存取專案所需的 Outlook 需求</span><span class="sxs-lookup"><span data-stu-id="a8857-151">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="a8857-152">若要存取儲存在自動展開的封存中的郵件，使用者必須使用下列其中一個 Outlook 用戶端：</span><span class="sxs-lookup"><span data-stu-id="a8857-152">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="a8857-153">Outlook 2016 或 Outlook 2019 for Windows</span><span class="sxs-lookup"><span data-stu-id="a8857-153">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="a8857-154">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="a8857-154">Outlook on the web</span></span>

- <span data-ttu-id="a8857-155">Outlook 2016 或 Outlook 2019 （適用于 Mac）</span><span class="sxs-lookup"><span data-stu-id="a8857-155">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="a8857-156">以下是使用 Outlook 或 Outlook 網頁版時所要考慮的一些事項，以存取儲存在自動擴充封存中的郵件。</span><span class="sxs-lookup"><span data-stu-id="a8857-156">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="a8857-157">您可以存取封存信箱中的任何資料夾，包括已移至自動擴充儲存區域的資料夾。</span><span class="sxs-lookup"><span data-stu-id="a8857-157">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="a8857-158">僅限預覽人員組建16.0.12716.10000 時，才可在 Outlook Desktop 中搜尋自動擴充的封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-158">Search for auto-expanded archiving is only available in Outlook Desktop as of Insiders build 16.0.12716.10000.</span></span> <span data-ttu-id="a8857-159">網頁版 Outlook 中提供搜尋。</span><span class="sxs-lookup"><span data-stu-id="a8857-159">Search is available in Outlook for the web.</span></span> <span data-ttu-id="a8857-160">類似于線上封存，您只需搜尋資料夾本身，即可搜尋移至其他儲存體區域的專案。</span><span class="sxs-lookup"><span data-stu-id="a8857-160">Similar to Online Archive, you can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="a8857-161">這表示您必須選取 [資料夾清單] 中的 [封存] 資料夾，以選取 **目前的資料夾** 選項作為搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="a8857-161">This means that you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="a8857-162">同樣地，如果自動擴充的儲存體區域中的資料夾包含子資料夾，您必須分別搜尋每個子資料夾。</span><span class="sxs-lookup"><span data-stu-id="a8857-162">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span>

- <span data-ttu-id="a8857-163">Outlook 中的專案計數和已讀取/未讀取的計數 (在自動展開的封存中的 Outlook 和 Outlook 網頁) 中，可能不會準確。</span><span class="sxs-lookup"><span data-stu-id="a8857-163">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="a8857-164">您可以刪除子資料夾中的專案，使其指向自動擴充的儲存區，但是無法刪除資料夾本身。</span><span class="sxs-lookup"><span data-stu-id="a8857-164">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="a8857-165">您無法使用 [復原刪除的郵件] 功能，從自動擴充的儲存區中復原已刪除的專案。</span><span class="sxs-lookup"><span data-stu-id="a8857-165">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-compliance-features"></a><span data-ttu-id="a8857-166">自動展開封存和其他符合性功能</span><span class="sxs-lookup"><span data-stu-id="a8857-166">Auto-expanding archiving and other compliance features</span></span>

<span data-ttu-id="a8857-167">本節說明自動擴充封存與其他法規遵從性及資料管理功能之間的功能。</span><span class="sxs-lookup"><span data-stu-id="a8857-167">This section explains the functionality between auto-expanding archiving and other compliance and data governance features.</span></span>

- <span data-ttu-id="a8857-168">**eDiscovery：** 當您使用 eDiscovery 工具（例如內容搜尋或 In-Place 電子檔探索）時，也會搜尋自動擴充封存中的其他儲存區。</span><span class="sxs-lookup"><span data-stu-id="a8857-168">**eDiscovery:** When you use an eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="a8857-169">**保留：** 當您使用 Exchange Online 中的訴訟資料暫止或 eDiscovery 案例保留和保留原則，將信箱保留在「保留」狀態時，位於自動展開封存中的內容也會處於暫止狀態。</span><span class="sxs-lookup"><span data-stu-id="a8857-169">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="a8857-170">**通訊記錄管理 (MRM) ：** 如果您使用 Exchange Online 中的 MRM 刪除原則永久刪除過期的信箱專案，則也會刪除位於自動展開封存中的已過期專案。</span><span class="sxs-lookup"><span data-stu-id="a8857-170">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="a8857-171">匯**入服務：** 您可以使用 Office 365 匯入服務，將 PST 檔案匯入至使用者的自動擴充封存。</span><span class="sxs-lookup"><span data-stu-id="a8857-171">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="a8857-172">您可以將最多 100 GB 的資料從 PST 檔案匯入至使用者的封存信箱。</span><span class="sxs-lookup"><span data-stu-id="a8857-172">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="a8857-173">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a8857-173">More information</span></span>

<span data-ttu-id="a8857-174">如需自動展開封存的相關技術詳細資訊，請參閱 [Microsoft 365：自動展開的封存常見問題](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)。</span><span class="sxs-lookup"><span data-stu-id="a8857-174">For more technical details about auto-expanding archiving, see [Microsoft 365: Auto-Expanding Archives FAQ](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).</span></span>
