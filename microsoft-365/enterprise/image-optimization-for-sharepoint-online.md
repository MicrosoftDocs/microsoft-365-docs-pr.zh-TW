---
title: SharePoint 線上傳統發佈網站的影像優化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: 瞭解如何使用格式副本及子畫面，以提升 SharePoint 線上傳統發佈網站上的影像效能。
ms.openlocfilehash: 0f0dd078ce28b86fc998b2f83ac19d04b1a3ab02
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907477"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a><span data-ttu-id="ce82d-103">SharePoint 線上傳統發佈網站的影像優化</span><span class="sxs-lookup"><span data-stu-id="ce82d-103">Image optimization for SharePoint Online classic publishing sites</span></span>

<span data-ttu-id="ce82d-104">網頁的載入速度取決於轉譯頁面（包括影像、HTML、JavaScript 及 CSS）所需之所有元件的組合大小。</span><span class="sxs-lookup"><span data-stu-id="ce82d-104">The loading speed of a webpage depends on the combined size of all the components required to render the page including images, HTML, JavaScript, and CSS.</span></span> <span data-ttu-id="ce82d-105">影像是讓您的網站更有吸引力，但其大小可能會影響效能的極佳方式。</span><span class="sxs-lookup"><span data-stu-id="ce82d-105">Images are a great way to make your site more appealing, but their size can affect performance.</span></span> <span data-ttu-id="ce82d-106">透過壓縮和調整大小，並使用子畫面，您可以抵消超大影像的效果。</span><span class="sxs-lookup"><span data-stu-id="ce82d-106">By optimizing your images with compression and resizing, and using sprites, you can offset the effects of very large images.</span></span> <span data-ttu-id="ce82d-107">您可以使用 SharePoint 影像轉譯，上傳單一大影像，並顯示影像的區段，以允許重複使用，而不是重新載入。</span><span class="sxs-lookup"><span data-stu-id="ce82d-107">Using SharePoint image renditions, you can upload a single large image, and display sections of the image allowing it to be reused rather than reloaded.</span></span>

