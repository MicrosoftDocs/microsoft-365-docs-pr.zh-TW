---
title: 在 Office 365 中的無限制封存概觀
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
description: 了解自動展開封存在 Office 365 中，可提供無限制的封存儲存 Exchange Online 信箱。
ms.openlocfilehash: 56070fde9f56223becbb72bd701242ca243abbcb
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802616"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a><span data-ttu-id="4cc64-103">在 Office 365 中的無限制封存概觀</span><span class="sxs-lookup"><span data-stu-id="4cc64-103">Overview of unlimited archiving in Office 365</span></span>

<span data-ttu-id="4cc64-104">在 Office 365 中封存信箱提供使用者額外信箱儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4cc64-104">In Office 365, archive mailboxes provide users with additional mailbox storage space.</span></span> <span data-ttu-id="4cc64-105">啟用使用者的封存信箱之後，最多 100 GB 的額外儲存空間使用。</span><span class="sxs-lookup"><span data-stu-id="4cc64-105">After a user's archive mailbox is enabled, up to 100 GB of additional storage is available.</span></span> <span data-ttu-id="4cc64-106">在過去，當已達到 100 GB 的儲存空間配額，組織必須與 Microsoft 連絡到的封存信箱的要求額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4cc64-106">In the past, when the 100-GB storage quota was reached, organizations had to contact Microsoft to request additional storage space for an archive mailbox.</span></span> <span data-ttu-id="4cc64-107">這不再是這種情況。</span><span class="sxs-lookup"><span data-stu-id="4cc64-107">That's no longer the case.</span></span>

<span data-ttu-id="4cc64-108">（稱為*自動展開封存*） 的 Office 365 中的無限制封存功能提供最多 1 TB 的封存信箱中的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4cc64-108">The unlimited archiving feature in Office 365 (called *auto-expanding archiving*) provides up to 1 TB of additional storage in archive mailboxes.</span></span> <span data-ttu-id="4cc64-109">達到封存信箱中的儲存配額時，Office 365 會自動增加的封存，這表示使用者不會用盡信箱儲存空間和系統管理員不需要要求封存信箱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4cc64-109">When the storage quota in the archive mailbox is reached, Office 365 automatically increases the size of the archive, which means that users won't run out of mailbox storage space and administrators won't have to request additional storage for archive mailboxes.</span></span>

