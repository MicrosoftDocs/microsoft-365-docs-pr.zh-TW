---
title: 針對 Microsoft 受管理的桌上型電腦的組態設定參考 （英文)
description: 在 Microsoft 受管理的桌上型電腦中的組態設定的設定類別
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051094"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="5ad27-104">可設定的設定參考 （英文)-Microsoft 受管理的桌上型電腦</span><span class="sxs-lookup"><span data-stu-id="5ad27-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="5ad27-p101">本主題將列出客戶能設定 Microsoft 受管理的桌上型電腦設定類別。每個設定類別包含在需求、 最佳做法，以及如何自訂設定類別的資訊。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p101">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop. Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="5ad27-107">桌面背景圖片</span><span class="sxs-lookup"><span data-stu-id="5ad27-107">Desktop background picture</span></span>
<span data-ttu-id="5ad27-p102">您可以在組織中自訂 Microsoft 受管理的桌上型電腦裝置桌面背景圖片。您可能會使用此公司品牌或行銷套用</span><span class="sxs-lookup"><span data-stu-id="5ad27-p102">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization. You might use this to apply a company brand or marketing</span></span> 

### <a name="requirements"></a><span data-ttu-id="5ad27-110">需求</span><span class="sxs-lookup"><span data-stu-id="5ad27-110">Requirements</span></span>

