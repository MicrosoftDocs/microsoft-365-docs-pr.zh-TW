---
title: Microsoft 受管理電腦的組態設定參考
description: Microsoft 受管理電腦中的組態設定的設定類別
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 296602422cf4d590ae17335d7a0bbbc939d929ed
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278316"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="d5d0b-104">可設定的設定參照-Microsoft 受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="d5d0b-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="d5d0b-105">本主題列出客戶可以使用 Microsoft 受管理的電腦設定的設定類別。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-105">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop.</span></span> <span data-ttu-id="d5d0b-106">每個設定類別包含需求、 最佳作法，以及如何自訂 [設定] 類別的資訊。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-106">Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="d5d0b-107">桌面背景圖片</span><span class="sxs-lookup"><span data-stu-id="d5d0b-107">Desktop background picture</span></span>
<span data-ttu-id="d5d0b-108">您可以在組織中自訂 Microsoft 受管理的電腦裝置的桌面背景圖片。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-108">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization.</span></span> <span data-ttu-id="d5d0b-109">您可以使用此方式套用公司品牌或行銷資料。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-109">You might use this to apply a company brand or marketing material.</span></span> 

### <a name="requirements"></a><span data-ttu-id="d5d0b-110">需求</span><span class="sxs-lookup"><span data-stu-id="d5d0b-110">Requirements</span></span>

