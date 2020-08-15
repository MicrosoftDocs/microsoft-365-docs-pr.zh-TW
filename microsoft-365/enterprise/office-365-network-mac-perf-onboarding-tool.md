---
title: Microsoft 365 connectivity test (preview) Microsoft 365 系統管理中心
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: 'Microsoft 365 connectivity test in M365 Admin Center (預覽) '
ms.openlocfilehash: 421df459e2a8a1c1c62680b2d3658f5bdd297b25
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688538"
---
# <a name="microsoft-365-connectivity-test-in-the-microsoft-365-admin-center-preview"></a><span data-ttu-id="28d61-103">Microsoft 365 connectivity test in the Microsoft 365 admin center (preview) </span><span class="sxs-lookup"><span data-stu-id="28d61-103">Microsoft 365 connectivity test in the Microsoft 365 admin center (preview)</span></span>

<span data-ttu-id="28d61-104">Microsoft 365 connectivity test 位於 <https://connectivity.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="28d61-104">The Microsoft 365 connectivity test is located at <https://connectivity.office.com>.</span></span> <span data-ttu-id="28d61-105">其為輔助工具，可在 Microsoft 365 系統管理中心的 [ **健康情況 |] 底下使用網路洞察力和網路總分資訊。網路效能** 功能表。</span><span class="sxs-lookup"><span data-stu-id="28d61-105">It is an adjunct tool to the network insights and network score information available in the Microsoft 365 admin center under the **Health | Network Performance** menu.</span></span>

>[!NOTE]
><span data-ttu-id="28d61-106">上架工具支援 WW 商業銀行和 GCC 中的承租人，但不支援 GCC 高、DoD、德國或中國的承租人。</span><span class="sxs-lookup"><span data-stu-id="28d61-106">The onboarding tool supports tenants in WW Commercial and GCC Moderate but not GCC High, DoD, Germany or China.</span></span>

<span data-ttu-id="28d61-107">Microsoft 365 系統管理中心的網路洞察力是以 Microsoft 365 租使用者的產品度量為基礎。</span><span class="sxs-lookup"><span data-stu-id="28d61-107">The network insights in the Microsoft 365 Admin Center are based on in-product measurements for your Microsoft 365 tenant.</span></span> <span data-ttu-id="28d61-108">相比之下，來自 Microsoft 365 連線測試的網路洞察力是在本機的工具中執行。</span><span class="sxs-lookup"><span data-stu-id="28d61-108">In comparison, the network insights from the Microsoft 365 connectivity test are run locally in the tool.</span></span> <span data-ttu-id="28d61-109">您可以在產品中執行的測試是有限的，而且在使用者可以收集更多資料的地方執行測試時，可能會產生更深入的洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-109">Testing that can be done in-product is limited and by running tests local to the user more data can be gathered resulting in deeper insights.</span></span> <span data-ttu-id="28d61-110">請考慮，Microsoft 365 系統管理中心的網路洞察力會顯示在特定辦公室位置使用 Microsoft 365 的網路問題。</span><span class="sxs-lookup"><span data-stu-id="28d61-110">Consider then that the network insights in the Microsoft 365 Admin Center will show that there is a networking problem for use of Microsoft 365 at a specific office location.</span></span> <span data-ttu-id="28d61-111">Microsoft 365 連線測試可協助識別導致網路效能改進動作的問題根源。</span><span class="sxs-lookup"><span data-stu-id="28d61-111">The Microsoft 365 connectivity test can help to identify the root cause of that problem leading to a recommended network performance improvement action.</span></span>

<span data-ttu-id="28d61-112">建議您將這些功能搭配使用，讓您可以在 Microsoft 365 系統管理中心中評估每個辦公室位置的網路品質狀態，並且在部署以 Microsoft 365 連線測試為基礎的測試之後找到更多細節。</span><span class="sxs-lookup"><span data-stu-id="28d61-112">We recommend that these be used together where networking quality status can be assessed for each office location in the Microsoft 365 Admin Center and more specifics can be found after deployment of testing based on the Microsoft 365 connectivity test.</span></span>

