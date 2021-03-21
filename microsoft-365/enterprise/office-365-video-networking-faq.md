---
title: Office 365 影片的常見問題
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: 在頻寬規劃、加密 & 服務利用內容傳遞網路 (Cdn) 的方式，尋找一些常見問題的答案。
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921567"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a><span data-ttu-id="2ed5b-103">Office 365 影片的常見問題</span><span class="sxs-lookup"><span data-stu-id="2ed5b-103">Office 365 Video networking Frequently Asked Questions</span></span>

<span data-ttu-id="2ed5b-104">Office 365 影片存放庫及流式處理服務可讓組織內的儲存及流式處理影片輕鬆。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-104">The Office 365 Video repository and streaming services make storing and streaming videos within your organization simple.</span></span> <span data-ttu-id="2ed5b-105">[有關 Office 365 影片](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)的許多重要資訊，請這種網路常見問題的設計是針對頻寬規劃、加密，以及服務利用[內容傳遞網路](content-delivery-networks.md) (cdn) 的最常見問題進行解答。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-105">There's a lot of great [information about Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50); this networking FAQ is designed to answer the most common questions around bandwidth planning, encryption, and how the service leverages [Content Delivery Networks](content-delivery-networks.md) (CDNs).</span></span>
  
<span data-ttu-id="2ed5b-106">如果您還沒有完全瞭解影片上載或播放的方式，請參閱這段影片：我們將影片放在一起，將 [影片檔上傳至 Office 365 影片時會發生什麼情況](https://www.youtube.com/watch?v=HXSZ0jYBKlM)。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-106">If you don't already have a thorough understanding of what happens when a video is uploaded or played back, have a look at this video we put together, [What happens to a video file when uploaded to Office 365 Video](https://www.youtube.com/watch?v=HXSZ0jYBKlM).</span></span>
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a><span data-ttu-id="2ed5b-107">Office 365 的影片頻寬需求為何？</span><span class="sxs-lookup"><span data-stu-id="2ed5b-107">What are the Office 365 Video bandwidth requirements?</span></span>

<span data-ttu-id="2ed5b-108">有許多支援的 [影片格式](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) 可上傳至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-108">There are a numerous [supported video formats](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) that can be uploaded to Office 365.</span></span> <span data-ttu-id="2ed5b-109">然後，會將每個影片檔編碼為具有多種不同影片品質的標準格式，以供播放。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-109">Each video file is then encoded to a standard format with several different video qualities for playback.</span></span> <span data-ttu-id="2ed5b-110">Office 365 影片使用自我調整高位元速率資料流程，根據可用的網路頻寬和影片大小，選取最佳的影片播放品質。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-110">Office 365 Video uses adaptive bitrate streaming to select the best video playback quality based on the available network bandwidth and size of the video player.</span></span> <span data-ttu-id="2ed5b-111">若要這麼做，播放者最初會要求最低的播放品質。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-111">To do this, the player initially requests the lowest playback quality.</span></span> <span data-ttu-id="2ed5b-112">然後，此服務會開始傳送2秒的影片片段到影片播放機。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-112">The service then begins sending 2-second video segments to the video player.</span></span> <span data-ttu-id="2ed5b-113">然後，播放機便可根據每次傳遞每個片段的速度來要求較高或較低的播放品質。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-113">The player can then request higher or lower playback quality based on how quickly each segment is delivered.</span></span>
  
<span data-ttu-id="2ed5b-114">自我調整高位元速率流式處理會在後臺執行，但播放頻率最少的中斷或緩衝。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-114">The adaptive bitrate streaming does all this in the background while the video plays with the least amount of disruption or buffering.</span></span> <span data-ttu-id="2ed5b-115">在影片播放期間，影片播放機可讓 viewer 手動覆寫自動播放品質，以選取特定的影片播放品質。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-115">During video playback, the video player allows the viewer to manually override the automatic playback quality, to select a specific video playback quality.</span></span>
  
<span data-ttu-id="2ed5b-116">以下是概述每個影片播放品質之網路需求的快速表格。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-116">Here's a quick table that outlines the network requirements for each of the video playback qualities.</span></span> <span data-ttu-id="2ed5b-117">播放影片所需的每個人最小頻寬是802Kbps。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-117">The minimum bandwidth per person needed to play a video is 802Kbps.</span></span>
  
| <span data-ttu-id="2ed5b-118">播放品質</span><span class="sxs-lookup"><span data-stu-id="2ed5b-118">Playback Quality</span></span> | <span data-ttu-id="2ed5b-119">網路速度</span><span class="sxs-lookup"><span data-stu-id="2ed5b-119">Network Speed</span></span> |
|:-----|:-----|
|<span data-ttu-id="2ed5b-120">288p</span><span class="sxs-lookup"><span data-stu-id="2ed5b-120">288p</span></span>  <br/> |<span data-ttu-id="2ed5b-121">802Kbps</span><span class="sxs-lookup"><span data-stu-id="2ed5b-121">802Kbps</span></span>  <br/> |
|<span data-ttu-id="2ed5b-122">360p</span><span class="sxs-lookup"><span data-stu-id="2ed5b-122">360p</span></span>  <br/> |<span data-ttu-id="2ed5b-123">1.2 Mbps</span><span class="sxs-lookup"><span data-stu-id="2ed5b-123">1.2 Mbps</span></span>  <br/> |
|<span data-ttu-id="2ed5b-124">576p</span><span class="sxs-lookup"><span data-stu-id="2ed5b-124">576p</span></span>  <br/> |<span data-ttu-id="2ed5b-125">2.5 Mbps</span><span class="sxs-lookup"><span data-stu-id="2ed5b-125">2.5 Mbps</span></span>  <br/> |
|<span data-ttu-id="2ed5b-126">720p</span><span class="sxs-lookup"><span data-stu-id="2ed5b-126">720p</span></span>  <br/> |<span data-ttu-id="2ed5b-127">3.8 Mbps</span><span class="sxs-lookup"><span data-stu-id="2ed5b-127">3.8 Mbps</span></span>  <br/> |

<span data-ttu-id="2ed5b-128"> ([回到頁首](office-365-video-networking-faq.md)) </span><span class="sxs-lookup"><span data-stu-id="2ed5b-128">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a><span data-ttu-id="2ed5b-129">內容傳遞網路如何 (Cdn) 協助影片播放？</span><span class="sxs-lookup"><span data-stu-id="2ed5b-129">How do Content Delivery Networks (CDNs) help video playback?</span></span>

<span data-ttu-id="2ed5b-130">如果相同地理位置內來自相同組織的多個人員已使用相同的影片 (s) 中，則 Cdn 會將這些影片的副本儲存在距離該地理區域更近的位置。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-130">If several people from the same organization within the same geographic location are streaming the same video(s), CDNs will store a copy of these videos in a location closer to that geographic region.</span></span> <span data-ttu-id="2ed5b-131">在儲存的影片上，或快取至最接近的位置時，每個人會從最接近的位置，而不是從遠處的位置流向影片。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-131">With the video stored, or cached at the closest location, each person streams the video from the location closest to them instead of a location further away.</span></span> <span data-ttu-id="2ed5b-132">Office 365 影片使用 Azure 媒體服務來管理 Azure Cdn 中快取的內容，以及多長的時間。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-132">Office 365 Video uses Azure Media Services to manage what is cached in the Azure CDNs, and for how long.</span></span> <span data-ttu-id="2ed5b-133">Azure 媒體服務可使用任何 [AZURE CDN 位置](/azure/cdn/cdn-pop-locations) ，將影片片段和資訊清單快取幾天。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-133">Azure Media Services can use any of the [Azure CDN locations](/azure/cdn/cdn-pop-locations) to cache video fragments and manifests for a few days.</span></span> <span data-ttu-id="2ed5b-134">如果您組織中的人員繼續觀賞快取的快取影片。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-134">If people in your organization continue to watch the cached videos they'll stay in the cache.</span></span> <span data-ttu-id="2ed5b-135">如果沒有人存取影片一天內，則會最後從快取中刪除影片。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-135">If no one accesses the video for several days, the video will eventually drop be dropped from the cache.</span></span> <span data-ttu-id="2ed5b-136">下一次有人嘗試觀賞影片時，它會再次快取到最近的 CDN 位置。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-136">The next time someone attempts to watch the video it's once again cached at the nearest CDN location.</span></span>
  
<span data-ttu-id="2ed5b-137">在內容快取時，嘗試觀賞影片的每個人都會從影片中快取較近的位置，而在大多數情況下則不會有較低的躍點。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-137">Everyone who attempts to watch the video while the content is cached at a nearby CDN benefits from the video being closer, and in most cases less hops, away.</span></span> <span data-ttu-id="2ed5b-138">這會改善影片播放速度;不過，它不會變更網路需求以播放影片。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-138">This improves video playback speed; however, it doesn't change the network requirement to play the video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2ed5b-139">在某些情況下（例如，我們已達到容量限制），在達到三天之後可能會移除影片。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-139">There are some circumstances, such as our capacity limit being reached, where the video may be removed before the three days has been reached.</span></span>
  
<span data-ttu-id="2ed5b-140"> ([回到頁首](office-365-video-networking-faq.md)) </span><span class="sxs-lookup"><span data-stu-id="2ed5b-140">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a><span data-ttu-id="2ed5b-141">我是否可以在本機快取影片以取得更快的播放功能？</span><span class="sxs-lookup"><span data-stu-id="2ed5b-141">Can I cache the videos locally for faster playback?</span></span>

<span data-ttu-id="2ed5b-142">是。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-142">Yes.</span></span> <span data-ttu-id="2ed5b-143">Office 365 不會防止您使用本機 CDN 或快取 proxy 將影片或其他 Office 365 內容帶入您的本機網路，以加快存取速度。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-143">Office 365 won't prevent you from using a local CDN or a caching proxy to bring video or other Office 365 content into your local network for faster access.</span></span> <span data-ttu-id="2ed5b-144">有幾種方式可以在您的網路上實施本機快取解決方案，最常用的方法是使用可在本機快取內容的 proxy 解決方案。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-144">There are several ways to implement a local caching solution on your network, the most common method is to use a proxy solution that caches content locally.</span></span> <span data-ttu-id="2ed5b-145">當 proxy 或私人 CDN 快取了影片片段和資訊清單之後，對透過 proxy 或私人 CDN 路由傳送的檔案，以後的要求會從本機快取中取出，而不是從網際網路位置提取。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-145">Once a proxy or private CDN has cached the video fragments and manifests, future requests for those files that route through the proxy or private CDN are pulled from the local cache and not pulled from an internet location.</span></span> <span data-ttu-id="2ed5b-146">在規劃像這樣的解決方案時，請考慮網路頻寬、容量和影片播放併發性。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-146">Consider network bandwidth, capacity, and video playback concurrency during the planning of a solution like this.</span></span>
  
<span data-ttu-id="2ed5b-147"> ([回到頁首](office-365-video-networking-faq.md)) </span><span class="sxs-lookup"><span data-stu-id="2ed5b-147">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-videos-are-encrypted-and-secured"></a><span data-ttu-id="2ed5b-148">如何加密及保護影片的方式？</span><span class="sxs-lookup"><span data-stu-id="2ed5b-148">How videos are encrypted and secured?</span></span>

<span data-ttu-id="2ed5b-149">Office 365 影片知道保護資料安全和私人的重要程度。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-149">Office 365 Video knows how important it is to keep your data secure and private.</span></span> <span data-ttu-id="2ed5b-150">[Microsoft 信任中心](https://products.office.com/business/office-365-trust-center-welcome) 描述我們對內容隱私權和安全性的承諾。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-150">[Microsoft Trust Center](https://products.office.com/business/office-365-trust-center-welcome) describes our commitment to the privacy and security of your content.</span></span> <span data-ttu-id="2ed5b-151">透過影片播放，速度對於良好的經驗很重要;不過，我們並未以 exchange 為速度降低您的安全性或隱私權。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-151">With video playback, speed is important for a good experience; however, we don't compromise your security or privacy in exchange for speed.</span></span> <span data-ttu-id="2ed5b-152">以下是我們如何適應速度、安全性和隱私權。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-152">Here's how we accommodate speed, security and privacy.</span></span>
  
<span data-ttu-id="2ed5b-153">當您或貴組織中的人員上傳新影片時，該影片會 transcoded、加密 AES-128 加密，並儲存在 Azure Media Services 中。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-153">When you or someone in your organization uploads a new video, that video is transcoded, encrypted with AES-128 encryption, and stored in Azure Media Services.</span></span> <span data-ttu-id="2ed5b-154">這表示影片會在傳輸和靜止時加密。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-154">This means the videos are encrypted both in transit and at rest.</span></span>
  
<span data-ttu-id="2ed5b-155">當您組織中的某人嘗試觀賞新影片時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2ed5b-155">When someone in your organization attempts to watch a new video, they follow these steps:</span></span>
  
1. <span data-ttu-id="2ed5b-156">如果他們具有查看影片的許可權，請詢問 SharePoint 線上。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-156">Ask SharePoint Online if they have permission to view the video.</span></span>

2. <span data-ttu-id="2ed5b-157">線上 SharePoint 會使用檔案許可權來判斷人員是否可以收看影片。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-157">SharePoint Online uses the file permissions to determine if the person can watch the video.</span></span>

3. <span data-ttu-id="2ed5b-158">如果允許，SharePoint 線上從 Azure 檢索權杖，以提供給影片播放機。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-158">If they're allowed, SharePoint Online retrieves a token from Azure to give to the video player.</span></span>

4. <span data-ttu-id="2ed5b-159">然後，影片播放機會使用權杖從 Azure 要求解密金鑰。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-159">The video player then uses the token to request the decryption key from Azure.</span></span>

5. <span data-ttu-id="2ed5b-160">使用「解密金鑰」時，影片播放機便可以對流進行播放。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-160">With the decryption key in hand, the video player is able to stream the video.</span></span>

![O365 影片播放](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
<span data-ttu-id="2ed5b-162"> ([回到頁首](office-365-video-networking-faq.md)) </span><span class="sxs-lookup"><span data-stu-id="2ed5b-162">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a><span data-ttu-id="2ed5b-163">播放 Office 365 影片的需求為何？</span><span class="sxs-lookup"><span data-stu-id="2ed5b-163">What are the requirements to playback Office 365 Video?</span></span>

<span data-ttu-id="2ed5b-164">Office 365 影片支援的作業系統和網頁瀏覽器與 [office 365 系統需求](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45)的 SharePoint 線上需求相同。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-164">Office 365 Video supported operating systems and web browsers are the same as the SharePoint Online requirements in [Office 365 system requirements](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45).</span></span> <span data-ttu-id="2ed5b-165">根據您所擁有的作業系統和網頁瀏覽器設定，會決定影片播放機的特定需求。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-165">Depending on which operating system and web browser configuration you have will determine the specific needs of the video player.</span></span> <span data-ttu-id="2ed5b-166">以下是有關 [影片播放需求](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-166">Here's more information on [video playback requirements](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).</span></span>
  
<span data-ttu-id="2ed5b-167"> ([回到頁首](office-365-video-networking-faq.md)) </span><span class="sxs-lookup"><span data-stu-id="2ed5b-167">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a><span data-ttu-id="2ed5b-168">我無法讓 Office 365 影片正常運作，我應該從何處開始？</span><span class="sxs-lookup"><span data-stu-id="2ed5b-168">I can't get Office 365 video to work, where should I start?</span></span>

<span data-ttu-id="2ed5b-169">疑難排解 Office 365 影片的連線問題包括疑難排解您的網路、您的 ISP (s) ，以及您設定的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-169">Troubleshooting connectivity to Office 365 Video involves troubleshooting your network, your ISP(s), and your configuration of Office 365.</span></span> <span data-ttu-id="2ed5b-170">開始的第一個位置是服務健康情況儀表板。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-170">The first place to start is the service health dashboard.</span></span> <span data-ttu-id="2ed5b-171">這會告訴您 Office 365 影片有問題。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-171">This will tell you of Office 365 Video is having a problem or not.</span></span> <span data-ttu-id="2ed5b-172">如果一切看起來很不錯，以下是一些額外的資源可協助您。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-172">If everything looks great there, here's some additional resources to help you.</span></span>
  
- <span data-ttu-id="2ed5b-173">請確定您可以連線到 [Office 365 影片所需的網路端點](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-173">Make sure you can connect to the [network endpoints required for Office 365 Video](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

- <span data-ttu-id="2ed5b-174">使用 [Office 365 網路疑難排解指南](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)，檢查您的網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-174">Check your network connectivity using our [Office 365 network troubleshooting guide](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).</span></span>

- <span data-ttu-id="2ed5b-175">請參閱我們 [在慢速網路上使用 Office 365 的最佳作法](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-175">See our [best practices for using Office 365 on a slow network](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span>

- <span data-ttu-id="2ed5b-176">[尋找有關 Office 365 影片](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)設定的說明。</span><span class="sxs-lookup"><span data-stu-id="2ed5b-176">[Find help about Office 365 Video configuration](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).</span></span>

<span data-ttu-id="2ed5b-177"> ([回到頁首](office-365-video-networking-faq.md)) </span><span class="sxs-lookup"><span data-stu-id="2ed5b-177">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="office-365-video-resources"></a><span data-ttu-id="2ed5b-178">Office 365 影片資源</span><span class="sxs-lookup"><span data-stu-id="2ed5b-178">Office 365 Video resources</span></span>

<span data-ttu-id="2ed5b-179">以下是協助您成功部署和使用 Office 365 影片的其他一些資源：</span><span class="sxs-lookup"><span data-stu-id="2ed5b-179">Here's a few other resources to help you successfully deploy and use Office 365 Video:</span></span>
  
[<span data-ttu-id="2ed5b-180">尋找 Office 365 影片設定的說明</span><span class="sxs-lookup"><span data-stu-id="2ed5b-180">Find help about Office 365 Video configuration</span></span>](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[<span data-ttu-id="2ed5b-181">符合 Office 365 影片</span><span class="sxs-lookup"><span data-stu-id="2ed5b-181">Meet Office 365 Video</span></span>](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[<span data-ttu-id="2ed5b-182">在 Office 365 影片中建立及管理通道</span><span class="sxs-lookup"><span data-stu-id="2ed5b-182">Create and manage a channel in Office 365 Video</span></span>](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[<span data-ttu-id="2ed5b-183">管理 Office 365 影片入口網站</span><span class="sxs-lookup"><span data-stu-id="2ed5b-183">Manage your Office 365 Video portal</span></span>](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[<span data-ttu-id="2ed5b-184">在 Office 365 影片中運作的影片格式</span><span class="sxs-lookup"><span data-stu-id="2ed5b-184">Video formats that work in Office 365 Video</span></span>](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
<span data-ttu-id="2ed5b-185"> ([回到頁首](office-365-video-networking-faq.md)) </span><span class="sxs-lookup"><span data-stu-id="2ed5b-185">([Back to top](office-365-video-networking-faq.md))</span></span>
  
<span data-ttu-id="2ed5b-186">您可以使用下列短連結返回這裡：[https://aka.ms/video365networkfaq]()</span><span class="sxs-lookup"><span data-stu-id="2ed5b-186">Here's a short link you can use to come back: [https://aka.ms/video365networkfaq]()</span></span>