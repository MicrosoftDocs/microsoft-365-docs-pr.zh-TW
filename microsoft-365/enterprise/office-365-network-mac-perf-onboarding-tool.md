---
title: 'Microsoft 365 network connectivity test 工具 (預覽) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: 'Microsoft 365 network connectivity test 工具 (預覽) '
ms.openlocfilehash: b29eb29cd390c3febd0992e942cf8ab39f652fb2
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "49569984"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a><span data-ttu-id="44f9b-103">Microsoft 365 network connectivity test 工具 (預覽) </span><span class="sxs-lookup"><span data-stu-id="44f9b-103">Microsoft 365 network connectivity test tool (preview)</span></span>

<span data-ttu-id="44f9b-104">Microsoft 365 network connectivity test 工具位於 <https://connectivity.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="44f9b-104">The Microsoft 365 network connectivity test tool is located at <https://connectivity.office.com>.</span></span> <span data-ttu-id="44f9b-105">其為輔助工具，可在 Microsoft 365 系統管理中心的 [ **健康情況 |] 底下使用網路評估和網路洞察力資訊。連接** 功能表。</span><span class="sxs-lookup"><span data-stu-id="44f9b-105">It is an adjunct tool to the network assessment and network insights information available in the Microsoft 365 admin center under the **Health | Connectivity** menu.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44f9b-106">請務必登入您的 Microsoft 365 租使用者，因為在您登入時，所有的測試報告都會與您的系統管理員共用，並上傳至租使用者。</span><span class="sxs-lookup"><span data-stu-id="44f9b-106">It is important to sign in to your Microsoft 365 tenant as all test reports are shared with your administrator and uploaded to the tenant while you are signed in.</span></span>