>[!IMPORTANT]
><span data-ttu-id="28d61-113">Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="28d61-113">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="the-advanced-tests-client-application"></a><span data-ttu-id="28d61-114">高級測試用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="28d61-114">The advanced tests client application</span></span>

<span data-ttu-id="28d61-115">Microsoft 365 connectivity test 有兩個部分。</span><span class="sxs-lookup"><span data-stu-id="28d61-115">There are two parts to the Microsoft 365 connectivity test.</span></span> <span data-ttu-id="28d61-116">網站有可供 <https://connectivity.office.com> 下載的 Windows 用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="28d61-116">There is the web site <https://connectivity.office.com> and there is a downloadable Windows client application.</span></span> <span data-ttu-id="28d61-117">可供下載的用戶端執行高級網路連線測試，大部分的測試都需要執行。</span><span class="sxs-lookup"><span data-stu-id="28d61-117">The downloadable client runs advanced network connectivity tests and most of the tests require this to be run.</span></span>

<span data-ttu-id="28d61-118">您可以從網站執行高級用戶端測試，它會在執行時，將結果填入回網頁。</span><span class="sxs-lookup"><span data-stu-id="28d61-118">You can run the advanced client test from the web site, and it will populate results back into the web page as it runs.</span></span>

![O365 網路上架工具範例測試結果](../media/m365-mac-perf/m365-mac-perf-onboarding-tool-tests.png)

## <a name="user-office-location"></a><span data-ttu-id="28d61-120">使用者辦公室位置</span><span class="sxs-lookup"><span data-stu-id="28d61-120">User office location</span></span>

<span data-ttu-id="28d61-121">使用者辦公室位置是從使用者網頁瀏覽器中偵測到。</span><span class="sxs-lookup"><span data-stu-id="28d61-121">The user office location is detected from the users web browser.</span></span> <span data-ttu-id="28d61-122">用來識別商業網路周邊特定部分的網路距離。</span><span class="sxs-lookup"><span data-stu-id="28d61-122">It is used to identify network distances to specific parts of the enterprise network perimeter.</span></span>

<span data-ttu-id="28d61-123">使用者辦公室位置會顯示在地圖視圖上。</span><span class="sxs-lookup"><span data-stu-id="28d61-123">The user office location is shown on the map view.</span></span>

## <a name="distance-to-the-network-egress-location"></a><span data-ttu-id="28d61-124">網路出局位置的距離</span><span class="sxs-lookup"><span data-stu-id="28d61-124">Distance to the network egress location</span></span>

<span data-ttu-id="28d61-125">我們會在伺服器端識別網路出局 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="28d61-125">We identify the network egress IP Address on the server side.</span></span> <span data-ttu-id="28d61-126">位置資料庫是用來查詢網路出口的大致位置，並決定從該位置到辦公室位置的距離。</span><span class="sxs-lookup"><span data-stu-id="28d61-126">Location databases are used to look up the approximate location for the network egress and determine the distance from that location to the office location.</span></span> <span data-ttu-id="28d61-127">如果距離大於500英里 (800 公里) 會顯示為網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-127">This is shown as a network insight if the distance is greater than 500 miles (800 kilometers).</span></span>

<span data-ttu-id="28d61-128">網路出局位置會顯示在地圖視圖上，並聯機至使用者辦公室位置，表示企業 WAN 內部的網路 backhaul。</span><span class="sxs-lookup"><span data-stu-id="28d61-128">The network egress location is shown on the map view and connected to the user office location indicating the network backhaul inside of the enterprise WAN.</span></span>

