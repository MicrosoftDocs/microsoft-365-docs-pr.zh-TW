---
title: Office 365 影片中的租用戶隔離
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
f1.keywords:
- NOCSH
description: 在本文中，將說明租使用者隔離如何將每個租使用者的儲存影片分別保留在 Office 365 影片中。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 626a995fc5a3ac971c48cc87bec1017134e87b88
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332241"
---
# <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="00332-103">Office 365 影片中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="00332-103">Tenant Isolation in Office 365 Video</span></span>

> [!NOTE]
> <span data-ttu-id="00332-104">Office 365 影片將會由 Microsoft Stream 取代。</span><span class="sxs-lookup"><span data-stu-id="00332-104">Office 365 Video will be replaced by Microsoft Stream.</span></span> <span data-ttu-id="00332-105">若要深入瞭解將智慧加入影片共同作業的新企業影片服務，並瞭解目前 Microsoft 365 影片客戶的過渡計畫，請參閱 [Office 365 video 中轉至 Microsoft Stream](https://docs.microsoft.com/stream/migrate-from-office-365)。</span><span class="sxs-lookup"><span data-stu-id="00332-105">To learn more about the new enterprise video service that adds intelligence to video collaboration and learn about the transition plans for current Microsoft 365 Video customers, see [Office 365 Video transition to Microsoft Stream overview](https://docs.microsoft.com/stream/migrate-from-office-365).</span></span>

## <a name="introduction"></a><span data-ttu-id="00332-106">簡介</span><span class="sxs-lookup"><span data-stu-id="00332-106">Introduction</span></span>

<span data-ttu-id="00332-107">Azure 儲存體用來儲存多個 Office 365 服務的資料，包括 Office 365 影片和 Sway。</span><span class="sxs-lookup"><span data-stu-id="00332-107">Azure Storage is used to store data for multiple Office 365 services, including Office 365 Video and Sway.</span></span> <span data-ttu-id="00332-108">Azure 儲存體包含 Blob 儲存區，也就是用來儲存非結構化資料的高擴充性、REST 型雲端物件存放區。</span><span class="sxs-lookup"><span data-stu-id="00332-108">Azure Storage includes Blob storage, which is a highly-scalable, REST-based, cloud object store that is used for storing unstructured data.</span></span> <span data-ttu-id="00332-109">Azure 儲存體使用簡易的存取控制模型;每個 Azure 訂閱可以建立一或多個儲存帳戶。</span><span class="sxs-lookup"><span data-stu-id="00332-109">Azure Storage uses a simple access control model; each Azure subscription can create one or more Storage Accounts.</span></span> <span data-ttu-id="00332-110">每個儲存帳戶都有單一私密金鑰，用來控制對該儲存體帳戶中所有資料的存取。</span><span class="sxs-lookup"><span data-stu-id="00332-110">Each Storage Account has a single secret key that is used to control access to all data in that Storage Account.</span></span> <span data-ttu-id="00332-111">這支援與應用程式相關聯的儲存體，而且這些應用程式可完全控制其相關聯的資料;例如，Sway 將內容儲存在 Azure 儲存體中。</span><span class="sxs-lookup"><span data-stu-id="00332-111">This supports the typical scenario where storage is associated with applications and those applications have full control over their associated data; for example, Sway storing content in Azure Storage.</span></span> <span data-ttu-id="00332-112">Sway 的所有客戶內容都儲存在共用的 Azure 儲存體帳戶中。</span><span class="sxs-lookup"><span data-stu-id="00332-112">All customer content for Sway is stored in shared Azure storage accounts.</span></span> <span data-ttu-id="00332-113">每個使用者的內容位於 Azure storage 中個別的 blob 目錄樹中。</span><span class="sxs-lookup"><span data-stu-id="00332-113">Each user's content is in a separate directory tree of blobs in Azure storage.</span></span>

<span data-ttu-id="00332-114">管理客戶環境存取權的系統 (例如，Azure 入口網站、SMAPI 等 ) 會在 Microsoft 所運作的 Azure 應用程式內隔離。</span><span class="sxs-lookup"><span data-stu-id="00332-114">The systems managing access to customer environments (e.g., the Azure Portal, SMAPI, etc.) are isolated within an Azure application operated by Microsoft.</span></span> <span data-ttu-id="00332-115">這會以邏輯方式將客戶存取基礎結構與客戶應用程式和儲存層分隔開來。</span><span class="sxs-lookup"><span data-stu-id="00332-115">This logically separates the customer access infrastructure from the customer applications and storage layer.</span></span>

## <a name="tenant-isolation-in-office-365-video"></a><span data-ttu-id="00332-116">Office 365 影片中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="00332-116">Tenant Isolation in Office 365 Video</span></span>

<span data-ttu-id="00332-117">[Office 365 影片](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) 是一個企業入口網站，可提供組織，以高安全性組織的目標，以進行電子公告、共用及探索影片內容。</span><span class="sxs-lookup"><span data-stu-id="00332-117">[Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) is an enterprise portal that provides organizations with a highly secure, organization-wide destination for posting, sharing, and discovering video content.</span></span> <span data-ttu-id="00332-118">在 Office 365 影片中，每個租使用者的影片都會在所有位置保持隔離和加密，而且只有具有組織影片存取權和許可權的已驗證使用者可以使用這些影片。</span><span class="sxs-lookup"><span data-stu-id="00332-118">In Office 365 Video, each tenant's videos are kept isolated and encrypted in all locations, and are only available to authenticated users that have access and permissions to the organization's videos.</span></span> <span data-ttu-id="00332-119">Office 365 影片使用技術組合來達成此目的：</span><span class="sxs-lookup"><span data-stu-id="00332-119">Office 365 Video uses a combination of technologies to accomplish this:</span></span>

- <span data-ttu-id="00332-120">線上 SharePoint 用來儲存影片檔及中繼資料 (影片標題、描述等等 ) 。</span><span class="sxs-lookup"><span data-stu-id="00332-120">SharePoint Online is used for storing the video file and metadata (video title, description, etc.).</span></span> <span data-ttu-id="00332-121">它也會提供安全性與合規性層 (，包括驗證) 和搜尋功能。</span><span class="sxs-lookup"><span data-stu-id="00332-121">It also provides the security and compliance layer (including authentication), and search features.</span></span>
- <span data-ttu-id="00332-122">Azure 媒體服務提供轉碼、適應性流式處理、使用 AES 加密) 的安全傳遞 (，以及縮圖功能。</span><span class="sxs-lookup"><span data-stu-id="00332-122">Azure Media Services provides transcoding, adaptive streaming, secure delivery (using AES encryption), and thumbnail features.</span></span>

<span data-ttu-id="00332-123">[Azure 媒體服務](https://azure.microsoft.com/services/media-services/) 是一種平臺即服務，可在雲端啟用端對端媒體工作流程。</span><span class="sxs-lookup"><span data-stu-id="00332-123">[Azure Media Services](https://azure.microsoft.com/services/media-services/) is a platform-as-a-service offering for enabling end-to-end media workflows in the cloud.</span></span> <span data-ttu-id="00332-124">此平臺提供 REST API，以利用 PlayReady) 進行上傳、編碼、加密 (，以及透過全球的 Azure 資料中心傳遞媒體。</span><span class="sxs-lookup"><span data-stu-id="00332-124">The platform provides a REST API for uploading, encoding, encrypting (with PlayReady), and delivery of media through Azure datacenters around the world.</span></span>

<span data-ttu-id="00332-125">所有上傳的 Office 365 影片都會透過 HTTPS 進行。</span><span class="sxs-lookup"><span data-stu-id="00332-125">All uploads for Office 365 Video occur via HTTPS.</span></span> <span data-ttu-id="00332-126">當上載影片檔時，它會儲存在 SharePoint 線上，而且檔案的副本會透過加密通道傳送至 Azure 媒體服務。</span><span class="sxs-lookup"><span data-stu-id="00332-126">When a video file is uploaded, it is stored in SharePoint Online, and a copy of the file is sent via an encrypted channel to Azure Media Services.</span></span> <span data-ttu-id="00332-127">Azure 媒體服務會將影片 transcodes 成多種格式，以針對觀賞體驗 (例如行動、低頻寬、高頻寬等 ) 進行優化。</span><span class="sxs-lookup"><span data-stu-id="00332-127">Azure Media Services transcodes the video into multiple formats that are optimized for viewing experience (e.g., mobile, low-bandwidth, high-bandwidth, etc.).</span></span> <span data-ttu-id="00332-128">這些檔案和上傳時所取得的原始檔案，都是儲存在 Azure Blob 儲存區中。</span><span class="sxs-lookup"><span data-stu-id="00332-128">These files, along with the original file acquired during upload, are stored in Azure Blob storage.</span></span> <span data-ttu-id="00332-129">使用每個 MPEG 通用加密封裝演算法 (或舊版 PlayReady 版本) 進行播放，然後在儲存至 Azure Blob 儲存區之前，使用 AES 256 儲存量加密，以 AES 128 加密檔。</span><span class="sxs-lookup"><span data-stu-id="00332-129">The files are encrypted using AES 128 per the MPEG Common Encryption packaging algorithm (or an earlier PlayReady version) for playback, and encrypted using AES 256 storage encryption before being stored in Azure Blob storage.</span></span> <span data-ttu-id="00332-130"> (使用 Azure 媒體服務用戶端 SDK，客戶可以控制使用哪些加密。</span><span class="sxs-lookup"><span data-stu-id="00332-130">(Using the Azure Media Services Client SDK, customers can control which encryption is used.</span></span> <span data-ttu-id="00332-131">例如，在上傳 it Azure Blob 儲存裝置之前，客戶可以套用 Azure 媒體服務儲存加密 (AES 256) 到高價值媒體資產。 ) </span><span class="sxs-lookup"><span data-stu-id="00332-131">For example, a customer could apply Azure Media Services storage encryption (AES 256) to a high-value media asset before uploading it Azure Blob storage.)</span></span>

<span data-ttu-id="00332-132">Azure 媒體服務也會產生影片的縮圖，它會隨同縮圖中繼資料一起傳送，以透過加密通道 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="00332-132">Azure Media Services also generates a thumbnail for the video, which it transmits along with thumbnail metadata to SharePoint Online via an encrypted channel.</span></span>
