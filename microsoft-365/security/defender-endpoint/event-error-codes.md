---
title: 使用事件檢視器審閱事件和錯誤
description: 取得 Microsoft Defender for Endpoint service 所報告之所有事件的必要) ，以取得描述及進一步的疑難排解步驟 (。
keywords: 疑難排解、事件檢視器、記錄摘要、失敗代碼、失敗、Microsoft Defender for Endpoint service、無法啟動、已中斷、無法啟動
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060552"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="701e7-104">使用事件檢視器審閱事件和錯誤</span><span class="sxs-lookup"><span data-stu-id="701e7-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="701e7-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="701e7-105">**Applies to:**</span></span>
- <span data-ttu-id="701e7-106">事件檢視器</span><span class="sxs-lookup"><span data-stu-id="701e7-106">Event Viewer</span></span>
- [<span data-ttu-id="701e7-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="701e7-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="701e7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="701e7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="701e7-109">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="701e7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="701e7-110">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="701e7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="701e7-111">您可以在個別裝置的 [事件檢視器](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 中審閱事件 IDs。</span><span class="sxs-lookup"><span data-stu-id="701e7-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="701e7-112">例如，如果裝置未出現在 [裝置] **清單** 中，您可能需要在裝置上尋找事件 IDs。</span><span class="sxs-lookup"><span data-stu-id="701e7-112">For example, if devices are not appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="701e7-113">您可以使用此表格來決定進一步的疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="701e7-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="701e7-114">**開啟事件檢視器，並尋找 Microsoft Defender for Endpoint service 事件記錄檔：**</span><span class="sxs-lookup"><span data-stu-id="701e7-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="701e7-115">在 [Windows] 功能表上，按一下 [ **開始** ]，輸入 **事件檢視器**，然後按 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="701e7-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="701e7-116">在 [記錄檔] 清單的 [**記錄摘要**] 下，向內滾動，直到看到 [ **Microsoft-Windows------Windows-**</span><span class="sxs-lookup"><span data-stu-id="701e7-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="701e7-117">按兩下專案以開啟記錄檔。</span><span class="sxs-lookup"><span data-stu-id="701e7-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="701e7-118">a.</span><span class="sxs-lookup"><span data-stu-id="701e7-118">a.</span></span>  <span data-ttu-id="701e7-119">您也可以透過擴充 **應用程式和服務記錄**  >  **Microsoft**  >  **Windows**  >  **感知**，然後按一下 [**操作**] 來存取記錄。</span><span class="sxs-lookup"><span data-stu-id="701e7-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="701e7-120">判斷是指用來表示為 Microsoft Defender for Endpoint 供電的行為感應器的內部名稱。</span><span class="sxs-lookup"><span data-stu-id="701e7-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="701e7-121">服務所記錄的事件會出現在記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="701e7-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="701e7-122">如需服務所記錄的事件清單，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="701e7-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="701e7-123">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="701e7-123">Event ID</span></span></th>
<th><span data-ttu-id="701e7-124">郵件</span><span class="sxs-lookup"><span data-stu-id="701e7-124">Message</span></span></th>
<th><span data-ttu-id="701e7-125">描述</span><span class="sxs-lookup"><span data-stu-id="701e7-125">Description</span></span></th>
<th><span data-ttu-id="701e7-126">動作</span><span class="sxs-lookup"><span data-stu-id="701e7-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="701e7-127">1</span><span class="sxs-lookup"><span data-stu-id="701e7-127">1</span></span></td>
<td><span data-ttu-id="701e7-128">Microsoft Defender for Endpoint service 已開始 (版本 <code>variable</code>) 。</span><span class="sxs-lookup"><span data-stu-id="701e7-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="701e7-129">在系統啟動、關機及 onbboarding 期間發生。</span><span class="sxs-lookup"><span data-stu-id="701e7-129">Occurs during system start up, shut down, and during onbboarding.</span></span></td>
<td><span data-ttu-id="701e7-130">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-131">2 </span><span class="sxs-lookup"><span data-stu-id="701e7-131">2</span></span></td>
<td><span data-ttu-id="701e7-132">Microsoft Defender for Endpoint service 關閉。</span><span class="sxs-lookup"><span data-stu-id="701e7-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="701e7-133">當裝置關閉或 offboarded 時會發生此事件。</span><span class="sxs-lookup"><span data-stu-id="701e7-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="701e7-134">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-135">3 </span><span class="sxs-lookup"><span data-stu-id="701e7-135">3</span></span></td>
<td><span data-ttu-id="701e7-136">無法啟動 Microsoft Defender for Endpoint service。</span><span class="sxs-lookup"><span data-stu-id="701e7-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="701e7-137">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-138">服務未啟動。</span><span class="sxs-lookup"><span data-stu-id="701e7-138">Service did not start.</span></span></td>
<td><span data-ttu-id="701e7-139">請複查其他訊息，以判斷可能的原因及疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="701e7-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-140">4 </span><span class="sxs-lookup"><span data-stu-id="701e7-140">4</span></span></td>
<td><span data-ttu-id="701e7-141">Microsoft Defender for Endpoint service 已于的伺服器取得聯繫 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-142">Variable = 端點處理伺服器的 Defender URL。</span><span class="sxs-lookup"><span data-stu-id="701e7-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="701e7-143">此 URL 會比對防火牆或網路活動中所看到的。</span><span class="sxs-lookup"><span data-stu-id="701e7-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="701e7-144">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-145">5 </span><span class="sxs-lookup"><span data-stu-id="701e7-145">5</span></span></td>
<td><span data-ttu-id="701e7-146">Microsoft Defender for Endpoint service 無法連線至上的伺服器 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-147">Variable = 端點處理伺服器的 Defender URL。</span><span class="sxs-lookup"><span data-stu-id="701e7-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="701e7-148">服務無法與位於該 URL 的外部處理伺服器聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-148">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="701e7-149">檢查 URL 的連線。</span><span class="sxs-lookup"><span data-stu-id="701e7-149">Check the connection to the URL.</span></span> <span data-ttu-id="701e7-150">請參閱 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">設定 proxy 和網際網路連線</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-151">6 </span><span class="sxs-lookup"><span data-stu-id="701e7-151">6</span></span></td>
<td><span data-ttu-id="701e7-152">Microsoft Defender for Endpoint service 未架，且找不到任何上架參數。</span><span class="sxs-lookup"><span data-stu-id="701e7-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="701e7-153">裝置上架不正確，不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="701e7-153">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="701e7-154">在啟動服務之前，必須先執行上架。</span><span class="sxs-lookup"><span data-stu-id="701e7-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="701e7-155">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-156">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-157">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-158">7 </span><span class="sxs-lookup"><span data-stu-id="701e7-158">7</span></span></td>
<td><span data-ttu-id="701e7-159">Microsoft Defender for Endpoint service 無法讀取上架參數。</span><span class="sxs-lookup"><span data-stu-id="701e7-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="701e7-160">失敗： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-161">Variable = 詳細的錯誤描述。</span><span class="sxs-lookup"><span data-stu-id="701e7-161">Variable = detailed error description.</span></span> <span data-ttu-id="701e7-162">裝置上架不正確，不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="701e7-162">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="701e7-163">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-164">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-165">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-166">8 </span><span class="sxs-lookup"><span data-stu-id="701e7-166">8</span></span></td>
<td><span data-ttu-id="701e7-167">Microsoft Defender for Endpoint service 無法清除其設定。</span><span class="sxs-lookup"><span data-stu-id="701e7-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="701e7-168">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-169"><b>在上架期間：</b> 服務無法在上架期間清除其設定。</span><span class="sxs-lookup"><span data-stu-id="701e7-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="701e7-170">上架處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="701e7-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="701e7-171"><b>脫離時：</b> 服務無法在脫離期間清除其設定。</span><span class="sxs-lookup"><span data-stu-id="701e7-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="701e7-172">脫離處理常式完成，但服務仍在執行中。</span><span class="sxs-lookup"><span data-stu-id="701e7-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="701e7-173">上<b>架：</b>不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="701e7-174"><b>脫離：</b> 重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="701e7-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="701e7-175">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-176">9 </span><span class="sxs-lookup"><span data-stu-id="701e7-176">9</span></span></td>
<td><span data-ttu-id="701e7-177">Microsoft Defender for Endpoint service 無法變更其啟動類型。</span><span class="sxs-lookup"><span data-stu-id="701e7-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="701e7-178">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-179"><b>在上架期間：</b> 裝置上架不正確，不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="701e7-179"><b>During onboarding:</b> The device did not onboard correctly and will not be reporting to the portal.</span></span> <br><br><span data-ttu-id="701e7-180"><b>脫離時：</b> 無法變更服務啟動類型。</span><span class="sxs-lookup"><span data-stu-id="701e7-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="701e7-181">脫離處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="701e7-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="701e7-182">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-183">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-184">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-185">10 </span><span class="sxs-lookup"><span data-stu-id="701e7-185">10</span></span></td>
<td><span data-ttu-id="701e7-186">Microsoft Defender for Endpoint service 無法保留上架資訊。</span><span class="sxs-lookup"><span data-stu-id="701e7-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="701e7-187">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-188">裝置上架不正確，不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="701e7-188">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="701e7-189">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-190">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-191">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-192">11 </span><span class="sxs-lookup"><span data-stu-id="701e7-192">11</span></span></td>
<td><span data-ttu-id="701e7-193">上架服務已完成的 Defender 或重新加入。</span><span class="sxs-lookup"><span data-stu-id="701e7-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="701e7-194">裝置架正確。</span><span class="sxs-lookup"><span data-stu-id="701e7-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="701e7-195">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="701e7-196">可能需要數小時的時間，裝置才會出現在入口網站中。</span><span class="sxs-lookup"><span data-stu-id="701e7-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-197">12 </span><span class="sxs-lookup"><span data-stu-id="701e7-197">12</span></span></td>
<td><span data-ttu-id="701e7-198">Microsoft Defender for Endpoint 無法套用預設設定。</span><span class="sxs-lookup"><span data-stu-id="701e7-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="701e7-199">服務無法套用預設設定。</span><span class="sxs-lookup"><span data-stu-id="701e7-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="701e7-200">此錯誤應在一小段時間後解決。</span><span class="sxs-lookup"><span data-stu-id="701e7-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-201">13</span><span class="sxs-lookup"><span data-stu-id="701e7-201">13</span></span></td>
<td><span data-ttu-id="701e7-202">Microsoft Defender for Endpoint 設備識別碼已計算： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-203">正常工作處理程式。</span><span class="sxs-lookup"><span data-stu-id="701e7-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="701e7-204">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-205">15 </span><span class="sxs-lookup"><span data-stu-id="701e7-205">15</span></span></td>
<td><span data-ttu-id="701e7-206">Microsoft Defender for Endpoint 無法使用 URL: 啟動命令通道 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-207">Variable = 端點處理伺服器的 Defender URL。</span><span class="sxs-lookup"><span data-stu-id="701e7-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="701e7-208">服務無法與位於該 URL 的外部處理伺服器聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-208">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="701e7-209">檢查 URL 的連線。</span><span class="sxs-lookup"><span data-stu-id="701e7-209">Check the connection to the URL.</span></span> <span data-ttu-id="701e7-210">請參閱 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">設定 proxy 和網際網路連線</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-211">17 </span><span class="sxs-lookup"><span data-stu-id="701e7-211">17</span></span></td>
<td><span data-ttu-id="701e7-212">Microsoft Defender for Endpoint service 無法變更連線的使用者經驗和遙測服務位置。</span><span class="sxs-lookup"><span data-stu-id="701e7-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="701e7-213">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-214">Windows 遙測服務發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="701e7-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="701e7-216">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-217">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-218">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-219">18 </span><span class="sxs-lookup"><span data-stu-id="701e7-219">18</span></span></td>
<td><span data-ttu-id="701e7-220">已完成 OOBE (Windows 歡迎) 。</span><span class="sxs-lookup"><span data-stu-id="701e7-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="701e7-221">只有在任何 Windows 更新安裝完畢後，服務才會啟動。</span><span class="sxs-lookup"><span data-stu-id="701e7-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="701e7-222">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-223">19</span><span class="sxs-lookup"><span data-stu-id="701e7-223">19</span></span></td>
<td><span data-ttu-id="701e7-224">OOBE (Windows 歡迎) 尚未完成。</span><span class="sxs-lookup"><span data-stu-id="701e7-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="701e7-225">只有在任何 Windows 更新安裝完畢後，服務才會啟動。</span><span class="sxs-lookup"><span data-stu-id="701e7-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="701e7-226">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="701e7-227">如果此錯誤在系統重新開機之後仍然存在，請確定所有 Windows 更新已完整安裝。</span><span class="sxs-lookup"><span data-stu-id="701e7-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-228">共</span><span class="sxs-lookup"><span data-stu-id="701e7-228">20</span></span></td>
<td><span data-ttu-id="701e7-229">無法等候 OOBE (Windows 歡迎) 完成。</span><span class="sxs-lookup"><span data-stu-id="701e7-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="701e7-230">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-231">內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-231">Internal error.</span></span></td>
<td><span data-ttu-id="701e7-232">如果此錯誤在系統重新開機之後仍然存在，請確定所有 Windows 更新已完整安裝。</span><span class="sxs-lookup"><span data-stu-id="701e7-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-233">0.25</span><span class="sxs-lookup"><span data-stu-id="701e7-233">25</span></span></td>
<td><span data-ttu-id="701e7-234">Microsoft Defender for Endpoint service 無法重設登錄中的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="701e7-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="701e7-235">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-236">裝置上架不正確。</span><span class="sxs-lookup"><span data-stu-id="701e7-236">The device did not onboard correctly.</span></span>
<span data-ttu-id="701e7-237">它會向入口網站回報，但服務可能不會顯示在 SCCM 或登錄中的註冊。</span><span class="sxs-lookup"><span data-stu-id="701e7-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="701e7-238">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-239">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-240">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-241">得到</span><span class="sxs-lookup"><span data-stu-id="701e7-241">26</span></span></td>
<td><span data-ttu-id="701e7-242">Microsoft Defender for Endpoint service 無法在登錄中設定上架狀態。</span><span class="sxs-lookup"><span data-stu-id="701e7-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="701e7-243">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-244">裝置上架不正確。</span><span class="sxs-lookup"><span data-stu-id="701e7-244">The device did not onboard correctly.</span></span><br>
<span data-ttu-id="701e7-245">它會向入口網站回報，但服務可能不會顯示在 SCCM 或登錄中的註冊。</span><span class="sxs-lookup"><span data-stu-id="701e7-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="701e7-246">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-247">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-248">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-249">7</span><span class="sxs-lookup"><span data-stu-id="701e7-249">27</span></span></td>
<td><span data-ttu-id="701e7-250">Microsoft defender for Endpoint service 無法啟用 Microsoft Defender 防毒軟體中的感知感知模式。</span><span class="sxs-lookup"><span data-stu-id="701e7-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="701e7-251">上架過程失敗。</span><span class="sxs-lookup"><span data-stu-id="701e7-251">Onboarding process failed.</span></span> <span data-ttu-id="701e7-252">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-253">一般情況下，如果其他即時惡意程式碼產品已在裝置上正常執行，則 Microsoft Defender 防病毒會進入特殊的被動狀態，而且裝置會向 Defender 報告端點。</span><span class="sxs-lookup"><span data-stu-id="701e7-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="701e7-254">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-255">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-256">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="701e7-257">確定即時反惡意程式碼保護運作正常。</span><span class="sxs-lookup"><span data-stu-id="701e7-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-258">日</span><span class="sxs-lookup"><span data-stu-id="701e7-258">28</span></span></td>
<td><span data-ttu-id="701e7-259">Microsoft Defender 連線使用者經驗與遙測服務註冊失敗。</span><span class="sxs-lookup"><span data-stu-id="701e7-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="701e7-260">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-261">Windows 遙測服務發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="701e7-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="701e7-263">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-264">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-265">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-266">29</span><span class="sxs-lookup"><span data-stu-id="701e7-266">29</span></span></td>
<td><span data-ttu-id="701e7-267">無法讀取脫離參數。</span><span class="sxs-lookup"><span data-stu-id="701e7-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="701e7-268">錯誤類型： %1，錯誤碼： %2，描述： %3</span><span class="sxs-lookup"><span data-stu-id="701e7-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="701e7-269">當系統可以&#39;t 讀取脫離參數時，就會發生此事件。</span><span class="sxs-lookup"><span data-stu-id="701e7-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="701e7-270">確定裝置具有網際網路存取權，然後再次執行整個脫離程式。</span><span class="sxs-lookup"><span data-stu-id="701e7-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="701e7-271">確定脫離套件尚未過期。</span><span class="sxs-lookup"><span data-stu-id="701e7-271">Ensure the offboarding package has not expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-272">大約</span><span class="sxs-lookup"><span data-stu-id="701e7-272">30</span></span></td>
<td><span data-ttu-id="701e7-273">Microsoft Defender for Endpoint service 無法停用 Microsoft Defender 防病毒中的感知感知模式。</span><span class="sxs-lookup"><span data-stu-id="701e7-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="701e7-274">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-275">一般情況下，如果其他即時惡意程式碼產品已在裝置上正常執行，則 Microsoft Defender 防病毒會進入特殊的被動狀態，而且裝置會向 Defender 報告端點。</span><span class="sxs-lookup"><span data-stu-id="701e7-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="701e7-276">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-277">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-278">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a></span><span class="sxs-lookup"><span data-stu-id="701e7-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="701e7-279">確定即時反惡意程式碼保護運作正常。</span><span class="sxs-lookup"><span data-stu-id="701e7-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-280">加</span><span class="sxs-lookup"><span data-stu-id="701e7-280">31</span></span></td>
<td><span data-ttu-id="701e7-281">Microsoft Defender 連線使用者經驗與遙測服務登出失敗。</span><span class="sxs-lookup"><span data-stu-id="701e7-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="701e7-282">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-283">在上架期間執行 Windows 遙測服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="701e7-284">脫離處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="701e7-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="701e7-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">使用 Windows 遙測服務檢查錯誤</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-286">32</span><span class="sxs-lookup"><span data-stu-id="701e7-286">32</span></span></td>
<td><span data-ttu-id="701e7-287">Microsoft Defender for Endpoint service 無法在脫離程式後要求自行停用。</span><span class="sxs-lookup"><span data-stu-id="701e7-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="701e7-288">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="701e7-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="701e7-289">脫離時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="701e7-290">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="701e7-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-291">33</span><span class="sxs-lookup"><span data-stu-id="701e7-291">33</span></span></td>
<td><span data-ttu-id="701e7-292">Microsoft Defender for Endpoint service 無法保留感知 GUID。</span><span class="sxs-lookup"><span data-stu-id="701e7-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="701e7-293">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-294">唯一識別碼是用來表示每個向入口網站回報的裝置。</span><span class="sxs-lookup"><span data-stu-id="701e7-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="701e7-295">如果識別碼不存在，相同的裝置可能會出現在入口網站的兩倍。</span><span class="sxs-lookup"><span data-stu-id="701e7-295">If the identifier does not persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="701e7-296">請檢查裝置的登入權利，以確定服務可更新登錄。</span><span class="sxs-lookup"><span data-stu-id="701e7-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-297">34</span><span class="sxs-lookup"><span data-stu-id="701e7-297">34</span></span></td>
<td><span data-ttu-id="701e7-298">Microsoft Defender for Endpoint service 無法將其自我新增為對連接的使用者經驗和遙測服務的相依性，導致上架處理常式失敗。</span><span class="sxs-lookup"><span data-stu-id="701e7-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="701e7-299">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-300">Windows 遙測服務發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="701e7-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="701e7-302">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="701e7-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="701e7-303">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="701e7-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="701e7-304">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="701e7-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-305">35</span><span class="sxs-lookup"><span data-stu-id="701e7-305">35</span></span></td>
<td><span data-ttu-id="701e7-306">Microsoft Defender for Endpoint service 無法將其自我移除為對連接的使用者經驗和遙測服務的依賴性。</span><span class="sxs-lookup"><span data-stu-id="701e7-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="701e7-307">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-308">在脫離時執行 Windows 遙測服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="701e7-309">脫離處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="701e7-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="701e7-310">使用 Windows 診斷資料服務檢查錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-311">36</span><span class="sxs-lookup"><span data-stu-id="701e7-311">36</span></span></td>
<td><span data-ttu-id="701e7-312">Microsoft Defender 連線使用者經驗和遙測服務註冊成功。</span><span class="sxs-lookup"><span data-stu-id="701e7-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="701e7-313">完成碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="701e7-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="701e7-314">已成功完成登錄使用者經驗與遙測服務之端點的 Defender 註冊。</span><span class="sxs-lookup"><span data-stu-id="701e7-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="701e7-315">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-316">37</span><span class="sxs-lookup"><span data-stu-id="701e7-316">37</span></span></td>
<td><span data-ttu-id="701e7-317">Microsoft Defender for Endpoint A 模組即將超出其配額。</span><span class="sxs-lookup"><span data-stu-id="701e7-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="701e7-318">模組： %1，配額： {%2} {%3}，配額利用率百分比： %4。</span><span class="sxs-lookup"><span data-stu-id="701e7-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="701e7-319">裝置幾乎已使用目前24小時視窗的已分配配額。</span><span class="sxs-lookup"><span data-stu-id="701e7-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="701e7-320">即將受到節流。</span><span class="sxs-lookup"><span data-stu-id="701e7-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="701e7-321">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-322">38</span><span class="sxs-lookup"><span data-stu-id="701e7-322">38</span></span></td>
<td><span data-ttu-id="701e7-323">網路連線識別為低。</span><span class="sxs-lookup"><span data-stu-id="701e7-323">Network connection is identified as low.</span></span> <span data-ttu-id="701e7-324">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="701e7-325">流量 %2，網際網路可用： %3，可用空閒網路： %4。</span><span class="sxs-lookup"><span data-stu-id="701e7-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="701e7-326">裝置使用的是計量/收費網路，且將不會頻繁地聯繫伺服器。</span><span class="sxs-lookup"><span data-stu-id="701e7-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="701e7-327">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-328">39</span><span class="sxs-lookup"><span data-stu-id="701e7-328">39</span></span></td>
<td><span data-ttu-id="701e7-329">網路連線識別為正常。</span><span class="sxs-lookup"><span data-stu-id="701e7-329">Network connection is identified as normal.</span></span> <span data-ttu-id="701e7-330">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="701e7-331">流量 %2，網際網路可用： %3，可用空閒網路： %4。</span><span class="sxs-lookup"><span data-stu-id="701e7-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="701e7-332">裝置未使用計量中/付費的連線，因此會照常聯繫伺服器。</span><span class="sxs-lookup"><span data-stu-id="701e7-332">The device is not using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="701e7-333">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-334">40</span><span class="sxs-lookup"><span data-stu-id="701e7-334">40</span></span></td>
<td><span data-ttu-id="701e7-335">電池狀態識別為 [低]。</span><span class="sxs-lookup"><span data-stu-id="701e7-335">Battery state is identified as low.</span></span> <span data-ttu-id="701e7-336">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="701e7-337">電池狀態： %2。</span><span class="sxs-lookup"><span data-stu-id="701e7-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="701e7-338">裝置的電池計量低，且將不會頻繁地與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="701e7-339">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-340">41</span><span class="sxs-lookup"><span data-stu-id="701e7-340">41</span></span></td>
<td><span data-ttu-id="701e7-341">電池狀態識別為 [正常]。</span><span class="sxs-lookup"><span data-stu-id="701e7-341">Battery state is identified as normal.</span></span> <span data-ttu-id="701e7-342">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="701e7-343">電池狀態： %2。</span><span class="sxs-lookup"><span data-stu-id="701e7-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="701e7-344">裝置的電池計量低，且會照常聯繫伺服器。</span><span class="sxs-lookup"><span data-stu-id="701e7-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="701e7-345">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-346">42</span><span class="sxs-lookup"><span data-stu-id="701e7-346">42</span></span></td>
<td><span data-ttu-id="701e7-347">Microsoft Defender for Endpoint WDATP 元件無法執行動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="701e7-348">元件： %1，動作： %2，例外狀況類型： %3，例外訊息： %4</span><span class="sxs-lookup"><span data-stu-id="701e7-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="701e7-349">內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-349">Internal error.</span></span> <span data-ttu-id="701e7-350">無法啟動服務。</span><span class="sxs-lookup"><span data-stu-id="701e7-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="701e7-351">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-352">43</span><span class="sxs-lookup"><span data-stu-id="701e7-352">43</span></span></td>
<td><span data-ttu-id="701e7-353">Microsoft Defender for Endpoint WDATP 元件無法執行動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="701e7-354">元件： %1，動作： %2，例外狀況類型： %3，例外錯誤： %4，例外資訊： %5</span><span class="sxs-lookup"><span data-stu-id="701e7-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="701e7-355">內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-355">Internal error.</span></span> <span data-ttu-id="701e7-356">無法啟動服務。</span><span class="sxs-lookup"><span data-stu-id="701e7-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="701e7-357">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-358">44</span><span class="sxs-lookup"><span data-stu-id="701e7-358">44</span></span></td>
<td><span data-ttu-id="701e7-359">終結點服務的已完成的 Defender 服務。</span><span class="sxs-lookup"><span data-stu-id="701e7-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="701e7-360">已 offboarded 服務。</span><span class="sxs-lookup"><span data-stu-id="701e7-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="701e7-361">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-362">45</span><span class="sxs-lookup"><span data-stu-id="701e7-362">45</span></span></td>
<td><span data-ttu-id="701e7-363">無法註冊並啟動事件追蹤會話 [%1]。</span><span class="sxs-lookup"><span data-stu-id="701e7-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="701e7-364">錯誤碼： %2</span><span class="sxs-lookup"><span data-stu-id="701e7-364">Error code: %2</span></span></td>
<td><span data-ttu-id="701e7-365">建立 ETW 會話時，啟動服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="701e7-366">這會導致服務啟動失敗。</span><span class="sxs-lookup"><span data-stu-id="701e7-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="701e7-367">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="701e7-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-368">46</span><span class="sxs-lookup"><span data-stu-id="701e7-368">46</span></span></td>
<td><span data-ttu-id="701e7-369">由於資源缺乏，無法註冊並啟動事件追蹤會話 [%1]。</span><span class="sxs-lookup"><span data-stu-id="701e7-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="701e7-370">錯誤碼： %2。</span><span class="sxs-lookup"><span data-stu-id="701e7-370">Error code: %2.</span></span> <span data-ttu-id="701e7-371">這很可能是因為活動中的事件追蹤會話太多。</span><span class="sxs-lookup"><span data-stu-id="701e7-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="701e7-372">服務會在1分鐘後重試。</span><span class="sxs-lookup"><span data-stu-id="701e7-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="701e7-373">因為資源缺乏，所以在建立 ETW 會話時，啟動服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="701e7-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="701e7-374">服務已開始且正在執行，但在啟動 ETW 會話之前，不會報告任何感應器事件。</span><span class="sxs-lookup"><span data-stu-id="701e7-374">The service started and is running, but will not report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="701e7-375">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="701e7-376">服務每分鐘會嘗試啟動會話。</span><span class="sxs-lookup"><span data-stu-id="701e7-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-377">47</span><span class="sxs-lookup"><span data-stu-id="701e7-377">47</span></span></td>
<td><span data-ttu-id="701e7-378">已成功註冊並啟動事件追蹤會話-在先前的失敗嘗試之後復原。</span><span class="sxs-lookup"><span data-stu-id="701e7-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="701e7-379">此事件會在成功啟動 ETW 會話後，遵循上一個事件。</span><span class="sxs-lookup"><span data-stu-id="701e7-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="701e7-380">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="701e7-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="701e7-381">48</span><span class="sxs-lookup"><span data-stu-id="701e7-381">48</span></span></td>
<td><span data-ttu-id="701e7-382">無法將提供者 [%1] 新增至事件追蹤會話 [%2]。</span><span class="sxs-lookup"><span data-stu-id="701e7-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="701e7-383">錯誤碼： %3。</span><span class="sxs-lookup"><span data-stu-id="701e7-383">Error code: %3.</span></span> <span data-ttu-id="701e7-384">這表示不會報告來自此提供者的事件。</span><span class="sxs-lookup"><span data-stu-id="701e7-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="701e7-385">無法將提供者新增至 ETW 會話。</span><span class="sxs-lookup"><span data-stu-id="701e7-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="701e7-386">因此，不會報告提供者事件。</span><span class="sxs-lookup"><span data-stu-id="701e7-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="701e7-387">檢查錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="701e7-387">Check the error code.</span></span> <span data-ttu-id="701e7-388">如果此錯誤仍然存在，請聯繫支援人員。</span><span class="sxs-lookup"><span data-stu-id="701e7-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
</tbody>
</table>

><span data-ttu-id="701e7-389">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="701e7-389">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="701e7-390">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="701e7-390">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="701e7-391">相關主題</span><span class="sxs-lookup"><span data-stu-id="701e7-391">Related topics</span></span>
- [<span data-ttu-id="701e7-392">板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="701e7-392">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="701e7-393">設定裝置 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="701e7-393">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="701e7-394">疑難排解 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="701e7-394">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