<span data-ttu-id="d5d0b-111">為桌面背景圖片，必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="d5d0b-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="d5d0b-112">圖片檔案格式的.jpg、 jpeg 或.png</span><span class="sxs-lookup"><span data-stu-id="d5d0b-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="d5d0b-113">檔案位置-信任安全 http (https) 位置上的主機。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="d5d0b-114">不支援不允許-Http 和檔案共用 (unc) 位置。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="d5d0b-115">自訂及部署桌面背景圖片</span><span class="sxs-lookup"><span data-stu-id="d5d0b-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="d5d0b-116">**若要新增自訂的桌面背景圖片**</span><span class="sxs-lookup"><span data-stu-id="d5d0b-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="d5d0b-117">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d5d0b-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="d5d0b-118">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="d5d0b-119">在 [**可設定**工作區中，選取 [**桌面背景圖片**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="d5d0b-120">輸入您想要使用的圖片的位置。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="d5d0b-121">選取**階段部署**，以儲存變更，並將其部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-121">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="d5d0b-122">瀏覽器開始頁面</span><span class="sxs-lookup"><span data-stu-id="d5d0b-122">Browser start pages</span></span>
<span data-ttu-id="d5d0b-123">當使用者啟動 Microsoft Edge 中個別索引標籤開啟瀏覽器啟動頁面。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-123">Browser start pages open in individual tabs when your users start Microsoft Edge.</span></span> <span data-ttu-id="d5d0b-124">如果您想要讓方便您的使用者開啟一群使用者經常使用的網站，新增每個網站的瀏覽器啟動頁面。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-124">If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="d5d0b-125">需求</span><span class="sxs-lookup"><span data-stu-id="d5d0b-125">Requirements</span></span>

<span data-ttu-id="d5d0b-126">您必須提供的完整的網域名稱 (FQDN) 的內部網路或網際網路網站的瀏覽器啟動頁面。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-126">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages.</span></span> <span data-ttu-id="d5d0b-127">如果設定內部網站，讓使用者知道要在 office 中的內部網路連線時或使用 VPN 連線連線時，只允許這些網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-127">If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="d5d0b-128">自訂及部署瀏覽器開始頁面</span><span class="sxs-lookup"><span data-stu-id="d5d0b-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="d5d0b-129">**若要新增在瀏覽器啟動頁面**</span><span class="sxs-lookup"><span data-stu-id="d5d0b-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="d5d0b-130">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d5d0b-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="d5d0b-131">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="d5d0b-132">在 [**可設定**工作區中，選取 [**瀏覽器啟動頁面**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="d5d0b-133">選取 [**新增起始頁面**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="d5d0b-134">在 [**新增] 瀏覽器啟動] 頁面上**，輸入您要使用的網站 URL，然後選取 [**新增起始頁面**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="d5d0b-135">重複步驟 1 到 5 的其他瀏覽器啟動頁面。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="d5d0b-136">選取**階段部署**，以儲存變更，並將其部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-136">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="d5d0b-137">企業模式網站清單位置</span><span class="sxs-lookup"><span data-stu-id="d5d0b-137">Enterprise mode site list location</span></span>

<span data-ttu-id="d5d0b-138">如果您有特定的網站和應用程式，您知道有 Microsoft Edge 的相容性問題，您可以使用企業模式網站清單，以便網站會自動開啟使用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-138">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11.</span></span> <span data-ttu-id="d5d0b-139">此外，如果您知道您的內部網路網站不移至 Microsoft Edge 中正常運作，您可以設定所有的內部網路網站，若要開啟 [自動使用 Internet Explorer 11。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-139">Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically.</span></span> <span data-ttu-id="d5d0b-140">使用企業模式表示您可以繼續使用 Microsoft Edge 作為預設的瀏覽器，同時也確保您的應用程式，繼續在 Internet Explorer 11 上工作。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-140">Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11.</span></span> <span data-ttu-id="d5d0b-141">如需有關企業模式網站清單的詳細資訊，請參閱[企業模式和企業模式網站清單](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-141">For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="d5d0b-142">您可以指定 https:// 位置或您主控您的企業模式網站清單的內部共用的位置。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="d5d0b-143">需求</span><span class="sxs-lookup"><span data-stu-id="d5d0b-143">Requirements</span></span>

<span data-ttu-id="d5d0b-144">對於企業模式網站清單檔案，必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="d5d0b-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="d5d0b-145">檔案格式的 XML 檔案符合[檔案需求](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="d5d0b-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="d5d0b-146">檔案位置-內部 https 位置上的主機檔案。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="d5d0b-147">不允許-裝載內部檔案共用，例如 *//sharename*，不允許</span><span class="sxs-lookup"><span data-stu-id="d5d0b-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="d5d0b-148">最佳做法</span><span class="sxs-lookup"><span data-stu-id="d5d0b-148">Best practices</span></span>

<span data-ttu-id="d5d0b-149">這些最佳作法提供可協助客戶做出決策至現代化其 IT 基礎結構：</span><span class="sxs-lookup"><span data-stu-id="d5d0b-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="d5d0b-150">**選擇網站數目有限**– Microsoft 受管理的電腦會使用為慣用的瀏覽器 Microsoft Edge，以提升貴組織的整體安全性和使用者的可用性。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-150">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users.</span></span> <span data-ttu-id="d5d0b-151">在此清單中的大部分網站是需要較舊版本的瀏覽器中，將不會包含相同數目的安全性功能的舊版 web 應用程式 url。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-151">Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="d5d0b-152">**考慮替代**– 考慮不同的網站或不需要較舊的瀏覽器的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-152">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser.</span></span> <span data-ttu-id="d5d0b-153">或者，請考慮更新網站，以便其可以使用較新的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-153">Or, consider updating the site so that it can use newer browsers.</span></span> <span data-ttu-id="d5d0b-154">較新的瀏覽器使用的最新技術，並協助增進安全性。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-154">Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="d5d0b-155">自訂及部署企業網站模式] 清單位置</span><span class="sxs-lookup"><span data-stu-id="d5d0b-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="d5d0b-156">**若要新增企業網站模式] 清單位置**</span><span class="sxs-lookup"><span data-stu-id="d5d0b-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="d5d0b-157">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d5d0b-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="d5d0b-158">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="d5d0b-159">在 [**可設定**工作區中，選取**企業模式網站清單位置**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="d5d0b-160">輸入您的網站清單的 https 位置。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="d5d0b-161">選取**階段部署**，以儲存變更，並將其部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-161">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="d5d0b-162">信任的網站</span><span class="sxs-lookup"><span data-stu-id="d5d0b-162">Trusted sites</span></span>

<span data-ttu-id="d5d0b-163">受信任的網站可讓您自訂安全性區域，或其中一個站台可用於，不同的站台。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-163">Trusted sites allow you to customize security zones, or where a site can be used, for different sites.</span></span> <span data-ttu-id="d5d0b-164">安全性區域包含：</span><span class="sxs-lookup"><span data-stu-id="d5d0b-164">Security zones include:</span></span> 
- <span data-ttu-id="d5d0b-165">區域 1 – 近端內部網路區域</span><span class="sxs-lookup"><span data-stu-id="d5d0b-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="d5d0b-166">區域 2 – 受信任的網站] 區域</span><span class="sxs-lookup"><span data-stu-id="d5d0b-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="d5d0b-167">區域 3 – 網際網路區域</span><span class="sxs-lookup"><span data-stu-id="d5d0b-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="d5d0b-168">區域 4 – 限制的網站] 區域</span><span class="sxs-lookup"><span data-stu-id="d5d0b-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="d5d0b-169">需求</span><span class="sxs-lookup"><span data-stu-id="d5d0b-169">Requirements</span></span>

<span data-ttu-id="d5d0b-170">內部網路或網際網路網站的每個受信任的網站提供的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="d5d0b-171">自訂及部署信任的網站</span><span class="sxs-lookup"><span data-stu-id="d5d0b-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="d5d0b-172">**若要新增信任的網站**</span><span class="sxs-lookup"><span data-stu-id="d5d0b-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="d5d0b-173">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d5d0b-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="d5d0b-174">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="d5d0b-175">在 [**可設定**工作區中，選取 [**信任的網站**，，，然後選取 [**新增信任的網站**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="d5d0b-176">在 [**新增信任的網站**]，輸入的 URL，選擇 [安全性區域，，然後選取 [**新增信任的網站**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="d5d0b-177">針對每個您想要新增信任的網站重複步驟 1 到 4。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="d5d0b-178">選取**階段部署**，以儲存變更，並將其部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-178">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

<span data-ttu-id="d5d0b-179">**若要移除信任的網站**</span><span class="sxs-lookup"><span data-stu-id="d5d0b-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="d5d0b-180">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d5d0b-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="d5d0b-181">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="d5d0b-182">在 [**可設定**工作區中，選取 [**信任的網站**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="d5d0b-183">選取您要刪除的網站，然後選取 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="d5d0b-184">針對每個您想要刪除的信任網站重複步驟 1 到 4。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="d5d0b-185">選取**階段部署**，以儲存變更，並將其部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-185">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="proxy"></a><span data-ttu-id="d5d0b-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="d5d0b-186">Proxy</span></span>
<span data-ttu-id="d5d0b-187">您可以管理組織的網路 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-187">You can manage network proxy settings for your organization.</span></span> <span data-ttu-id="d5d0b-188">新增您的 proxy 伺服器和連接埠號碼，然後再新增 [您的 proxy 站台例外狀況。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-188">Add your proxy server and port number, and then add your proxy site exceptions.</span></span> <span data-ttu-id="d5d0b-189">Microsoft 受管理的電腦包含一組的預設 proxy 的例外狀況所需的操作的服務。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-189">Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate.</span></span> <span data-ttu-id="d5d0b-190">Microsoft 受管理的電腦服務可能只修改預設排除清單。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-190">The default exclusion list may only be modified by the Microsoft Managed Desktop service.</span></span>  <span data-ttu-id="d5d0b-191">如需詳細資訊，請參閱 < <b0>Microsoft 受管理電腦的網路組態</b0>。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-191">For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="d5d0b-192">您在 Microsoft 受管理電腦入口網站中新增的 proxy 站台例外狀況會新增至預設的 proxy 例外狀況隨附於 Microsoft 受管理的電腦服務。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="d5d0b-193">一律優先順序透過客戶部署更新的預設 proxy 例外狀況清單。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-193">Updating the default proxy exception list is always prioritized over customer deployments.</span></span> <span data-ttu-id="d5d0b-194">這表示如果沒有預設 proxy 例外狀況清單的部署，將會暫停分段的部署。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-194">This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="d5d0b-195">需求</span><span class="sxs-lookup"><span data-stu-id="d5d0b-195">Requirements</span></span>

<span data-ttu-id="d5d0b-196">Proxy 伺服器和 proxy 網站例外狀況，必須符合這些需求：</span><span class="sxs-lookup"><span data-stu-id="d5d0b-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="d5d0b-197">必須是有效的伺服器位址及連接埠號碼</span><span class="sxs-lookup"><span data-stu-id="d5d0b-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="d5d0b-198">Url 必須是有效的 http 網站</span><span class="sxs-lookup"><span data-stu-id="d5d0b-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="d5d0b-199">自訂及部署 proxy</span><span class="sxs-lookup"><span data-stu-id="d5d0b-199">Customize and deploy proxies</span></span>

<span data-ttu-id="d5d0b-200">**若要新增個別的 proxy 站台例外狀況**</span><span class="sxs-lookup"><span data-stu-id="d5d0b-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="d5d0b-201">登入[Microsoft 受管理電腦系統管理員入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="d5d0b-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="d5d0b-202">在 [**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="d5d0b-203">在 [**可設定**工作區中，選取 [ **Proxy**]。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="d5d0b-204">輸入您 proxy 伺服器的**位址**和**連接埠號碼**，然後選取 [**新增 proxy 例外狀況**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="d5d0b-205">輸入有效的 http 網站的 URL，然後選取 [**新增 proxy 例外狀況**。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="d5d0b-206">針對每個您想要新增信任的網站重複步驟 1-5。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="d5d0b-207">選取**階段部署**，以儲存變更，並將其部署至測試群組。</span><span class="sxs-lookup"><span data-stu-id="d5d0b-207">Select **Stage deployment** to save your changes and deploy them to the Test group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d5d0b-208">其他資源</span><span class="sxs-lookup"><span data-stu-id="d5d0b-208">Additional resources</span></span>
- [<span data-ttu-id="d5d0b-209">組態設定概觀</span><span class="sxs-lookup"><span data-stu-id="d5d0b-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="d5d0b-210">部署組態設定</span><span class="sxs-lookup"><span data-stu-id="d5d0b-210">Deploy configurable settings</span></span>](config-setting-deploy.md)
