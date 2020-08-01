---
title: Microsoft 受管理電腦的可設定參考
description: 設定 Microsoft Managed Desktop 中的可設定類別
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c3f8aec244b1b0685b8293fda0b048d662c7cef2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529358"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="53073-104">可設定的設定參考-Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="53073-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="53073-105">本主題列出客戶可以使用 Microsoft Managed Desktop 設定的設定類別。</span><span class="sxs-lookup"><span data-stu-id="53073-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="53073-106">每個設定類別都包含需求的資訊、最佳作法，以及如何自訂設定類別。</span><span class="sxs-lookup"><span data-stu-id="53073-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="53073-107">桌面背景圖片</span><span class="sxs-lookup"><span data-stu-id="53073-107">Desktop background picture</span></span>
<span data-ttu-id="53073-108">您可以為組織中的 Microsoft 受管理桌面裝置自訂桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="53073-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="53073-109">您可以使用此應用來套用公司品牌或行銷材料。</span><span class="sxs-lookup"><span data-stu-id="53073-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="53073-110">需求</span><span class="sxs-lookup"><span data-stu-id="53073-110">Requirements</span></span>

<span data-ttu-id="53073-111">您必須符合這些需求，才能取得桌面背景圖片：</span><span class="sxs-lookup"><span data-stu-id="53073-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="53073-112">圖片檔案格式-.jpg、jpeg 或 .png</span><span class="sxs-lookup"><span data-stu-id="53073-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="53073-113">檔案位置-主機位於受信任的安全 HTTP （HTTPs）位置。</span><span class="sxs-lookup"><span data-stu-id="53073-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="53073-114">不允許-不支援 Http 和檔案共用（unc）位置。</span><span class="sxs-lookup"><span data-stu-id="53073-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="53073-115">自訂及部署桌面背景圖片</span><span class="sxs-lookup"><span data-stu-id="53073-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="53073-116">**新增自訂桌面背景圖片**</span><span class="sxs-lookup"><span data-stu-id="53073-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="53073-117">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="53073-117">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="53073-118">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="53073-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="53073-119">在 [**可**設定的工作區] 中，選取 [**桌面背景圖片**]。</span><span class="sxs-lookup"><span data-stu-id="53073-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="53073-120">輸入您想要使用的圖片位置。</span><span class="sxs-lookup"><span data-stu-id="53073-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="53073-121">選取 [**階段部署**] 以儲存變更，並將變更部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="53073-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="53073-122">瀏覽器開始頁面</span><span class="sxs-lookup"><span data-stu-id="53073-122">Browser start pages</span></span>
<span data-ttu-id="53073-123">當使用者啟動 Microsoft Edge 時，瀏覽器起始頁面會在個別的索引標籤中開啟。</span><span class="sxs-lookup"><span data-stu-id="53073-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="53073-124">如果您想要讓使用者輕鬆地開啟一組經常使用的網站，請為每個網站新增瀏覽器開始頁面。</span><span class="sxs-lookup"><span data-stu-id="53073-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="53073-125">需求</span><span class="sxs-lookup"><span data-stu-id="53073-125">Requirements</span></span>

<span data-ttu-id="53073-126">您必須為瀏覽器開始頁面提供內部網路或網際網路網站的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="53073-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="53073-127">如果已設定內部網站，請讓使用者知道，當在辦公室或使用 VPN 連線時，連線至內部網路時，允許存取這些網站。</span><span class="sxs-lookup"><span data-stu-id="53073-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="53073-128">自訂及部署瀏覽器開始頁面</span><span class="sxs-lookup"><span data-stu-id="53073-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="53073-129">**新增瀏覽器開始頁面**</span><span class="sxs-lookup"><span data-stu-id="53073-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="53073-130">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="53073-130">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="53073-131">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="53073-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="53073-132">在**可**設定的工作區中，選取 [**瀏覽器開始頁面**]。</span><span class="sxs-lookup"><span data-stu-id="53073-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="53073-133">選取 [**新增開始頁面**]。</span><span class="sxs-lookup"><span data-stu-id="53073-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="53073-134">在 [**新增瀏覽器開始] 頁面**上，輸入您要使用之網站的 URL，然後選取 [**新增開始頁面**]。</span><span class="sxs-lookup"><span data-stu-id="53073-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="53073-135">重複步驟1-5 以取得其他瀏覽器開始頁面。</span><span class="sxs-lookup"><span data-stu-id="53073-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="53073-136">選取 [**階段部署**] 以儲存變更，並將變更部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="53073-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="53073-137">企業模式網站清單位置</span><span class="sxs-lookup"><span data-stu-id="53073-137">Enterprise mode site list location</span></span>