>[!NOTE]
><span data-ttu-id="ce82d-108">本主題適用于 SharePoint 線上傳統發佈網站，而非現代入口網站。</span><span class="sxs-lookup"><span data-stu-id="ce82d-108">This topic applies to SharePoint Online classic publishing sites, not modern portal sites.</span></span> <span data-ttu-id="ce82d-109">如需 SharePoint Online 新式入口網站中的圖像優化的詳細資訊，請參閱 [在 SharePoint Online 新式入口網站頁面中優化圖像](modern-image-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="ce82d-109">For information about image optimization in SharePoint Online modern portal sites, see [Optimize images in SharePoint Online modern portal pages](modern-image-optimization.md).</span></span>
  
## <a name="using-sprites-to-speed-up-image-loading"></a><span data-ttu-id="ce82d-110">使用子畫面加快影像載入速度</span><span class="sxs-lookup"><span data-stu-id="ce82d-110">Using sprites to speed up image loading</span></span>

|||
|:-----|:-----|
| <span data-ttu-id="ce82d-111">圖像 sprite 包含許多較小的影像。</span><span class="sxs-lookup"><span data-stu-id="ce82d-111">An image sprite contains many smaller images.</span></span> <span data-ttu-id="ce82d-112">使用 CSS 您可以選取複合影像的一部分，以絕對位置顯示頁面的特定部分。</span><span class="sxs-lookup"><span data-stu-id="ce82d-112">Using CSS you select a part of the composite image to display on a particular part of the page with absolute positioning.</span></span> <span data-ttu-id="ce82d-113">基本上，您只需在頁面上移動單一影像，而不是載入多個影像，並透過小型視窗顯示該圖像的一小部分，在此視窗中，會向使用者顯示其子畫面影像的必要部分。</span><span class="sxs-lookup"><span data-stu-id="ce82d-113">Basically, you move a single image around the page instead of loading multiple images, and make a small part of that image visible through a small window where the required part of the sprite image is shown to the end user.</span></span> <span data-ttu-id="ce82d-114">SharePoint 線上使用 sprite，在 sprite spcommon.png 中顯示其各種圖示。</span><span class="sxs-lookup"><span data-stu-id="ce82d-114">SharePoint Online uses sprites to display its various icons in the sprite spcommon.png.</span></span>  <br/>  <span data-ttu-id="ce82d-115">如下所述：</span><span class="sxs-lookup"><span data-stu-id="ce82d-115">What's covered here:</span></span>  <br/>  <span data-ttu-id="ce82d-116">影像壓縮</span><span class="sxs-lookup"><span data-stu-id="ce82d-116">Image compression</span></span>  <br/>  <span data-ttu-id="ce82d-117">圖像優化</span><span class="sxs-lookup"><span data-stu-id="ce82d-117">Image optimization</span></span>  <br/>  <span data-ttu-id="ce82d-118">SharePoint 影像轉譯</span><span class="sxs-lookup"><span data-stu-id="ce82d-118">SharePoint image renditions</span></span>  <br/> |![Spcommon 的螢幕擷取畫面](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
<span data-ttu-id="ce82d-120">這可提高效能，因為您只下載一個影像，而不是多個，然後再快取並重複使用該影像。</span><span class="sxs-lookup"><span data-stu-id="ce82d-120">This can increase performance because you download only one image instead of several and then cache and reuse that image.</span></span> <span data-ttu-id="ce82d-121">即使圖像未保持快取，但只要有單一影像（而不是多個影像），此方法就會減少對伺服器的 HTTP 要求總數，以減少頁面載入時間。</span><span class="sxs-lookup"><span data-stu-id="ce82d-121">Even if the image does not remain cached, by having a single image instead of multiple images, this method reduces the total number of HTTP requests to the server which will reduce page loading times.</span></span> <span data-ttu-id="ce82d-122">這實際上是一種圖像捆綁的形式。</span><span class="sxs-lookup"><span data-stu-id="ce82d-122">This is really a form of image bundling.</span></span> <span data-ttu-id="ce82d-123">如果影像不經常變更（例如，如上所述的 SharePoint 範例中所示），這是非常實用的技巧。</span><span class="sxs-lookup"><span data-stu-id="ce82d-123">This is a very useful technique if the images are not changing very often, for example, icons, as shown in the SharePoint example provided above.</span></span> <span data-ttu-id="ce82d-124">您可以使用 [Web Essentials](https://vswebessentials.com/)，協力廠商，以群組為基礎的專案，在 Microsoft Visual Studio 中輕鬆做到這一點。</span><span class="sxs-lookup"><span data-stu-id="ce82d-124">You can how to use [Web Essentials](https://vswebessentials.com/), a third-party, open-source, community-based project to achieve this easily in Microsoft Visual Studio.</span></span> <span data-ttu-id="ce82d-125">如需詳細資訊，請參閱 [SharePoint Online 中的縮制和捆綁](./minification-and-bundling-in-sharepoint-online.md)。</span><span class="sxs-lookup"><span data-stu-id="ce82d-125">For more information, see [Minification and bundling in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md).</span></span>
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a><span data-ttu-id="ce82d-126">使用影像壓縮及優化，以加速頁面載入速度</span><span class="sxs-lookup"><span data-stu-id="ce82d-126">Using image compression and optimization to speed up page loading</span></span>

<span data-ttu-id="ce82d-127">影像壓縮及優化是關於減少您在網站上使用之影像的檔案大小。</span><span class="sxs-lookup"><span data-stu-id="ce82d-127">Image compression and optimization is about reducing the file size of the images you use on your site.</span></span> <span data-ttu-id="ce82d-128">通常，減少圖像大小的最佳技巧是將圖像的大小調整為將在網站上查看的最大尺寸。</span><span class="sxs-lookup"><span data-stu-id="ce82d-128">Often, the best technique to reduce the size of an image is to resize the image to the maximum dimensions that it will be viewed on the site.</span></span> <span data-ttu-id="ce82d-129">使用的影像沒有任何意義的意義。</span><span class="sxs-lookup"><span data-stu-id="ce82d-129">There is no sense in having an image larger than it will ever be viewed.</span></span> <span data-ttu-id="ce82d-130">使用影像編輯器確定影像的尺寸是否正確，是減少頁面大小的快速快捷的方式。</span><span class="sxs-lookup"><span data-stu-id="ce82d-130">Making sure images are of the correct dimensions using an image editor is a quick and easy way to reduce the size of your page.</span></span>
  
<span data-ttu-id="ce82d-131">圖像大小正確之後，下一步是優化這些影像的壓縮。</span><span class="sxs-lookup"><span data-stu-id="ce82d-131">Once images are the right size, the next step is to optimize the compression of these images.</span></span> <span data-ttu-id="ce82d-132">有各種可用於壓縮及優化的工具，包括照片庫和協力廠商工具。</span><span class="sxs-lookup"><span data-stu-id="ce82d-132">There are various tools available to use for compression and optimization, including Photo Gallery and third-party tools.</span></span> <span data-ttu-id="ce82d-133">要壓縮的關鍵是為了盡可能縮小檔案大小，而不會喪失任何可辨識的品質給使用者。</span><span class="sxs-lookup"><span data-stu-id="ce82d-133">The key to compression is to reduce the file size as much as possible without losing any discernible quality for end users.</span></span> <span data-ttu-id="ce82d-134">請務必在高定義顯示幕上測試壓縮檔，以確保這些檔案的外觀仍有效。</span><span class="sxs-lookup"><span data-stu-id="ce82d-134">Make sure you test your compressed files on a high-definition display to ensure they will still look good.</span></span>
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a><span data-ttu-id="ce82d-135">使用 SharePoint 影像轉譯器加速頁面下載</span><span class="sxs-lookup"><span data-stu-id="ce82d-135">Speed up page downloads by using SharePoint image renditions</span></span>

<span data-ttu-id="ce82d-136">影像轉譯是 SharePoint Online 中的一項功能，可讓您根據預先定義的影像尺寸，提供不同版本的影像。</span><span class="sxs-lookup"><span data-stu-id="ce82d-136">Image renditions are a feature in SharePoint Online that allows you to serve up different versions of images based on pre-defined image dimensions.</span></span> <span data-ttu-id="ce82d-137">當網站上的 CSS 已修復使用者所產生的圖像內容或圖像維度（例如寬度和高度）時，這一點特別重要。</span><span class="sxs-lookup"><span data-stu-id="ce82d-137">This is especially important when there is user-generated image content or the image dimensions such as width and height are fixed by the CSS on the site.</span></span> <span data-ttu-id="ce82d-138">即使圖像是由 CSS 修正，仍然會載入完整解析度影像。</span><span class="sxs-lookup"><span data-stu-id="ce82d-138">Even if an image is fixed by CSS, the full resolution image is still loaded.</span></span> <span data-ttu-id="ce82d-139">在此情況下，您可以使用影像轉譯來減少檔案大小。</span><span class="sxs-lookup"><span data-stu-id="ce82d-139">In this case the file size can be reduced by using image renditions.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ce82d-140">轉譯功能只有在啟用發佈功能時才能 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="ce82d-140">Renditions are only available for SharePoint when publishing is enabled.</span></span> <span data-ttu-id="ce82d-141">您可以在 [設定網站設定] 下啟用發佈 [ \> \> 管理網站功能 \> SharePoint 伺服器發佈]。</span><span class="sxs-lookup"><span data-stu-id="ce82d-141">You can enable publishing under Settings \> Site Settings \> Manage site features \> SharePoint Server Publishing.</span></span> <span data-ttu-id="ce82d-142">否則不會出現此選項。</span><span class="sxs-lookup"><span data-stu-id="ce82d-142">The option will not appear otherwise.</span></span>
  
<span data-ttu-id="ce82d-143">影像轉譯重新調整大小的運作方式是取得您定義的最小尺寸（寬或高），然後調整圖像大小，以根據鎖定的長寬比例自動調整其他尺寸的大小。</span><span class="sxs-lookup"><span data-stu-id="ce82d-143">The image rendition resizing works by taking the smallest dimension you define, either width or height, and then resizing the image so that the other dimension is automatically resized based on the locked aspect ratio.</span></span> <span data-ttu-id="ce82d-144">根據預設，它會將圖像從中心裁剪掉剩餘的維度。</span><span class="sxs-lookup"><span data-stu-id="ce82d-144">By default, it will crop the image from the center by the remaining dimensions.</span></span> <span data-ttu-id="ce82d-145">例如，如果您定義 100px wide 和50px 的格式副本，而您的原始影像為1000px 寬和800px 高，將會調整大小，使800px 維度現在50px，而1000px 維度 (現在會從圖像中心裁剪的 62.5 px) 。</span><span class="sxs-lookup"><span data-stu-id="ce82d-145">For example, if you define a rendition of 100px wide and 50px high and your original image is 1000px wide and 800px high, it will be resized so that the 800px dimension is now 50px and the 1000px dimension (now 62.5px) is cropped from the center of the image.</span></span>
  
<span data-ttu-id="ce82d-146">步驟相對簡單，但若要使用轉譯格式，您必須先在 SharePoint 網站上的轉譯，再新增影像。</span><span class="sxs-lookup"><span data-stu-id="ce82d-146">The steps are relatively simple but for images to use the renditions, the renditions need to be on the SharePoint site before you add the images.</span></span> <span data-ttu-id="ce82d-147">此外，您還需要 SharePoint 伺服器發佈基礎結構 (網站集合層級) 和 SharePoint 的伺服器發佈 (網站層級) 功能已開啟。</span><span class="sxs-lookup"><span data-stu-id="ce82d-147">In addition, you also need to have the SharePoint Server Publishing Infrastructure (Site Collection Level) and SharePoint Server Publishing (Site Level) features turned on.</span></span>
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a><span data-ttu-id="ce82d-148">新增影像格式副本以加速頁面載入速度</span><span class="sxs-lookup"><span data-stu-id="ce82d-148">Add an image rendition to speed up page loading</span></span>
  
1. <span data-ttu-id="ce82d-149">確認執行此程式的使用者帳戶至少具有網站集合最上層網站的「設計」許可權，且該網站已發佈至網頁。</span><span class="sxs-lookup"><span data-stu-id="ce82d-149">Verify that the user account that is performing this procedure has, at minimum, Design permissions to the top-level site of the site collection, and that the site is being published to a webpage.</span></span>

2. <span data-ttu-id="ce82d-150">在網頁瀏覽器中，移至發佈網站集合的最上層網站。</span><span class="sxs-lookup"><span data-stu-id="ce82d-150">In a web browser, go to the top-level site of the publishing site collection.</span></span>

3. <span data-ttu-id="ce82d-151">選擇 [ **設定** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="ce82d-151">Choose the **Settings** icon.</span></span>

4. <span data-ttu-id="ce82d-152">在 [ **網站設定** ] 頁面的 [ **外觀與風格** ] 區段中，您將會看到內建的影像轉譯。</span><span class="sxs-lookup"><span data-stu-id="ce82d-152">On the **Site Settings** page, in the **Look and Feel** section, you will see the built-in image renditions.</span></span>

    <span data-ttu-id="ce82d-153">您可以使用現成的轉譯轉譯，或選擇 [ **影像** 轉譯] 來建立新的格式副本。</span><span class="sxs-lookup"><span data-stu-id="ce82d-153">You can use the out of the box renditions or choose **Image Renditions** to create a new one.</span></span>

    ![影像轉譯的螢幕擷取畫面](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. <span data-ttu-id="ce82d-155">在 [ **圖像** 轉譯] 頁面上，選擇 [ **新增專案**]。</span><span class="sxs-lookup"><span data-stu-id="ce82d-155">On the **Image Renditions** page, choose **Add new item**.</span></span>

    ![新增項目的螢幕擷取畫面](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. <span data-ttu-id="ce82d-157">在 [ **新增影像** 轉譯] 頁面的 [ **名稱** ] 方塊中，輸入此格式副本的名稱。</span><span class="sxs-lookup"><span data-stu-id="ce82d-157">On the **New Image Rendition** page, in the **Name** box, enter a name for the rendition.</span></span>

7. <span data-ttu-id="ce82d-158">在 [ **寬度** ] 和 [ **高度** ] 文字方塊中，輸入格式副本的寬度和高度（以圖元為單位），然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ce82d-158">In the **Width** and **Height** text boxes, enter the width and height, in pixels, of the rendition, and then choose **Save**.</span></span>

    ![影像轉譯名稱的螢幕擷取畫面](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a><span data-ttu-id="ce82d-160">使用影像轉譯的自訂裁剪</span><span class="sxs-lookup"><span data-stu-id="ce82d-160">Custom cropping with image renditions</span></span>

<span data-ttu-id="ce82d-161">根據預設，影像轉譯會從影像的中央產生。</span><span class="sxs-lookup"><span data-stu-id="ce82d-161">By default, an image rendition is generated from the center of the image.</span></span> <span data-ttu-id="ce82d-162">您可以裁剪您要使用的圖像部分，以調整個別圖像的圖像轉譯。</span><span class="sxs-lookup"><span data-stu-id="ce82d-162">You can adjust the image rendition for individual images by cropping the portion of the image that you want to use.</span></span> <span data-ttu-id="ce82d-163">您可以依格式副本逐個裁剪圖像。</span><span class="sxs-lookup"><span data-stu-id="ce82d-163">You can crop the images on an individual basis, per rendition.</span></span> <span data-ttu-id="ce82d-164">透過使用 SharePoint 的 blob 快取，為每個轉譯器建立影像的版本，裁剪圖像可加快頁面載入速度。</span><span class="sxs-lookup"><span data-stu-id="ce82d-164">Cropping the images speeds up page loading by using SharePoint's blob cache to create a version of the image for each rendition.</span></span> <span data-ttu-id="ce82d-165">這樣一來，伺服器負載便會減少，因為圖像只會重新調整大小一次，然後準備好將其提供給使用者多次。</span><span class="sxs-lookup"><span data-stu-id="ce82d-165">This way the server load is reduced because the image is only resized once and is then ready to serve to end users multiple times.</span></span> <span data-ttu-id="ce82d-166">如需如何裁切圖像呈現方式的詳細資訊，請參閱 [裁剪圖像](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels)轉譯。</span><span class="sxs-lookup"><span data-stu-id="ce82d-166">For more information on how to crop an image rendition, see [Crop an image rendition](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels).</span></span>
