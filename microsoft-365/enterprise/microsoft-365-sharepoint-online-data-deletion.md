---
title: Microsoft 365 SharePoint 線上資料刪除
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: 瞭解資料刪除在 SharePoint Online 中的運作方式，例如儲存已刪除內容的位置和時間。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e914e84f3679483e5030b7f2a06913cb052e5411
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332721"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="bc29d-103">在 Microsoft 365 中 SharePoint 線上資料刪除</span><span class="sxs-lookup"><span data-stu-id="bc29d-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="bc29d-104">SharePoint 線上將物件儲存為應用程式資料庫中的抽象程式碼。</span><span class="sxs-lookup"><span data-stu-id="bc29d-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="bc29d-105">當使用者將檔案上傳至 SharePoint 線上時，該檔案會被反彙編並轉譯成應用程式代碼，並儲存在多個資料庫的多個資料表中。</span><span class="sxs-lookup"><span data-stu-id="bc29d-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="bc29d-106">在線上 SharePoint 中，客戶上傳的所有內容都會分割成區塊、加密 (可能會有多個 AES 256 位金鑰) ，以及跨資料中心散佈。</span><span class="sxs-lookup"><span data-stu-id="bc29d-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="bc29d-107">如需有關區塊和加密程式的特定詳細資料，請參閱 [Microsoft Cloud 中的加密](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview)。</span><span class="sxs-lookup"><span data-stu-id="bc29d-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span> 

<span data-ttu-id="bc29d-108">在線上 SharePoint 中，專案會從您從原始位置刪除時起的93天內保留。</span><span class="sxs-lookup"><span data-stu-id="bc29d-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="bc29d-109">除非某人從該回收站刪除或清除該回收站，否則它們會一直保留在網站回收站中。</span><span class="sxs-lookup"><span data-stu-id="bc29d-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="bc29d-110">在此情況下，這些專案會移至網站集合的回收站，而這些專案會在剩餘的93天內保留。</span><span class="sxs-lookup"><span data-stu-id="bc29d-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="bc29d-111">如需還原已刪除專案的詳細資訊，請參閱 [還原 SharePoint 網站回收站中的專案](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) ，以及 [從網站集合回收站還原已刪除的專案](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)。</span><span class="sxs-lookup"><span data-stu-id="bc29d-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="bc29d-112">在 SharePoint Online 中無法設定回收站保留時間。</span><span class="sxs-lookup"><span data-stu-id="bc29d-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="bc29d-113">當您刪除網站集合時，也會刪除集合中的網站階層，並在其中的所有內容：</span><span class="sxs-lookup"><span data-stu-id="bc29d-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="bc29d-114">文件及文件庫</span><span class="sxs-lookup"><span data-stu-id="bc29d-114">Documents and document libraries</span></span>
- <span data-ttu-id="bc29d-115">清單和清單資料</span><span class="sxs-lookup"><span data-stu-id="bc29d-115">Lists and list data</span></span>
- <span data-ttu-id="bc29d-116">網站設定</span><span class="sxs-lookup"><span data-stu-id="bc29d-116">Site configuration settings</span></span>
- <span data-ttu-id="bc29d-117">網站或其子網站相關的角色與安全性資訊</span><span class="sxs-lookup"><span data-stu-id="bc29d-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="bc29d-118">頂層網站的子網站、其內容和使用者資訊</span><span class="sxs-lookup"><span data-stu-id="bc29d-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="bc29d-119">如果您不小心刪除網站集合，可以使用 SharePoint 系統管理中心，由全域或 SharePoint 系統管理員還原。</span><span class="sxs-lookup"><span data-stu-id="bc29d-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="bc29d-120">已刪除的網站集合會保留93天。</span><span class="sxs-lookup"><span data-stu-id="bc29d-120">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="bc29d-121">在 93 天之後，將會永久刪除網站及其所有內容和設定，包括清單、文件庫、頁面及所有子網站。</span><span class="sxs-lookup"><span data-stu-id="bc29d-121">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="bc29d-122">當使用者從網站集合回收站清除已刪除的專案、保留和備份期間到期時，或系統管理員使用 [Remove-SPODeletedSite Cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)永久刪除網站集合時，就會發生實刪除。</span><span class="sxs-lookup"><span data-stu-id="bc29d-122">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="bc29d-123">當使用者硬性刪除 (會永久刪除或清除 SharePoint Online 中的) 內容，所有已刪除區塊的加密金鑰也會同時刪除。</span><span class="sxs-lookup"><span data-stu-id="bc29d-123">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="bc29d-124">先前儲存已刪除之區塊的磁片區塊會標示為未使用，且可重複使用。</span><span class="sxs-lookup"><span data-stu-id="bc29d-124">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