<span data-ttu-id="53073-138">如果您有與 Microsoft Edge 相容性問題的特定網站和應用程式，您可以使用企業模式網站清單，讓網站自動使用 Internet Explorer 11 開啟。</span><span class="sxs-lookup"><span data-stu-id="53073-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="53073-139">此外，如果您知道內部網路網站不會與 Microsoft Edge 正確搭配使用，您可以設定所有內部網路網站，以自動開啟使用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="53073-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="53073-140">使用企業模式意味著您可以繼續使用 Microsoft Edge 做為您的預設瀏覽器，同時也可以確保您的應用程式繼續在 Internet Explorer 11 上運作。</span><span class="sxs-lookup"><span data-stu-id="53073-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="53073-141">如需企業模式網站清單的詳細資訊，請參閱[Enterprise mode And Enterprise Mode Site lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。</span><span class="sxs-lookup"><span data-stu-id="53073-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="53073-142">您可以指定 HTTPs://位置或存放您的企業模式網站清單所在內部共用的位置。</span><span class="sxs-lookup"><span data-stu-id="53073-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="53073-143">需求</span><span class="sxs-lookup"><span data-stu-id="53073-143">Requirements</span></span>

<span data-ttu-id="53073-144">企業模式網站清單檔案必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="53073-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="53073-145">檔案格式-符合[檔需求](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="53073-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="53073-146">檔案位置-主機檔案在內部 HTTPs 位置上。</span><span class="sxs-lookup"><span data-stu-id="53073-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="53073-147">不允許-不允許在內部檔案共用（如 *//sharename*）上裝載</span><span class="sxs-lookup"><span data-stu-id="53073-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="53073-148">最佳做法</span><span class="sxs-lookup"><span data-stu-id="53073-148">Best practices</span></span>

<span data-ttu-id="53073-149">提供這些最佳作法，以協助客戶決定讓其 IT 基礎結構現代化：</span><span class="sxs-lookup"><span data-stu-id="53073-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="53073-150">**選擇有限的網站數目**– Microsoft 受管理的桌面會使用 microsoft Edge 做為首選瀏覽器，以提升貴組織和使用者可用性的整體安全性。</span><span class="sxs-lookup"><span data-stu-id="53073-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="53073-151">此清單中的大部分網站適用于舊版 web 應用程式，需要舊版本的瀏覽器，不會包含任何的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="53073-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="53073-152">**請考慮**其他的網站，或不需要舊版瀏覽器的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="53073-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="53073-153">或者，請考慮更新網站，使其可使用較新的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="53073-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="53073-154">較新的瀏覽器使用最新的技術，協助改善安全性。</span><span class="sxs-lookup"><span data-stu-id="53073-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="53073-155">自訂及部署企業網站模式清單位置</span><span class="sxs-lookup"><span data-stu-id="53073-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="53073-156">**新增 enterprise site mode 清單位置**</span><span class="sxs-lookup"><span data-stu-id="53073-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="53073-157">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="53073-157">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="53073-158">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="53073-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="53073-159">在 [**可**設定的工作區] 中，選取 [**企業模式網站清單位置**]。</span><span class="sxs-lookup"><span data-stu-id="53073-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="53073-160">為您的網站清單輸入 HTTPs 位置。</span><span class="sxs-lookup"><span data-stu-id="53073-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="53073-161">選取 [**階段部署**] 以儲存變更，並將變更部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="53073-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="53073-162">信任的網站</span><span class="sxs-lookup"><span data-stu-id="53073-162">Trusted sites</span></span>

<span data-ttu-id="53073-163">「信任的網站」可讓您自訂安全性區域，或為不同的網站使用網站。</span><span class="sxs-lookup"><span data-stu-id="53073-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="53073-164">安全性區域包括：</span><span class="sxs-lookup"><span data-stu-id="53073-164">Security zones include:</span></span> 
- <span data-ttu-id="53073-165">Zone 1 –本機內部網路區域</span><span class="sxs-lookup"><span data-stu-id="53073-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="53073-166">區域2–信任的網站區域</span><span class="sxs-lookup"><span data-stu-id="53073-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="53073-167">區域3–網際網路區域</span><span class="sxs-lookup"><span data-stu-id="53073-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="53073-168">區域4–受限制的網站區域</span><span class="sxs-lookup"><span data-stu-id="53073-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="53073-169">需求</span><span class="sxs-lookup"><span data-stu-id="53073-169">Requirements</span></span>

