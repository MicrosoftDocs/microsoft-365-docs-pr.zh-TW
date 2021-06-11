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
ms.openlocfilehash: 7fd9ec25c21b2d70238bd5b0d6b58b60731088ea
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845471"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a><span data-ttu-id="b3823-104">在 Defender for Endpoint 中設定高級功能</span><span class="sxs-lookup"><span data-stu-id="b3823-104">Configure advanced features in Defender for Endpoint</span></span>

<span data-ttu-id="b3823-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b3823-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3823-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b3823-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3823-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3823-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> <span data-ttu-id="b3823-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b3823-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b3823-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b3823-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

<span data-ttu-id="b3823-110">根據您使用的 Microsoft 安全產品，有些高級功能可能可讓您將 Defender 與的端點整合。</span><span class="sxs-lookup"><span data-stu-id="b3823-110">Depending on the Microsoft security products that you use, some advanced features might be available for you to integrate Defender for Endpoint with.</span></span>

## <a name="enable-advanced-features"></a><span data-ttu-id="b3823-111">啟用高級功能</span><span class="sxs-lookup"><span data-stu-id="b3823-111">Enable advanced features</span></span>

1. <span data-ttu-id="b3823-112">在功能窗格中，選取 [**喜好設定**] [  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="b3823-112">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="b3823-113">選取您要設定的高級功能，並 **在開啟** 和 **關閉** 之間切換設定。</span><span class="sxs-lookup"><span data-stu-id="b3823-113">Select the advanced feature you want to configure and toggle the setting between **On** and **Off**.</span></span>
3. <span data-ttu-id="b3823-114">按一下 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b3823-114">Click **Save preferences**.</span></span>

<span data-ttu-id="b3823-115">使用下列高級功能，以更好地抵禦潛在的惡意檔案，並在安全性調查期間取得更佳的洞察力。</span><span class="sxs-lookup"><span data-stu-id="b3823-115">Use the following advanced features to get better protected from potentially malicious files and gain better insight during security investigations.</span></span>

## <a name="automated-investigation"></a><span data-ttu-id="b3823-116">自動調查</span><span class="sxs-lookup"><span data-stu-id="b3823-116">Automated investigation</span></span>

<span data-ttu-id="b3823-117">開啟此功能以利用服務的自動化調查和修正功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-117">Turn on this feature to take advantage of the automated investigation and remediation features of the service.</span></span> <span data-ttu-id="b3823-118">如需詳細資訊，請參閱 [自動化調查](automated-investigations.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-118">For more information, see [Automated investigation](automated-investigations.md).</span></span>

## <a name="live-response"></a><span data-ttu-id="b3823-119">即時回應</span><span class="sxs-lookup"><span data-stu-id="b3823-119">Live response</span></span>

<span data-ttu-id="b3823-120">開啟此功能，讓具有適當許可權的使用者可以在裝置上啟動即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="b3823-120">Turn on this feature so that users with the appropriate permissions can start a live response session on devices.</span></span>

<span data-ttu-id="b3823-121">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-121">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>

## <a name="live-response-for-servers"></a><span data-ttu-id="b3823-122">伺服器的即時回應</span><span class="sxs-lookup"><span data-stu-id="b3823-122">Live response for servers</span></span>
<span data-ttu-id="b3823-123">開啟此功能，讓具有適當許可權的使用者可以在伺服器上啟動即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="b3823-123">Turn on this feature so that users with the appropriate permissions can start a live response session on servers.</span></span>

<span data-ttu-id="b3823-124">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-124">For more information about role assignments, see [Create and manage roles](user-roles.md).</span></span>


## <a name="live-response-unsigned-script-execution"></a><span data-ttu-id="b3823-125">Live response 未簽署的腳本執行</span><span class="sxs-lookup"><span data-stu-id="b3823-125">Live response unsigned script execution</span></span>

<span data-ttu-id="b3823-126">啟用此功能可讓您在即時回應會話中執行未簽署的腳本。</span><span class="sxs-lookup"><span data-stu-id="b3823-126">Enabling this feature allows you to run unsigned scripts in a live response session.</span></span>

## <a name="always-remediate-pua"></a><span data-ttu-id="b3823-127">永遠修正 PUA</span><span class="sxs-lookup"><span data-stu-id="b3823-127">Always remediate PUA</span></span>
<span data-ttu-id="b3823-128">可能有害的應用程式 (PUA) 是一種軟體類別，可導致您的機器執行緩慢、顯示未預期的廣告，或是最壞的軟體安裝可能是意外或不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="b3823-128">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> 

<span data-ttu-id="b3823-129">開啟此功能，以便在租使用者中的所有裝置上修正 (PUA) 可能有害的應用程式，即使裝置上未設定 PUA 保護也是一樣。</span><span class="sxs-lookup"><span data-stu-id="b3823-129">Turn on this feature so that potentially unwanted applications (PUA) are remediated on all devices in your tenant even if PUA protection is not configured on the devices.</span></span> <span data-ttu-id="b3823-130">這有助於防止使用者不小心在其裝置上安裝不需要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3823-130">This will help protect users from inadvertently installing unwanted applications on their device.</span></span> <span data-ttu-id="b3823-131">關閉時，修正取決於裝置設定。</span><span class="sxs-lookup"><span data-stu-id="b3823-131">When turned off, remediation is dependent on the device configuration.</span></span> 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a><span data-ttu-id="b3823-132">限制範圍內裝置群組的關聯</span><span class="sxs-lookup"><span data-stu-id="b3823-132">Restrict correlation to within scoped device groups</span></span>
<span data-ttu-id="b3823-133">這種設定可用於本機 SOC 作業只想要將警示關聯限制為可以存取之裝置群組的情況。</span><span class="sxs-lookup"><span data-stu-id="b3823-133">This configuration can be used for scenarios where local SOC operations would like to limit alert correlations only to device groups that they can access.</span></span> <span data-ttu-id="b3823-134">開啟此設定，就不會再視為單一事件，由跨裝置群組的警示所組成的事件。</span><span class="sxs-lookup"><span data-stu-id="b3823-134">By turning this setting on, an incident composed of alerts that cross device groups will no longer be considered a single incident.</span></span> <span data-ttu-id="b3823-135">然後，本機 SOC 便可對該事件採取動作，因為他們有權存取相關的其中一個裝置群組。</span><span class="sxs-lookup"><span data-stu-id="b3823-135">The local SOC can then take action on the incident because they have access to one of the device groups involved.</span></span> <span data-ttu-id="b3823-136">不過，全域 SOC 會透過設備群組（而不是一個事件）看到數種不同的事件。</span><span class="sxs-lookup"><span data-stu-id="b3823-136">However, global SOC will see several different incidents by device group instead of one incident.</span></span> <span data-ttu-id="b3823-137">建議您不要開啟此設定，除非這麼做超過整個組織內的事件關聯的優點</span><span class="sxs-lookup"><span data-stu-id="b3823-137">We do not recommend turning this setting on unless doing so outweighs the benefits of incident correlation across the entire organization</span></span>
>[!NOTE]
><span data-ttu-id="b3823-138">變更此設定只會影響未來的警示關聯。</span><span class="sxs-lookup"><span data-stu-id="b3823-138">Changing this setting impacts future alert correlations only.</span></span>

## <a name="enable-edr-in-block-mode"></a><span data-ttu-id="b3823-139">在封鎖模式中啟用 EDR</span><span class="sxs-lookup"><span data-stu-id="b3823-139">Enable EDR in block mode</span></span>
<span data-ttu-id="b3823-140">端點偵測和回應 (EDR) 在封鎖模式中時，即使 Microsoft Defender 防毒軟體是以被動模式執行，也可以保護惡意的惡意資料。</span><span class="sxs-lookup"><span data-stu-id="b3823-140">Endpoint detection and response (EDR) in block mode provides protection from malicious artifacts, even when Microsoft Defender Antivirus is running in passive mode.</span></span> <span data-ttu-id="b3823-141">開啟時，以封鎖模式 EDR 會封鎖在裝置上偵測到的惡意的偽像或行為。</span><span class="sxs-lookup"><span data-stu-id="b3823-141">When turned on, EDR in block mode blocks malicious artifacts or behaviors that are detected on a device.</span></span> <span data-ttu-id="b3823-142">block 模式中的 EDR 會在幕後運作，以修正偵測到破壞後偵測到的惡意作品。</span><span class="sxs-lookup"><span data-stu-id="b3823-142">EDR in block mode works behind the scenes to remediate malicious artifacts that are detected post breach.</span></span>


## <a name="autoresolve-remediated-alerts"></a><span data-ttu-id="b3823-143">自動解析修正的警示</span><span class="sxs-lookup"><span data-stu-id="b3823-143">Autoresolve remediated alerts</span></span>

<span data-ttu-id="b3823-144">針對在 Windows 10 或之後建立的承租人，版本1809會預設設定自動調查和修正功能，以解決自動分析結果狀態為「沒有發現威脅」或「修正」的警示。</span><span class="sxs-lookup"><span data-stu-id="b3823-144">For tenants created on or after Windows 10, version 1809, the automated investigation and remediation capability is configured by default to resolve alerts where the automated analysis result status is "No threats found" or "Remediated".</span></span>  <span data-ttu-id="b3823-145">如果您不想要自動解決的提醒，您必須手動關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-145">If you don't want to have alerts auto-resolved, you'll need to manually turn off the feature.</span></span>

> [!TIP]
> <span data-ttu-id="b3823-146">針對在該版本之前建立的承租人，您必須從 [ [高級功能](https://securitycenter.windows.com/preferences2/integration) ] 頁面手動開啟此功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-146">For tenants created prior to that version, you'll need to manually turn this feature on from the [Advanced features](https://securitycenter.windows.com/preferences2/integration) page.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b3823-147">自動解決動作的結果可能會影響以裝置上所找到之主動警示為基礎的裝置風險等級計算。</span><span class="sxs-lookup"><span data-stu-id="b3823-147">The result of the auto-resolve action may influence the Device risk level calculation which is based on the active alerts found on a device.</span></span>
> - <span data-ttu-id="b3823-148">如果安全作業分析員手動將警示的狀態設定為「正在進行中」或「已解析」，則自動解析功能不會覆寫。</span><span class="sxs-lookup"><span data-stu-id="b3823-148">If a security operations analyst manually sets the status of an alert to "In progress" or "Resolved" the auto-resolve capability will not overwrite it.</span></span>

## <a name="allow-or-block-file"></a><span data-ttu-id="b3823-149">允許或封鎖檔</span><span class="sxs-lookup"><span data-stu-id="b3823-149">Allow or block file</span></span>

<span data-ttu-id="b3823-150">只有當您的組織符合這些需求時，才可使用封鎖：</span><span class="sxs-lookup"><span data-stu-id="b3823-150">Blocking is only available if your organization fulfills these requirements:</span></span>

- <span data-ttu-id="b3823-151">使用 Microsoft Defender 防毒軟體作為使用中的反惡意程式碼解決方案，並</span><span class="sxs-lookup"><span data-stu-id="b3823-151">Uses Microsoft Defender Antivirus as the active antimalware solution and,</span></span>
- <span data-ttu-id="b3823-152">已啟用雲端式保護功能</span><span class="sxs-lookup"><span data-stu-id="b3823-152">The cloud-based protection feature is enabled</span></span>

<span data-ttu-id="b3823-153">這項功能可讓您在網路中封鎖可能有害的檔案。</span><span class="sxs-lookup"><span data-stu-id="b3823-153">This feature enables you to block potentially malicious files in your network.</span></span> <span data-ttu-id="b3823-154">封鎖檔會使其無法在組織中的裝置上讀取、寫入或執行。</span><span class="sxs-lookup"><span data-stu-id="b3823-154">Blocking a file will prevent it from being read, written, or executed on devices in your organization.</span></span>

<span data-ttu-id="b3823-155">在下列情況開啟 **允許或封鎖** 檔案：</span><span class="sxs-lookup"><span data-stu-id="b3823-155">To turn **Allow or block** files on:</span></span>

1. <span data-ttu-id="b3823-156">在功能窗格中，選取 [**設定**  >  **高級功能**  >  **允許或封鎖檔**]。</span><span class="sxs-lookup"><span data-stu-id="b3823-156">In the navigation pane, select **Settings** > **Advanced features** > **Allow or block file**.</span></span>

1. <span data-ttu-id="b3823-157">切換設定為 **開啟** 或 **關閉**。</span><span class="sxs-lookup"><span data-stu-id="b3823-157">Toggle the setting between **On** and **Off**.</span></span>

    ![封鎖檔功能的高級設定影像](images/atp-preferences-setup.png)

1. <span data-ttu-id="b3823-159">選取頁面底部的 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="b3823-159">Select **Save preferences** at the bottom of the page.</span></span>

<span data-ttu-id="b3823-160">開啟此功能後，您可以透過檔案的設定檔頁面面上的 [**新增指示器**] 索引標籤來 [封鎖](respond-file-alerts.md#allow-or-block-file)檔案。</span><span class="sxs-lookup"><span data-stu-id="b3823-160">After turning on this feature, you can [block files](respond-file-alerts.md#allow-or-block-file) via the **Add Indicator** tab on a file's profile page.</span></span>

## <a name="custom-network-indicators"></a><span data-ttu-id="b3823-161">自訂網路指示器</span><span class="sxs-lookup"><span data-stu-id="b3823-161">Custom network indicators</span></span>

<span data-ttu-id="b3823-162">開啟此功能可讓您為 IP 位址、網域或 URLs 建立指示器，以根據您的自訂指示器清單，判斷是否允許或封鎖這些指標。</span><span class="sxs-lookup"><span data-stu-id="b3823-162">Turning on this feature allows you to create indicators for IP addresses, domains, or URLs, which determine whether they will be allowed or blocked based on your custom indicator list.</span></span>

<span data-ttu-id="b3823-163">若要使用此功能，裝置必須執行 Windows 10 版本1709或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b3823-163">To use this feature, devices must be running Windows 10 version 1709 or later.</span></span> <span data-ttu-id="b3823-164">他們也應以封鎖模式進行網路保護，以及反惡意程式碼平臺的版本4.18.1906.3 或更新版本， [請參閱 KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834)。</span><span class="sxs-lookup"><span data-stu-id="b3823-164">They should also have network protection in block mode and version 4.18.1906.3 or later of the antimalware platform [see KB 4052623](https://go.microsoft.com/fwlink/?linkid=2099834).</span></span>

<span data-ttu-id="b3823-165">如需詳細資訊，請參閱 [管理指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-165">For more information, see [Manage indicators](manage-indicators.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-166">網路保護會利用信譽服務處理要求的位置，這些位置可能位於您為您的 Defender for Endpoint data 所選取的位置以外。</span><span class="sxs-lookup"><span data-stu-id="b3823-166">Network protection leverages reputation services that process requests in locations that might be outside of the location you have selected for your Defender for Endpoint data.</span></span>

## <a name="tamper-protection"></a><span data-ttu-id="b3823-167">防篡改保護</span><span class="sxs-lookup"><span data-stu-id="b3823-167">Tamper protection</span></span>
<span data-ttu-id="b3823-168">在某些網路攻擊中，不良的演員會嘗試停用電腦上的安全性功能，例如防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="b3823-168">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="b3823-169">不良的演員，例如停用您的安全性功能，以更輕鬆地存取資料、安裝惡意程式碼，或利用您的資料、身分識別及裝置。</span><span class="sxs-lookup"><span data-stu-id="b3823-169">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span>

<span data-ttu-id="b3823-170">防篡改保護實質上會鎖定 Microsoft Defender 防毒軟體，並防止您的安全性設定透過應用程式和方法進行變更。</span><span class="sxs-lookup"><span data-stu-id="b3823-170">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods.</span></span>

<span data-ttu-id="b3823-171">如果您的組織使用 Microsoft Defender 防毒軟體和雲端型防護，則可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-171">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="b3823-172">如需詳細資訊，請參閱[使用下一代技術在 Microsoft Defender 防毒軟體中透過雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-172">For more information, see [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="b3823-173">使防篡改保護保持開啟，以避免安全性解決方案及其基本功能的不想要的變更。</span><span class="sxs-lookup"><span data-stu-id="b3823-173">Keep tamper protection turned on to prevent unwanted changes to your security solution and its essential features.</span></span>


## <a name="show-user-details"></a><span data-ttu-id="b3823-174">顯示使用者詳細資料</span><span class="sxs-lookup"><span data-stu-id="b3823-174">Show user details</span></span>

<span data-ttu-id="b3823-175">開啟此功能，讓您能看到儲存在 Azure Active Directory 中的使用者詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b3823-175">Turn on this feature so that you can see user details stored in Azure Active Directory.</span></span> <span data-ttu-id="b3823-176">詳細資料包括調查使用者帳戶實體時，使用者的圖片、名稱、標題及部門資訊。</span><span class="sxs-lookup"><span data-stu-id="b3823-176">Details include a user's picture, name, title, and department information  when investigating user account entities.</span></span> <span data-ttu-id="b3823-177">您可以在下列視圖中尋找使用者帳戶資訊：</span><span class="sxs-lookup"><span data-stu-id="b3823-177">You can find user account information in the following views:</span></span>

- <span data-ttu-id="b3823-178"> 安全性操作儀表板</span><span class="sxs-lookup"><span data-stu-id="b3823-178">Security operations dashboard</span></span>
- <span data-ttu-id="b3823-179">警示佇列</span><span class="sxs-lookup"><span data-stu-id="b3823-179">Alert queue</span></span>
- <span data-ttu-id="b3823-180">裝置詳細資料頁面</span><span class="sxs-lookup"><span data-stu-id="b3823-180">Device details page</span></span>

<span data-ttu-id="b3823-181">如需詳細資訊，請參閱 [調查使用者帳戶](investigate-user.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-181">For more information, see [Investigate a user account](investigate-user.md).</span></span>


## <a name="skype-for-business-integration"></a><span data-ttu-id="b3823-182">商務用 Skype 整合</span><span class="sxs-lookup"><span data-stu-id="b3823-182">Skype for Business integration</span></span>

<span data-ttu-id="b3823-183">啟用商務用 Skype 整合功能可讓您使用商務用 Skype、電子郵件或電話與使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b3823-183">Enabling the Skype for Business integration gives you the ability to communicate with users using Skype for Business, email, or phone.</span></span> <span data-ttu-id="b3823-184">當您需要與使用者通訊並減輕風險時，這會很便利。</span><span class="sxs-lookup"><span data-stu-id="b3823-184">This can be handy when you need to communicate with the user and mitigate risks.</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-185">當裝置與網路隔離時，會有一個快顯視窗，您可以在其中選擇啟用 Outlook 和 Skype 通訊，以便在使用者與網路中斷連線的情況下，與使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="b3823-185">When a device is being isolated from the network, there's a pop-up where you can choose to enable Outlook and Skype communications which allows communications to the user while they are disconnected from the network.</span></span> <span data-ttu-id="b3823-186">此設定適用于裝置處於隔離模式時 Skype 和 Outlook 通訊。</span><span class="sxs-lookup"><span data-stu-id="b3823-186">This setting applies to Skype and Outlook communication when devices are in isolation mode.</span></span>

## <a name="microsoft-defender-for-identity-integration"></a><span data-ttu-id="b3823-187">Microsoft Defender 用於身分識別整合</span><span class="sxs-lookup"><span data-stu-id="b3823-187">Microsoft Defender for Identity integration</span></span>

<span data-ttu-id="b3823-188">與 Microsoft Defender 身分識別的整合，可讓您直接在 Microsoft Identity security 產品中直接旋轉。</span><span class="sxs-lookup"><span data-stu-id="b3823-188">The integration with Microsoft Defender for Identity allows you to pivot directly into another Microsoft Identity security product.</span></span> <span data-ttu-id="b3823-189">Microsoft Defender for Identity 會以其他有關可疑已遭破壞之帳戶和相關資源之深入瞭解的觀點來增強調查。</span><span class="sxs-lookup"><span data-stu-id="b3823-189">Microsoft Defender for Identity augments an investigation with additional insights about a suspected compromised account and related resources.</span></span> <span data-ttu-id="b3823-190">透過啟用這項功能，您就可以透過從識別的觀點來切換網路，來充實裝置型調查功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-190">By enabling this feature, you'll enrich the device-based investigation capability by pivoting across the network from an identify point of view.</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-191">您必須具有適當的授權，才能啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-191">You'll need to have the appropriate license to enable this feature.</span></span>

## <a name="office-365-threat-intelligence-connection"></a><span data-ttu-id="b3823-192">Office 365威脅智慧連接</span><span class="sxs-lookup"><span data-stu-id="b3823-192">Office 365 Threat Intelligence connection</span></span>

<span data-ttu-id="b3823-193">只有當您具有使用中 Office 365 E5 或威脅情報附加元件時，才可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-193">This feature is only available if you have an active Office 365 E5 or the Threat Intelligence add-on.</span></span> <span data-ttu-id="b3823-194">如需詳細資訊，請參閱 Office 365 企業版 E5 產品頁面。</span><span class="sxs-lookup"><span data-stu-id="b3823-194">For more information, see the Office 365 Enterprise E5 product page.</span></span>

<span data-ttu-id="b3823-195">當您開啟此功能時，您可以將 Microsoft Defender 中 Office 365 的資料合併成 Microsoft Defender 資訊安全中心，以跨 Office 365 信箱及 Windows 裝置進行全面的安全性調查。</span><span class="sxs-lookup"><span data-stu-id="b3823-195">When you turn this feature on, you'll be able to incorporate data from Microsoft Defender for Office 365 into Microsoft Defender Security Center to conduct a comprehensive security investigation across Office 365 mailboxes and Windows devices.</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-196">您必須具有適當的授權，才能啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-196">You'll need to have the appropriate license to enable this feature.</span></span>

<span data-ttu-id="b3823-197">若要在 Office 365 威脅情報中接收上下文相關的裝置整合，您必須在安全性 & 規範儀表板中啟用 [Endpoint for Endpoint] 設定。</span><span class="sxs-lookup"><span data-stu-id="b3823-197">To receive contextual device integration in Office 365 Threat Intelligence, you'll need to enable the Defender for Endpoint settings in the Security & Compliance dashboard.</span></span> <span data-ttu-id="b3823-198">如需詳細資訊，請參閱 [威脅調查和回應](/microsoft-365/security/office-365-security/office-365-ti)。</span><span class="sxs-lookup"><span data-stu-id="b3823-198">For more information, see [Threat investigation and response](/microsoft-365/security/office-365-security/office-365-ti).</span></span>

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a><span data-ttu-id="b3823-199">Microsoft 威脅專家目標攻擊通知</span><span class="sxs-lookup"><span data-stu-id="b3823-199">Microsoft Threat Experts - Targeted Attack Notifications</span></span>

<span data-ttu-id="b3823-200">除了兩個 Microsoft 威脅專家元件，已設定目標攻擊通知是在正式發行時。</span><span class="sxs-lookup"><span data-stu-id="b3823-200">Out of the two Microsoft Threat Expert components, targeted attack notification is in general availability.</span></span> <span data-ttu-id="b3823-201">專家隨選功能仍在預覽中。</span><span class="sxs-lookup"><span data-stu-id="b3823-201">Experts-on-demand capability is still in preview.</span></span> <span data-ttu-id="b3823-202">如果您已套用預覽，且已核准您的應用程式，您只能使用專家隨選功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-202">You can only use the experts-on-demand capability if you have applied for preview and your application has been approved.</span></span> <span data-ttu-id="b3823-203">您可以從 Microsoft 威脅專家透過您的端點入口網站的 [警示] 儀表板，以及透過電子郵件（如果您設定它）來接收目標攻擊通知。</span><span class="sxs-lookup"><span data-stu-id="b3823-203">You can receive targeted attack notifications from Microsoft Threat Experts through your Defender for Endpoint portal's alerts dashboard and via email if you configure it.</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-204">Microsoft 威脅專家的 Defender for Endpoint 的功能可與[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)的 E5 授權搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b3823-204">The Microsoft Threat Experts capability in Defender for Endpoint is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security).</span></span>
## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="b3823-205">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b3823-205">Microsoft Cloud App Security</span></span>

<span data-ttu-id="b3823-206">啟用此設定時，會將 Defender 的端點信號轉寄至 Microsoft Cloud App Security，以提供 Cloud 應用程式使用的深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="b3823-206">Enabling this setting forwards Defender for Endpoint signals to Microsoft Cloud App Security to provide deeper visibility into cloud application usage.</span></span> <span data-ttu-id="b3823-207">轉寄的資料會儲存並處理雲端 App 安全性資料所在的相同位置。</span><span class="sxs-lookup"><span data-stu-id="b3823-207">Forwarded data is stored and processed in the same location as your Cloud App Security data.</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-208">在執行 Windows 10 的裝置上，將會有[Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)的 E5 授權、版本 1709 (os 組建16299.1085 （含[KB4493441](https://support.microsoft.com/help/4493441)) 、Windows 10、版本 1803 (os 組建17134.704 搭配[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10、版本 1809 (os 組建17763.379 搭配[KB4489899](https://support.microsoft.com/help/4489899)) （或更新版本）。</span><span class="sxs-lookup"><span data-stu-id="b3823-208">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)), or later Windows 10 versions.</span></span>

## <a name="microsoft-secure-score"></a><span data-ttu-id="b3823-209">Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="b3823-209">Microsoft Secure Score</span></span>

<span data-ttu-id="b3823-210">在 Microsoft 365 security center 中，將 microsoft Defender for Endpoint 信號轉寄給 microsoft 安全評分。</span><span class="sxs-lookup"><span data-stu-id="b3823-210">Forwards Microsoft Defender for Endpoint signals to Microsoft Secure Score in the Microsoft 365 security center.</span></span> <span data-ttu-id="b3823-211">開啟此功能可讓 Microsoft 安全分數看到裝置的安全性狀況。</span><span class="sxs-lookup"><span data-stu-id="b3823-211">Turning on this feature gives Microsoft Secure Score visibility into the device's security posture.</span></span> <span data-ttu-id="b3823-212">轉寄的資料會與您的 Microsoft 安全分數資料儲存在相同的位置。</span><span class="sxs-lookup"><span data-stu-id="b3823-212">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a><span data-ttu-id="b3823-213">從 Microsoft Defender for Identity 入口網站啟用 Microsoft Defender for Endpoint 整合</span><span class="sxs-lookup"><span data-stu-id="b3823-213">Enable the Microsoft Defender for Endpoint integration from the Microsoft Defender for Identity portal</span></span>

<span data-ttu-id="b3823-214">若要在 Microsoft Defender for Identity 中接收與內容相關的設備整合，您也需要啟用 Microsoft Defender for Identity 入口網站中的功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-214">To receive contextual device integration in Microsoft Defender for Identity, you'll also need to enable the feature in the Microsoft Defender for Identity portal.</span></span>

1. <span data-ttu-id="b3823-215">使用全域系統管理員或安全性管理員角色，登入 [Microsoft Defender 的身分識別入口網站](https://portal.atp.azure.com/) 。</span><span class="sxs-lookup"><span data-stu-id="b3823-215">Log in to the [Microsoft Defender for Identity portal](https://portal.atp.azure.com/) with a Global Administrator or Security Administrator role.</span></span>

2. <span data-ttu-id="b3823-216">按一下 [ **建立您的實例**]。</span><span class="sxs-lookup"><span data-stu-id="b3823-216">Click **Create your instance**.</span></span>

3. <span data-ttu-id="b3823-217">將 Integration 設定切換為 [ **開啟** ]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b3823-217">Toggle the Integration setting to **On** and click **Save**.</span></span>

<span data-ttu-id="b3823-218">完成這兩個入口網站的整合步驟之後，您可以在 [裝置詳細資料] 或 [使用者詳細資料] 頁面看到相關的警示。</span><span class="sxs-lookup"><span data-stu-id="b3823-218">After completing the integration steps on both portals, you'll be able to see relevant alerts in the device details or user details page.</span></span>

## <a name="web-content-filtering"></a><span data-ttu-id="b3823-219">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="b3823-219">Web content filtering</span></span>
<span data-ttu-id="b3823-220">封鎖包含有害內容之網站的存取，並追蹤所有網域中的 web 活動。</span><span class="sxs-lookup"><span data-stu-id="b3823-220">Block access to websites containing unwanted content and track web activity across all domains.</span></span> <span data-ttu-id="b3823-221">若要指定您要封鎖的 web 內容類別別，請建立 [web 內容篩選原則](https://security.microsoft.com/preferences2/web_content_filtering_policy)。</span><span class="sxs-lookup"><span data-stu-id="b3823-221">To specify the web content categories you want to block, create a [web content filtering policy](https://security.microsoft.com/preferences2/web_content_filtering_policy).</span></span> <span data-ttu-id="b3823-222">在部署 [Microsoft Defender For Endpoint security 基準](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)時，確保您具有封鎖模式中的網路保護。</span><span class="sxs-lookup"><span data-stu-id="b3823-222">Ensure you have network protection in block mode when deploying the [Microsoft Defender for Endpoint security baseline](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2).</span></span>


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a><span data-ttu-id="b3823-223">與 Microsoft 規範中心共用端點警示</span><span class="sxs-lookup"><span data-stu-id="b3823-223">Share endpoint alerts with Microsoft Compliance Center</span></span>
<span data-ttu-id="b3823-224">將端點安全性警示和其會審狀態轉寄給 Microsoft 規範中心，讓您能夠使用預警增強內幕風險管理原則，並在內部風險造成損害之前加以修正。</span><span class="sxs-lookup"><span data-stu-id="b3823-224">Forwards endpoint security alerts and their triage status to Microsoft Compliance Center, allowing you to enhance insider risk management policies with alerts and remediate internal risks before they cause harm.</span></span> <span data-ttu-id="b3823-225">轉寄的資料會處理並儲存在與 Office 365 資料相同的位置。</span><span class="sxs-lookup"><span data-stu-id="b3823-225">Forwarded data is processed and stored in the same location as your Office 365 data.</span></span>

<span data-ttu-id="b3823-226">在「內幕風險管理」設定中設定 [安全性原則違規指示器](/microsoft-365/compliance/insider-risk-management-settings#indicators) 後，就會與適用使用者的「內部使用者風險管理」共用端點警示。</span><span class="sxs-lookup"><span data-stu-id="b3823-226">After configuring the [Security policy violation indicators](/microsoft-365/compliance/insider-risk-management-settings#indicators) in the insider risk management settings, Defender for Endpoint alerts will be shared with insider risk management for applicable users.</span></span>



## <a name="microsoft-intune-connection"></a><span data-ttu-id="b3823-227">Microsoft Intune 連接</span><span class="sxs-lookup"><span data-stu-id="b3823-227">Microsoft Intune connection</span></span>

<span data-ttu-id="b3823-228">可以將 Endpoint for 端點與[Microsoft Intune](/intune/what-is-intune)整合，以[啟用裝置風險的條件式存取](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="b3823-228">Defender for Endpoint can be integrated with [Microsoft Intune](/intune/what-is-intune) to [enable device risk-based conditional access](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span> <span data-ttu-id="b3823-229">當您 [開啟此功能](configure-conditional-access.md)時，您可以使用 Intune 與 Intune 共用 Defender 裝置資訊，進而增強原則的執行能力。</span><span class="sxs-lookup"><span data-stu-id="b3823-229">When you [turn on this feature](configure-conditional-access.md), you'll be able to share Defender for Endpoint device information with Intune, enhancing policy enforcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3823-230">您必須在 Intune 和 Defender for Endpoint 上啟用整合，才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-230">You'll need to enable the integration on both Intune and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="b3823-231">如需特定步驟的詳細資訊，請參閱 [在 Defender For Endpoint 中設定條件式存取](configure-conditional-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-231">For more information on specific steps, see [Configure Conditional Access in Defender for Endpoint](configure-conditional-access.md).</span></span>

<span data-ttu-id="b3823-232">只有在下列情況下，才可使用此功能：</span><span class="sxs-lookup"><span data-stu-id="b3823-232">This feature is only available if you have the following:</span></span>

- <span data-ttu-id="b3823-233">企業行動力 + 安全性 E3 的授權租使用者，以及 Windows e5 (或 Microsoft 365 企業版 e5) </span><span class="sxs-lookup"><span data-stu-id="b3823-233">A licensed tenant for Enterprise Mobility + Security E3, and Windows E5 (or Microsoft 365 Enterprise E5)</span></span>
- <span data-ttu-id="b3823-234">使用 Intune 管理 Windows 10 裝置的作用中 Microsoft Intune 環境會[連接 Azure AD](/azure/active-directory/devices/concept-azure-ad-join/)。</span><span class="sxs-lookup"><span data-stu-id="b3823-234">An active Microsoft Intune environment, with Intune-managed Windows 10 devices [Azure AD-joined](/azure/active-directory/devices/concept-azure-ad-join/).</span></span>


### <a name="conditional-access-policy"></a><span data-ttu-id="b3823-235">條件式存取原則</span><span class="sxs-lookup"><span data-stu-id="b3823-235">Conditional Access policy</span></span>

<span data-ttu-id="b3823-236">當您啟用 Intune 整合時，Intune 會自動建立傳統的條件式存取 (CA) 原則。</span><span class="sxs-lookup"><span data-stu-id="b3823-236">When you enable Intune integration, Intune will automatically create a classic Conditional Access (CA) policy.</span></span> <span data-ttu-id="b3823-237">這項傳統 CA 原則是設定狀態報表至 Intune 的必要條件。</span><span class="sxs-lookup"><span data-stu-id="b3823-237">This classic CA policy is a prerequisite for setting up status reports to Intune.</span></span> <span data-ttu-id="b3823-238">不應該刪除。</span><span class="sxs-lookup"><span data-stu-id="b3823-238">It should not be deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-239">Intune 所建立的傳統 CA 原則與新式條件式 [存取原則](/azure/active-directory/conditional-access/overview/)不同，用來設定端點。</span><span class="sxs-lookup"><span data-stu-id="b3823-239">The classic CA policy created by Intune is distinct from modern [Conditional Access policies](/azure/active-directory/conditional-access/overview/), which are used for configuring endpoints.</span></span>


## <a name="device-discovery"></a><span data-ttu-id="b3823-240">裝置探索</span><span class="sxs-lookup"><span data-stu-id="b3823-240">Device discovery</span></span>
<span data-ttu-id="b3823-241">協助您找出連接至公司網路的非管理裝置，不需要額外裝置或繁瑣的處理常式變更。</span><span class="sxs-lookup"><span data-stu-id="b3823-241">Helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span> <span data-ttu-id="b3823-242">使用架裝置，您可以在網路中尋找未受管理的裝置，並評估漏洞和風險。</span><span class="sxs-lookup"><span data-stu-id="b3823-242">Using onboarded devices, you can find unmanaged devices in your network and assess vulnerabilities and risks.</span></span> <span data-ttu-id="b3823-243">如需詳細資訊，請參閱 [Device discovery](device-discovery.md)。</span><span class="sxs-lookup"><span data-stu-id="b3823-243">For more information, see [Device discovery](device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b3823-244">您永遠可以套用篩選器，以從裝置庫存清單中排除未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="b3823-244">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="b3823-245">您也可以在 API 查詢上使用 [上架狀態] 欄，以篩選出未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="b3823-245">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="b3823-246">預覽功能</span><span class="sxs-lookup"><span data-stu-id="b3823-246">Preview features</span></span>

<span data-ttu-id="b3823-247">瞭解適用于 Defender 的端點預覽版本中的新功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-247">Learn about new features in the Defender for Endpoint preview release.</span></span> <span data-ttu-id="b3823-248">開啟預覽體驗，嘗試即將推出的功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-248">Try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="b3823-249">您將可以存取即將推出的功能，您可以在其中提供意見反應，以協助改善整體體驗，使其成為一般可用功能。</span><span class="sxs-lookup"><span data-stu-id="b3823-249">You'll have access to upcoming features, which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>




## <a name="related-topics"></a><span data-ttu-id="b3823-250">相關主題</span><span class="sxs-lookup"><span data-stu-id="b3823-250">Related topics</span></span>

- [<span data-ttu-id="b3823-251">更新資料保留設定</span><span class="sxs-lookup"><span data-stu-id="b3823-251">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="b3823-252">設定警示通知</span><span class="sxs-lookup"><span data-stu-id="b3823-252">Configure alert notifications</span></span>](configure-email-notifications.md)
