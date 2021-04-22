---
title: 修正 Microsoft Defender for Endpoint 中的狀況不良感應器
description: 修正報告為錯誤設定或非使用中的設備感應器，以供服務接收來自裝置的資料。
keywords: 誤設定、非使用中、修復感應器、感應器狀況、無感應器資料、感應器資料、受損通訊、通訊
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935362"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="66afb-104">修正 Microsoft Defender for Endpoint 中的狀況不良感應器</span><span class="sxs-lookup"><span data-stu-id="66afb-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="66afb-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="66afb-105">**Applies to:**</span></span>
- [<span data-ttu-id="66afb-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="66afb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="66afb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66afb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="66afb-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="66afb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="66afb-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="66afb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="66afb-110">分類為設定錯誤或非使用中的裝置會因原因不同而加以標記。</span><span class="sxs-lookup"><span data-stu-id="66afb-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="66afb-111">本節提供一些有關可能導致裝置分類為非使用中或設定不當的說明。</span><span class="sxs-lookup"><span data-stu-id="66afb-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="66afb-112">非使用中的裝置</span><span class="sxs-lookup"><span data-stu-id="66afb-112">Inactive devices</span></span>

<span data-ttu-id="66afb-113">非使用中的裝置不一定會因問題而標示。</span><span class="sxs-lookup"><span data-stu-id="66afb-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="66afb-114">對裝置執行下列動作可能會造成裝置分類為非使用中：</span><span class="sxs-lookup"><span data-stu-id="66afb-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="66afb-115">裝置未使用中</span><span class="sxs-lookup"><span data-stu-id="66afb-115">Device is not in use</span></span>

<span data-ttu-id="66afb-116">如果裝置由於任何原因尚未使用超過7天，它會保持入口網站中的「非使用中」狀態。</span><span class="sxs-lookup"><span data-stu-id="66afb-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="66afb-117">裝置已重新安裝或重新命名</span><span class="sxs-lookup"><span data-stu-id="66afb-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="66afb-118">重新安裝或重新命名的裝置會在 Microsoft Defender Security Center 中產生新的裝置實體。</span><span class="sxs-lookup"><span data-stu-id="66afb-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="66afb-119">在入口網站中，舊的裝置實體仍會保持「非使用中」狀態。</span><span class="sxs-lookup"><span data-stu-id="66afb-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="66afb-120">如果您重新安裝裝置，並部署了端點套件的 Defender 套件，請搜尋新的裝置名稱，以確認裝置正常報告。</span><span class="sxs-lookup"><span data-stu-id="66afb-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="66afb-121">裝置已 offboarded</span><span class="sxs-lookup"><span data-stu-id="66afb-121">Device was offboarded</span></span>
<span data-ttu-id="66afb-122">如果裝置 offboarded，它仍會出現在 [裝置] 清單中。</span><span class="sxs-lookup"><span data-stu-id="66afb-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="66afb-123">7天后，裝置健康狀態應該變更為 [非使用中]。</span><span class="sxs-lookup"><span data-stu-id="66afb-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="66afb-124">裝置未傳送信號</span><span class="sxs-lookup"><span data-stu-id="66afb-124">Device is not sending signals</span></span>
<span data-ttu-id="66afb-125">如果裝置在任何原因（包括設定未設定的裝置分類中的條件）上，不會將任何信號傳送至任何 Microsoft Defender for Endpoint 通道，則會將裝置視為非使用中。</span><span class="sxs-lookup"><span data-stu-id="66afb-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="66afb-126">您期望裝置處於「主動」狀態嗎？</span><span class="sxs-lookup"><span data-stu-id="66afb-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="66afb-127">[開啟支援票證](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561)。</span><span class="sxs-lookup"><span data-stu-id="66afb-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="66afb-128">錯誤的裝置</span><span class="sxs-lookup"><span data-stu-id="66afb-128">Misconfigured devices</span></span>
<span data-ttu-id="66afb-129">設定錯誤的裝置可進一步分類為：</span><span class="sxs-lookup"><span data-stu-id="66afb-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="66afb-130">受損的通訊</span><span class="sxs-lookup"><span data-stu-id="66afb-130">Impaired communications</span></span>
- <span data-ttu-id="66afb-131">無感應器資料</span><span class="sxs-lookup"><span data-stu-id="66afb-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="66afb-132">受損的通訊</span><span class="sxs-lookup"><span data-stu-id="66afb-132">Impaired communications</span></span>
<span data-ttu-id="66afb-133">此狀態表示裝置與服務之間的通訊有限。</span><span class="sxs-lookup"><span data-stu-id="66afb-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="66afb-134">下列建議的動作可協助修正已設定不當之裝置的相關問題，但通訊已受損：</span><span class="sxs-lookup"><span data-stu-id="66afb-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="66afb-135">確定裝置具有網際網路連線</span><span class="sxs-lookup"><span data-stu-id="66afb-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="66afb-136">適用於端點的 Microsoft Defender 感應器需要 Microsoft Windows HTTP (WinHTTP) 回報感應器資料，並與適用於端點的 Microsoft Defender 服務通訊。</span><span class="sxs-lookup"><span data-stu-id="66afb-136">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="66afb-137">驗證 Endpoint service URLs 的用戶端與 Microsoft Defender 的連線能力</span><span class="sxs-lookup"><span data-stu-id="66afb-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="66afb-138">驗證 proxy 設定是否順利完成，該 WinHTTP 可以透過您環境中的 proxy 伺服器探索和通訊，而且 proxy 伺服器允許流量至 Microsoft Defender for Endpoint service URLs。</span><span class="sxs-lookup"><span data-stu-id="66afb-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="66afb-139">如果您採取了糾正動作但裝置狀態仍設定不正確，請 [開啟支援票證](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="66afb-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="66afb-140">無感應器資料</span><span class="sxs-lookup"><span data-stu-id="66afb-140">No sensor data</span></span>
<span data-ttu-id="66afb-141">錯誤設定的裝置具有狀態 ' 無感應器資料」與服務的通訊，但只能報告部分感應器資料。</span><span class="sxs-lookup"><span data-stu-id="66afb-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="66afb-142">遵循下列動作，修正與錯誤設定的裝置相關的已知問題，狀態為「沒有感應器資料」：</span><span class="sxs-lookup"><span data-stu-id="66afb-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="66afb-143">確定裝置具有網際網路連線</span><span class="sxs-lookup"><span data-stu-id="66afb-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="66afb-144">適用於端點的 Microsoft Defender 感應器需要 Microsoft Windows HTTP (WinHTTP) 回報感應器資料，並與適用於端點的 Microsoft Defender 服務通訊。</span><span class="sxs-lookup"><span data-stu-id="66afb-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="66afb-145">驗證 Endpoint service URLs 的用戶端與 Microsoft Defender 的連線能力</span><span class="sxs-lookup"><span data-stu-id="66afb-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  <span data-ttu-id="66afb-146">驗證 proxy 設定是否順利完成，該 WinHTTP 可以透過您環境中的 proxy 伺服器探索和通訊，而且 proxy 伺服器允許流量至 Microsoft Defender for Endpoint service URLs。</span><span class="sxs-lookup"><span data-stu-id="66afb-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="66afb-147">確定已啟用診斷資料服務</span><span class="sxs-lookup"><span data-stu-id="66afb-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="66afb-148">如果裝置的報告不正確，您可能需要檢查 Windows 10 診斷資料服務是否設定為自動啟動，並在端點上執行。</span><span class="sxs-lookup"><span data-stu-id="66afb-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="66afb-149">確定原則未停用 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="66afb-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="66afb-150">如果您的裝置執行的是協力廠商反惡意軟體用戶端，則該 Defender 代理程式需要 Microsoft Defender 防毒程式的早期發行反惡意軟體 (ELAM) 驅動程式才能啟用。</span><span class="sxs-lookup"><span data-stu-id="66afb-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="66afb-151">如果您採取了糾正動作但裝置狀態仍設定不正確，請 [開啟支援票證](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="66afb-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="66afb-152">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66afb-152">See also</span></span>
- [<span data-ttu-id="66afb-153">檢查 Microsoft Defender for Endpoint 中的感應器健康狀態</span><span class="sxs-lookup"><span data-stu-id="66afb-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
