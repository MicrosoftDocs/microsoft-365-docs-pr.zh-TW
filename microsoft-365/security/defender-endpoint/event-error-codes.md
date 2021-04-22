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
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933838"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="7d2bc-104">使用事件檢視器審閱事件和錯誤</span><span class="sxs-lookup"><span data-stu-id="7d2bc-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7d2bc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="7d2bc-105">**Applies to:**</span></span>
- <span data-ttu-id="7d2bc-106">事件檢視器</span><span class="sxs-lookup"><span data-stu-id="7d2bc-106">Event Viewer</span></span>
- [<span data-ttu-id="7d2bc-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7d2bc-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="7d2bc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d2bc-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="7d2bc-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="7d2bc-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d2bc-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="7d2bc-111">您可以在個別裝置的 [事件檢視器](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 中審閱事件 IDs。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="7d2bc-112">例如，如果裝置未出現在 [ **裝置] 清單** 中，您可能需要在裝置上尋找事件 IDs。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="7d2bc-113">您可以使用此表格來決定進一步的疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="7d2bc-114">**開啟事件檢視器，並尋找 Microsoft Defender for Endpoint service 事件記錄檔：**</span><span class="sxs-lookup"><span data-stu-id="7d2bc-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="7d2bc-115">在 [Windows] 功能表上，按一下 [ **開始** ]，輸入 **事件檢視器**，然後按 **enter** 鍵。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="7d2bc-116">在 [記錄檔] 清單的 [**記錄摘要**] 下，向內滾動，直到看到 [ **Microsoft-Windows------Windows-**</span><span class="sxs-lookup"><span data-stu-id="7d2bc-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="7d2bc-117">按兩下專案以開啟記錄檔。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="7d2bc-118">a.</span><span class="sxs-lookup"><span data-stu-id="7d2bc-118">a.</span></span>  <span data-ttu-id="7d2bc-119">您也可以透過擴充 **應用程式和服務記錄**  >  **Microsoft**  >  **Windows**  >  **感知**，然後按一下 [**操作**] 來存取記錄。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7d2bc-120">判斷是指用來表示為 Microsoft Defender for Endpoint 供電的行為感應器的內部名稱。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="7d2bc-121">服務所記錄的事件會出現在記錄檔中。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="7d2bc-122">如需服務所記錄的事件清單，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="7d2bc-123">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="7d2bc-123">Event ID</span></span></th>
<th><span data-ttu-id="7d2bc-124">訊息</span><span class="sxs-lookup"><span data-stu-id="7d2bc-124">Message</span></span></th>
<th><span data-ttu-id="7d2bc-125">描述</span><span class="sxs-lookup"><span data-stu-id="7d2bc-125">Description</span></span></th>
<th><span data-ttu-id="7d2bc-126">動作</span><span class="sxs-lookup"><span data-stu-id="7d2bc-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-127">1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-127">1</span></span></td>
<td><span data-ttu-id="7d2bc-128">Microsoft Defender for Endpoint service 已開始 (版本 <code>variable</code>) 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="7d2bc-129">發生于系統啟動、關機和上架期間。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="7d2bc-130">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-131">第</span><span class="sxs-lookup"><span data-stu-id="7d2bc-131">2</span></span></td>
<td><span data-ttu-id="7d2bc-132">Microsoft Defender for Endpoint service 關閉。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="7d2bc-133">當裝置關閉或 offboarded 時會發生此事件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="7d2bc-134">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-135">個</span><span class="sxs-lookup"><span data-stu-id="7d2bc-135">3</span></span></td>
<td><span data-ttu-id="7d2bc-136">無法啟動 Microsoft Defender for Endpoint service。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="7d2bc-137">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-138">服務未啟動。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="7d2bc-139">請複查其他訊息，以判斷可能的原因及疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-140">4 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-140">4</span></span></td>
<td><span data-ttu-id="7d2bc-141">Microsoft Defender for Endpoint service 已于的伺服器取得聯繫 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-142">Variable = 端點處理伺服器的 Defender URL。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="7d2bc-143">此 URL 會比對防火牆或網路活動中所看到的。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="7d2bc-144">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-145">5 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-145">5</span></span></td>
<td><span data-ttu-id="7d2bc-146">Microsoft Defender for Endpoint service 無法連線至上的伺服器 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-147">Variable = 端點處理伺服器的 Defender URL。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="7d2bc-148">服務無法與位於該 URL 的外部處理伺服器聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="7d2bc-149">檢查 URL 的連線。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-149">Check the connection to the URL.</span></span> <span data-ttu-id="7d2bc-150">請參閱 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">設定 proxy 和網際網路連線</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-151">6 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-151">6</span></span></td>
<td><span data-ttu-id="7d2bc-152">Microsoft Defender for Endpoint service 未架，且找不到任何上架參數。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="7d2bc-153">裝置沒有正確板載，而且不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="7d2bc-154">在啟動服務之前，必須先執行上架。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="7d2bc-155">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-156">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-157">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-158">7 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-158">7</span></span></td>
<td><span data-ttu-id="7d2bc-159">Microsoft Defender for Endpoint service 無法讀取上架參數。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="7d2bc-160">失敗： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-161">Variable = 詳細的錯誤描述。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-161">Variable = detailed error description.</span></span> <span data-ttu-id="7d2bc-162">裝置沒有正確板載，而且不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="7d2bc-163">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-164">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-165">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-166">8 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-166">8</span></span></td>
<td><span data-ttu-id="7d2bc-167">Microsoft Defender for Endpoint service 無法清除其設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="7d2bc-168">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-169"><b>在上架期間：</b> 服務無法在上架期間清除其設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="7d2bc-170">上架處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="7d2bc-171"><b>脫離時：</b> 服務無法在脫離期間清除其設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="7d2bc-172">脫離處理常式完成，但服務仍在執行中。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="7d2bc-173">上<b>架：</b>不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="7d2bc-174"><b>脫離：</b> 重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="7d2bc-175">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-176">9 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-176">9</span></span></td>
<td><span data-ttu-id="7d2bc-177">Microsoft Defender for Endpoint service 無法變更其啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="7d2bc-178">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-179"><b>在上架期間：</b> 裝置沒有正確板載，而且不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="7d2bc-180"><b>脫離時：</b> 無法變更服務啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="7d2bc-181">脫離處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="7d2bc-182">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-183">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-184">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-185">10 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-185">10</span></span></td>
<td><span data-ttu-id="7d2bc-186">Microsoft Defender for Endpoint service 無法保留上架資訊。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="7d2bc-187">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-188">裝置沒有正確板載，而且不會向入口網站回報。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="7d2bc-189">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-190">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-191">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-192">11 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-192">11</span></span></td>
<td><span data-ttu-id="7d2bc-193">上架服務已完成的 Defender 或重新加入。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="7d2bc-194">裝置架正確。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="7d2bc-195">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="7d2bc-196">可能需要數小時的時間，裝置才會出現在入口網站中。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-197">12 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-197">12</span></span></td>
<td><span data-ttu-id="7d2bc-198">Microsoft Defender for Endpoint 無法套用預設設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="7d2bc-199">服務無法套用預設設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="7d2bc-200">此錯誤應在一小段時間後解決。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-201">13</span><span class="sxs-lookup"><span data-stu-id="7d2bc-201">13</span></span></td>
<td><span data-ttu-id="7d2bc-202">Microsoft Defender for Endpoint 設備識別碼已計算： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-203">正常工作處理程式。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="7d2bc-204">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-205">15 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-205">15</span></span></td>
<td><span data-ttu-id="7d2bc-206">Microsoft Defender for Endpoint 無法使用 URL: 啟動命令通道 <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-207">Variable = 端點處理伺服器的 Defender URL。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="7d2bc-208">服務無法與位於該 URL 的外部處理伺服器聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="7d2bc-209">檢查 URL 的連線。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-209">Check the connection to the URL.</span></span> <span data-ttu-id="7d2bc-210">請參閱 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">設定 proxy 和網際網路連線</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-211">17 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-211">17</span></span></td>
<td><span data-ttu-id="7d2bc-212">Microsoft Defender for Endpoint service 無法變更連線的使用者經驗和遙測服務位置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="7d2bc-213">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-214">Windows 遙測服務發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="7d2bc-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="7d2bc-216">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-217">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-218">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-219">18 </span><span class="sxs-lookup"><span data-stu-id="7d2bc-219">18</span></span></td>
<td><span data-ttu-id="7d2bc-220">已完成 OOBE (Windows 歡迎) 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="7d2bc-221">只有在任何 Windows 更新安裝完畢後，服務才會啟動。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="7d2bc-222">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-223">19</span><span class="sxs-lookup"><span data-stu-id="7d2bc-223">19</span></span></td>
<td><span data-ttu-id="7d2bc-224">OOBE (Windows 歡迎) 尚未完成。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="7d2bc-225">只有在任何 Windows 更新安裝完畢後，服務才會啟動。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="7d2bc-226">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="7d2bc-227">如果此錯誤在系統重新開機之後仍然存在，請確定所有 Windows 更新已完整安裝。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-228">共</span><span class="sxs-lookup"><span data-stu-id="7d2bc-228">20</span></span></td>
<td><span data-ttu-id="7d2bc-229">無法等候 OOBE (Windows 歡迎) 完成。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="7d2bc-230">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-231">內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-231">Internal error.</span></span></td>
<td><span data-ttu-id="7d2bc-232">如果此錯誤在系統重新開機之後仍然存在，請確定所有 Windows 更新已完整安裝。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-233">0.25</span><span class="sxs-lookup"><span data-stu-id="7d2bc-233">25</span></span></td>
<td><span data-ttu-id="7d2bc-234">Microsoft Defender for Endpoint service 無法重設登錄中的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="7d2bc-235">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-236">裝置沒有正確板載。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="7d2bc-237">它會向入口網站回報，但服務可能不會顯示在 SCCM 或登錄中的註冊。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="7d2bc-238">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-239">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-240">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-241">得到</span><span class="sxs-lookup"><span data-stu-id="7d2bc-241">26</span></span></td>
<td><span data-ttu-id="7d2bc-242">Microsoft Defender for Endpoint service 無法在登錄中設定上架狀態。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="7d2bc-243">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-244">裝置沒有正確板載。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="7d2bc-245">它會向入口網站回報，但服務可能不會顯示在 SCCM 或登錄中的註冊。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="7d2bc-246">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-247">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-248">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-249">7</span><span class="sxs-lookup"><span data-stu-id="7d2bc-249">27</span></span></td>
<td><span data-ttu-id="7d2bc-250">Microsoft defender for Endpoint service 無法啟用 Microsoft Defender 防毒軟體中的感知感知模式。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="7d2bc-251">上架過程失敗。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-251">Onboarding process failed.</span></span> <span data-ttu-id="7d2bc-252">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-253">一般情況下，如果其他即時惡意程式碼產品已在裝置上正常執行，則 Microsoft Defender 防病毒會進入特殊的被動狀態，而且裝置會向 Defender 報告端點。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="7d2bc-254">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-255">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-256">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="7d2bc-257">確定即時反惡意程式碼保護運作正常。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-258">日</span><span class="sxs-lookup"><span data-stu-id="7d2bc-258">28</span></span></td>
<td><span data-ttu-id="7d2bc-259">Microsoft Defender 連線使用者經驗與遙測服務註冊失敗。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="7d2bc-260">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-261">Windows 遙測服務發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="7d2bc-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="7d2bc-263">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-264">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-265">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-266">29</span><span class="sxs-lookup"><span data-stu-id="7d2bc-266">29</span></span></td>
<td><span data-ttu-id="7d2bc-267">無法讀取脫離參數。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="7d2bc-268">錯誤類型： %1，錯誤碼： %2，描述： %3</span><span class="sxs-lookup"><span data-stu-id="7d2bc-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="7d2bc-269">當系統可以&#39;t 讀取脫離參數時，就會發生此事件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="7d2bc-270">確定裝置具有網際網路存取權，然後再次執行整個脫離程式。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="7d2bc-271">確定脫離套件尚未過期。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-272">大約</span><span class="sxs-lookup"><span data-stu-id="7d2bc-272">30</span></span></td>
<td><span data-ttu-id="7d2bc-273">Microsoft Defender for Endpoint service 無法停用 Microsoft Defender 防病毒中的感知感知模式。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="7d2bc-274">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-275">一般情況下，如果其他即時惡意程式碼產品已在裝置上正常執行，則 Microsoft Defender 防病毒會進入特殊的被動狀態，而且裝置會向 Defender 報告端點。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="7d2bc-276">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-277">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-278">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a></span><span class="sxs-lookup"><span data-stu-id="7d2bc-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="7d2bc-279">確定即時反惡意程式碼保護運作正常。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-280">加</span><span class="sxs-lookup"><span data-stu-id="7d2bc-280">31</span></span></td>
<td><span data-ttu-id="7d2bc-281">Microsoft Defender 連線使用者經驗與遙測服務登出失敗。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="7d2bc-282">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-283">在上架期間執行 Windows 遙測服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="7d2bc-284">脫離處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="7d2bc-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">使用 Windows 遙測服務檢查錯誤</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-286">32</span><span class="sxs-lookup"><span data-stu-id="7d2bc-286">32</span></span></td>
<td><span data-ttu-id="7d2bc-287">Microsoft Defender for Endpoint service 無法在脫離程式後要求自行停用。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="7d2bc-288">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="7d2bc-289">脫離時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="7d2bc-290">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-291">33</span><span class="sxs-lookup"><span data-stu-id="7d2bc-291">33</span></span></td>
<td><span data-ttu-id="7d2bc-292">Microsoft Defender for Endpoint service 無法保留感知 GUID。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="7d2bc-293">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-294">唯一識別碼是用來表示每個向入口網站回報的裝置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="7d2bc-295">如果識別碼不存在，相同的裝置可能會出現在入口網站的兩倍。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="7d2bc-296">請檢查裝置的登入權利，以確定服務可更新登錄。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-297">34</span><span class="sxs-lookup"><span data-stu-id="7d2bc-297">34</span></span></td>
<td><span data-ttu-id="7d2bc-298">Microsoft Defender for Endpoint service 無法將其自我新增為對連接的使用者經驗和遙測服務的相依性，導致上架處理常式失敗。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="7d2bc-299">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-300">Windows 遙測服務發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="7d2bc-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">確定已啟用診斷資料服務</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="7d2bc-302">檢查是否已正確部署上架設定和腳本。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="7d2bc-303">嘗試重新部署設定套件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="7d2bc-304">請參閱 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">板載 Windows 10 裝置</a>。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-305">35</span><span class="sxs-lookup"><span data-stu-id="7d2bc-305">35</span></span></td>
<td><span data-ttu-id="7d2bc-306">Microsoft Defender for Endpoint service 無法將其自我移除為對連接的使用者經驗和遙測服務的依賴性。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="7d2bc-307">失敗代碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-308">在脫離時執行 Windows 遙測服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="7d2bc-309">脫離處理常式會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="7d2bc-310">使用 Windows 診斷資料服務檢查錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-311">36</span><span class="sxs-lookup"><span data-stu-id="7d2bc-311">36</span></span></td>
<td><span data-ttu-id="7d2bc-312">Microsoft Defender 連線使用者經驗和遙測服務註冊成功。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="7d2bc-313">完成碼： <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="7d2bc-314">已成功完成登錄使用者經驗與遙測服務之端點的 Defender 註冊。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="7d2bc-315">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-316">37</span><span class="sxs-lookup"><span data-stu-id="7d2bc-316">37</span></span></td>
<td><span data-ttu-id="7d2bc-317">Microsoft Defender for Endpoint A 模組即將超出其配額。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="7d2bc-318">模組： %1，配額： {%2} {%3}，配額利用率百分比： %4。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="7d2bc-319">裝置幾乎已使用目前24小時視窗的已分配配額。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="7d2bc-320">即將受到節流。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="7d2bc-321">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-322">38</span><span class="sxs-lookup"><span data-stu-id="7d2bc-322">38</span></span></td>
<td><span data-ttu-id="7d2bc-323">網路連線識別為低。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-323">Network connection is identified as low.</span></span> <span data-ttu-id="7d2bc-324">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="7d2bc-325">流量 %2，網際網路可用： %3，可用空閒網路： %4。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="7d2bc-326">裝置使用的是計量/收費網路，且將不會頻繁地聯繫伺服器。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="7d2bc-327">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-328">39</span><span class="sxs-lookup"><span data-stu-id="7d2bc-328">39</span></span></td>
<td><span data-ttu-id="7d2bc-329">網路連線識別為正常。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-329">Network connection is identified as normal.</span></span> <span data-ttu-id="7d2bc-330">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="7d2bc-331">流量 %2，網際網路可用： %3，可用空閒網路： %4。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="7d2bc-332">裝置未使用計量中/付費的連線，因此會照常聯繫伺服器。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="7d2bc-333">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-334">40</span><span class="sxs-lookup"><span data-stu-id="7d2bc-334">40</span></span></td>
<td><span data-ttu-id="7d2bc-335">電池狀態識別為 [低]。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-335">Battery state is identified as low.</span></span> <span data-ttu-id="7d2bc-336">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="7d2bc-337">電池狀態： %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="7d2bc-338">裝置的電池計量低，且將不會頻繁地與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="7d2bc-339">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-340">41</span><span class="sxs-lookup"><span data-stu-id="7d2bc-340">41</span></span></td>
<td><span data-ttu-id="7d2bc-341">電池狀態識別為 [正常]。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-341">Battery state is identified as normal.</span></span> <span data-ttu-id="7d2bc-342">Microsoft Defender for Endpoint 會每隔 %1 分鐘與伺服器取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="7d2bc-343">電池狀態： %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="7d2bc-344">裝置的電池計量低，且會照常聯繫伺服器。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="7d2bc-345">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-346">42</span><span class="sxs-lookup"><span data-stu-id="7d2bc-346">42</span></span></td>
<td><span data-ttu-id="7d2bc-347">Microsoft Defender for Endpoint 元件無法執行動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="7d2bc-348">元件： %1，動作： %2，例外狀況類型： %3，例外訊息： %4</span><span class="sxs-lookup"><span data-stu-id="7d2bc-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="7d2bc-349">內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-349">Internal error.</span></span> <span data-ttu-id="7d2bc-350">無法啟動服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="7d2bc-351">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-352">43</span><span class="sxs-lookup"><span data-stu-id="7d2bc-352">43</span></span></td>
<td><span data-ttu-id="7d2bc-353">Microsoft Defender for Endpoint 元件無法執行動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="7d2bc-354">元件： %1，動作： %2，例外狀況類型： %3，例外錯誤： %4，例外資訊： %5</span><span class="sxs-lookup"><span data-stu-id="7d2bc-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="7d2bc-355">內部錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-355">Internal error.</span></span> <span data-ttu-id="7d2bc-356">無法啟動服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="7d2bc-357">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-358">44</span><span class="sxs-lookup"><span data-stu-id="7d2bc-358">44</span></span></td>
<td><span data-ttu-id="7d2bc-359">終結點服務的已完成的 Defender 服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="7d2bc-360">已 offboarded 服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="7d2bc-361">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-362">45</span><span class="sxs-lookup"><span data-stu-id="7d2bc-362">45</span></span></td>
<td><span data-ttu-id="7d2bc-363">無法註冊並啟動事件追蹤會話 [%1]。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="7d2bc-364">錯誤碼： %2</span><span class="sxs-lookup"><span data-stu-id="7d2bc-364">Error code: %2</span></span></td>
<td><span data-ttu-id="7d2bc-365">建立 ETW 會話時，啟動服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="7d2bc-366">這會導致服務啟動失敗。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="7d2bc-367">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-368">46</span><span class="sxs-lookup"><span data-stu-id="7d2bc-368">46</span></span></td>
<td><span data-ttu-id="7d2bc-369">由於資源缺乏，無法註冊並啟動事件追蹤會話 [%1]。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="7d2bc-370">錯誤碼： %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-370">Error code: %2.</span></span> <span data-ttu-id="7d2bc-371">這很可能是因為活動中的事件追蹤會話太多。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="7d2bc-372">服務會在1分鐘後重試。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="7d2bc-373">因為資源缺乏，所以在建立 ETW 會話時，啟動服務時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="7d2bc-374">服務已開始且正在執行，但在啟動 ETW 會話之前，不會報告任何感應器事件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="7d2bc-375">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="7d2bc-376">服務每分鐘會嘗試啟動會話。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-377">47</span><span class="sxs-lookup"><span data-stu-id="7d2bc-377">47</span></span></td>
<td><span data-ttu-id="7d2bc-378">已成功註冊並啟動事件追蹤會話-在先前的失敗嘗試之後復原。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="7d2bc-379">此事件會在成功啟動 ETW 會話後，遵循上一個事件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="7d2bc-380">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="7d2bc-381">48</span><span class="sxs-lookup"><span data-stu-id="7d2bc-381">48</span></span></td>
<td><span data-ttu-id="7d2bc-382">無法將提供者 [%1] 新增至事件追蹤會話 [%2]。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="7d2bc-383">錯誤碼： %3。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-383">Error code: %3.</span></span> <span data-ttu-id="7d2bc-384">這表示不會報告來自此提供者的事件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="7d2bc-385">無法將提供者新增至 ETW 會話。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="7d2bc-386">因此，不會報告提供者事件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="7d2bc-387">檢查錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-387">Check the error code.</span></span> <span data-ttu-id="7d2bc-388">如果此錯誤仍然存在，請聯繫支援人員。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-389">49</span><span class="sxs-lookup"><span data-stu-id="7d2bc-389">49</span></span></td>
   <td><span data-ttu-id="7d2bc-390">接收和忽略的雲端設定命令無效。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="7d2bc-391">版本： %1，狀態： %2，錯誤碼： %3，郵件： %4</span><span class="sxs-lookup"><span data-stu-id="7d2bc-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="7d2bc-392">從已忽略的雲端服務接收到不正確設定檔。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="7d2bc-393">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-394">50</span><span class="sxs-lookup"><span data-stu-id="7d2bc-394">50</span></span></td>
   <td><span data-ttu-id="7d2bc-395">已成功套用新的雲端設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="7d2bc-396">版本： %1。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="7d2bc-397">已成功從雲端服務套用新設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="7d2bc-398">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-399">51</span><span class="sxs-lookup"><span data-stu-id="7d2bc-399">51</span></span></td>
   <td><span data-ttu-id="7d2bc-400">無法套用新的雲端設定，版本： %1。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="7d2bc-401">已成功套用最後一個已知良好的設定，版本 %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="7d2bc-402">從雲端服務接收到錯誤的設定檔。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="7d2bc-403">已成功套用上一個正確的設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="7d2bc-404">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-405">52</span><span class="sxs-lookup"><span data-stu-id="7d2bc-405">52</span></span></td>
   <td><span data-ttu-id="7d2bc-406">無法套用新的雲端設定，版本： %1。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="7d2bc-407">也無法套用最後一個已知良好的設定，版本 %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="7d2bc-408">已成功套用預設設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="7d2bc-409">從雲端服務接收到錯誤的設定檔。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="7d2bc-410">無法套用最近一次的正確設定，且已套用預設設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="7d2bc-411">服務會在5分鐘內嘗試下載新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="7d2bc-412">如果您看不到事件 #50-請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-413">53</span><span class="sxs-lookup"><span data-stu-id="7d2bc-413">53</span></span></td>
   <td><span data-ttu-id="7d2bc-414">從持久性儲存體載入雲端設定，版本： %1。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="7d2bc-415">在服務啟動時從持久性儲存體載入設定。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="7d2bc-416">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-417">55</span><span class="sxs-lookup"><span data-stu-id="7d2bc-417">55</span></span></td>
   <td><span data-ttu-id="7d2bc-418">無法建立安全的 ETW 自動記錄器。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="7d2bc-419">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-420">無法建立安全的 ETW 記錄記錄。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="7d2bc-421">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-421">Reboot the device.</span></span> <span data-ttu-id="7d2bc-422">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-423">56</span><span class="sxs-lookup"><span data-stu-id="7d2bc-423">56</span></span></td>
   <td><span data-ttu-id="7d2bc-424">無法移除 Secure ETW 自動記錄器。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="7d2bc-425">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-426">無法在脫離時移除 secure ETW 會話。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="7d2bc-427">聯繫支援人員。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-428">57</span><span class="sxs-lookup"><span data-stu-id="7d2bc-428">57</span></span></td>
   <td><span data-ttu-id="7d2bc-429">出於疑難排解目的，捕獲機器的快照。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="7d2bc-430">會收集調查套件（也稱為取證套件）。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="7d2bc-431">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-432">59</span><span class="sxs-lookup"><span data-stu-id="7d2bc-432">59</span></span></td>
   <td><span data-ttu-id="7d2bc-433">開始命令： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-434">開始回應命令的執行。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="7d2bc-435">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-436">60</span><span class="sxs-lookup"><span data-stu-id="7d2bc-436">60</span></span></td>
   <td><span data-ttu-id="7d2bc-437">無法執行命令 %1，錯誤： %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="7d2bc-438">無法執行回應命令。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="7d2bc-439">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-440">61</span><span class="sxs-lookup"><span data-stu-id="7d2bc-440">61</span></span></td>
   <td><span data-ttu-id="7d2bc-441">資料收集命令參數無效： SasUri： %1，compressionLevel： %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="7d2bc-442">無法讀取或剖析資料收集命令引數 (不正確引數) 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="7d2bc-443">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-444">62</span><span class="sxs-lookup"><span data-stu-id="7d2bc-444">62</span></span></td>
   <td><span data-ttu-id="7d2bc-445">無法啟動連線使用者體驗和遙測服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="7d2bc-446">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-447">連線的使用者經驗和遙測 (diagtrack) 服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="7d2bc-448">不會從此機器傳送非 Microsoft Defender for Endpoint 遙測。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="7d2bc-449">請參閱事件記錄檔中的更多疑難排解提示： Microsoft-Windows-UniversalTelemetryClient/Operational。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-450">63</span><span class="sxs-lookup"><span data-stu-id="7d2bc-450">63</span></span></td>
   <td><span data-ttu-id="7d2bc-451">更新外部服務的啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-451">Updating the start type of external service.</span></span> <span data-ttu-id="7d2bc-452">名稱： %1，實際啟動類型： %2，預期啟動類型： %3，退出程式碼： %4</span><span class="sxs-lookup"><span data-stu-id="7d2bc-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="7d2bc-453">更新的外部服務啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="7d2bc-454">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-455">64</span><span class="sxs-lookup"><span data-stu-id="7d2bc-455">64</span></span></td>
   <td><span data-ttu-id="7d2bc-456">開始已停止的外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-456">Starting stopped external service.</span></span> <span data-ttu-id="7d2bc-457">名稱： %1，退出程式碼： %2</span><span class="sxs-lookup"><span data-stu-id="7d2bc-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="7d2bc-458">啟動外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="7d2bc-459">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-460">65</span><span class="sxs-lookup"><span data-stu-id="7d2bc-460">65</span></span></td>
   <td><span data-ttu-id="7d2bc-461">無法載入 Microsoft Security 事件元件微篩選器驅動程式。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="7d2bc-462">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-463">無法載入 MsSecFlt.sys 的 filesystem 微篩選器。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="7d2bc-464">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-464">Reboot the device.</span></span> <span data-ttu-id="7d2bc-465">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-466">66</span><span class="sxs-lookup"><span data-stu-id="7d2bc-466">66</span></span></td>
   <td><span data-ttu-id="7d2bc-467">原則更新：延遲模式-%1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="7d2bc-468">已更新 C&C connection frequency 原則。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="7d2bc-469">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-470">68</span><span class="sxs-lookup"><span data-stu-id="7d2bc-470">68</span></span></td>
   <td><span data-ttu-id="7d2bc-471">服務的啟動類型是意外的。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="7d2bc-472">服務名稱： %1，實際啟動類型： %2，預期啟動類型： %3</span><span class="sxs-lookup"><span data-stu-id="7d2bc-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="7d2bc-473">意外的外部服務啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="7d2bc-474">修正外部服務啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-475">69</span><span class="sxs-lookup"><span data-stu-id="7d2bc-475">69</span></span></td>
   <td><span data-ttu-id="7d2bc-476">服務已停止。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-476">The service is stopped.</span></span> <span data-ttu-id="7d2bc-477">服務名稱： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-478">停止外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="7d2bc-479">啟動外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-480">70</span><span class="sxs-lookup"><span data-stu-id="7d2bc-480">70</span></span></td>
   <td><span data-ttu-id="7d2bc-481">原則更新：允許範例集合-%1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="7d2bc-482">已更新範例集合原則。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="7d2bc-483">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-484">71</span><span class="sxs-lookup"><span data-stu-id="7d2bc-484">71</span></span></td>
   <td><span data-ttu-id="7d2bc-485">已成功執行命令： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-486">已成功執行命令。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="7d2bc-487">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-488">72</span><span class="sxs-lookup"><span data-stu-id="7d2bc-488">72</span></span></td>
   <td><span data-ttu-id="7d2bc-489">嘗試傳送第一個完整的電腦設定檔報告。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="7d2bc-490">結果代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-491">僅供參考。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-491">Informational only.</span></span></td>
   <td><span data-ttu-id="7d2bc-492">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-493">73</span><span class="sxs-lookup"><span data-stu-id="7d2bc-493">73</span></span></td>
   <td><span data-ttu-id="7d2bc-494">平臺： %1 的感知開始</span><span class="sxs-lookup"><span data-stu-id="7d2bc-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-495">僅供參考。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-495">Informational only.</span></span></td>
   <td><span data-ttu-id="7d2bc-496">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-497">74</span><span class="sxs-lookup"><span data-stu-id="7d2bc-497">74</span></span></td>
   <td><span data-ttu-id="7d2bc-498">登錄中的裝置標記超過長度限制。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="7d2bc-499">標記名稱： %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-499">Tag name: %2.</span></span> <span data-ttu-id="7d2bc-500">長度限制： %1。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="7d2bc-501">Device 標記超過長度限制。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="7d2bc-502">使用較短的裝置標記。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-503">81</span><span class="sxs-lookup"><span data-stu-id="7d2bc-503">81</span></span></td>
   <td><span data-ttu-id="7d2bc-504">無法為端點 ETW 自動記錄器建立 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="7d2bc-505">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-506">無法建立 ETW 會話。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="7d2bc-507">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-507">Reboot the device.</span></span> <span data-ttu-id="7d2bc-508">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-509">82</span><span class="sxs-lookup"><span data-stu-id="7d2bc-509">82</span></span></td>
   <td><span data-ttu-id="7d2bc-510">無法為端點 ETW 自動記錄器移除 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="7d2bc-511">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-512">無法刪除 ETW 會話。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="7d2bc-513">聯繫支援人員。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-514">84</span><span class="sxs-lookup"><span data-stu-id="7d2bc-514">84</span></span></td>
   <td><span data-ttu-id="7d2bc-515">設定 Windows Defender 防毒程式執行模式。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="7d2bc-516">強制被動模式： %1，結果代碼： %2。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="7d2bc-517">設定 (主動或被動) 的 defender 執行模式。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="7d2bc-518">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-519">85</span><span class="sxs-lookup"><span data-stu-id="7d2bc-519">85</span></span></td>
   <td><span data-ttu-id="7d2bc-520">無法觸發 Microsoft Defender for Endpoint executable。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="7d2bc-521">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-522">Starring SenseIR 可執行檔失敗。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="7d2bc-523">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-523">Reboot the device.</span></span> <span data-ttu-id="7d2bc-524">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-525">86</span><span class="sxs-lookup"><span data-stu-id="7d2bc-525">86</span></span></td>
   <td><span data-ttu-id="7d2bc-526">重新開始已停止應啟動的外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="7d2bc-527">名稱： %1，退出程式碼： %2</span><span class="sxs-lookup"><span data-stu-id="7d2bc-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="7d2bc-528">重新開機外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="7d2bc-529">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-530">87</span><span class="sxs-lookup"><span data-stu-id="7d2bc-530">87</span></span></td>
   <td><span data-ttu-id="7d2bc-531">無法啟動外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-531">Cannot start the external service.</span></span> <span data-ttu-id="7d2bc-532">名稱： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-532">Name: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-533">無法啟動外部服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="7d2bc-534">聯繫支援人員。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-535">88</span><span class="sxs-lookup"><span data-stu-id="7d2bc-535">88</span></span></td>
   <td><span data-ttu-id="7d2bc-536">重新更新外部服務的啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-536">Updating the start type of external service again.</span></span> <span data-ttu-id="7d2bc-537">名稱： %1，實際啟動類型： %2，預期啟動類型： %3，退出程式碼： %4</span><span class="sxs-lookup"><span data-stu-id="7d2bc-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="7d2bc-538">已更新外部服務的啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="7d2bc-539">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-540">89</span><span class="sxs-lookup"><span data-stu-id="7d2bc-540">89</span></span></td>
   <td><span data-ttu-id="7d2bc-541">無法更新外部服務的啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="7d2bc-542">名稱： %1，實際啟動類型： %2，預期啟動類型： %3</span><span class="sxs-lookup"><span data-stu-id="7d2bc-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="7d2bc-543">無法更新外部服務的啟動類型。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="7d2bc-544">聯繫支援人員。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-545">90</span><span class="sxs-lookup"><span data-stu-id="7d2bc-545">90</span></span></td>
   <td><span data-ttu-id="7d2bc-546">無法設定 System Guard Runtime Monitor 以連接地理區域 %1 中的雲端服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="7d2bc-547">失敗代碼： %2</span><span class="sxs-lookup"><span data-stu-id="7d2bc-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="7d2bc-548">System Guard Runtime Monitor 不會將證明資料傳送至雲端服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="7d2bc-549">檢查註冊路徑的許可權： "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="7d2bc-550">若未發現任何問題，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-551">91</span><span class="sxs-lookup"><span data-stu-id="7d2bc-551">91</span></span></td>
   <td><span data-ttu-id="7d2bc-552">無法移除 System Guard Runtime Monitor 地理區域資訊。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="7d2bc-553">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-554">System Guard Runtime Monitor 不會將證明資料傳送至雲端服務。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="7d2bc-555">檢查註冊路徑的許可權： "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="7d2bc-556">若未發現任何問題，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-557">92</span><span class="sxs-lookup"><span data-stu-id="7d2bc-557">92</span></span></td>
   <td><span data-ttu-id="7d2bc-558">因為超過資料配額，所以停止傳送感應器網路資料配額。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="7d2bc-559">會在配額週期過後繼續傳送。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="7d2bc-560">狀態遮罩： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-561">超過節流限制。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="7d2bc-562">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-563">93</span><span class="sxs-lookup"><span data-stu-id="7d2bc-563">93</span></span></td>
   <td><span data-ttu-id="7d2bc-564">繼續傳送感應器網路資料。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="7d2bc-565">狀態遮罩： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-566">繼續網路資料提交。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="7d2bc-567">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-568">94</span><span class="sxs-lookup"><span data-stu-id="7d2bc-568">94</span></span></td>
   <td><span data-ttu-id="7d2bc-569">Microsoft Defender for Endpoint executable 已開始</span><span class="sxs-lookup"><span data-stu-id="7d2bc-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="7d2bc-570">SenseCE 可執行檔已開始。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="7d2bc-571">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-572">95</span><span class="sxs-lookup"><span data-stu-id="7d2bc-572">95</span></span></td>
   <td><span data-ttu-id="7d2bc-573">Microsoft Defender for Endpoint 可執行檔已結束</span><span class="sxs-lookup"><span data-stu-id="7d2bc-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="7d2bc-574">SenseCE 可執行檔已結束。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="7d2bc-575">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-576">96</span><span class="sxs-lookup"><span data-stu-id="7d2bc-576">96</span></span></td>
   <td><span data-ttu-id="7d2bc-577">Microsoft Defender for Endpoint Init 已呼叫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="7d2bc-578">結果代碼： %2</span><span class="sxs-lookup"><span data-stu-id="7d2bc-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="7d2bc-579">SenseCE 可執行檔叫用 MCE 初始化。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="7d2bc-580">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-581">97</span><span class="sxs-lookup"><span data-stu-id="7d2bc-581">97</span></span></td>
   <td><span data-ttu-id="7d2bc-582">DLP 案例中的雲端存在連線性問題</span><span class="sxs-lookup"><span data-stu-id="7d2bc-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="7d2bc-583">存在會影響 DLP 分類流程的網路連線問題。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="7d2bc-584">請檢查網路連線性。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-585">98</span><span class="sxs-lookup"><span data-stu-id="7d2bc-585">98</span></span></td>
   <td><span data-ttu-id="7d2bc-586">已還原 DLP 案例的雲端連接</span><span class="sxs-lookup"><span data-stu-id="7d2bc-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="7d2bc-587">已還原網路的連線，且 DLP 分類流程可以繼續。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="7d2bc-588">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-589">99</span><span class="sxs-lookup"><span data-stu-id="7d2bc-589">99</span></span></td>
   <td><span data-ttu-id="7d2bc-590">在與伺服器通訊時，感知發生下列錯誤： (% 1) 。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="7d2bc-591">結果： (% 2) </span><span class="sxs-lookup"><span data-stu-id="7d2bc-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="7d2bc-592">發生通訊錯誤。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="7d2bc-593">如需詳細資訊，請參閱事件記錄檔中的下列事件。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-594">100</span><span class="sxs-lookup"><span data-stu-id="7d2bc-594">100</span></span></td>
   <td><span data-ttu-id="7d2bc-595">無法啟動 Microsoft Defender for Endpoint to executable。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="7d2bc-596">失敗代碼： %1</span><span class="sxs-lookup"><span data-stu-id="7d2bc-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="7d2bc-597">SenseCE 可執行檔無法啟動。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="7d2bc-598">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-598">Reboot the device.</span></span> <span data-ttu-id="7d2bc-599">如果此錯誤仍然存在，請與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-600">102</span><span class="sxs-lookup"><span data-stu-id="7d2bc-600">102</span></span></td>
   <td><span data-ttu-id="7d2bc-601">Microsoft Defender for Endpoint 網路偵測和回應可執行檔已開始</span><span class="sxs-lookup"><span data-stu-id="7d2bc-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="7d2bc-602">SenseNdr 可執行檔已開始。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="7d2bc-603">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="7d2bc-604">103</span><span class="sxs-lookup"><span data-stu-id="7d2bc-604">103</span></span></td>
   <td><span data-ttu-id="7d2bc-605">Microsoft Defender for Endpoint 網路偵測和回應可執行檔已結束</span><span class="sxs-lookup"><span data-stu-id="7d2bc-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="7d2bc-606">SenseNdr 可執行檔已結束。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="7d2bc-607">正常運作通知;不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="7d2bc-608">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="7d2bc-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7d2bc-609">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="7d2bc-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="7d2bc-610">相關主題</span><span class="sxs-lookup"><span data-stu-id="7d2bc-610">Related topics</span></span>
- [<span data-ttu-id="7d2bc-611">將 Windows 10 裝置上線</span><span class="sxs-lookup"><span data-stu-id="7d2bc-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="7d2bc-612">設定裝置 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="7d2bc-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="7d2bc-613">為適用於端點的 Microsoft Defender 疑難排解</span><span class="sxs-lookup"><span data-stu-id="7d2bc-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
