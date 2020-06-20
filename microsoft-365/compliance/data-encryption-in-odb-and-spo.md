---
title: 商務用 OneDrive 和 SharePoint Online 中的資料加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 了解 OneDrive for Business 和 SharePoint Online 中的資料安全性加密基本項目。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0c78a9ca6e6bad1e4aea707f8be5dec818b7a27
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817922"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="1a8f2-103">商務用 OneDrive 和 SharePoint Online 中的資料加密</span><span class="sxs-lookup"><span data-stu-id="1a8f2-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="1a8f2-104">了解 OneDrive for Business 和 SharePoint Online 中的資料安全性加密基本項目。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="security-and-data-encryption-in-office-365"></a><span data-ttu-id="1a8f2-105">Office 365 中的安全性和資料加密</span><span class="sxs-lookup"><span data-stu-id="1a8f2-105">Security and data encryption in Office 365</span></span>

<span data-ttu-id="1a8f2-106">Microsoft 365 是高度安全的環境，可提供多層的廣泛保護：實體資料中心安全性、網路安全性、存取安全性、應用程式安全性和資料安全性。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-106">Microsoft 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security.</span></span> <span data-ttu-id="1a8f2-107">本文特別著重在OneDrive for Business 和 SharePoint Online 的傳輸中和靜態加密等方面。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-107">This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="1a8f2-108">觀看下列影片，了解資料加密如何運作。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-108">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="1a8f2-109">傳輸中資料的加密</span><span class="sxs-lookup"><span data-stu-id="1a8f2-109">Encryption of data in transit</span></span>

<span data-ttu-id="1a8f2-110">在OneDrive for Business 和 SharePoint Online 中，資料進出資料中心的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-110">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="1a8f2-111">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-111">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections.</span></span> <span data-ttu-id="1a8f2-112">All SSL connections are established using 2048-bit keys.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-112">All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="1a8f2-113">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-113">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery.</span></span> <span data-ttu-id="1a8f2-114">For instance, SQL Server transaction logs and blob storage deltas travel along this pipe.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-114">For instance, SQL Server transaction logs and blob storage deltas travel along this pipe.</span></span> <span data-ttu-id="1a8f2-115">While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-115">While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="1a8f2-116">靜態資料的加密</span><span class="sxs-lookup"><span data-stu-id="1a8f2-116">Encryption of data at rest</span></span>

<span data-ttu-id="1a8f2-117">靜態加密包括兩個元件：BitLocker 磁碟層級加密，以及客戶內容的每一檔案加密。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-117">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="1a8f2-118">服務針對OneDrive for Business 和 SharePoint Online 部署了 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-118">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="1a8f2-119">在 Microsoft 365 多承租人和以多承租人技術為基礎的新專用環境中 SharePoint，每個檔案加密也是在商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-119">Per-file encryption is also in OneDrive for Business and SharePoint Online in Microsoft 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="1a8f2-120">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-120">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file.</span></span> <span data-ttu-id="1a8f2-121">Further, every update to every file is encrypted using its own encryption key.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-121">Further, every update to every file is encrypted using its own encryption key.</span></span> <span data-ttu-id="1a8f2-122">Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-122">Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content.</span></span> <span data-ttu-id="1a8f2-123">Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-123">Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant.</span></span> <span data-ttu-id="1a8f2-124">The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-124">The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials.</span></span> <span data-ttu-id="1a8f2-125">These credentials are stored in a separate physical location from either the content or the content keys.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-125">These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="1a8f2-126">如需有關 FIPS 140-2 規範的詳細資訊，請參閱[FIPS 140-2 相容性](https://go.microsoft.com/fwlink/?LinkId=517625)。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-126">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="1a8f2-127">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-127">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection.</span></span> <span data-ttu-id="1a8f2-128">All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-128">All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage.</span></span> <span data-ttu-id="1a8f2-129">Here's how that data is secured:</span><span class="sxs-lookup"><span data-stu-id="1a8f2-129">Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="1a8f2-130">All content is encrypted, potentially with multiple keys, and distributed across the datacenter.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-130">All content is encrypted, potentially with multiple keys, and distributed across the datacenter.</span></span> <span data-ttu-id="1a8f2-131">Each file to be stored is broken into one or more chunks, depending its size.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-131">Each file to be stored is broken into one or more chunks, depending its size.</span></span> <span data-ttu-id="1a8f2-132">Then, each chunk is encrypted using its own unique key.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-132">Then, each chunk is encrypted using its own unique key.</span></span> <span data-ttu-id="1a8f2-133">Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-133">Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="1a8f2-134">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-134">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store.</span></span> <span data-ttu-id="1a8f2-135">They also are randomly distributed across multiple blob containers.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-135">They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="1a8f2-136">用來從其元件中重新組合檔案的「地圖」則儲存在內容資料庫中。</span><span class="sxs-lookup"><span data-stu-id="1a8f2-136">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="1a8f2-137">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete).</span><span class="sxs-lookup"><span data-stu-id="1a8f2-137">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete).</span></span> <span data-ttu-id="1a8f2-138">Each set of credentials is held in the secure Key Store and is regularly refreshed.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-138">Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="1a8f2-139">換句話說，每一檔案靜態加密都包含三種不同的儲存類型，每個類型都有不同的功能：</span><span class="sxs-lookup"><span data-stu-id="1a8f2-139">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="1a8f2-140">Content is stored as encrypted blobs in the blob store.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-140">Content is stored as encrypted blobs in the blob store.</span></span> <span data-ttu-id="1a8f2-141">The key to each chunk of content is encrypted and stored separately in the content database.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-141">The key to each chunk of content is encrypted and stored separately in the content database.</span></span> <span data-ttu-id="1a8f2-142">The content itself holds no clue as to how it can be decrypted.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-142">The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="1a8f2-143">The Content Database is a SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-143">The Content Database is a SQL Server database.</span></span> <span data-ttu-id="1a8f2-144">It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-144">It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="1a8f2-145">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-145">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate.</span></span> <span data-ttu-id="1a8f2-146">The information held in any one of the components is unusable on its own.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-146">The information held in any one of the components is unusable on its own.</span></span> <span data-ttu-id="1a8f2-147">This provides an unprecedented level of security.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-147">This provides an unprecedented level of security.</span></span> <span data-ttu-id="1a8f2-148">Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span><span class="sxs-lookup"><span data-stu-id="1a8f2-148">Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>
