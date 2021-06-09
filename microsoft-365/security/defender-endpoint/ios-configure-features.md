---
title: 在 iOS 功能上設定 Microsoft Defender for Endpoint
description: 說明如何在 iOS 功能上部署 Microsoft Defender for Endpoint
keywords: microsoft，defender，Microsoft Defender for Endpoint，ios，configure，features，ios
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d32d40ac8ce086caedd53e0a69aac2a3025dc702
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842251"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="38d91-104">在 iOS 功能上設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="38d91-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="38d91-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="38d91-105">**Applies to:**</span></span>
- [<span data-ttu-id="38d91-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="38d91-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="38d91-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38d91-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="38d91-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="38d91-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="38d91-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="38d91-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="38d91-110">IOS 上的 Defender for Endpoint 會使用 VPN，以便提供 Web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="38d91-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="38d91-111">這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。</span><span class="sxs-lookup"><span data-stu-id="38d91-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="38d91-112">在 iOS 上使用 Defender for Endpoint 進行條件式存取</span><span class="sxs-lookup"><span data-stu-id="38d91-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="38d91-113">Microsoft Defender for Endpoint on iOS 隨 Microsoft Intune 和 Azure Active Directory 可根據裝置風險分數強制強制執行裝置合規性和條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="38d91-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="38d91-114">Defender for Endpoint 是行動威脅防護 (MTD) 解決方案，您可以透過 Intune 部署此功能，以利用這項功能。</span><span class="sxs-lookup"><span data-stu-id="38d91-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="38d91-115">如需如何設定 iOS 上的使用 Defender for Endpoint 的條件式存取的相關資訊，請參閱 [Defender For endpoint And Intune](/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="38d91-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="38d91-116">Microsoft Defender for Endpoint 的 Jailbreak 偵測</span><span class="sxs-lookup"><span data-stu-id="38d91-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="38d91-117">Microsoft Defender for Endpoint 具備偵測已越獄之受管理和受管理裝置的能力。</span><span class="sxs-lookup"><span data-stu-id="38d91-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="38d91-118">如果偵測到裝置已越獄，將會向安全中心報告 **高** 風險警示，而且如果根據裝置風險分數設定條件式存取，則系統會封鎖裝置以存取公司資料。</span><span class="sxs-lookup"><span data-stu-id="38d91-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="38d91-119">Web 保護和 VPN</span><span class="sxs-lookup"><span data-stu-id="38d91-119">Web Protection and VPN</span></span>

<span data-ttu-id="38d91-120">根據預設，iOS 上的 Defender for Endpoint 會包含並啟用 web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="38d91-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="38d91-121">[Web 保護](web-protection-overview.md) 可協助保護裝置免受網頁威脅，並保護使用者免受網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="38d91-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="38d91-122">IOS 上的 Defender for Endpoint 會使用 VPN，以提供此保護。</span><span class="sxs-lookup"><span data-stu-id="38d91-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="38d91-123">請注意，這是本機 VPN，與傳統 VPN 不同，網路流量不會傳送到裝置外。</span><span class="sxs-lookup"><span data-stu-id="38d91-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="38d91-124">預設為啟用時，可能需要停用 VPN。</span><span class="sxs-lookup"><span data-stu-id="38d91-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="38d91-125">例如，當設定 VPN 時，您想要執行一些無法運作的應用程式。</span><span class="sxs-lookup"><span data-stu-id="38d91-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="38d91-126">在這種情況下，您可以依照下列步驟，從裝置上的應用程式中選擇停用 VPN：</span><span class="sxs-lookup"><span data-stu-id="38d91-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="38d91-127">在您的 iOS 裝置上，開啟 **設定** 應用程式，按一下或點擊 **[一般**]，然後再按一下 [ **VPN**]。</span><span class="sxs-lookup"><span data-stu-id="38d91-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="38d91-128">按一下或點擊 Microsoft Defender for Endpoint 的「i」按鈕。</span><span class="sxs-lookup"><span data-stu-id="38d91-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="38d91-129">關閉連線停用 VPN 的 **要求**。</span><span class="sxs-lookup"><span data-stu-id="38d91-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38d91-130">![需要時 VPN 設定連接](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="38d91-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="38d91-131">停用 VPN 時，將無法使用 Web 保護。</span><span class="sxs-lookup"><span data-stu-id="38d91-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="38d91-132">若要重新啟用 Web 保護，請開啟裝置上的 Microsoft Defender for Endpoint app，然後按一下或點擊 [ **啟動 VPN**]。</span><span class="sxs-lookup"><span data-stu-id="38d91-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="38d91-133">共同存在多個 VPN 設定檔</span><span class="sxs-lookup"><span data-stu-id="38d91-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="38d91-134">Apple iOS 不支援多個全裝置的 Vpn 同時作用中。</span><span class="sxs-lookup"><span data-stu-id="38d91-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="38d91-135">雖然裝置上可以有多個 VPN 設定檔，但一次只能有一個 VPN 可用。</span><span class="sxs-lookup"><span data-stu-id="38d91-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="38d91-136">設定已越獄裝置的相容性原則</span><span class="sxs-lookup"><span data-stu-id="38d91-136">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="38d91-137">為了保護公司資料無法在已越獄的 iOS 裝置上存取，我們建議您在 Intune 上設定下列符合性原則。</span><span class="sxs-lookup"><span data-stu-id="38d91-137">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="38d91-138">Jailbreak 偵測是 Microsoft Defender for Endpoint on iOS 所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="38d91-138">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="38d91-139">不過，我們建議您將此原則設定為其他防禦層級，以防禦 jailbreak 案例。</span><span class="sxs-lookup"><span data-stu-id="38d91-139">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="38d91-140">請遵循下列步驟，建立對已越獄裝置的相容性原則。</span><span class="sxs-lookup"><span data-stu-id="38d91-140">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="38d91-141">在 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，移至 [**裝置**  ->  **規範原則**] [  ->  **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="38d91-141">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="38d91-142">選取 "iOS/iPadOS" 作為平臺，然後按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="38d91-142">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38d91-143">![建立原則](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="38d91-143">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="38d91-144">指定原則的名稱，例如「Jailbreak 的合規性原則」。</span><span class="sxs-lookup"><span data-stu-id="38d91-144">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="38d91-145">在 [規範設定] 頁面上，按一下以展開 [**裝置健全**] 區段，然後按一下 [封鎖 **裝置** 的 **封鎖**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="38d91-145">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38d91-146">![原則設定](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="38d91-146">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="38d91-147">在 [不 *符合之動作* ] 區段中，根據您的需求選取動作，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="38d91-147">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="38d91-148">![原則動作](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="38d91-148">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="38d91-149">在 [ *工作分派* ] 區段中，選取您要包含此原則的使用者群組，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="38d91-149">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="38d91-150">在 [ **複查 + 建立** ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="38d91-150">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="38d91-151">設定自訂指示器</span><span class="sxs-lookup"><span data-stu-id="38d91-151">Configure custom indicators</span></span>

<span data-ttu-id="38d91-152">IOS 上的 Defender for Endpoint 可讓系統管理員也在 iOS 裝置上設定自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="38d91-152">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="38d91-153">如需如何設定自訂指示器的詳細資訊，請參閱 [管理指示器](/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="38d91-153">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="38d91-154">IOS 上的 Defender for Endpoint 支援只為 IP 位址和 URLs/網域建立自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="38d91-154">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="38d91-155">報告不安全的網站</span><span class="sxs-lookup"><span data-stu-id="38d91-155">Report unsafe site</span></span>

<span data-ttu-id="38d91-156">網路釣魚網站會為了取得您的個人或財務資訊，模仿可信的網站。</span><span class="sxs-lookup"><span data-stu-id="38d91-156">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="38d91-157">如果您想要報告可能是網路釣魚網站的網站，請造訪 [ [提供有關網路保護的意見](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 反應] 頁面。</span><span class="sxs-lookup"><span data-stu-id="38d91-157">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