<span data-ttu-id="5ad27-111">桌面背景圖片必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="5ad27-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="5ad27-112">圖片檔案格式-.jpg、 jpeg 或.png</span><span class="sxs-lookup"><span data-stu-id="5ad27-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="5ad27-113">檔案位置-信任安全 http (https) 位置上的主機。</span><span class="sxs-lookup"><span data-stu-id="5ad27-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="5ad27-114">不允許-不支援 Http 及檔案共用 (unc) 位置。</span><span class="sxs-lookup"><span data-stu-id="5ad27-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="5ad27-115">自訂及部署桌面背景圖片</span><span class="sxs-lookup"><span data-stu-id="5ad27-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="5ad27-116">**若要新增自訂桌面背景圖片**</span><span class="sxs-lookup"><span data-stu-id="5ad27-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="5ad27-117">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5ad27-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="5ad27-118">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="5ad27-119">**可設定**工作區中選取 [**桌面背景圖片**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="5ad27-120">輸入您想要使用的圖片的位置。</span><span class="sxs-lookup"><span data-stu-id="5ad27-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="5ad27-121">選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-121">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="5ad27-122">瀏覽器開始頁面</span><span class="sxs-lookup"><span data-stu-id="5ad27-122">Browser start pages</span></span>
<span data-ttu-id="5ad27-p103">當您的使用者啟動 Microsoft Edge 個別索引標籤中開啟瀏覽器起始頁面。如果您想要讓您開啟一組他們常用的站台的使用者更容易，新增每個網站的瀏覽器起始頁面。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p103">Browser start pages open in individual tabs when your users start Microsoft Edge. If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="5ad27-125">需求</span><span class="sxs-lookup"><span data-stu-id="5ad27-125">Requirements</span></span>

<span data-ttu-id="5ad27-p104">您必須提供的完整的網域名稱 (FQDN) 的內部網路或網際網路網站的瀏覽器啟動頁面。如果設定內部網站，可讓使用者知道只允許存取這些網站連線至在 office 中的內部網路或時使用 VPN 連線。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p104">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages. If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="5ad27-128">自訂及部署瀏覽器開始頁面</span><span class="sxs-lookup"><span data-stu-id="5ad27-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="5ad27-129">**若要新增的瀏覽器開始頁面**</span><span class="sxs-lookup"><span data-stu-id="5ad27-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="5ad27-130">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5ad27-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="5ad27-131">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="5ad27-132">**可設定**工作區中選取 [**瀏覽器啟動頁面**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="5ad27-133">選取 [**新增起始畫面**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="5ad27-134">在**新增瀏覽器啟動] 頁面上**，輸入您要使用的網站的 URL，然後選取**新增起始畫面**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="5ad27-135">重複步驟 1-5 其他瀏覽器啟動頁面。</span><span class="sxs-lookup"><span data-stu-id="5ad27-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="5ad27-136">選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-136">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="5ad27-137">企業模式的網站清單位置</span><span class="sxs-lookup"><span data-stu-id="5ad27-137">Enterprise mode site list location</span></span>

<span data-ttu-id="5ad27-p105">如果您有特定的網站與您知道有 Microsoft Edge 的相容性問題的應用程式，您可以使用企業模式的網站] 清單中，讓網站會自動開啟使用 Internet Explorer 11。此外，如果您知道您的內部網路網站未移至 Microsoft 邊緣正常運作，您可以設定若要開啟 [自動使用 Internet Explorer 11 的所有內部網路網站。使用企業模式表示您可以繼續為預設瀏覽器中使用 Microsoft Edge 時也確保您的應用程式在 Internet Explorer 11 繼續運作。企業模式網站清單上的詳細資訊，請參閱[企業模式及企業模式網站清單](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p105">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11. Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11. For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="5ad27-142">您可以指定 https:// 位置或內部共用您主控您企業模式的網站清單的位置。</span><span class="sxs-lookup"><span data-stu-id="5ad27-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="5ad27-143">需求</span><span class="sxs-lookup"><span data-stu-id="5ad27-143">Requirements</span></span>

<span data-ttu-id="5ad27-144">企業模式網站清單檔案必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="5ad27-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="5ad27-145">檔案格式-符合[檔案需求](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="5ad27-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="5ad27-146">檔案位置上內部 https 位置的主機檔案。</span><span class="sxs-lookup"><span data-stu-id="5ad27-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="5ad27-147">不允許使用-like *//sharename*、 內部檔案共用上主控不允許</span><span class="sxs-lookup"><span data-stu-id="5ad27-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="5ad27-148">最佳做法</span><span class="sxs-lookup"><span data-stu-id="5ad27-148">Best practices</span></span>

<span data-ttu-id="5ad27-149">下列最佳作法被提供可協助客戶做出現代化其 IT 基礎結構的決策：</span><span class="sxs-lookup"><span data-stu-id="5ad27-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="5ad27-p106">**選擇的網站數目有限**– Microsoft 受管理的桌上型電腦使用慣用的瀏覽器 Microsoft Edge 增進貴組織的整體安全性與使用者的使用性。這份清單中的大部分網站需要將不會包含相同數目的安全性功能的瀏覽器的舊版本的舊版的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p106">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users. Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="5ad27-p107">**考慮替代**– 考慮不同的網站或不需要較舊的瀏覽器的 web 應用程式。或者，請考慮以便其可以使用較新的瀏覽器更新網站。較新的瀏覽器使用的最新技術並協助增進安全性。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p107">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser. Or, consider updating the site so that it can use newer browsers. Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="5ad27-155">自訂及部署企業網站模式] 清單位置</span><span class="sxs-lookup"><span data-stu-id="5ad27-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="5ad27-156">**新增企業網站模式] 清單位置**</span><span class="sxs-lookup"><span data-stu-id="5ad27-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="5ad27-157">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5ad27-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="5ad27-158">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="5ad27-159">**可設定**工作區中選取 [**企業模式的網站清單位置**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="5ad27-160">輸入您的網站清單的 https 位置。</span><span class="sxs-lookup"><span data-stu-id="5ad27-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="5ad27-161">選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-161">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="5ad27-162">受信任的網站</span><span class="sxs-lookup"><span data-stu-id="5ad27-162">Trusted sites</span></span>

<span data-ttu-id="5ad27-p108">信任的網站可讓您自訂安全性區域的外部網路，或站台可使用的針對不同站台。安全性區域包括：</span><span class="sxs-lookup"><span data-stu-id="5ad27-p108">Trusted sites allow you to customize security zones, or where a site can be used, for different sites. Security zones include:</span></span> 
- <span data-ttu-id="5ad27-165">區域 1 – 近端內部網路區域</span><span class="sxs-lookup"><span data-stu-id="5ad27-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="5ad27-166">區域 2 – 信任的網站] 區域</span><span class="sxs-lookup"><span data-stu-id="5ad27-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="5ad27-167">區域 3 – 網際網路區域</span><span class="sxs-lookup"><span data-stu-id="5ad27-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="5ad27-168">區域 4 – 限制的網站] 區域</span><span class="sxs-lookup"><span data-stu-id="5ad27-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="5ad27-169">需求</span><span class="sxs-lookup"><span data-stu-id="5ad27-169">Requirements</span></span>

<span data-ttu-id="5ad27-170">提供內部網路或網際網路網站的每一個受信任的網站的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="5ad27-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="5ad27-171">自訂及部署受信任的網站</span><span class="sxs-lookup"><span data-stu-id="5ad27-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="5ad27-172">**新增信任的網站**</span><span class="sxs-lookup"><span data-stu-id="5ad27-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="5ad27-173">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5ad27-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="5ad27-174">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="5ad27-175">**可設定**工作區中選取 [**信任的網站**，並再選取 [**新增信任的網站**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="5ad27-176">在 [**新增信任的網站**上輸入 URL，並選擇 [安全性區域，然後選取 [**新增信任的網站**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="5ad27-177">針對每一個您想要新增信任的網站重複步驟 1 到 4。</span><span class="sxs-lookup"><span data-stu-id="5ad27-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="5ad27-178">選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-178">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

<span data-ttu-id="5ad27-179">**若要移除信任的網站**</span><span class="sxs-lookup"><span data-stu-id="5ad27-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="5ad27-180">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5ad27-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="5ad27-181">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="5ad27-182">**可設定**工作區中選取 [**信任的網站**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="5ad27-183">選取您要刪除的網站，然後選取 [**刪除**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="5ad27-184">針對每一個您想要刪除信任的網站重複步驟 1 到 4。</span><span class="sxs-lookup"><span data-stu-id="5ad27-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="5ad27-185">選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-185">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="proxy"></a><span data-ttu-id="5ad27-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="5ad27-186">Proxy</span></span>
<span data-ttu-id="5ad27-p109">您可以為組織管理網路 proxy 設定。新增 proxy 伺服器與連接埠號碼，然後再新增 [proxy 網站例外狀況。Microsoft 受管理的桌上型電腦包含一組的預設 proxy 例外狀況所需的操作的服務。僅限可藉由 Microsoft 受管理的桌上型電腦服務修改預設排除清單。 如需詳細資訊，請參閱[Microsoft 受管理的桌上型電腦的網路組態](../get-ready/network.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p109">You can manage network proxy settings for your organization. Add your proxy server and port number, and then add your proxy site exceptions. Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate. The default exclusion list may only be modified by the Microsoft Managed Desktop service.  For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="5ad27-192">您在 Microsoft 受管理的桌上型電腦入口網站中新增的 proxy 網站例外會新增至 Microsoft 受管理的桌上型電腦服務所含的預設 proxy 例外。</span><span class="sxs-lookup"><span data-stu-id="5ad27-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ad27-p110">更新的預設 proxy 例外狀況清單一律透過客戶部署排列優先順序。這表示如果沒有預設 proxy 例外狀況清單的部署，會暫停分段的部署。</span><span class="sxs-lookup"><span data-stu-id="5ad27-p110">Updating the default proxy exception list is always prioritized over customer deployments. This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="5ad27-195">需求</span><span class="sxs-lookup"><span data-stu-id="5ad27-195">Requirements</span></span>

<span data-ttu-id="5ad27-196">Proxy 伺服器和 proxy 網站例外狀況都必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="5ad27-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="5ad27-197">必須是有效的伺服器位址和連接埠號碼</span><span class="sxs-lookup"><span data-stu-id="5ad27-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="5ad27-198">Url 必須是有效的 http 網站</span><span class="sxs-lookup"><span data-stu-id="5ad27-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="5ad27-199">自訂及部署 proxy</span><span class="sxs-lookup"><span data-stu-id="5ad27-199">Customize and deploy proxies</span></span>

<span data-ttu-id="5ad27-200">**若要新增 proxy 個別網站例外狀況**</span><span class="sxs-lookup"><span data-stu-id="5ad27-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="5ad27-201">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="5ad27-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="5ad27-202">[**設定**] 下選取 [**可設定**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="5ad27-203">**可設定**工作區中選取 [ **Proxy**]。</span><span class="sxs-lookup"><span data-stu-id="5ad27-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="5ad27-204">輸入您 proxy 伺服器的**位址**及**連接埠號碼**，然後選取 [**新增 proxy 例外狀況**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="5ad27-205">輸入有效的 http 網站的 URL，然後選取 [**新增 proxy 例外狀況**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="5ad27-206">針對每一個您想要新增信任的網站重複步驟 1-5。</span><span class="sxs-lookup"><span data-stu-id="5ad27-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="5ad27-207">選取 [以儲存變更並將其部署至測試響鈴的**階段部署**。</span><span class="sxs-lookup"><span data-stu-id="5ad27-207">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ad27-208">其他資源</span><span class="sxs-lookup"><span data-stu-id="5ad27-208">Additional resources</span></span>
- [<span data-ttu-id="5ad27-209">組態設定概觀 （英文)</span><span class="sxs-lookup"><span data-stu-id="5ad27-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="5ad27-210">部署組態設定</span><span class="sxs-lookup"><span data-stu-id="5ad27-210">Deploy configurable settings</span></span>](config-setting-deploy.md)