<span data-ttu-id="28d61-129">從網路出局 IP 位址查看的位置可能不正確，這會導致此測試的錯誤結果。</span><span class="sxs-lookup"><span data-stu-id="28d61-129">The location looked up from the network egress IP Address may not be accurate and this would lead to a false result from this test.</span></span> <span data-ttu-id="28d61-130">若要驗證特定 IP 位址是否發生此錯誤，您可以使用可公開存取的網路 IP 位址位置網站。</span><span class="sxs-lookup"><span data-stu-id="28d61-130">To validate if this error is occurring for a specific IP Address you can use publicly accessible network IP Address location web sites.</span></span>

<span data-ttu-id="28d61-131">建議使用 Microsoft 365 網路連線，將使用者辦公室位置的本機和直接網路輸出實施至網際網路。</span><span class="sxs-lookup"><span data-stu-id="28d61-131">Implementing local and direct network egress from user office locations to the Internet is recommended for Microsoft 365 network connectivity.</span></span> <span data-ttu-id="28d61-132">對本機和直接出口的增強功能是解決這種網路洞察力的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="28d61-132">Improvements to local and direct egress are the best way to address this network insight.</span></span>

## <a name="exchange-online-service-front-door"></a><span data-ttu-id="28d61-133">Exchange Online 服務前面門</span><span class="sxs-lookup"><span data-stu-id="28d61-133">Exchange Online service front door</span></span>

<span data-ttu-id="28d61-134">「使用中 Exchange Online 服務前門」是以 Outlook 這麼做的相同方式來識別，我們會從使用者辦公室位置測量網路的 TCP 延遲。</span><span class="sxs-lookup"><span data-stu-id="28d61-134">The in-use Exchange Online service front door is identified in the same way that Outlook does this and we measure the network TCP latency from the user office location to it.</span></span> <span data-ttu-id="28d61-135">這兩種都是顯示的，與目前位置的建議最佳服務前端門清單相較。</span><span class="sxs-lookup"><span data-stu-id="28d61-135">These are both shown and the in-use Exchange Online service front door is compared to the list of recommended optimal service front doors for the current location.</span></span> <span data-ttu-id="28d61-136">如果使用非最佳 Exchange Online 服務前門，這會顯示為網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-136">This is shown as a network insight if a non-optimal Exchange Online service front door is in use.</span></span>

<span data-ttu-id="28d61-137">使用非最優 Exchange Online 服務前門可能是由網路 backhaul 在公司網路出口之前所造成，因此我們建議您在本機和直接的網路出口。</span><span class="sxs-lookup"><span data-stu-id="28d61-137">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="28d61-138">這種情況也可能是使用遠端 DNS 遞迴解析伺服器所造成，在此情況下，我們建議您將 DNS 遞迴解析程式伺服器與網路出局對齊。</span><span class="sxs-lookup"><span data-stu-id="28d61-138">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

<span data-ttu-id="28d61-139">我們計算對 Exchange Online 服務前門的 TCP 延遲的潛在改進。</span><span class="sxs-lookup"><span data-stu-id="28d61-139">We calculate a potential improvement in TCP latency to the Exchange Online service front door.</span></span> <span data-ttu-id="28d61-140">若要執行此動作，請查看已測試的使用者 office 位置網路延遲，並從目前的位置減去網路延遲，以 closets Exchange Online 服務前門。</span><span class="sxs-lookup"><span data-stu-id="28d61-140">This is done by looking at the tested user office location network latency and subtracting the network latency from the current location to the closets Exchange Online service front door.</span></span> <span data-ttu-id="28d61-141">差異代表潛在的改進機會。</span><span class="sxs-lookup"><span data-stu-id="28d61-141">The difference represents the potential opportunity for improvement.</span></span>

## <a name="comparison-of-performance-of-customers-in-the-area"></a><span data-ttu-id="28d61-142">區域中客戶效能的比較</span><span class="sxs-lookup"><span data-stu-id="28d61-142">Comparison of performance of customers in the area</span></span>

