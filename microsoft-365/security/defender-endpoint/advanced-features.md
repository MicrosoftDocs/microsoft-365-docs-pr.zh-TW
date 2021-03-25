---
title: 在 Microsoft Defender for Endpoint 中設定高級功能
description: 在 Microsoft Defender for Endpoint 中開啟諸如封鎖檔等高級功能。
keywords: 「高級功能」、「設定」、「封鎖檔案」、「自動調查」、「自動解析」、skype、microsoft defender 身分識別、office 365、azure 資訊保護、intune
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
ms.technology: mde
ms.openlocfilehash: 41c97d122362ec1fa945fc012ab7a1da46a43b68
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165582"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="43f15-104">在 Defender for Endpoint 中設定高級功能</span><span class="sxs-lookup"><span data-stu-id="43f15-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="43f15-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="43f15-105">**Applies to:**</span></span>
- [<span data-ttu-id="43f15-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="43f15-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43f15-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43f15-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="43f15-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="43f15-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="43f15-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="43f15-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="43f15-110">根據您使用的 Microsoft 安全產品，有些高級功能可能可讓您將 Defender 與的端點整合。</span><span class="sxs-lookup"><span data-stu-id="43f15-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="43f15-111">啟用高級功能</span><span class="sxs-lookup"><span data-stu-id="43f15-111">Enable advanced features</span></span>

1. <span data-ttu-id="43f15-112">在功能窗格中，選取 [**喜好設定**] [  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="43f15-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="43f15-113">選取您要設定的高級功能，並 **在開啟** 和 **關閉** 之間切換設定。</span><span class="sxs-lookup"><span data-stu-id="43f15-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="43f15-114">按一下 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="43f15-114">Click **Save preferences**.</span></span>

<span data-ttu-id="43f15-115">使用下列高級功能，以更好地抵禦潛在的惡意檔案，並在安全性調查期間取得更佳的洞察力。</span><span class="sxs-lookup"><span data-stu-id="43f15-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="43f15-116">自動調查</span><span class="sxs-lookup"><span data-stu-id="43f15-116">Automated investigation</span></span>

<span data-ttu-id="43f15-117">開啟此功能以利用服務的自動化調查和修正功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="43f15-118">如需詳細資訊，請參閱 [自動化調查](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="43f15-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="43f15-119">即時回應</span><span class="sxs-lookup"><span data-stu-id="43f15-119">Live response</span></span>

<span data-ttu-id="43f15-120">開啟此功能，讓具有適當許可權的使用者可以在裝置上啟動即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="43f15-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="43f15-121">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="43f15-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="43f15-122">伺服器的即時回應</span><span class="sxs-lookup"><span data-stu-id="43f15-122">Live response for servers</span></span>
<span data-ttu-id="43f15-123">開啟此功能，讓具有適當許可權的使用者可以在伺服器上啟動即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="43f15-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="43f15-124">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="43f15-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="43f15-125">Live response 未簽署的腳本執行</span><span class="sxs-lookup"><span data-stu-id="43f15-125">Live response unsigned script execution</span></span>

<span data-ttu-id="43f15-126">啟用此功能可讓您在即時回應會話中執行未簽署的腳本。</span><span class="sxs-lookup"><span data-stu-id="43f15-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="43f15-127">自動解析修正的警示</span><span class="sxs-lookup"><span data-stu-id="43f15-127">Autoresolve remediated alerts</span></span>

<span data-ttu-id="43f15-128">針對在 Windows 10、版本1809上建立的承租人，預設會設定自動調查和修正功能，以解決自動分析結果狀態為「沒有發現威脅」或「修正」的警示。</span><span class="sxs-lookup"><span data-stu-id="43f15-128">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="43f15-129">如果您不想要自動解決的提醒，您必須手動關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-129">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="43f15-130">針對在該版本之前建立的承租人，您必須從 [ [高級功能](https://securitycenter.windows.com/preferences2/integration) ] 頁面手動開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-130">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="43f15-131">自動解決動作的結果可能會影響以裝置上所找到之主動警示為基礎的裝置風險等級計算。</span><span class="sxs-lookup"><span data-stu-id="43f15-131">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="43f15-132">如果安全作業分析員手動將警示的狀態設定為「正在進行中」或「已解析」，則自動解析功能不會覆寫。</span><span class="sxs-lookup"><span data-stu-id="43f15-132">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="43f15-133">允許或封鎖檔</span><span class="sxs-lookup"><span data-stu-id="43f15-133">Allow or block file</span></span>

<span data-ttu-id="43f15-134">只有當您的組織符合這些需求時，才可使用封鎖：</span><span class="sxs-lookup"><span data-stu-id="43f15-134">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="43f15-135">使用 Microsoft Defender 防毒程式作為使用中的反惡意程式碼解決方案，並</span><span class="sxs-lookup"><span data-stu-id="43f15-135">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="43f15-136">已啟用雲端式保護功能</span><span class="sxs-lookup"><span data-stu-id="43f15-136">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="43f15-137">這項功能可讓您在網路中封鎖可能有害的檔案。</span><span class="sxs-lookup"><span data-stu-id="43f15-137">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="43f15-138">封鎖檔會使其無法在組織中的裝置上讀取、寫入或執行。</span><span class="sxs-lookup"><span data-stu-id="43f15-138">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="43f15-139">在下列情況開啟 **允許或封鎖** 檔案：</span><span class="sxs-lookup"><span data-stu-id="43f15-139">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="43f15-140">在功能窗格中，選取 [**設定**] [  >  **高級功能**  >  **允許或封鎖檔**]。</span><span class="sxs-lookup"><span data-stu-id="43f15-140">In the navigation pane, select **Settings** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="43f15-141">切換設定為 **開啟** 或 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="43f15-141">Toggle the setting between **On** and **Off**.</span></span>

    ![封鎖檔功能的高級設定影像](images/atp-preferences-setup.png)

1. <span data-ttu-id="43f15-143">選取頁面底部的 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="43f15-143">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="43f15-144">開啟此功能後，您可以透過檔案的設定檔頁面面上的 [**新增指示器**] 索引標籤來 [封鎖](respond-file-alerts.md#allow-or-block-file)檔案。</span><span class="sxs-lookup"><span data-stu-id="43f15-144">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="43f15-145">自訂網路指示器</span><span class="sxs-lookup"><span data-stu-id="43f15-145">Custom network indicators</span></span>

<span data-ttu-id="43f15-146">開啟此功能可讓您為 IP 位址、網域或 URLs 建立指示器，以根據您的自訂指示器清單，判斷是否允許或封鎖這些指標。</span><span class="sxs-lookup"><span data-stu-id="43f15-146">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="43f15-147">若要使用此功能，裝置必須執行 Windows 10 版本1709或更新版本。</span><span class="sxs-lookup"><span data-stu-id="43f15-147">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="43f15-148">他們也應以封鎖模式進行網路保護，以及反惡意程式碼平臺的版本4.18.1906.3 或更新版本， [請參閱 KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834)。</span><span class="sxs-lookup"><span data-stu-id="43f15-148">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="43f15-149">如需詳細資訊，請參閱 [管理指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="43f15-149">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="43f15-150">網路保護會利用信譽服務處理要求的位置，這些位置可能位於您為您的 Defender for Endpoint data 所選取的位置以外。</span><span class="sxs-lookup"><span data-stu-id="43f15-150">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="show-user-details"></a><span data-ttu-id="43f15-151">顯示使用者詳細資料</span><span class="sxs-lookup"><span data-stu-id="43f15-151">Show user details</span></span>

<span data-ttu-id="43f15-152">開啟此功能，讓您可以看到儲存在 Azure Active Directory 中的使用者詳細資料。</span><span class="sxs-lookup"><span data-stu-id="43f15-152">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="43f15-153">詳細資料包括調查使用者帳戶實體時，使用者的圖片、名稱、標題及部門資訊。</span><span class="sxs-lookup"><span data-stu-id="43f15-153">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="43f15-154">您可以在下列視圖中尋找使用者帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="43f15-154">You can find user account information in the following views:</span></span>

- <span data-ttu-id="43f15-155">安全性操作儀表板</span><span class="sxs-lookup"><span data-stu-id="43f15-155">Security operations dashboard</span></span>
- <span data-ttu-id="43f15-156">警示佇列</span><span class="sxs-lookup"><span data-stu-id="43f15-156">Alert queue</span></span>
- <span data-ttu-id="43f15-157">裝置詳細資料頁面</span><span class="sxs-lookup"><span data-stu-id="43f15-157">Device details page</span></span>

<span data-ttu-id="43f15-158">如需詳細資訊，請參閱 [調查使用者帳戶](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="43f15-158">For more information, see [Investigate a user account](investigate-user.md).</span></span>

## <a name="skype-for-business-integration"></a><span data-ttu-id="43f15-159">商務用 Skype 整合</span><span class="sxs-lookup"><span data-stu-id="43f15-159">Skype for Business integration</span></span>

<span data-ttu-id="43f15-160">啟用商務用 Skype 的整合功能可讓您與使用商務用 Skype、電子郵件或電話的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="43f15-160">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="43f15-161">當您需要與使用者通訊並減輕風險時，這會很便利。</span><span class="sxs-lookup"><span data-stu-id="43f15-161">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="43f15-162">當裝置與網路隔離時，會有一個快顯視窗，您可以在其中選擇啟用 Outlook 和 Skype 通訊，以便在使用者與網路中斷連線時，允許與該使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="43f15-162">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="43f15-163">當裝置處於隔離模式時，此設定會套用到 Skype 和 Outlook 通訊。</span><span class="sxs-lookup"><span data-stu-id="43f15-163">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="azure-advanced-threat-protection-integration"></a><span data-ttu-id="43f15-164">Azure 高級威脅防護整合</span><span class="sxs-lookup"><span data-stu-id="43f15-164">Azure Advanced Threat Protection integration</span></span>

<span data-ttu-id="43f15-165">與 Azure 高級威脅防護的整合，可讓您直接在 Microsoft Identity security 產品中直接旋轉。</span><span class="sxs-lookup"><span data-stu-id="43f15-165">The integration with Azure Advanced Threat Protection allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="43f15-166">Azure 高級威脅防護增強了有關可疑的帳戶和相關資源之其他深入資訊的調查。</span><span class="sxs-lookup"><span data-stu-id="43f15-166">Azure Advanced Threat Protection augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="43f15-167">透過啟用這項功能，您就可以透過從識別的觀點來切換網路，來充實裝置型調查功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-167">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="43f15-168">您必須具有適當的授權，才能啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-168">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="43f15-169">Office 365 威脅情報連接</span><span class="sxs-lookup"><span data-stu-id="43f15-169">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="43f15-170">只有當您具有使用中的 Office 365 E5 或威脅情報附加元件時，才可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-170">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="43f15-171">如需詳細資訊，請參閱 Office 365 企業版 E5 產品頁面。</span><span class="sxs-lookup"><span data-stu-id="43f15-171">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="43f15-172">當您開啟此功能時，您可以將 Office 365 高級威脅防護中的資料合併至 Microsoft Defender 安全中心，以在 Office 365 信箱和 Windows 裝置上進行全面的安全性調查。</span><span class="sxs-lookup"><span data-stu-id="43f15-172">When you turn this feature on, you'll be able to incorporate data from Office 365 Advanced Threat Protection into Microsoft Defender Security Center to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="43f15-173">您必須具有適當的授權，才能啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-173">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="43f15-174">若要在 Office 365 威脅情報中接收上下文相關的裝置整合，您必須在安全性 & 規範儀表板中啟用 [Endpoint for Endpoint] 設定。</span><span class="sxs-lookup"><span data-stu-id="43f15-174">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="43f15-175">如需詳細資訊，請參閱 [威脅調查和回應](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-ti)。</span><span class="sxs-lookup"><span data-stu-id="43f15-175">For more information, see [Threat investigation and response](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts"></a><span data-ttu-id="43f15-176">Microsoft 威脅專家</span><span class="sxs-lookup"><span data-stu-id="43f15-176">Microsoft Threat Experts</span></span>

<span data-ttu-id="43f15-177">除了兩個 Microsoft 威脅專家元件，已設定目標攻擊通知是在正式發行時。</span><span class="sxs-lookup"><span data-stu-id="43f15-177">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="43f15-178">專家隨選功能仍在預覽中。</span><span class="sxs-lookup"><span data-stu-id="43f15-178">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="43f15-179">如果您已套用預覽，且已核准您的應用程式，您只能使用專家隨選功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-179">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="43f15-180">您可以從 Microsoft 威脅專家透過您的端點入口網站的 [提醒] 儀表板，以及透過電子郵件（如果您設定它）來接收目標攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="43f15-180">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="43f15-181">適用于 Microsoft 的 Defender for Endpoint 的 Microsoft 威脅專家功能，具有 E5 授權 for [Enterprise 可移動性 + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)。</span><span class="sxs-lookup"><span data-stu-id="43f15-181">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="43f15-182">Microsoft 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="43f15-182">Microsoft Cloud App Security</span></span>

<span data-ttu-id="43f15-183">啟用此設定時，會將 Defender for Endpoint 信號轉寄至 Microsoft Cloud App Security，以提供 Cloud 應用程式使用狀況的更深入可視性。</span><span class="sxs-lookup"><span data-stu-id="43f15-183">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="43f15-184">轉寄的資料會與您的雲端應用程式安全性資料儲存在相同的位置。</span><span class="sxs-lookup"><span data-stu-id="43f15-184">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="43f15-185">這項功能可搭配執行 Windows 10、版本 1709 (OS 組建16299.1085 （ [) 含](https://support.microsoft.com/help/4493441) [KB4493464](https://support.microsoft.com/help/4493464)) 1809、windows 10、版本 1803 (Os 組建17134.704 搭配[KB4489899](https://support.microsoft.com/help/4489899) (或更新版本的 windows 10 版本）之裝置上的[Enterprise 可移動性 + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)的 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="43f15-185">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="azure-information-protection"></a><span data-ttu-id="43f15-186">Azure 資訊保護</span><span class="sxs-lookup"><span data-stu-id="43f15-186">Azure Information Protection</span></span>

<span data-ttu-id="43f15-187">開啟此設定可允許將信號轉送到 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="43f15-187">Turning on this setting allows signals to be forwarded to Azure Information Protection.</span></span> <span data-ttu-id="43f15-188">它可讓資料擁有者和系統管理員看到架裝置上受保護的資料和裝置風險評級。</span><span class="sxs-lookup"><span data-stu-id="43f15-188">It gives data owners and administrators visibility into protected data on onboarded devices and device risk ratings.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="43f15-189">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="43f15-189">Microsoft Secure Score</span></span>

<span data-ttu-id="43f15-190">將 Microsoft Defender for Endpoint 信號轉寄給 microsoft 365 安全性中心內的 Microsoft Secure 得分。</span><span class="sxs-lookup"><span data-stu-id="43f15-190">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="43f15-191">開啟此功能可讓 Microsoft 安全分數看到裝置的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="43f15-191">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="43f15-192">轉寄的資料會與您的 Microsoft 安全分數資料儲存在相同的位置。</span><span class="sxs-lookup"><span data-stu-id="43f15-192">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="43f15-193">從 Microsoft Defender for Identity 入口網站啟用 Microsoft Defender for Endpoint 整合</span><span class="sxs-lookup"><span data-stu-id="43f15-193">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="43f15-194">若要在 Microsoft Defender for Identity 中接收與內容相關的設備整合，您也需要啟用 Microsoft Defender for Identity 入口網站中的功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-194">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="43f15-195">使用全域系統管理員或安全性管理員角色，登入 [Microsoft Defender 的身分識別入口網站](https://portal.atp.azure.com/) 。</span><span class="sxs-lookup"><span data-stu-id="43f15-195">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="43f15-196">按一下 [ **建立您的實例**]。</span><span class="sxs-lookup"><span data-stu-id="43f15-196">Click **Create your instance**.</span></span>

3. <span data-ttu-id="43f15-197">將 Integration 設定切換為 [ **開啟** ]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="43f15-197">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="43f15-198">完成這兩個入口網站的整合步驟之後，您可以在 [裝置詳細資料] 或 [使用者詳細資料] 頁面看到相關的警示。</span><span class="sxs-lookup"><span data-stu-id="43f15-198">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="microsoft-intune-connection"></a><span data-ttu-id="43f15-199">Microsoft Intune 連線</span><span class="sxs-lookup"><span data-stu-id="43f15-199">Microsoft Intune connection</span></span>

<span data-ttu-id="43f15-200">可以與 [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) 整合的 Endpoint for Endpoint，以 [啟用裝置風險的條件式存取](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="43f15-200">Defender for Endpoint can be integrated with [Microsoft Intune](https://docs.microsoft.com/intune/what-is-intune) to [enable device risk-based conditional access](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="43f15-201">當您 [開啟此功能](configure-conditional-access.md)時，您可以使用 Intune 與 Intune 共用 Defender 裝置資訊，進而增強原則的執行能力。</span><span class="sxs-lookup"><span data-stu-id="43f15-201">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43f15-202">您必須在 Intune 和 Defender for Endpoint 上啟用整合，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-202">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="43f15-203">如需特定步驟的詳細資訊，請參閱 [在 Defender For Endpoint 中設定條件式存取](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="43f15-203">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="43f15-204">只有在下列情況下，才可使用此功能：</span><span class="sxs-lookup"><span data-stu-id="43f15-204">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="43f15-205">適用于 Enterprise 可移動性 + Security E3 的授權租使用者，以及 Windows E5 (或 Microsoft 365 企業版 E5) </span><span class="sxs-lookup"><span data-stu-id="43f15-205">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="43f15-206">使用 Intune 管理 Windows 10 裝置的使用中 Microsoft Intune 環境， [Azure 已加入 Azure](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/)。</span><span class="sxs-lookup"><span data-stu-id="43f15-206">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join/).</span></span>

### <a name="conditional-access-policy"></a><span data-ttu-id="43f15-207">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="43f15-207">Conditional Access policy</span></span>

<span data-ttu-id="43f15-208">當您啟用 Intune 整合時，Intune 會自動建立傳統的條件式存取 (CA) 原則。</span><span class="sxs-lookup"><span data-stu-id="43f15-208">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="43f15-209">這項傳統 CA 原則是設定狀態報表至 Intune 的必要條件。</span><span class="sxs-lookup"><span data-stu-id="43f15-209">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="43f15-210">不應該刪除。</span><span class="sxs-lookup"><span data-stu-id="43f15-210">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="43f15-211">Intune 所建立的傳統 CA 原則與新式條件式 [存取原則](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/)不同，用來設定端點。</span><span class="sxs-lookup"><span data-stu-id="43f15-211">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>

## <a name="preview-features"></a><span data-ttu-id="43f15-212">預覽功能</span><span class="sxs-lookup"><span data-stu-id="43f15-212">Preview features</span></span>

<span data-ttu-id="43f15-213">深入瞭解 Defender for Endpoint preview 發行版本中的新功能，並在第一次嘗試使用預覽體驗的情況中嘗試後續的功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-213">Learn about new features in the Defender for Endpoint preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="43f15-214">您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。</span><span class="sxs-lookup"><span data-stu-id="43f15-214">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="43f15-215">與 Microsoft 規範中心共用端點警示</span><span class="sxs-lookup"><span data-stu-id="43f15-215">Share endpoint alerts with Microsoft Compliance Center</span></span>

<span data-ttu-id="43f15-216">將端點安全性警示和其會審狀態轉寄給 Microsoft 規範中心，讓您能夠使用預警增強內幕風險管理原則，並在內部風險造成損害之前加以修正。</span><span class="sxs-lookup"><span data-stu-id="43f15-216">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="43f15-217">轉寄的資料會處理並儲存于 Office 365 資料所在的相同位置。</span><span class="sxs-lookup"><span data-stu-id="43f15-217">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="43f15-218">在「內幕風險管理」設定中設定 [安全性原則違規指示器](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) 後，就會與適用使用者的「內部使用者風險管理」共用端點警示。</span><span class="sxs-lookup"><span data-stu-id="43f15-218">After configuring the [Security policy violation indicators](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-settings.md#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43f15-219">相關主題</span><span class="sxs-lookup"><span data-stu-id="43f15-219">Related topics</span></span>

- [<span data-ttu-id="43f15-220">更新資料保留設定</span><span class="sxs-lookup"><span data-stu-id="43f15-220">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="43f15-221">設定警示通知</span><span class="sxs-lookup"><span data-stu-id="43f15-221">Configure alert notifications</span></span>](configure-email-notifications.md)