![Connectivity test 工具](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
><span data-ttu-id="44f9b-108">Network connectivity test 工具支援位於 WW 和德國的承租人，但不支援 GCC 適中、GCC 高、DoD 或中國。</span><span class="sxs-lookup"><span data-stu-id="44f9b-108">The network connectivity test tool supports tenants in WW Commercial and Germany but not GCC Moderate, GCC High, DoD or China.</span></span>

<span data-ttu-id="44f9b-109">Microsoft 365 系統管理中心的網路洞察力是以週期性產品測量值為基礎，針對每日進行匯總的 Microsoft 365 租使用者。</span><span class="sxs-lookup"><span data-stu-id="44f9b-109">The network insights in the Microsoft 365 Admin Center are based on regular in-product measurements for your Microsoft 365 tenant which are aggregated each day.</span></span> <span data-ttu-id="44f9b-110">相比之下，來自 Microsoft 365 網路連線測試的網路洞察力會在本機執行，並在工具中執行一次。</span><span class="sxs-lookup"><span data-stu-id="44f9b-110">In comparison, the network insights from the Microsoft 365 network connectivity test are run locally and one time in the tool.</span></span> <span data-ttu-id="44f9b-111">您可以在產品中執行的測試是有限的，而且在使用者可以收集更多資料的地方執行測試時，可能會產生更深入的洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-111">Testing that can be done in-product is limited and by running tests local to the user more data can be gathered resulting in deeper insights.</span></span> <span data-ttu-id="44f9b-112">請考慮，Microsoft 365 系統管理中心的網路洞察力會顯示在特定辦公室位置使用 Microsoft 365 的網路問題。</span><span class="sxs-lookup"><span data-stu-id="44f9b-112">Consider then that the network insights in the Microsoft 365 Admin Center will show that there is a networking problem for use of Microsoft 365 at a specific office location.</span></span> <span data-ttu-id="44f9b-113">Microsoft 365 連線測試可協助識別導致網路效能改進動作的問題根源。</span><span class="sxs-lookup"><span data-stu-id="44f9b-113">The Microsoft 365 connectivity test can help to identify the root cause of that problem leading to a recommended network performance improvement action.</span></span>

<span data-ttu-id="44f9b-114">建議您將這些功能搭配使用，讓您可以在 Microsoft 365 系統管理中心中評估每個辦公室位置的網路品質狀態，並且在部署以 Microsoft 365 連線測試為基礎的測試之後找到更多細節。</span><span class="sxs-lookup"><span data-stu-id="44f9b-114">We recommend that these be used together where networking quality status can be assessed for each office location in the Microsoft 365 Admin Center and more specifics can be found after deployment of testing based on the Microsoft 365 connectivity test.</span></span>

>[!IMPORTANT]
><span data-ttu-id="44f9b-115">Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。</span><span class="sxs-lookup"><span data-stu-id="44f9b-115">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="what-happens-at-each-test-step"></a><span data-ttu-id="44f9b-116">每個測試步驟會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="44f9b-116">What happens at each test step</span></span>

### <a name="office-location-identification"></a><span data-ttu-id="44f9b-117">辦公室位置識別</span><span class="sxs-lookup"><span data-stu-id="44f9b-117">Office location identification</span></span>

<span data-ttu-id="44f9b-118">當您按一下 [執行測試] 按鈕時，會顯示 [正在執行的測試] 頁面，並識別辦公室位置。</span><span class="sxs-lookup"><span data-stu-id="44f9b-118">When you click the run test button we show the running test page and identify the office location.</span></span> <span data-ttu-id="44f9b-119">您可以使用城市、州和國家輸入您的位置，也可以從網頁瀏覽器中偵測到該位置。</span><span class="sxs-lookup"><span data-stu-id="44f9b-119">You can type in your location by city, state, and country or you can have it detected from the web browser.</span></span> <span data-ttu-id="44f9b-120">如果您偵測到這種情況，我們會從網頁瀏覽器要求緯度和經度，並在使用之前限制 300m 300m 的精確度。</span><span class="sxs-lookup"><span data-stu-id="44f9b-120">If you detect it then we request the latitude and longitude from the web browser and limit the accuracy to 300m by 300m before use.</span></span> <span data-ttu-id="44f9b-121">之所以這麼做，是因為不需要更正確地識別位置，而不是網路效能的大樓。</span><span class="sxs-lookup"><span data-stu-id="44f9b-121">We do this because it is not necessary to identify the location more accurately than the building for network performance.</span></span> 

### <a name="javascript-tests"></a><span data-ttu-id="44f9b-122">JavaScript 測試</span><span class="sxs-lookup"><span data-stu-id="44f9b-122">JavaScript tests</span></span>

<span data-ttu-id="44f9b-123">在 office 位置識別後，我們會在 JavaScript 中執行 TCP 延遲測試，我們會向服務要求有關使用中及建議的 Office 365 服務前端伺服器的資料。</span><span class="sxs-lookup"><span data-stu-id="44f9b-123">After office location identification we run a TCP latency test in JavaScript and we request data from the service about in-use and recommended Office 365 service front door servers.</span></span> <span data-ttu-id="44f9b-124">完成這些工作之後，我們會在地圖和 [詳細資料] 索引標籤中顯示它們，以在下一個步驟之前查看。</span><span class="sxs-lookup"><span data-stu-id="44f9b-124">When these are completed we show them on the map and in the details tab where they can be viewed prior to the next step.</span></span>

### <a name="download-the-advanced-tests-client-application"></a><span data-ttu-id="44f9b-125">下載高級測試用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="44f9b-125">Download the advanced tests client application</span></span>

<span data-ttu-id="44f9b-126">接下來，我們將開始下載高級測試用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="44f9b-126">Next we start the download of the advanced tests client application.</span></span> <span data-ttu-id="44f9b-127">我們依靠使用者來啟動用戶端應用程式，而且也必須已安裝 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="44f9b-127">We rely on the user to launch the client application and they must also have .NET Core installed.</span></span>

<span data-ttu-id="44f9b-128">Microsoft 365 網路連線測試有兩個部分; <https://connectivity.office.com> 可執行高級網路連線測試的網站和可下載的 Windows 用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="44f9b-128">There are two parts to the Microsoft 365 network connectivity test; the web site <https://connectivity.office.com> and a downloadable Windows client application that runs advanced network connectivity tests.</span></span> <span data-ttu-id="44f9b-129">大部分的測試都需要執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="44f9b-129">Most of the tests require the application to be run.</span></span> <span data-ttu-id="44f9b-130">它會在執行時，將結果填回網頁。</span><span class="sxs-lookup"><span data-stu-id="44f9b-130">It will populate results back into the web page as it runs.</span></span>

<span data-ttu-id="44f9b-131">網頁瀏覽器測試完成後，系統會提示您從網站下載高級用戶端測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="44f9b-131">You will be prompted to download the advanced client test application from the web site after the web browser tests have completed.</span></span> <span data-ttu-id="44f9b-132">出現提示時，開啟並執行檔。</span><span class="sxs-lookup"><span data-stu-id="44f9b-132">Open and run the file when prompted.</span></span>

![高級測試用戶端應用程式](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a><span data-ttu-id="44f9b-134">啟動 [高級測試] 用戶端應用程式</span><span class="sxs-lookup"><span data-stu-id="44f9b-134">Start the advanced tests client application</span></span>

<span data-ttu-id="44f9b-135">一旦用戶端應用程式啟動網頁，便會更新以顯示這種情況，而且測試資料將會開始接收到網頁。</span><span class="sxs-lookup"><span data-stu-id="44f9b-135">Once the client application starts the web page will update to show this and test data will start to be received to the web page.</span></span> <span data-ttu-id="44f9b-136">它會在每次接收新資料時更新，您可以在資料到達時查看資料。</span><span class="sxs-lookup"><span data-stu-id="44f9b-136">It updates each time new data is received and you can review the data as it arrives.</span></span>

### <a name="advanced-tests-completed-and-test-report-upload"></a><span data-ttu-id="44f9b-137">已完成的高級測試及測試報表上載</span><span class="sxs-lookup"><span data-stu-id="44f9b-137">Advanced tests completed and test report upload</span></span>

<span data-ttu-id="44f9b-138">測試完成後，網頁和高級測試用戶端會同時指出這一點，而且如果使用者已登入測試報告，就會將其上傳至客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="44f9b-138">Once the tests are completed the web page and the advanced tests client will both indicate this and if the user is signed in the test report will be uploaded to the customers tenant.</span></span>

## <a name="sharing-your-test-report"></a><span data-ttu-id="44f9b-139">共用您的測試報告</span><span class="sxs-lookup"><span data-stu-id="44f9b-139">Sharing your test report</span></span>

<span data-ttu-id="44f9b-140">測試報表需要登入您的 Office 365 帳戶。</span><span class="sxs-lookup"><span data-stu-id="44f9b-140">The test report requires sign-in to your Office 365 account.</span></span> <span data-ttu-id="44f9b-141">您的系統管理員會選取如何共用您的測試報告。</span><span class="sxs-lookup"><span data-stu-id="44f9b-141">Your administrator selects how you can share your test report.</span></span>

### <a name="sharing-your-report-with-your-administrator"></a><span data-ttu-id="44f9b-142">與系統管理員共用您的報表</span><span class="sxs-lookup"><span data-stu-id="44f9b-142">Sharing your report with your administrator</span></span>

<span data-ttu-id="44f9b-143">登入時的所有測試報告都會與您的系統管理員共用。</span><span class="sxs-lookup"><span data-stu-id="44f9b-143">All test reports while you are signed in are shared with your administrator.</span></span>

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a><span data-ttu-id="44f9b-144">與您的 Microsoft 帳戶小組、支援或其他人員共用</span><span class="sxs-lookup"><span data-stu-id="44f9b-144">Sharing with your Microsoft account team, support or other personnel</span></span>

<span data-ttu-id="44f9b-145">不含任何個人身分識別的測試報告會與 Microsoft 員工共用。</span><span class="sxs-lookup"><span data-stu-id="44f9b-145">Test reports excluding any personal identification are shared with Microsoft employees.</span></span> <span data-ttu-id="44f9b-146">預設為啟用，您的系統管理員可以在 **健康情況 | 中停用此項。** Microsoft 365 系統管理中心的 [網路連接] 頁面。</span><span class="sxs-lookup"><span data-stu-id="44f9b-146">This is enabled by default and can be disabled by your administrator in the **Health | Network Connectivity** page in the Microsoft 365 Admin Center.</span></span>

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a><span data-ttu-id="44f9b-147">與登入相同 Office 365 租使用者的其他使用者共用</span><span class="sxs-lookup"><span data-stu-id="44f9b-147">Sharing with other users who sign in to the same Office 365 tenant</span></span>

<span data-ttu-id="44f9b-148">您可以選擇要與其共用報告的使用者，且預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="44f9b-148">You can choose users to share your report with and this is enabled by default.</span></span> <span data-ttu-id="44f9b-149">您的系統管理員也可以停用此功能。</span><span class="sxs-lookup"><span data-stu-id="44f9b-149">It can also be disabled by your administrator.</span></span>

![與使用者共用測試結果的連結](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a><span data-ttu-id="44f9b-151">使用 ReportID 連結與任何人共用</span><span class="sxs-lookup"><span data-stu-id="44f9b-151">Sharing with anyone using a ReportID link</span></span>

<span data-ttu-id="44f9b-152">您可以透過提供 ReportID 連結的存取權，與任何人共用您的測試報告。</span><span class="sxs-lookup"><span data-stu-id="44f9b-152">You can share your test report with anyone by providing access to a ReportID link.</span></span> <span data-ttu-id="44f9b-153">這會產生 URL 供您傳送給某人，讓他們可以在未登入的情況下，顯示測試報表。</span><span class="sxs-lookup"><span data-stu-id="44f9b-153">This generates a URL that you can send to someone so that they can bring up the test report without signing in.</span></span> <span data-ttu-id="44f9b-154">預設會停用此功能，必須由您的系統管理員加以啟用。</span><span class="sxs-lookup"><span data-stu-id="44f9b-154">This is disabled by default and must be enabled by your administrator.</span></span>

![共用測試結果的連結](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a><span data-ttu-id="44f9b-156">網路連線測試結果</span><span class="sxs-lookup"><span data-stu-id="44f9b-156">Network Connectivity Test Results</span></span>

<span data-ttu-id="44f9b-157">結果會顯示在 [ **摘要** ] 和 [ **詳細資料** ] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="44f9b-157">The results are shown in the **Summary** and **Details** tabs.</span></span> <span data-ttu-id="44f9b-158">[摘要] 索引標籤會顯示偵測到之網路周邊的對應，以及網路評估與附近其他 Office 365 客戶的比較。</span><span class="sxs-lookup"><span data-stu-id="44f9b-158">The summary tab shows a map of the detected network perimeter and a comparison of the network assessment to other Office 365 customers nearby.</span></span> <span data-ttu-id="44f9b-159">它也允許共用測試報告。</span><span class="sxs-lookup"><span data-stu-id="44f9b-159">It also allows for sharing of the test report.</span></span> <span data-ttu-id="44f9b-160">[摘要結果] 視圖的外觀如下。</span><span class="sxs-lookup"><span data-stu-id="44f9b-160">Here's what the summary results view looks like.</span></span>

![網路連線測試控管摘要結果](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

<span data-ttu-id="44f9b-162">以下是該工具顯示之詳細資料] 索引標籤輸出的範例。</span><span class="sxs-lookup"><span data-stu-id="44f9b-162">Here is an example of the details tab output that the tool shows.</span></span> <span data-ttu-id="44f9b-163">在 [詳細資料] 索引標籤上，如果結果比對臨界值比較，我們會顯示綠色圓圈核取記號。</span><span class="sxs-lookup"><span data-stu-id="44f9b-163">On the details tab we show a green circle check mark if the result was compared favorably to a threshold.</span></span> <span data-ttu-id="44f9b-164">如果結果超過表示網路洞察力的臨界值，我們就會顯示紅色三角形驚嘆號。</span><span class="sxs-lookup"><span data-stu-id="44f9b-164">We show a red triangle exclamation point if the result exceeded a threshold indicating a network insight.</span></span> <span data-ttu-id="44f9b-165">下列各節說明每一個詳細資料索引標籤的結果列，並說明用於網路洞察力的門限。</span><span class="sxs-lookup"><span data-stu-id="44f9b-165">The following sections describe each of the details tab results rows and explains the thresholds used for network insights.</span></span>

![Network connectivity test 工具範例測試結果](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a><span data-ttu-id="44f9b-167">您的位置資訊</span><span class="sxs-lookup"><span data-stu-id="44f9b-167">Your location information</span></span>

<span data-ttu-id="44f9b-168">本節顯示與您的位置相關的測試結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-168">This section shows test results related to your location.</span></span>

#### <a name="your-location"></a><span data-ttu-id="44f9b-169">您的位置</span><span class="sxs-lookup"><span data-stu-id="44f9b-169">Your location</span></span>

<span data-ttu-id="44f9b-170">使用者位置是從使用者網頁瀏覽器中偵測到，也可以在使用者選擇中輸入。</span><span class="sxs-lookup"><span data-stu-id="44f9b-170">The user location is detected from the users web browser, or it can be typed in at the users choice.</span></span> <span data-ttu-id="44f9b-171">用來識別商業網路周邊特定部分的網路距離。</span><span class="sxs-lookup"><span data-stu-id="44f9b-171">It is used to identify network distances to specific parts of the enterprise network perimeter.</span></span> <span data-ttu-id="44f9b-172">只有來自此位置偵測的城市和其他網路點的距離會儲存于報告中。</span><span class="sxs-lookup"><span data-stu-id="44f9b-172">Only the city from this location detection and the distance to other network points are saved in the report.</span></span>

<span data-ttu-id="44f9b-173">使用者辦公室位置會顯示在地圖視圖上。</span><span class="sxs-lookup"><span data-stu-id="44f9b-173">The user office location is shown on the map view.</span></span>

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a><span data-ttu-id="44f9b-174">網路出局位置 (網路連接至 ISP 的位置) </span><span class="sxs-lookup"><span data-stu-id="44f9b-174">Network egress location (the location where your network connects to your ISP)</span></span>

<span data-ttu-id="44f9b-175">我們會在伺服器端識別網路出局 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="44f9b-175">We identify the network egress IP address on the server side.</span></span> <span data-ttu-id="44f9b-176">位置資料庫是用來查詢網路出口的大致位置。</span><span class="sxs-lookup"><span data-stu-id="44f9b-176">Location databases are used to look up the approximate location for the network egress.</span></span> <span data-ttu-id="44f9b-177">這些資料庫一般會有大約90% 的 IP 位址準確度。</span><span class="sxs-lookup"><span data-stu-id="44f9b-177">These databases typically have an accuracy of about 90% of IP addresses.</span></span> <span data-ttu-id="44f9b-178">如果從網路出局 IP 位址查看的位置不正確，則此測試會導致錯誤結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-178">If the location looked up from the network egress IP address is not accurate then this would lead to a false result from this test.</span></span> <span data-ttu-id="44f9b-179">若要驗證特定 IP 位址是否發生此錯誤，您可以使用可公開存取的網路 IP 位址位置網站，以與您的實際位置進行比較。</span><span class="sxs-lookup"><span data-stu-id="44f9b-179">To validate if this error is occurring for a specific IP address you can use publicly accessible network IP address location web sites to compare to your actual location.</span></span>

#### <a name="your-distance-from-the-network-egress-location"></a><span data-ttu-id="44f9b-180">網路出局位置的距離</span><span class="sxs-lookup"><span data-stu-id="44f9b-180">Your distance from the network egress location</span></span>

<span data-ttu-id="44f9b-181">我們決定從該位置到辦公室地點的距離。</span><span class="sxs-lookup"><span data-stu-id="44f9b-181">We determine the distance from that location to the office location.</span></span> <span data-ttu-id="44f9b-182">這會顯示為網路洞察力，如果距離大於 **500 英里** (800 公里) 因為這可能會使 TCP 延遲超過25ms，而且可能會影響使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="44f9b-182">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers) since that is likely to increase the TCP latency by more than 25ms and may affect user experience.</span></span>

<span data-ttu-id="44f9b-183">網路出局位置會顯示在地圖視圖上，並聯機至使用者辦公室位置，表示企業 WAN 內部的網路 backhaul。</span><span class="sxs-lookup"><span data-stu-id="44f9b-183">The network egress location is shown on the map view and connected to the user office location indicating the network backhaul inside of the enterprise WAN.</span></span>

<span data-ttu-id="44f9b-184">建議使用 Microsoft 365 網路連線，將使用者辦公室位置的本機和直接網路輸出實施至網際網路。</span><span class="sxs-lookup"><span data-stu-id="44f9b-184">Implementing local and direct network egress from user office locations to the Internet is recommended for Microsoft 365 network connectivity.</span></span> <span data-ttu-id="44f9b-185">對本機和直接出口的增強功能是解決這種網路洞察力的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="44f9b-185">Improvements to local and direct egress are the best way to address this network insight.</span></span>

#### <a name="proxy-server-information"></a><span data-ttu-id="44f9b-186">Proxy 伺服器資訊</span><span class="sxs-lookup"><span data-stu-id="44f9b-186">Proxy server information</span></span>

<span data-ttu-id="44f9b-187">我們識別在本機電腦上設定的 proxy 伺服器 (s) 。</span><span class="sxs-lookup"><span data-stu-id="44f9b-187">We identify proxy server(s) configured on the local machine.</span></span> <span data-ttu-id="44f9b-188">我們會識別是否有任何在網路路徑中設定，以優化類別 Microsoft 365 網路流量。</span><span class="sxs-lookup"><span data-stu-id="44f9b-188">We identify if any of these are configured in the network path for optimize category Microsoft 365 network traffic.</span></span> <span data-ttu-id="44f9b-189">我們識別從使用者辦公室位置到 proxy 伺服器的距離。</span><span class="sxs-lookup"><span data-stu-id="44f9b-189">We identify the distance from the user office location to the proxy servers.</span></span> <span data-ttu-id="44f9b-190">會先透過 ICMP ping 測試距離，如果失敗，我們會使用 TCP ping 進行測試，最後如果失敗，我們會在 IP 位址位置資料庫中查詢 proxy 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="44f9b-190">The distance is tested first by ICMP ping and if that fails we test with TCP ping and finally if that fails we look up the proxy server IP Address in an IP Address location database.</span></span> <span data-ttu-id="44f9b-191">如果 proxy 伺服器的 **500 英里後超過英里** (800 公里) 離開使用者辦公室位置，我們就會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-191">We show a network insight if the proxy server is further than **500 miles** (800 kilometers) away from the user office location.</span></span>

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a><span data-ttu-id="44f9b-192">虛擬私人網路 (用來連接組織的 VPN) </span><span class="sxs-lookup"><span data-stu-id="44f9b-192">Virtual private network (VPN) you use to connect to your organization</span></span>

<span data-ttu-id="44f9b-193">這會偵測您是否使用 VPN 連線到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="44f9b-193">This detects if you are using a VPN to connect to Office 365.</span></span> <span data-ttu-id="44f9b-194">如果您沒有 VPN，或者您有 VPN 搭配 Office 365 的建議分割隧道設定，則會顯示傳遞結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-194">A passing result will show if you have no VPN, or if you have a VPN with recommended split tunnel configuration for Office 365.</span></span>

#### <a name="vpn-split-tunnel"></a><span data-ttu-id="44f9b-195">VPN 分割隧道</span><span class="sxs-lookup"><span data-stu-id="44f9b-195">VPN Split Tunnel</span></span>

<span data-ttu-id="44f9b-196">Exchange Online 的每個最優化類別路由、SharePoint 線上，以及 Microsoft 團隊會進行測試，以查看其是否為 VPN 上的隧道功能。</span><span class="sxs-lookup"><span data-stu-id="44f9b-196">Each optimize category route for Exchange Online, SharePoint Online, and Microsoft Teams is tested to see if it is tunneled on the VPN or not.</span></span> <span data-ttu-id="44f9b-197">分割的工作負載可以完全避免 VPN。</span><span class="sxs-lookup"><span data-stu-id="44f9b-197">A split out workload avoids the VPN entirely.</span></span> <span data-ttu-id="44f9b-198">隧道工作負載全部透過 VPN 傳送。</span><span class="sxs-lookup"><span data-stu-id="44f9b-198">A tunneled workload is all sent over the VPN.</span></span> <span data-ttu-id="44f9b-199">選擇性隧道工作負載會透過 VPN 傳送某些路由，並進行一些分割。如果所有工作負載都已分割或選擇性隧道，將會顯示傳遞結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-199">A selective tunneled workload has some routes sent over the VPN and some split out. A passing result will show if all workloads are split out or selective tunneled.</span></span>

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a><span data-ttu-id="44f9b-200">具有較佳效能的大都市區域中的客戶</span><span class="sxs-lookup"><span data-stu-id="44f9b-200">Customers in your metropolitan area with better performance</span></span>

<span data-ttu-id="44f9b-201">Exchange Online 服務前端的使用者辦公室位置的網路 TCP 延遲會與其他 Microsoft 365 客戶在相同大都市區域中進行比較。</span><span class="sxs-lookup"><span data-stu-id="44f9b-201">The network TCP latency of the user office location to the Exchange Online service front door is compared to other Microsoft 365 customers in the same metro area.</span></span> <span data-ttu-id="44f9b-202">如果相同地鐵區域中10% 以上的客戶都具有較佳的效能，就會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-202">A network insight is shown if 10% or more of customers in the same metro area have better performance.</span></span> <span data-ttu-id="44f9b-203">這表示在 Microsoft 365 使用者介面中，使用者的效能會比較好。</span><span class="sxs-lookup"><span data-stu-id="44f9b-203">This means their users will have better performance in the Microsoft 365 user interface.</span></span>

<span data-ttu-id="44f9b-204">在城市中的所有使用者都可以存取相同的電信基礎結構，以及對網際網路電路和 Microsoft 網路的接近程度，就會產生網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-204">This network insight is generated on the basis that all users in a city have access to the same telecommunications infrastructure and the same proximity to Internet circuits and Microsoft's network.</span></span>

#### <a name="time-to-make-a-dns-request-on-your-network"></a><span data-ttu-id="44f9b-205">在您的網路上進行 DNS 要求的時間</span><span class="sxs-lookup"><span data-stu-id="44f9b-205">Time to make a DNS request on your network</span></span>

<span data-ttu-id="44f9b-206">這會顯示在執行測試的用戶端電腦上設定的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="44f9b-206">This shows the DNS server configured on the client machine that ran the tests.</span></span> <span data-ttu-id="44f9b-207">它可能是 DNS 遞迴解析器伺服器，但這不常見。</span><span class="sxs-lookup"><span data-stu-id="44f9b-207">It might be a DNS Recursive Resolver server however this is uncommon.</span></span> <span data-ttu-id="44f9b-208">這很可能是 DNS 轉寄站伺服器，可快取 DNS 結果並將任何未緩存的 DNS 要求轉送至另一部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="44f9b-208">It is more likely to be a DNS forwarder server which caches DNS results and forwards any uncached DNS requests to another DNS server.</span></span>

<span data-ttu-id="44f9b-209">這只是為了提供資訊，不會參與任何網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-209">This is provided for information only and does not contribute to any network insight.</span></span>

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a><span data-ttu-id="44f9b-210">連接至 DNS 遞迴解析程式的距離和/或時間</span><span class="sxs-lookup"><span data-stu-id="44f9b-210">Your distance from and/or time to connect to a DNS recursive resolver</span></span>

<span data-ttu-id="44f9b-211">在 [使用中的 DNS 遞迴解析程式] 中，進行特定的 DNS 要求，然後要求 DNS 名稱伺服器接收相同的要求時，便會加以識別。</span><span class="sxs-lookup"><span data-stu-id="44f9b-211">The in-use DNS Recursive Resolver is identified by making a specific DNS request and then asking the DNS Name Server for the IP Address that it received the same request from.</span></span> <span data-ttu-id="44f9b-212">此 IP 位址是 DNS 遞迴解析程式，它會在 IP 位址位置資料庫中查閱，以尋找位置。</span><span class="sxs-lookup"><span data-stu-id="44f9b-212">This IP Address is the DNS Recursive Resolver and it will be looked up in IP Address location databases to find the location.</span></span> <span data-ttu-id="44f9b-213">然後計算從使用者辦公室位置到 DNS 遞迴解析伺服器位置的距離。</span><span class="sxs-lookup"><span data-stu-id="44f9b-213">The distance from the user office location to the DNS Recursive Resolver server location is then calculated.</span></span> <span data-ttu-id="44f9b-214">如果距離大於 **500 英里** (800 公里) 會顯示為網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-214">This is shown as a network insight if the distance is greater than **500 miles** (800 kilometers).</span></span>

<span data-ttu-id="44f9b-215">從網路出局 IP 位址查看的位置可能不正確，這會導致此測試的錯誤結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-215">The location looked up from the network egress IP Address may not be accurate and this would lead to a false result from this test.</span></span> <span data-ttu-id="44f9b-216">若要驗證特定 IP 位址是否發生此錯誤，您可以使用可公開存取的網路 IP 位址位置網站。</span><span class="sxs-lookup"><span data-stu-id="44f9b-216">To validate if this error is occurring for a specific IP Address you can use publicly accessible network IP Address location web sites.</span></span>

<span data-ttu-id="44f9b-217">這項網路洞察力特別會影響 Exchange Online 服務前端的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="44f9b-217">This network insight will specifically impact the selection of the Exchange Online service front door.</span></span> <span data-ttu-id="44f9b-218">若要解決此深入瞭解，本機和 direct 網路出局應該是必要條件，而且 DNS 遞迴解析器應該位於該網路出口之外。</span><span class="sxs-lookup"><span data-stu-id="44f9b-218">To address this insight local and direct network egress should be a pre-requisite and then DNS Recursive Resolver should be located close to that network egress.</span></span>

### <a name="exchange-online"></a><span data-ttu-id="44f9b-219">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="44f9b-219">Exchange Online</span></span>

<span data-ttu-id="44f9b-220">本節顯示與 Exchange Online 相關的測試結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-220">This section shows test results related to Exchange Online.</span></span>

#### <a name="exchange-service-front-door-location"></a><span data-ttu-id="44f9b-221">Exchange 服務的前門位置</span><span class="sxs-lookup"><span data-stu-id="44f9b-221">Exchange service front door location</span></span>

<span data-ttu-id="44f9b-222">「使用中 Exchange 服務前門」是以 Outlook 這麼做的相同方式來識別，我們會從使用者位置測量網路的 TCP 延遲。</span><span class="sxs-lookup"><span data-stu-id="44f9b-222">The in-use Exchange service front door is identified in the same way that Outlook does this and we measure the network TCP latency from the user location to it.</span></span> <span data-ttu-id="44f9b-223">會顯示 TCP 延遲，並將使用中 Exchange 服務的前蓋與目前位置的最佳服務前門清單進行比較。</span><span class="sxs-lookup"><span data-stu-id="44f9b-223">The TCP latency is shown and the in-use Exchange service front door is compared to the list of best service front doors for the current location.</span></span> <span data-ttu-id="44f9b-224">如果其中一個最佳 Exchange 服務前門 (s) 並未使用中，這會顯示為網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-224">This is shown as a network insight if one of the best Exchange service front door(s) is not in use.</span></span>

<span data-ttu-id="44f9b-225">[！附注] 在公司網路出口之前，不使用其中一個最佳 Exchange 服務前門 (s) 可能是由網路 backhaul 造成的，我們建議您在本機和直接的網路出口。</span><span class="sxs-lookup"><span data-stu-id="44f9b-225">Not using one of the best Exchange service front door(s) could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="44f9b-226">這種情況也可能是使用遠端 DNS 遞迴解析伺服器所造成，在此情況下，我們建議您將 DNS 遞迴解析程式伺服器與網路出局對齊。</span><span class="sxs-lookup"><span data-stu-id="44f9b-226">It could also be caused by use of a remote DNS recursive resolver server in which case we recommend aligning the DNS recursive resolver server with the network egress.</span></span>

<span data-ttu-id="44f9b-227">我們計算對 Exchange 服務前門 (ms) 的 TCP 延遲的潛在改進。</span><span class="sxs-lookup"><span data-stu-id="44f9b-227">We calculate a potential improvement in TCP latency (ms) to the Exchange service front door.</span></span> <span data-ttu-id="44f9b-228">若要執行此動作，請查看已測試的使用者 office 位置網路延遲，並從目前的位置減去網路延遲，直到 closets Exchange 服務的前門。</span><span class="sxs-lookup"><span data-stu-id="44f9b-228">This is done by looking at the tested user office location network latency and subtracting the network latency from the current location to the closets Exchange service front door.</span></span> <span data-ttu-id="44f9b-229">差異代表潛在的改進機會。</span><span class="sxs-lookup"><span data-stu-id="44f9b-229">The difference represents the potential opportunity for improvement.</span></span>

#### <a name="best-exchange-service-front-doors-for-your-location"></a><span data-ttu-id="44f9b-230">您位置的最佳 Exchange 服務前門 (s) </span><span class="sxs-lookup"><span data-stu-id="44f9b-230">Best Exchange service front door(s) for your location</span></span>

<span data-ttu-id="44f9b-231">這會列出您所在地區的最佳 Exchange 服務前門位置（按城市）。</span><span class="sxs-lookup"><span data-stu-id="44f9b-231">This lists the best Exchange service front door locations by city for your location.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="44f9b-232">在用戶端 DNS 中記錄的服務前面門</span><span class="sxs-lookup"><span data-stu-id="44f9b-232">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="44f9b-233">這會顯示您定向的 Exchange 服務前端伺服器的 DNS 名稱及 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="44f9b-233">This shows the DNS name and IP Address of the Exchange service front door server that you were directed to.</span></span> <span data-ttu-id="44f9b-234">只提供此資訊，而且沒有相關聯的網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-234">It is provided for information only and there is no associated network insight.</span></span>

### <a name="sharepoint-online"></a><span data-ttu-id="44f9b-235">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="44f9b-235">SharePoint Online</span></span>

<span data-ttu-id="44f9b-236">本節顯示與 SharePoint 線上及 OneDrive 相關的測試結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-236">This section shows test results related to SharePoint Online and OneDrive.</span></span>

#### <a name="the-service-front-door-location"></a><span data-ttu-id="44f9b-237">服務的前門位置</span><span class="sxs-lookup"><span data-stu-id="44f9b-237">The service front door location</span></span>

<span data-ttu-id="44f9b-238">使用中 SharePoint 服務的前門是以 OneDrive 用戶端所用的相同方式來識別，而且我們會從使用者辦公室位置測量網路的 TCP 延遲。</span><span class="sxs-lookup"><span data-stu-id="44f9b-238">The in-use SharePoint service front door is identified in the same way that the OneDrive client does and we measure the network TCP latency from the user office location to it.</span></span>

#### <a name="download-speed"></a><span data-ttu-id="44f9b-239">下載速度</span><span class="sxs-lookup"><span data-stu-id="44f9b-239">Download speed</span></span>

<span data-ttu-id="44f9b-240">我們從 SharePoint 服務的前門，測量15Mb 檔案的下載速度。</span><span class="sxs-lookup"><span data-stu-id="44f9b-240">We measure the download speed for a 15Mb file from the SharePoint service front door.</span></span> <span data-ttu-id="44f9b-241">結果會以每秒 mb 為單位顯示，以指出可以從 SharePoint 或 OneDrive 中的 **一秒** 內的哪一個大小的檔案下載 mb。</span><span class="sxs-lookup"><span data-stu-id="44f9b-241">The result is shown in megabytes per second to indicate what size file in megabytes can be downloaded from SharePoint or OneDrive in **one second**.</span></span> <span data-ttu-id="44f9b-242">此數目應類似于每秒百萬位元最小電路頻寬的十分之一。</span><span class="sxs-lookup"><span data-stu-id="44f9b-242">The number should be similar to one tenth of the minimum circuit bandwidth in megabits per second.</span></span> <span data-ttu-id="44f9b-243">例如，如果您有100mbps 網際網路連線，可能會預期每秒 10 mb (10MBps) 。</span><span class="sxs-lookup"><span data-stu-id="44f9b-243">For example if you have a 100mbps internet connection, you may expect 10 megabytes per second (10MBps).</span></span>

#### <a name="buffer-bloat"></a><span data-ttu-id="44f9b-244">緩衝區膨脹</span><span class="sxs-lookup"><span data-stu-id="44f9b-244">Buffer bloat</span></span>

<span data-ttu-id="44f9b-245">在15Mb 下載期間，我們會測量 SharePoint 服務前門的 TCP 延遲。</span><span class="sxs-lookup"><span data-stu-id="44f9b-245">During the 15Mb download we measure the TCP latency to the SharePoint service front door.</span></span> <span data-ttu-id="44f9b-246">這是負載下的延遲時間，在未負載下時比較為延遲時間。</span><span class="sxs-lookup"><span data-stu-id="44f9b-246">This is the latency under load and it is compared to the latency when not under load.</span></span> <span data-ttu-id="44f9b-247">當負載不足時，延遲的增加通常是由 (或 bloated) 中載入的消費網路裝置緩衝區所造成。</span><span class="sxs-lookup"><span data-stu-id="44f9b-247">The increase in latency when under load is often attributable to consumer network device buffers being loaded (or bloated).</span></span> <span data-ttu-id="44f9b-248">任何1000或更多的膨脹都會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-248">A network insight is shown for any bloat of 1,000 or more.</span></span>

#### <a name="service-front-door-recorded-in-the-client-dns"></a><span data-ttu-id="44f9b-249">在用戶端 DNS 中記錄的服務前面門</span><span class="sxs-lookup"><span data-stu-id="44f9b-249">Service front door recorded in the client DNS</span></span>

<span data-ttu-id="44f9b-250">這會顯示您定向的 SharePoint 服務前門伺服器的 DNS 名稱和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="44f9b-250">This shows the DNS name and IP Address of the SharePoint service front door server that you were directed to.</span></span> <span data-ttu-id="44f9b-251">只提供此資訊，而且沒有相關聯的網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-251">It is provided for information only and there is no associated network insight.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="44f9b-252">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44f9b-252">Microsoft Teams</span></span>

<span data-ttu-id="44f9b-253">本節顯示與 Microsoft 小組相關的測試結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-253">This section shows test results related to Microsoft Teams.</span></span>

#### <a name="media-connectivity-audio-video-and-application-sharing"></a><span data-ttu-id="44f9b-254">Media connectivity (音訊、影片和應用程式共用) </span><span class="sxs-lookup"><span data-stu-id="44f9b-254">Media connectivity (audio, video, and application sharing)</span></span>

<span data-ttu-id="44f9b-255">這會測試對 Microsoft 小組服務前門的 UDP 連線。</span><span class="sxs-lookup"><span data-stu-id="44f9b-255">This tests for UDP connectivity to the Microsoft Teams service front door.</span></span> <span data-ttu-id="44f9b-256">如果遭到封鎖，則 Microsoft 小組可能仍然使用 TCP，但音訊和影片會受損。</span><span class="sxs-lookup"><span data-stu-id="44f9b-256">If this is blocked then Microsoft Teams may still work using TCP, but audio and video will be impaired.</span></span> <span data-ttu-id="44f9b-257">閱讀更多有關這些 UDP 網路度量的資訊，這些是在[商務用 Skype Online 中的媒體質量和網路連線效能](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)上套用至 Microsoft 小組的。</span><span class="sxs-lookup"><span data-stu-id="44f9b-257">Read more about these UDP network measurements which also apply to Microsoft Teams at [Media Quality and Network Connectivity Performance in Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)</span></span>

#### <a name="packet-loss"></a><span data-ttu-id="44f9b-258">封包遺失</span><span class="sxs-lookup"><span data-stu-id="44f9b-258">Packet loss</span></span>

<span data-ttu-id="44f9b-259">顯示 UDP 封包遺失，以10秒的測試音訊撥號從用戶端到 Microsoft 小組服務的前門。</span><span class="sxs-lookup"><span data-stu-id="44f9b-259">Shows the UDP packet loss measured in a 10 second test audio call from the client to the Microsoft Teams service front door.</span></span> <span data-ttu-id="44f9b-260">這應低於 **1.00%** 的傳遞。</span><span class="sxs-lookup"><span data-stu-id="44f9b-260">This should be lower than **1.00%** for a pass.</span></span>

#### <a name="latency"></a><span data-ttu-id="44f9b-261">延遲</span><span class="sxs-lookup"><span data-stu-id="44f9b-261">Latency</span></span>

<span data-ttu-id="44f9b-262">顯示測定的 UDP 延遲，它應低於 **100ms**。</span><span class="sxs-lookup"><span data-stu-id="44f9b-262">Shows the measured UDP latency, which should be lower than **100ms**.</span></span>

#### <a name="jitter"></a><span data-ttu-id="44f9b-263">抖動</span><span class="sxs-lookup"><span data-stu-id="44f9b-263">Jitter</span></span>

<span data-ttu-id="44f9b-264">顯示測定的 UDP 抖動，它應低於 **30ms**。</span><span class="sxs-lookup"><span data-stu-id="44f9b-264">Shows the measured UDP jitter, which should be lower than **30ms**.</span></span>

#### <a name="connectivity"></a><span data-ttu-id="44f9b-265">連線能力</span><span class="sxs-lookup"><span data-stu-id="44f9b-265">Connectivity</span></span>

<span data-ttu-id="44f9b-266">我們會將使用者辦公室位置的 HTTP 連線測試至所有必要的 Microsoft 365 網路端點。</span><span class="sxs-lookup"><span data-stu-id="44f9b-266">We test for HTTP connectivity from the user office location to all of the required Microsoft 365 network endpoints.</span></span> <span data-ttu-id="44f9b-267">這些是發佈于 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。</span><span class="sxs-lookup"><span data-stu-id="44f9b-267">These are published at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="44f9b-268">對於任何無法連線的必要網路端點，都會顯示網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-268">A network insight is shown for any required network endpoints which cannot be connected to.</span></span>

<span data-ttu-id="44f9b-269">在商業網路周邊的 proxy 伺服器、防火牆或其他網路安全裝置可能會封鎖連線能力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-269">Connectivity may be blocked by a proxy server, a firewall, or another network security device on the enterprise network perimeter.</span></span> <span data-ttu-id="44f9b-270">以 HTTP 要求來測試與 TCP 埠80的連線，並使用 HTTPS 要求來測試 TCP 埠443的連線。</span><span class="sxs-lookup"><span data-stu-id="44f9b-270">Connectivity to TCP port 80 is tested with an HTTP request and connectivity to TCP port 443 is tested with an HTTPS request.</span></span> <span data-ttu-id="44f9b-271">如果沒有任何回應，FQDN 會標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="44f9b-271">If there is no response the FQDN is marked as a failure.</span></span> <span data-ttu-id="44f9b-272">如果有 HTTP 回應碼407，FQDN 會標示為失敗。</span><span class="sxs-lookup"><span data-stu-id="44f9b-272">If there is an HTTP response code 407 the FQDN is marked as a failure.</span></span> <span data-ttu-id="44f9b-273">如果有 HTTP 回應碼403，我們會檢查回應的 Server 屬性，如果它似乎是 proxy 伺服器，我們會將其標記為失敗。</span><span class="sxs-lookup"><span data-stu-id="44f9b-273">If there is an HTTP response code 403 then we check the Server attribute of the response and if it appears to be a proxy server we mark this as a failure.</span></span> <span data-ttu-id="44f9b-274">您可以使用 Windows 命令列工具 curl.exe 來模擬我們所執行的測試。</span><span class="sxs-lookup"><span data-stu-id="44f9b-274">You can simulate the tests we perform with the Windows command line tool curl.exe.</span></span>

<span data-ttu-id="44f9b-275">我們會在每個必要的 Microsoft 365 網路端點（已于所定義的 [優化] 或 [允許] 類別中）測試 SSL 憑證 [https://aka.ms/o365ip](https://aka.ms/o365ip) 。</span><span class="sxs-lookup"><span data-stu-id="44f9b-275">We test the SSL certificate at each required Microsoft 365 network endpoint that is in the optimize or allow category as defined at [https://aka.ms/o365ip](https://aka.ms/o365ip).</span></span> <span data-ttu-id="44f9b-276">如果任何測試未找到 Microsoft SSL 憑證，則所連接的加密網路必須已被仲介網路裝置截獲。</span><span class="sxs-lookup"><span data-stu-id="44f9b-276">If any tests do not find a Microsoft SSL certificate, then the encrypted network connected must have been intercepted by an intermediary network device.</span></span> <span data-ttu-id="44f9b-277">網路洞察力會顯示在任何截獲的加密網路端點上。</span><span class="sxs-lookup"><span data-stu-id="44f9b-277">A network insight is shown on any intercepted encrypted network endpoints.</span></span>

<span data-ttu-id="44f9b-278">如果 Microsoft 未提供 SSL 憑證，我們會顯示測試的 FQDN 和使用中的 SSL 憑證擁有者。</span><span class="sxs-lookup"><span data-stu-id="44f9b-278">Where an SSL certificate is found that isn't provided by Microsoft, we show the FQDN for the test and the in-use SSL certificate owner.</span></span> <span data-ttu-id="44f9b-279">這個 SSL 憑證擁有者可能是 proxy 伺服器廠商，也可能是企業自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="44f9b-279">This SSL certificate owner may be a proxy server vendor, or it may be an enterprise self-signed certificate.</span></span>

#### <a name="network-path"></a><span data-ttu-id="44f9b-280">網路路徑</span><span class="sxs-lookup"><span data-stu-id="44f9b-280">Network path</span></span>

<span data-ttu-id="44f9b-281">本節顯示 ICMP traceroute 至 Exchange Online 服務前門、SharePoint Online 服務前門和 Microsoft 團隊服務前門的結果。</span><span class="sxs-lookup"><span data-stu-id="44f9b-281">This section shows the results of an ICMP traceroute to the Exchange Online service front door, the SharePoint Online service front door, and the Microsoft Teams service front door.</span></span> <span data-ttu-id="44f9b-282">只提供此資訊，而且沒有相關聯的網路洞察力。</span><span class="sxs-lookup"><span data-stu-id="44f9b-282">It is provided for information only and there is no associated network insight.</span></span> <span data-ttu-id="44f9b-283">提供三種 traceroutes。</span><span class="sxs-lookup"><span data-stu-id="44f9b-283">There are three traceroutes provided.</span></span> <span data-ttu-id="44f9b-284">Traceroute 至 _outlook.office365.com_、traceroute 至客戶 SharePoint 前端或 _microsoft.sharepoint.com_ （如果未提供），以及 traceroute 到 _world.tr.teams.microsoft.com_。</span><span class="sxs-lookup"><span data-stu-id="44f9b-284">A traceroute to _outlook.office365.com_, a traceroute to the customers SharePoint front end or to _microsoft.sharepoint.com_ if one was not provided, and a traceroute to _world.tr.teams.microsoft.com_.</span></span>

## <a name="connectivity-reports"></a><span data-ttu-id="44f9b-285">連線性報告</span><span class="sxs-lookup"><span data-stu-id="44f9b-285">Connectivity reports</span></span>

<span data-ttu-id="44f9b-286">登入後，您可以查看先前所執行的報告。</span><span class="sxs-lookup"><span data-stu-id="44f9b-286">When you are signed in you can review previous reports that you have run.</span></span> <span data-ttu-id="44f9b-287">您也可以將其共用或從清單中刪除。</span><span class="sxs-lookup"><span data-stu-id="44f9b-287">You can also share them or delete them from the list.</span></span>

![報告](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a><span data-ttu-id="44f9b-289">網路健康狀態</span><span class="sxs-lookup"><span data-stu-id="44f9b-289">Network health status</span></span>

<span data-ttu-id="44f9b-290">這會顯示 Microsoft 全球網路的任何重大健康情況問題，可能會影響 Microsoft 365 客戶。</span><span class="sxs-lookup"><span data-stu-id="44f9b-290">This shows any significant health issues with Microsoft's global network which might impact Microsoft 365 customers.</span></span>

![網路健康狀態](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a><span data-ttu-id="44f9b-292">常見問題集</span><span class="sxs-lookup"><span data-stu-id="44f9b-292">FAQ</span></span>

<span data-ttu-id="44f9b-293">以下是一些常見問題的解答。</span><span class="sxs-lookup"><span data-stu-id="44f9b-293">Here are answers to some of our frequently asked questions.</span></span>

### <a name="is-this-tool-released-and-supported-by-microsoft"></a><span data-ttu-id="44f9b-294">Microsoft 是否已發行及支援此工具？</span><span class="sxs-lookup"><span data-stu-id="44f9b-294">Is this tool released and supported by Microsoft?</span></span>

<span data-ttu-id="44f9b-295">這是一種預覽方式，我們計畫定期提供更新，直到我們達到一般可用性發行狀態時，才會從 Microsoft 取得支援。</span><span class="sxs-lookup"><span data-stu-id="44f9b-295">It is currently a preview and we plan to provide updates regularly until we reach general availability release status with support from Microsoft.</span></span> <span data-ttu-id="44f9b-296">請提供意見反應以協助我們改進。</span><span class="sxs-lookup"><span data-stu-id="44f9b-296">Please provide feedback to help us improve.</span></span> <span data-ttu-id="44f9b-297">我們打算將更詳細的 Office 365 網路上架指南發佈為此工具的一部分，此工具是由其測試結果自訂為組織的一部分。</span><span class="sxs-lookup"><span data-stu-id="44f9b-297">We are planning to publish a more detailed Office 365 Network Onboarding guide as part of this tool which is customized for the organization by its test results.</span></span>

### <a name="what-is-required-to-run-the-advanced-test-client"></a><span data-ttu-id="44f9b-298">執行高級測試用戶端的必要條件為何？</span><span class="sxs-lookup"><span data-stu-id="44f9b-298">What is required to run the advanced test client?</span></span>

<span data-ttu-id="44f9b-299">高級測試用戶端需要 .NET Core 3.1 Desktop Runtime。</span><span class="sxs-lookup"><span data-stu-id="44f9b-299">The advanced test client requires .NET Core 3.1 Desktop Runtime.</span></span> <span data-ttu-id="44f9b-300">如果您執行的是未安裝的高級測試用戶端，將會定向至 [.Net Core 3.1 installer 頁面](https://dotnet.microsoft.com/download/dotnet-core/3.1)。</span><span class="sxs-lookup"><span data-stu-id="44f9b-300">If you run the advanced test client without that installed you will be directed to [the .NET Core 3.1 installer page](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="44f9b-301">請務必安裝桌面執行時間，而不是 SDK，或頁面上較高的 ASP.NET 核心執行時間。</span><span class="sxs-lookup"><span data-stu-id="44f9b-301">Be sure to install the Desktop Runtime and not the SDK, or the ASP.NET Core Runtime which are higher up on the page.</span></span> <span data-ttu-id="44f9b-302">需要有機器的系統管理員許可權，才能安裝 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="44f9b-302">Administrator permissions on the machine is required to install .NET Core.</span></span>

### <a name="what-is-microsoft-365-service-front-door"></a><span data-ttu-id="44f9b-303">何謂 Microsoft 365 服務的前門？</span><span class="sxs-lookup"><span data-stu-id="44f9b-303">What is Microsoft 365 service front door?</span></span>

<span data-ttu-id="44f9b-304">Microsoft 365 服務前端是 Microsoft 全球網路的進入點，Office 用戶端和服務會在此位置中斷其網路連線。</span><span class="sxs-lookup"><span data-stu-id="44f9b-304">The Microsoft 365 service front door is an entry point on Microsoft's global network where Office clients and services terminate their network connection.</span></span> <span data-ttu-id="44f9b-305">為了獲得最佳網路連接至 Microsoft 365，建議您的網路連線在您的城市或地鐵的最接近的 Microsoft 365 前端。</span><span class="sxs-lookup"><span data-stu-id="44f9b-305">For an optimal network connection to Microsoft 365, it is recommended that your network connection is terminated into the closest Microsoft 365 front door in your city or metro.</span></span>

<span data-ttu-id="44f9b-306">附注： Microsoft 365 服務前端沒有 azure marketplace 中可用的 **Azure 前端服務** 產品的直接關聯。</span><span class="sxs-lookup"><span data-stu-id="44f9b-306">Note: Microsoft 365 service front door has no direct relationship to the **Azure Front Door Service** product available in the Azure marketplace.</span></span>

### <a name="what-is-the-best-microsoft-365-service-front-door"></a><span data-ttu-id="44f9b-307">最佳的 Microsoft 365 服務前門是什麼？</span><span class="sxs-lookup"><span data-stu-id="44f9b-307">What is the best Microsoft 365 service front door?</span></span>

<span data-ttu-id="44f9b-308">最佳的 Microsoft 365 服務前門 (（先前稱為最佳服務前門) 是最接近網路出口的最佳服務，通常是在您的城市或大都市區內。</span><span class="sxs-lookup"><span data-stu-id="44f9b-308">A best Microsoft 365 service front door (formerly known as an optimal service front door) is one that is closest to your network egress, generally in your city or metro area.</span></span> <span data-ttu-id="44f9b-309">使用 Microsoft 365 網路效能工具判斷您使用中的 Microsoft 365 服務前門和最佳的服務前門 (s) 。</span><span class="sxs-lookup"><span data-stu-id="44f9b-309">Use the Microsoft 365 network performance tool to determine location of your in-use Microsoft 365 service front door and the best service front door(s).</span></span> <span data-ttu-id="44f9b-310">如果工具判斷您的使用中的前門是其中一個是最佳的，則您應該會指望 Microsoft 的全球網路的連線能力很好。</span><span class="sxs-lookup"><span data-stu-id="44f9b-310">If the tool determines your in-use front door is one of the best ones, then you should expect great connectivity into Microsoft's global network.</span></span>

### <a name="what-is-an-internet-egress-location"></a><span data-ttu-id="44f9b-311">何謂網際網路出口的位置？</span><span class="sxs-lookup"><span data-stu-id="44f9b-311">What is an internet egress location?</span></span>

<span data-ttu-id="44f9b-312">網際網路出局位置是網路流量結束商業網路並連接到網際網路的位置。</span><span class="sxs-lookup"><span data-stu-id="44f9b-312">The internet egress Location is the location where your network traffic exits your enterprise network and connects to the Internet.</span></span> <span data-ttu-id="44f9b-313">此位置也會識別為您具有網路位址轉譯 (NAT) 裝置的位置，通常是您與網際網路服務提供者 (ISP) 的位置。</span><span class="sxs-lookup"><span data-stu-id="44f9b-313">This is also identified as the location where you have a Network Address Translation (NAT) device and usually where you connect with an Internet Service Provider (ISP).</span></span> <span data-ttu-id="44f9b-314">如果您看到位置和網際網路出局位置之間有長距離的距離，則這可能會識別重要的 WAN backhaul。</span><span class="sxs-lookup"><span data-stu-id="44f9b-314">If you see a long distance between your location and your internet egress location, then this may identify a significant WAN backhaul.</span></span>

## <a name="related-topics"></a><span data-ttu-id="44f9b-315">相關主題</span><span class="sxs-lookup"><span data-stu-id="44f9b-315">Related topics</span></span>

[<span data-ttu-id="44f9b-316">Microsoft 365 系統管理中心的網路連線 (預覽) </span><span class="sxs-lookup"><span data-stu-id="44f9b-316">Network connectivity in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="44f9b-317">Microsoft 365 網路效能深入 (預覽) </span><span class="sxs-lookup"><span data-stu-id="44f9b-317">Microsoft 365 network performance insights (preview)</span></span>](office-365-network-mac-perf-insights.md)

[<span data-ttu-id="44f9b-318">Microsoft 365 網路評估 (預覽) </span><span class="sxs-lookup"><span data-stu-id="44f9b-318">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="44f9b-319">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="44f9b-319">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