<span data-ttu-id="4cc64-110">如需逐步指示的開啟自動展開封存，請參閱[啟用 Office 365 中的無限制封存](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc64-110">For step-by-step instructions for turning on auto-expanding archiving, see [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4cc64-111">自動展開封存也支援共用信箱。</span><span class="sxs-lookup"><span data-stu-id="4cc64-111">Auto-expanding archiving also supports shared mailboxes.</span></span> <span data-ttu-id="4cc64-112">若要啟用信箱的共用信箱的封存，Exchange Online Plan 2 授權或具有 Exchange Online Archiving 授權的 Exchange Online Plan 1 授權就需要。</span><span class="sxs-lookup"><span data-stu-id="4cc64-112">To enable the archive for a shared mailbox, an Exchange Online Plan 2 license or an Exchange Online Plan 1 license with an Exchange Online Archiving license is required.</span></span>

## <a name="how-auto-expanding-archiving-works"></a><span data-ttu-id="4cc64-113">如何自動展開封存的運作</span><span class="sxs-lookup"><span data-stu-id="4cc64-113">How auto-expanding archiving works</span></span>

<span data-ttu-id="4cc64-114">為先前所述的其他信箱啟用使用者的封存信箱時，會建立儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4cc64-114">As previously explained, additional mailbox storage space is created when a user's archive mailbox is enabled.</span></span> <span data-ttu-id="4cc64-115">啟用自動展開封存時，Office 365 會定期檢查封存信箱的大小。</span><span class="sxs-lookup"><span data-stu-id="4cc64-115">When auto-expanding archiving is enabled, Office 365 periodically checks the size of the archive mailbox.</span></span> <span data-ttu-id="4cc64-116">當封存信箱取得接近其儲存限制時，Office 365 會自動建立封存信箱的額外儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4cc64-116">When an archive mailbox gets close to its storage limit, Office 365 automatically creates additional storage space for the archive mailbox.</span></span> <span data-ttu-id="4cc64-117">此額外的空間會呼叫*輔助封存*。</span><span class="sxs-lookup"><span data-stu-id="4cc64-117">This additional space is called an *auxiliary archive*.</span></span> <span data-ttu-id="4cc64-118">如果使用者執行輔助封存中的儲存空間不足，Office 365 會自動加入新的輔助封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-118">If the user runs out of storage space in an auxiliary archive, Office 365 will automatically add a new auxiliary archive.</span></span> <span data-ttu-id="4cc64-119">Office 365 新增最多 1 TB 的額外儲存空間總計的 20 輔助封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-119">Office 365 adds a maximum of 20 auxiliary archives for a total of 1 TB of additional storage.</span></span> <span data-ttu-id="4cc64-120">這表示系統管理員不需要管理自動展開封存此程序會自動發生。</span><span class="sxs-lookup"><span data-stu-id="4cc64-120">This process happens automatically, which means administrators don't have to manage auto-expanding archiving.</span></span>

<span data-ttu-id="4cc64-121">以下是程序的簡要概觀。</span><span class="sxs-lookup"><span data-stu-id="4cc64-121">Here's a quick overview of the process.</span></span>

![自動展開封存程序概觀](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. <span data-ttu-id="4cc64-123">使用者信箱或共用的信箱啟用封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-123">Archiving is enabled for a user mailbox or a shared mailbox.</span></span> <span data-ttu-id="4cc64-124">會建立封存信箱具有 100 GB 的儲存空間，且封存信箱的 [警告] 配額設為 90 GB。</span><span class="sxs-lookup"><span data-stu-id="4cc64-124">An archive mailbox with 100 GB of storage space is created, and the warning quota for the archive mailbox is set to 90 GB.</span></span>

2. <span data-ttu-id="4cc64-125">系統管理員可讓自動展開封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4cc64-125">An administrator enables auto-expanding archiving for the mailbox.</span></span> <span data-ttu-id="4cc64-126">當封存信箱 （包括 [可復原的項目] 資料夾） 達到 90 GB 時，則會轉換成自動展開封存，與 Office 365 會儲存空間新增至封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-126">When the archive mailbox (including the Recoverable Items folder) reaches 90 GB, it's converted to an auto-expanding archive, and Office 365 adds storage space to the archive.</span></span> <span data-ttu-id="4cc64-127">可能需要最多 30 天的額外儲存空間來佈建。</span><span class="sxs-lookup"><span data-stu-id="4cc64-127">It can take up to 30 days for the additional storage space to be provisioned.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4cc64-128">如果信箱會處於暫止狀態或指派給 Office 365 保留原則，啟用自動展開封存時增加封存信箱的儲存配額為 110 GB。</span><span class="sxs-lookup"><span data-stu-id="4cc64-128">If a mailbox is placed on hold or assigned to an Office 365 retention policy, the storage quota for the archive mailbox is increased to 110 GB when auto-expanding archiving is enabled.</span></span> <span data-ttu-id="4cc64-129">同樣地，封存警告配額增加到 100GB。</span><span class="sxs-lookup"><span data-stu-id="4cc64-129">Similarly, the archive warning quota is increased to 100 GB.</span></span>

3. <span data-ttu-id="4cc64-130">Office 365 會自動新增更多儲存空間，必要時。</span><span class="sxs-lookup"><span data-stu-id="4cc64-130">Office 365 automatically adds more storage space when necessary.</span></span> <span data-ttu-id="4cc64-131">如先前所述，Office 365 新增最多 20 輔助封存，最多 1 TB 的額外的封存儲存空間。</span><span class="sxs-lookup"><span data-stu-id="4cc64-131">As previously stated, Office 365 adds up to 20 auxiliary archives, for a maximum of 1 TB of additional archive storage space.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4cc64-132">自動展開封存才支援信箱用於個別使用者 （或共用信箱） 不會超過 1 GB，每天成長率。</span><span class="sxs-lookup"><span data-stu-id="4cc64-132">Auto-expanding archive is only supported for mailboxes used for individual users (or shared mailboxes) with a growth rate that doesn't exceed 1 GB per day.</span></span> <span data-ttu-id="4cc64-133">使用者的封存信箱僅供該使用者使用。</span><span class="sxs-lookup"><span data-stu-id="4cc64-133">A user's archive mailbox is intended for just that user.</span></span> <span data-ttu-id="4cc64-134">不允許使用日誌、 傳輸規則或自動轉寄規則將郵件複製到封存信箱。</span><span class="sxs-lookup"><span data-stu-id="4cc64-134">Using journaling, transport rules, or auto-forwarding rules to copy messages to an archive mailbox is not permitted.</span></span> <span data-ttu-id="4cc64-135">Microsoft 保留在使用者封存信箱中用來儲存其他使用者之封存資料的執行個體中拒絕不受限封存的權限。</span><span class="sxs-lookup"><span data-stu-id="4cc64-135">Microsoft reserves the right to deny unlimited archiving in instances where a user's archive mailbox is used to store archive data for other users.</span></span>

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a><span data-ttu-id="4cc64-136">項目取得移至其他封存儲存空間？</span><span class="sxs-lookup"><span data-stu-id="4cc64-136">What gets moved to the additional archive storage space?</span></span>

<span data-ttu-id="4cc64-137">若要有效使用自動展開封存儲存，可能會移動資料夾。</span><span class="sxs-lookup"><span data-stu-id="4cc64-137">To make efficient use of auto-expanding archive storage, folders may get moved.</span></span> <span data-ttu-id="4cc64-138">Office 365 會決定哪些資料夾取得移至封存新增額外的儲存空間時。</span><span class="sxs-lookup"><span data-stu-id="4cc64-138">Office 365 determines which folders get moved when additional storage is added to the archive.</span></span> <span data-ttu-id="4cc64-139">有時時移動資料夾，會自動建立一或多個的子資料夾，原來的資料夾中的項目會分配到這些資料夾以利移動程序。</span><span class="sxs-lookup"><span data-stu-id="4cc64-139">Sometimes when a folder is moved, one or more subfolders are automatically created and items from the original folder are distributed to these folders to facilitate the moving process.</span></span> <span data-ttu-id="4cc64-140">當您在 Outlook 中檢視資料夾清單] 的封存部分，這些子資料夾會顯示原始資料夾下。</span><span class="sxs-lookup"><span data-stu-id="4cc64-140">When viewing the archive portion of the folder list in Outlook, these subfolders are displayed under the original folder.</span></span>  <span data-ttu-id="4cc64-141">Office 365 使用來命名這些子資料夾的命名慣例為**\<資料夾名稱\>_yyyy （上建立 mmm dd，yyyy h_mm）**，其中：</span><span class="sxs-lookup"><span data-stu-id="4cc64-141">The naming convention that Office 365 uses to name these subfolders is **\<folder name\>_yyyy (Created on mmm dd, yyyy h_mm)**, where:</span></span>

- <span data-ttu-id="4cc64-142">**yyyy**是所收到的郵件] 資料夾中的年份。</span><span class="sxs-lookup"><span data-stu-id="4cc64-142">**yyyy** is the year the messages in the folder were received.</span></span>