<span data-ttu-id="28d61-143">Exchange Online 服務前端的使用者辦公室位置的網路 TCP 延遲會與其他 Microsoft 365 客戶在相同大都市區域中進行比較。</span><span class="sxs-lookup"><span data-stu-id="28d61-143">The network TCP latency of the user office location to the Exchange Online service front door is compared to other Microsoft 365 customers in the same metro area.</span></span> <span data-ttu-id="28d61-144">如果相同地鐵區域中10% 以上的客戶都具有較佳的效能，就會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-144">A network insight is shown if 10% or more of customers in the same metro area have better performance.</span></span>

<span data-ttu-id="28d61-145">在城市中的所有使用者都可以存取相同的電信基礎結構，以及對網際網路電路和 Microsoft 網路的接近程度，就會產生網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-145">This network insight is generated on the basis that all users in a city have access to the same telecommunications infrastructure and the same proximity to Internet circuits and Microsoft's network.</span></span>

## <a name="in-use-default-gateway"></a><span data-ttu-id="28d61-146">使用預設閘道</span><span class="sxs-lookup"><span data-stu-id="28d61-146">In use default gateway</span></span>

<span data-ttu-id="28d61-147">「使用中的預設閘道」是測試用戶端為路由 TCP/IP 網路連線所設定的路由器。</span><span class="sxs-lookup"><span data-stu-id="28d61-147">The in-use default gateway is the router that the test client has configured for routing TCP/IP network connections.</span></span>

<span data-ttu-id="28d61-148">這只是為了提供資訊，不會參與任何網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-148">This is provided for information only and does not contribute to any network insight.</span></span>

## <a name="in-use-dns-servers"></a><span data-ttu-id="28d61-149">在 [使用 DNS 伺服器 (s) </span><span class="sxs-lookup"><span data-stu-id="28d61-149">In use DNS server(s)</span></span>

<span data-ttu-id="28d61-150">這會顯示在執行測試的用戶端電腦上設定的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="28d61-150">This shows the DNS server configured on the client machine that ran the tests.</span></span> <span data-ttu-id="28d61-151">它可能是 DNS 遞迴解析器伺服器，但這不常見。</span><span class="sxs-lookup"><span data-stu-id="28d61-151">It might be a DNS Recursive Resolver server however this is uncommon.</span></span> <span data-ttu-id="28d61-152">這很可能是 DNS 轉寄站伺服器，可快取 DNS 結果並將任何未緩存的 DNS 要求轉送至另一部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="28d61-152">It is more likely to be a DNS forwarder server which caches DNS results and forwards any uncached DNS requests to another DNS server.</span></span>

<span data-ttu-id="28d61-153">這只是為了提供資訊，不會參與任何網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-153">This is provided for information only and does not contribute to any network insight.</span></span>

## <a name="identified-dns-recursive-resolver-server"></a><span data-ttu-id="28d61-154">已識別 DNS 遞迴解析程式伺服器</span><span class="sxs-lookup"><span data-stu-id="28d61-154">Identified DNS Recursive Resolver server</span></span>

<span data-ttu-id="28d61-155">在 [使用中的 DNS 遞迴解析程式] 中，進行特定的 DNS 要求，然後要求 DNS 名稱伺服器接收相同的要求時，便會加以識別。</span><span class="sxs-lookup"><span data-stu-id="28d61-155">The in-use DNS Recursive Resolver is identified by making a specific DNS request and then asking the DNS Name Server for the IP Address that it received the same request from.</span></span> <span data-ttu-id="28d61-156">此 IP 位址是 DNS 遞迴解析程式，它會在 IP 位址位置資料庫中查閱，以尋找位置。</span><span class="sxs-lookup"><span data-stu-id="28d61-156">This IP Address is the DNS Recursive Resolver and it will be looked up in IP Address location databases to find the location.</span></span> <span data-ttu-id="28d61-157">然後計算從使用者辦公室位置到 DNS 遞迴解析伺服器位置的距離。</span><span class="sxs-lookup"><span data-stu-id="28d61-157">The distance from the user office location to the DNS Recursive Resolver server location is then calculated.</span></span> <span data-ttu-id="28d61-158">如果距離大於500英里 (800 公里) 會顯示為網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-158">This is shown as a network insight if the distance is greater than 500 miles (800 kilometers).</span></span>

