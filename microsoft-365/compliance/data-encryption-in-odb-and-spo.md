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
ms.openlocfilehash: e882bf3bf633c821fe50246316b5b1065cfa4693
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633338"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="989b5-103">商務用 OneDrive 和 SharePoint Online 中的資料加密</span><span class="sxs-lookup"><span data-stu-id="989b5-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="989b5-104">了解 OneDrive for Business 和 SharePoint Online 中的資料安全性加密基本項目。</span><span class="sxs-lookup"><span data-stu-id="989b5-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="overview"></a><span data-ttu-id="989b5-105">概觀</span><span class="sxs-lookup"><span data-stu-id="989b5-105">Overview</span></span>

<span data-ttu-id="989b5-106">Microsoft 365 是高度安全的環境，可提供多層的廣泛保護：實體資料中心安全性、網路安全性、存取安全性、應用程式安全性和資料安全性。</span><span class="sxs-lookup"><span data-stu-id="989b5-106">Microsoft 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security.</span></span> <span data-ttu-id="989b5-107">本文特別著重在OneDrive for Business 和 SharePoint Online 的傳輸中和靜態加密等方面。</span><span class="sxs-lookup"><span data-stu-id="989b5-107">This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="989b5-108">如需 Microsoft 365 安全性整體的說明，請參閱[安全性白皮書](https://go.microsoft.com/fwlink/p/?LinkId=270895)。</span><span class="sxs-lookup"><span data-stu-id="989b5-108">For a description of Microsoft 365 security as a whole, see [Security White Paper](https://go.microsoft.com/fwlink/p/?LinkId=270895).</span></span>
  
<span data-ttu-id="989b5-109">觀看下列影片，了解資料加密如何運作。</span><span class="sxs-lookup"><span data-stu-id="989b5-109">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="989b5-110">傳輸中資料的加密</span><span class="sxs-lookup"><span data-stu-id="989b5-110">Encryption of data in transit</span></span>

<span data-ttu-id="989b5-111">在OneDrive for Business 和 SharePoint Online 中，資料進出資料中心的方式有兩種。</span><span class="sxs-lookup"><span data-stu-id="989b5-111">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="989b5-p102">**用戶端與伺服器通訊** 在網際網路上使用 SSL/TLS 連線與OneDrive for Business 通訊。所有 SSL 連線都是使用 2048 位元機碼加以建立。</span><span class="sxs-lookup"><span data-stu-id="989b5-p102">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="989b5-p103">**在資料中心間移動資料** 在資料中心間移動資料的主要原因是為了讓異地複寫進行災害復原。例如，SQL Server交易記錄和 Blob 儲存體差異會隨時此管道流動。若己使用私人網路傳輸資料，則系統會進一步以業界領先的加密方式保護資料。</span><span class="sxs-lookup"><span data-stu-id="989b5-p103">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="989b5-117">靜態資料的加密</span><span class="sxs-lookup"><span data-stu-id="989b5-117">Encryption of data at rest</span></span>

<span data-ttu-id="989b5-118">靜態加密包括兩個元件：BitLocker 磁碟層級加密，以及客戶內容的每一檔案加密。</span><span class="sxs-lookup"><span data-stu-id="989b5-118">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="989b5-119">服務針對OneDrive for Business 和 SharePoint Online 部署了 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="989b5-119">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="989b5-120">在 Microsoft 365 多承租人和以多承租人技術為基礎的新專用環境中 SharePoint，每個檔案加密也是在商務用 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="989b5-120">Per-file encryption is also in OneDrive for Business and SharePoint Online in Microsoft 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="989b5-p105">當 BitLocker 加密磁碟中的所有資料時，每一檔案的加密會進一步地納入每個檔案唯一的加密金鑰。此外，每個檔案的每次更新都會使用自己的加密金鑰進行加密。在儲存之前，已加密內容的金鑰會儲存在與內容不同的實體位置。此加密的每個步驟都會使用搭配 256 位元機碼的進階加密標準 (AES)，並與聯邦資訊處理標準 (FIPS) 140-2 相容。已加密的內容會分散到資料中心的數個容器中，而且每個容器都有唯一的認證。這些認證會儲存在內容或內容金鑰等不同的實體位置。</span><span class="sxs-lookup"><span data-stu-id="989b5-p105">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="989b5-127">如需有關 FIPS 140-2 規範的詳細資訊，請參閱[FIPS 140-2 相容性](https://go.microsoft.com/fwlink/?LinkId=517625)。</span><span class="sxs-lookup"><span data-stu-id="989b5-127">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="989b5-p106">檔案層級的靜態加密會利用 Blob 儲存體提供無限制的虛擬儲存體成長空間，以便提供更全面的保護。OneDrive for Business 和 SharePoint Online 中的所有客戶內容都會移轉至 Blob 儲存體。以下是保護資料的方法：</span><span class="sxs-lookup"><span data-stu-id="989b5-p106">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="989b5-p107">所有內容都會以多個金鑰加密，並分散到資料中心。每個要儲存的檔案都會依大小分成一或多個區塊。接著，每個區塊都會使用自己唯一的金鑰加密。也會以相同的方式處理更新：由使用者提交的變更集或差異項目都會分成數個區塊，每個區塊都會以自己的金鑰加密。</span><span class="sxs-lookup"><span data-stu-id="989b5-p107">All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="989b5-p108">所有這些區塊包括檔案、檔案片段及更新差異項目都會在我們的 Blob 存放區中儲存為 Blob。這些區塊也會隨機地分散至多個 Blob 容器中。</span><span class="sxs-lookup"><span data-stu-id="989b5-p108">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="989b5-137">用來從其元件中重新組合檔案的「地圖」則儲存在內容資料庫中。</span><span class="sxs-lookup"><span data-stu-id="989b5-137">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="989b5-p109">每個 Blob 容器中的存取類型 (包括讀取、寫入、列舉及刪除) 都有自己特有的認證。每個認證集都會保留在安全的金鑰存放區中，且會定期重新整理。</span><span class="sxs-lookup"><span data-stu-id="989b5-p109">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="989b5-140">換句話說，每一檔案靜態加密都包含三種不同的儲存類型，每個類型都有不同的功能：</span><span class="sxs-lookup"><span data-stu-id="989b5-140">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="989b5-p110">內容會在 Blob 存放區中儲存為已加密 Blob。每個內容區塊的金鑰都會加密，且分別儲存在內容資料庫中。內容本身不會保留任何解密線索。</span><span class="sxs-lookup"><span data-stu-id="989b5-p110">Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="989b5-p111">內容資料庫是 SQL Server 資料庫，它會保留一份地圖，以便尋找並重新組合 Blob 存放庫中保留的所有內容 Blob，以及解密這些 Blob 所需的金鑰。</span><span class="sxs-lookup"><span data-stu-id="989b5-p111">The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="989b5-p112">Blob 存放區、內容資料庫以及金鑰存放區等三種儲存體元件都位於不同的實體位置，而這些元件中保留的資訊其本身均無法使用。如此提供了前所未有的安全性層級。若非存取這三種元件，則無法擷取區塊的金鑰、也無法將金鑰解密以供使用；無法將金鑰與其對應的區塊相關聯，也無法從其組成的區塊中重新建構文件。</span><span class="sxs-lookup"><span data-stu-id="989b5-p112">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>