<span data-ttu-id="53073-170">為每個受信任的網站提供內部網路或網際網路網站的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="53073-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="53073-171">自訂及部署信任的網站</span><span class="sxs-lookup"><span data-stu-id="53073-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="53073-172">**新增信任的網站**</span><span class="sxs-lookup"><span data-stu-id="53073-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="53073-173">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="53073-173">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="53073-174">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="53073-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="53073-175">在**可**設定的工作區中，選取 [**信任的網站**]，然後選取 [**新增信任的網站**]</span><span class="sxs-lookup"><span data-stu-id="53073-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="53073-176">在 [**新增信任的網站**] 上，輸入 URL、選擇安全性區域，然後選取 [**新增信任的網站**]。</span><span class="sxs-lookup"><span data-stu-id="53073-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="53073-177">針對您要新增的每個信任網站，重複步驟1-4。</span><span class="sxs-lookup"><span data-stu-id="53073-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="53073-178">選取 [**階段部署**] 以儲存變更，並將變更部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="53073-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="53073-179">**移除信任的網站**</span><span class="sxs-lookup"><span data-stu-id="53073-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="53073-180">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="53073-180">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="53073-181">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="53073-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="53073-182">在**可**設定的工作區中，選取 [**信任的網站**]。</span><span class="sxs-lookup"><span data-stu-id="53073-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="53073-183">選取您要刪除的網站，然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="53073-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="53073-184">針對每個您想要刪除的信任網站，重複步驟1-4。</span><span class="sxs-lookup"><span data-stu-id="53073-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="53073-185">選取 [**階段部署**] 以儲存變更，並將變更部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="53073-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="53073-186">代理</span><span class="sxs-lookup"><span data-stu-id="53073-186">Proxy</span></span>
<span data-ttu-id="53073-187">您可以管理組織的網路 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="53073-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="53073-188">新增 proxy 伺服器及埠號碼，然後新增 proxy 網站例外狀況。</span><span class="sxs-lookup"><span data-stu-id="53073-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="53073-189">Microsoft 受管理的桌面包含一組預設 proxy 例外，供服務運作所需。</span><span class="sxs-lookup"><span data-stu-id="53073-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="53073-190">預設的排除清單可能只會由 Microsoft Managed Desktop 服務修改。</span><span class="sxs-lookup"><span data-stu-id="53073-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="53073-191">如需詳細資訊，請參閱[Microsoft Managed Desktop 的網路](../get-ready/network.md)設定。</span><span class="sxs-lookup"><span data-stu-id="53073-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="53073-192">您在 Microsoft 管理的桌面入口網站中新增的 proxy 網站例外狀況會新增至 Microsoft Managed Desktop service 隨附的預設 proxy 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="53073-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="53073-193">更新預設 proxy 例外狀況清單時，總會優先于客戶部署。</span><span class="sxs-lookup"><span data-stu-id="53073-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="53073-194">這表示如果有預設 proxy 例外清單的部署，您的分段部署會暫停。</span><span class="sxs-lookup"><span data-stu-id="53073-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="53073-195">需求</span><span class="sxs-lookup"><span data-stu-id="53073-195">Requirements</span></span>

<span data-ttu-id="53073-196">Proxy 伺服器及 proxy 網站例外必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="53073-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="53073-197">必須是有效的伺服器位址及埠號碼</span><span class="sxs-lookup"><span data-stu-id="53073-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="53073-198">URLs 必須是有效的 HTTP 網站</span><span class="sxs-lookup"><span data-stu-id="53073-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="53073-199">自訂及部署代理伺服器</span><span class="sxs-lookup"><span data-stu-id="53073-199">Customize and deploy proxies</span></span>

<span data-ttu-id="53073-200">**新增個別 proxy 網站例外狀況**</span><span class="sxs-lookup"><span data-stu-id="53073-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="53073-201">登入[Microsoft Managed Desktop Admin 入口網站](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="53073-201">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="53073-202">在 [設定] 底下，選取 [**可\*\*\*\*設定**]。</span><span class="sxs-lookup"><span data-stu-id="53073-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="53073-203">在 [**可**設定的工作區] 中，選取**Proxy**。</span><span class="sxs-lookup"><span data-stu-id="53073-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="53073-204">輸入 proxy 伺服器的**位址**與**埠號碼**，然後選取 [**新增 proxy 例外**狀況]。</span><span class="sxs-lookup"><span data-stu-id="53073-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="53073-205">輸入有效的 HTTP 網站 URL，然後選取 [**新增 proxy 例外**狀況]。</span><span class="sxs-lookup"><span data-stu-id="53073-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="53073-206">針對您要新增的每個信任網站，重複步驟1-5。</span><span class="sxs-lookup"><span data-stu-id="53073-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="53073-207">選取 [**階段部署**] 以儲存變更，並將變更部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="53073-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="53073-208">其他資源</span><span class="sxs-lookup"><span data-stu-id="53073-208">Additional resources</span></span>
- [<span data-ttu-id="53073-209">可設定的設定概述</span><span class="sxs-lookup"><span data-stu-id="53073-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="53073-210">部署可設定的設定</span><span class="sxs-lookup"><span data-stu-id="53073-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