<span data-ttu-id="28d61-159">從網路出局 IP 位址查看的位置可能不正確，這會導致此測試的錯誤結果。</span><span class="sxs-lookup"><span data-stu-id="28d61-159">The location looked up from the network egress IP Address may not be accurate and this would lead to a false result from this test.</span></span> <span data-ttu-id="28d61-160">若要驗證特定 IP 位址是否發生此錯誤，您可以使用可公開存取的網路 IP 位址位置網站。</span><span class="sxs-lookup"><span data-stu-id="28d61-160">To validate if this error is occurring for a specific IP Address you can use publicly accessible network IP Address location web sites.</span></span>

<span data-ttu-id="28d61-161">這項網路洞察力特別會影響 Exchange Online 服務前端的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="28d61-161">This network insight will specifically impact the selection of the Exchange Online service front door.</span></span> <span data-ttu-id="28d61-162">若要解決此深入瞭解，本機和 direct 網路出局應該是必要條件，而且 DNS 遞迴解析器應該位於該網路出口之外。</span><span class="sxs-lookup"><span data-stu-id="28d61-162">To address this insight local and direct network egress should be a pre-requisite and then DNS Recursive Resolver should be located close to that network egress.</span></span>

## <a name="dns-lookup-of-exchange-online-front-end-server-and-sharepoint-online-front-end-server"></a><span data-ttu-id="28d61-163">Exchange Online 前端伺服器及 SharePoint 線上前端伺服器的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="28d61-163">DNS lookup of Exchange Online front end server and SharePoint Online front end server</span></span>

<span data-ttu-id="28d61-164">這些會顯示這兩種 Microsoft 365 工作負載的服務前門的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="28d61-164">These show the DNS record for the service front door for these two Microsoft 365 workloads.</span></span> <span data-ttu-id="28d61-165">它們僅供參考，而且沒有相關聯的網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-165">They are provided for information only and there is no associated network insight.</span></span>

## <a name="proxy-server-identification"></a><span data-ttu-id="28d61-166">Proxy 伺服器識別</span><span class="sxs-lookup"><span data-stu-id="28d61-166">Proxy server identification</span></span>

<span data-ttu-id="28d61-167">我們識別在本機電腦上設定的 proxy 伺服器 (s) 。</span><span class="sxs-lookup"><span data-stu-id="28d61-167">We identify proxy server(s) configured on the local machine.</span></span> <span data-ttu-id="28d61-168">我們會識別是否有任何在網路路徑中設定，以優化類別 Microsoft 365 網路流量。</span><span class="sxs-lookup"><span data-stu-id="28d61-168">We identify if any of these are configured in the network path for optimize category Microsoft 365 network traffic.</span></span> <span data-ttu-id="28d61-169">我們識別從使用者辦公室位置到 proxy 伺服器的距離。</span><span class="sxs-lookup"><span data-stu-id="28d61-169">We identify the distance from the user office location to the proxy servers.</span></span> <span data-ttu-id="28d61-170">會先透過 ICMP ping 測試距離，如果失敗，我們會使用 TCP ping 進行測試，最後如果失敗，我們會在 IP 位址位置資料庫中查詢 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="28d61-170">The distance is tested first by ICMP ping and if that fails we test with TCP ping and finally if that fails we look up the proxy server IP Address in an IP Address location database.</span></span> <span data-ttu-id="28d61-171">如果 proxy 伺服器的500英里後超過英里 (800 公里) 離開使用者辦公室位置，我們就會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-171">We show a network insight if the proxy server is further than 500 miles (800 kilometers) away from the user office location.</span></span>