- <span data-ttu-id="4cc64-143">**mmm dd，yyyy h_m**是子資料夾由 Office 365 中，建立以 UTC 格式，根據使用者的時區和 Outlook 中的地區設定的時間與日期。</span><span class="sxs-lookup"><span data-stu-id="4cc64-143">**mmm dd, yyyy h_m** is the date and time that the subfolder was created by Office 365, in UTC format, based on the user's time zone and regional settings in Outlook.</span></span>

<span data-ttu-id="4cc64-144">下列螢幕擷取畫面顯示的資料夾清單前面和後面的郵件會移至自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-144">The following screenshots show a folder list before and after messages are moved to an auto-expanded archive.</span></span>

 <span data-ttu-id="4cc64-145">**之前新增額外儲存空間**</span><span class="sxs-lookup"><span data-stu-id="4cc64-145">**Before additional storage is added**</span></span>

![之前已佈建自動展開封存的封存信箱的資料夾清單](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 <span data-ttu-id="4cc64-147">**之後新增額外儲存空間**</span><span class="sxs-lookup"><span data-stu-id="4cc64-147">**After additional storage is added**</span></span>

![之後已佈建自動展開封存的封存信箱的資料夾清單](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> <span data-ttu-id="4cc64-149">如先前所述，Office 365 將項目移至子資料夾 （以及它們使用的命名慣例上面所述的名稱），協助分配到輔助封存的內容。</span><span class="sxs-lookup"><span data-stu-id="4cc64-149">As previously described, Office 365 moves items to subfolders (and names them using the naming convention described above) to help distribute content to an auxiliary archive.</span></span> <span data-ttu-id="4cc64-150">但是，將項目移至子資料夾不一定大小寫。</span><span class="sxs-lookup"><span data-stu-id="4cc64-150">But moving items to subfolders may not always be the case.</span></span> <span data-ttu-id="4cc64-151">有時整個資料夾可能會移到輔助封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-151">Sometimes an entire folder may be moved to an auxiliary archive.</span></span> <span data-ttu-id="4cc64-152">在此情況下，該資料夾會保留其原始的名稱。</span><span class="sxs-lookup"><span data-stu-id="4cc64-152">In this case, the folder will retain its original name.</span></span>  <span data-ttu-id="4cc64-153">它不會明顯資料夾已移至輔助封存在 Outlook 中的資料夾清單。</span><span class="sxs-lookup"><span data-stu-id="4cc64-153">It won't be apparent in the folder list in Outlook that the folder was moved to an auxiliary archive.</span></span>

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a><span data-ttu-id="4cc64-154">Outlook 需求，來存取自動展開封存中的項目</span><span class="sxs-lookup"><span data-stu-id="4cc64-154">Outlook requirements for accessing items in an auto-expanded archive</span></span>

<span data-ttu-id="4cc64-155">若要存取儲存在自動展開封存的郵件，使用者必須使用下列其中一個下列 Outlook 用戶端：</span><span class="sxs-lookup"><span data-stu-id="4cc64-155">To access messages that are stored in an auto-expanded archive, users have to use one of the following Outlook clients:</span></span>

- <span data-ttu-id="4cc64-156">Outlook 2016 或 Windows 版 Outlook 2019</span><span class="sxs-lookup"><span data-stu-id="4cc64-156">Outlook 2016 or Outlook 2019 for Windows</span></span>

- <span data-ttu-id="4cc64-157">Outlook 網頁版</span><span class="sxs-lookup"><span data-stu-id="4cc64-157">Outlook on the web</span></span>

- <span data-ttu-id="4cc64-158">Outlook 2016 或 Outlook for Mac 的 2019</span><span class="sxs-lookup"><span data-stu-id="4cc64-158">Outlook 2016 or Outlook 2019 for Mac</span></span>

<span data-ttu-id="4cc64-159">以下是使用 Outlook 或 Outlook 來存取郵件中自動展開封存儲存網頁時要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="4cc64-159">Here are some things to consider when using Outlook or Outlook on the web to access messages stored in an auto-expanded archive.</span></span>

- <span data-ttu-id="4cc64-160">您可以存取封存信箱時，包括已移至自動展開存放區中的任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="4cc64-160">You can access any folder in your archive mailbox, including ones that were moved to the auto-expanded storage area.</span></span>

- <span data-ttu-id="4cc64-161">您可以搜尋的只是藉由搜尋資料夾本身已移至其他儲存區的項目。</span><span class="sxs-lookup"><span data-stu-id="4cc64-161">You can search for items that were moved to an additional storage area only by searching the folder itself.</span></span> <span data-ttu-id="4cc64-162">這表示您已選取 [封存] 資料夾在資料夾清單中選取 [**目前的資料夾**選項作為搜尋範圍。</span><span class="sxs-lookup"><span data-stu-id="4cc64-162">This means that you have to select the archive folder in the folder list to select the **Current Folder** option as the search scope.</span></span> <span data-ttu-id="4cc64-163">同樣地，如果自動展開存放區中的資料夾含有子資料夾，您必須個別搜尋每個子資料夾。</span><span class="sxs-lookup"><span data-stu-id="4cc64-163">Similarly, if a folder in an auto-expanded storage area contains subfolders, you have to search each subfolder separately.</span></span>

- <span data-ttu-id="4cc64-164">Outlook 中的項目計數，而且可能無法正確自動展開封存中的讀取/未讀計數 （在 Outlook 和 outlook 網頁版）。</span><span class="sxs-lookup"><span data-stu-id="4cc64-164">Item counts in Outlook and Read/Unread counts (in Outlook and Outlook on the web) in an auto-expanded archive might not be accurate.</span></span>

- <span data-ttu-id="4cc64-165">您可以刪除指向自動展開存放裝置] 區域中，子資料夾中的項目，但不能刪除資料夾本身。</span><span class="sxs-lookup"><span data-stu-id="4cc64-165">You can delete items in a subfolder that points to an auto-expanded storage area, but the folder itself can't be deleted.</span></span>

- <span data-ttu-id="4cc64-166">您無法使用 [復原刪除的項目] 功能來復原已從自動展開存放區刪除的項目。</span><span class="sxs-lookup"><span data-stu-id="4cc64-166">You can't use the Recover Deleted Items feature to recover an item that was deleted from an auto-expanded storage area.</span></span>

## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a><span data-ttu-id="4cc64-167">自動展開封存和其他 Office 365 合規性功能</span><span class="sxs-lookup"><span data-stu-id="4cc64-167">Auto-expanding archiving and other Office 365 compliance features</span></span>

<span data-ttu-id="4cc64-168">本章節說明自動展開封存和其他 Office 365 合規性和資料控管功能之間的功能。</span><span class="sxs-lookup"><span data-stu-id="4cc64-168">This section explains the functionality between auto-expanding archiving and other Office 365 compliance and data governance features.</span></span>

- <span data-ttu-id="4cc64-169">**eDiscovery:** 當您使用 Office 365 電子文件探索工具，例如內容搜尋 」 或 「 就地 eDiscovery 」 也會搜尋中自動展開封存的額外儲存空間區域。</span><span class="sxs-lookup"><span data-stu-id="4cc64-169">**eDiscovery:** When you use an Office 365 eDiscovery tool, such as Content Search or In-Place eDiscovery, the additional storage areas in an auto-expanded archive are also searched.</span></span>

- <span data-ttu-id="4cc64-170">**保留：** 當您讓信箱處於保留使用例如訴訟暫止的工具在 Exchange 線上] 或 [eDiscovery 案例保留與位於自動展開封存的保留原則中的安全性與合規性中心，內容也會處於暫止。</span><span class="sxs-lookup"><span data-stu-id="4cc64-170">**Retention:** When you put a mailbox on hold by using tools such as Litigation Hold in Exchange Online or eDiscovery case holds and retention policies in the security and compliance center, content located in an auto-expanded archive is also placed on hold.</span></span>

- <span data-ttu-id="4cc64-171">**通訊記錄管理 (MRM):** 如果您使用 Exchange Online 中的 MRM 刪除原則若要永久刪除過期的信箱項目，也會刪除過期的項目位於自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-171">**Messaging records management (MRM):** If you use MRM deletion policies in Exchange Online to permanently delete expired mailbox items, expired items located in the auto-expanded archive will also be deleted.</span></span>

- <span data-ttu-id="4cc64-172">**匯入服務：** 您可以使用 Office 365 匯入服務將 PST 檔案匯入使用者的自動展開封存。</span><span class="sxs-lookup"><span data-stu-id="4cc64-172">**Import service:** You can use the Office 365 Import service to import PST files to a user's auto-expanded archive.</span></span> <span data-ttu-id="4cc64-173">您可以到使用者的封存信箱，最多 100 GB 的資料匯入從 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="4cc64-173">You can import up to 100 GB of data from PST files to the user's archive mailbox.</span></span>

## <a name="more-information"></a><span data-ttu-id="4cc64-174">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="4cc64-174">More information</span></span>

<span data-ttu-id="4cc64-175">如需自動展開封存，請參閱詳細技術的詳細資訊[Office 365： 自動展開封存常見問題集](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/)。</span><span class="sxs-lookup"><span data-stu-id="4cc64-175">For more technical details about auto-expanding archiving, see [Office 365: Auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).</span></span>