## <a name="media-quality-checks"></a><span data-ttu-id="28d61-172">媒體質量檢查</span><span class="sxs-lookup"><span data-stu-id="28d61-172">Media quality checks</span></span>

<span data-ttu-id="28d61-173">此測試會安裝並執行商務用 Skype 網路評估工具，並解釋結果。</span><span class="sxs-lookup"><span data-stu-id="28d61-173">This test installs and runs the Skype for Business network assessment tool and interprets the results.</span></span> <span data-ttu-id="28d61-174">可在上找到工具 [https://www.microsoft.com/download/details.aspx?id=53885](https://www.microsoft.com/download/details.aspx?id=53885) 。</span><span class="sxs-lookup"><span data-stu-id="28d61-174">The tool can be found at [https://www.microsoft.com/download/details.aspx?id=53885](https://www.microsoft.com/download/details.aspx?id=53885).</span></span>

<span data-ttu-id="28d61-175">這些是 Microsoft 小組音訊和視頻通話及會議功能所使用的 UDP 通訊協定測試。</span><span class="sxs-lookup"><span data-stu-id="28d61-175">These are UDP protocol tests as is used by Microsoft Teams audio and video call and conferencing functionality.</span></span> <span data-ttu-id="28d61-176">我們測試 UDP 封包遺失、UDP 網路延遲、UDP 抖動及 UDP 封包重新排序。</span><span class="sxs-lookup"><span data-stu-id="28d61-176">We test for UDP packet loss, UDP network latency, UDP jitter, and UDP packet reorder.</span></span> <span data-ttu-id="28d61-177">如果有任何一種情況超出允許的範圍，就會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-177">A network insight is shown if any of these are over the allowable range.</span></span>

## <a name="tcp-connectivity-tests"></a><span data-ttu-id="28d61-178">TCP 連線測試</span><span class="sxs-lookup"><span data-stu-id="28d61-178">TCP Connectivity tests</span></span>

<span data-ttu-id="28d61-179">我們會將使用者辦公室位置的 HTTP 連線測試至所有必要的 Microsoft 365 網路端點。</span><span class="sxs-lookup"><span data-stu-id="28d61-179">We test for HTTP connectivity from the user office location to all of the required Microsoft 365 network endpoints.</span></span> <span data-ttu-id="28d61-180">這些是發佈于 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。</span><span class="sxs-lookup"><span data-stu-id="28d61-180">These are published at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="28d61-181">對於任何無法連線的必要網路端點，都會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-181">A network insight is shown for any required network endpoints which cannot be connected to.</span></span>

<span data-ttu-id="28d61-182">在商業網路周邊或使用做為雲端 proxy 的 proxy 伺服器、防火牆或其他網路安全裝置封鎖連線能力 ay。</span><span class="sxs-lookup"><span data-stu-id="28d61-182">Connectivity ay be blocked by a proxy server, a firewall, or another network security device on the enterprise network perimeter or in use as a cloud proxy.</span></span>

## <a name="ssl-interception-tests"></a><span data-ttu-id="28d61-183">SSL 截取測試</span><span class="sxs-lookup"><span data-stu-id="28d61-183">SSL interception tests</span></span>

<span data-ttu-id="28d61-184">我們會在每個必要的 Microsoft 365 網路端點（已于所定義的 [優化] 或 [允許] 類別中）測試 SSL 憑證 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。</span><span class="sxs-lookup"><span data-stu-id="28d61-184">We test the SSL certificate at each required Microsoft 365 network endpoint that is in the optimize or allow category as defined at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="28d61-185">如果任何測試未找到 Microsoft SSL 憑證，則所連接的加密網路必須已被仲介網路裝置截獲。</span><span class="sxs-lookup"><span data-stu-id="28d61-185">If any tests do not find a Microsoft SSL certificate, then the encrypted network connected must have been intercepted by an intermediary network device.</span></span> <span data-ttu-id="28d61-186">網路洞察力會顯示在任何截獲的加密網路端點上。</span><span class="sxs-lookup"><span data-stu-id="28d61-186">A network insight is shown on any intercepted encrypted network endpoints.</span></span>

<span data-ttu-id="28d61-187">如果 Microsoft 未提供 SSL 憑證，我們會顯示測試的 FQDN 和使用中的 SSL 憑證擁有者。</span><span class="sxs-lookup"><span data-stu-id="28d61-187">Where an SSL certificate is found that isn't provided by Microsoft, we show the FQDN for the test and the in-use SSL certificate owner.</span></span> <span data-ttu-id="28d61-188">這個 SSL 憑證擁有者可能是 proxy 伺服器廠商，也可能是企業自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="28d61-188">This SSL certificate owner may be a proxy server vendor, or it may be an enterprise self-signed certificate.</span></span>

## <a name="network-path-diagnostics"></a><span data-ttu-id="28d61-189">網路路徑診斷</span><span class="sxs-lookup"><span data-stu-id="28d61-189">Network path diagnostics</span></span>

<span data-ttu-id="28d61-190">本節顯示 ICMP traceroute 至 Exchange Online 服務前門、SharePoint Online 服務前門和 Microsoft 團隊服務前門的結果。</span><span class="sxs-lookup"><span data-stu-id="28d61-190">This section shows the results of an ICMP traceroute to the Exchange Online service front door, the SharePoint Online service front door, and the Microsoft Teams service front door.</span></span> <span data-ttu-id="28d61-191">只提供此資訊，而且沒有相關聯的網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="28d61-191">It is provided for information only and there is no associated network insight.</span></span>

## <a name="faq"></a><span data-ttu-id="28d61-192">常見問題集</span><span class="sxs-lookup"><span data-stu-id="28d61-192">FAQ</span></span>

<span data-ttu-id="28d61-193">以下是一些常見問題的解答。</span><span class="sxs-lookup"><span data-stu-id="28d61-193">Here are answers to some of our frequently asked questions.</span></span>

### <a name="is-this-tool-released-and-supported-by-microsoft"></a><span data-ttu-id="28d61-194">Microsoft 是否已發行及支援此工具？</span><span class="sxs-lookup"><span data-stu-id="28d61-194">Is this tool released and supported by Microsoft?</span></span>

<span data-ttu-id="28d61-195">這是一項概念證明，我們計畫定期提供更新，直到我們達到一般可用性發行狀態時，才會從 Microsoft 取得支援。</span><span class="sxs-lookup"><span data-stu-id="28d61-195">It is currently a proof of concept and we plan to provide updates regularly until we reach general availability release status with support from Microsoft.</span></span> <span data-ttu-id="28d61-196">請提供意見反應以協助我們改進。</span><span class="sxs-lookup"><span data-stu-id="28d61-196">Please provide feedback to help us improve.</span></span> <span data-ttu-id="28d61-197">我們打算將更詳細的 Office 365 網路上架指南發佈為此工具的一部分，此工具是由其測試結果自訂為組織的一部分。</span><span class="sxs-lookup"><span data-stu-id="28d61-197">We are planning to publish a more detailed Office 365 Network Onboarding guide as part of this tool which is customized for the organization by its test results.</span></span>

### <a name="what-is-microsoft-365-service-front-door"></a><span data-ttu-id="28d61-198">何謂 Microsoft 365 服務的前門？</span><span class="sxs-lookup"><span data-stu-id="28d61-198">What is Microsoft 365 service front door?</span></span>

<span data-ttu-id="28d61-199">Microsoft 365 服務前端是 Microsoft 全球網路的進入點，Office 用戶端和服務會在此位置中斷其網路連線。</span><span class="sxs-lookup"><span data-stu-id="28d61-199">The Microsoft 365 service front door is an entry point on Microsoft's global network where Office clients and services terminate their network connection.</span></span> <span data-ttu-id="28d61-200">為了獲得最佳網路連接至 Microsoft 365，建議您的網路連線在您的城市或地鐵的最接近的 Microsoft 365 前端。</span><span class="sxs-lookup"><span data-stu-id="28d61-200">For an optimal network connection to Microsoft 365, it is recommended that your network connection is terminated into the closest Microsoft 365 front door in your city or metro.</span></span>

<span data-ttu-id="28d61-201">附注： Microsoft 365 服務前端與 Azure marketplace 中提供的「Azure 前門服務」產品沒有直接關聯。</span><span class="sxs-lookup"><span data-stu-id="28d61-201">Note: Microsoft 365 service front door has no direct relationship to the "Azure Front Door Service" product available in the Azure marketplace.</span></span>

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a><span data-ttu-id="28d61-202">何謂最優的 Microsoft 365 服務前門？</span><span class="sxs-lookup"><span data-stu-id="28d61-202">What is an optimal Microsoft 365 service front door?</span></span>

<span data-ttu-id="28d61-203">最佳的 Microsoft 365 服務前端是最接近您的網路出局，通常是在您的城市或大都市區域中。</span><span class="sxs-lookup"><span data-stu-id="28d61-203">An optimal Microsoft 365 service front door is one that is closest to your network egress, generally in your city or metro area.</span></span> <span data-ttu-id="28d61-204">使用 Microsoft 365 網路效能工具判斷您使用中的 Microsoft 365 服務前門和最優服務前門的位置。</span><span class="sxs-lookup"><span data-stu-id="28d61-204">Use the Microsoft 365 network performance tool to determine location of your in-use Microsoft 365 service front door and optimal service front door.</span></span> <span data-ttu-id="28d61-205">如果工具判斷您的使用中的前門是最優的，您就會以最優化方式連線至 Microsoft 的全球網路。</span><span class="sxs-lookup"><span data-stu-id="28d61-205">If the tool determines your in-use front door is optimal, then you are optimally connecting into Microsoft's global network.</span></span>

### <a name="what-is-an-internet-egress-location"></a><span data-ttu-id="28d61-206">何謂網際網路出口的位置？</span><span class="sxs-lookup"><span data-stu-id="28d61-206">What is an internet egress location?</span></span>

<span data-ttu-id="28d61-207">網際網路出局位置是網路流量結束商業網路並連接到網際網路的位置。</span><span class="sxs-lookup"><span data-stu-id="28d61-207">The internet egress Location is the location where your network traffic exits your enterprise network and connects to the Internet.</span></span> <span data-ttu-id="28d61-208">此位置也會識別為您具有網路位址轉譯 (NAT) 裝置的位置，通常是您與網際網路服務提供者 (ISP) 的位置。</span><span class="sxs-lookup"><span data-stu-id="28d61-208">This is also identified as the location where you have a Network Address Translation (NAT) device and usually where you connect with an Internet Service Provider (ISP).</span></span> <span data-ttu-id="28d61-209">如果您看到位置和網際網路出局位置之間有長距離的距離，則這可能會識別重要的 WAN backhaul。</span><span class="sxs-lookup"><span data-stu-id="28d61-209">If you see a long distance between your location and your internet egress Location, then this may identify a significant WAN backhaul.</span></span>

## <a name="related-topics"></a><span data-ttu-id="28d61-210">相關主題</span><span class="sxs-lookup"><span data-stu-id="28d61-210">Related topics</span></span>

[<span data-ttu-id="28d61-211">Microsoft 365 系統管理中心的網路效能建議 (預覽) </span><span class="sxs-lookup"><span data-stu-id="28d61-211">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="28d61-212">Microsoft 365 網路效能深入 (預覽) </span><span class="sxs-lookup"><span data-stu-id="28d61-212">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="28d61-213">Microsoft 365 網路評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="28d61-213">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="28d61-214">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="28d61-214">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
