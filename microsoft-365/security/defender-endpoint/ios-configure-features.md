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
ms.openlocfilehash: dab72da02927c3fff6025eb2d0fa9ed0fdf1d0d7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245273"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="3b379-104">在 iOS 功能上設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3b379-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3b379-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3b379-105">**Applies to:**</span></span>
- [<span data-ttu-id="3b379-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3b379-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3b379-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b379-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3b379-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3b379-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3b379-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3b379-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="3b379-110">IOS 上的 Defender for Endpoint 會使用 VPN，以便提供 Web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="3b379-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="3b379-111">這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。</span><span class="sxs-lookup"><span data-stu-id="3b379-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="3b379-112">在 iOS 上使用 Defender for Endpoint 進行條件式存取</span><span class="sxs-lookup"><span data-stu-id="3b379-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="3b379-113">Microsoft Defender for Endpoint on iOS 隨 Microsoft Intune 和 Azure Active Directory 可根據裝置風險分數強制強制執行裝置合規性和條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="3b379-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="3b379-114">Defender for Endpoint 是行動威脅防護 (MTD) 解決方案，您可以透過 Intune 部署此功能，以利用這項功能。</span><span class="sxs-lookup"><span data-stu-id="3b379-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="3b379-115">如需如何設定 iOS 上的使用 Defender for Endpoint 的條件式存取的相關資訊，請參閱 [Defender For endpoint And Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="3b379-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="3b379-116">**Jailbreak 中 Microsoft Defender for IOS Endpoint 的偵測目前正在預覽中**。</span><span class="sxs-lookup"><span data-stu-id="3b379-116">**Jailbreak detection by Microsoft Defender for Endpoint on iOS is currently in preview**.</span></span> <span data-ttu-id="3b379-117">如果偵測到裝置已受到 Microsoft Defender for Endpoint 的鎖定，將會向安全中心報告 **高** 風險警示，而且如果根據裝置風險分數設定條件式存取，則系統會封鎖裝置存取公司資料。</span><span class="sxs-lookup"><span data-stu-id="3b379-117">If a device is detected to be jailbroken by Microsoft Defender for Endpoint, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="3b379-118">Web 保護和 VPN</span><span class="sxs-lookup"><span data-stu-id="3b379-118">Web Protection and VPN</span></span>

<span data-ttu-id="3b379-119">根據預設，iOS 上的 Defender for Endpoint 會包含並啟用 web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="3b379-119">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="3b379-120">[Web 保護](web-protection-overview.md) 可協助保護裝置免受網頁威脅，並保護使用者免受網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="3b379-120">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="3b379-121">IOS 上的 Defender for Endpoint 會使用 VPN，以提供此保護。</span><span class="sxs-lookup"><span data-stu-id="3b379-121">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="3b379-122">請注意，這是本機 VPN，與傳統 VPN 不同，網路流量不會傳送到裝置外。</span><span class="sxs-lookup"><span data-stu-id="3b379-122">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="3b379-123">預設為啟用時，可能需要停用 VPN。</span><span class="sxs-lookup"><span data-stu-id="3b379-123">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="3b379-124">例如，當設定 VPN 時，您想要執行一些無法運作的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3b379-124">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="3b379-125">在這種情況下，您可以依照下列步驟，從裝置上的應用程式中選擇停用 VPN：</span><span class="sxs-lookup"><span data-stu-id="3b379-125">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="3b379-126">在您的 iOS 裝置上，開啟 **設定** 應用程式，按一下或點擊 **[一般**]，然後再按一下 [ **VPN**]。</span><span class="sxs-lookup"><span data-stu-id="3b379-126">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="3b379-127">按一下或點擊 Microsoft Defender for Endpoint 的「i」按鈕。</span><span class="sxs-lookup"><span data-stu-id="3b379-127">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="3b379-128">關閉連線停用 VPN 的 **要求**。</span><span class="sxs-lookup"><span data-stu-id="3b379-128">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3b379-129">![需要時 VPN 設定連接](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="3b379-129">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="3b379-130">停用 VPN 時，將無法使用 Web 保護。</span><span class="sxs-lookup"><span data-stu-id="3b379-130">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="3b379-131">若要重新啟用 Web 保護，請開啟裝置上的 Microsoft Defender for Endpoint app，然後按一下或點擊 [ **啟動 VPN**]。</span><span class="sxs-lookup"><span data-stu-id="3b379-131">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="3b379-132">共同存在多個 VPN 設定檔</span><span class="sxs-lookup"><span data-stu-id="3b379-132">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="3b379-133">Apple iOS 不支援多個全裝置的 Vpn 同時作用中。</span><span class="sxs-lookup"><span data-stu-id="3b379-133">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="3b379-134">雖然裝置上可以有多個 VPN 設定檔，但一次只能有一個 VPN 可用。</span><span class="sxs-lookup"><span data-stu-id="3b379-134">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="3b379-135">設定已越獄裝置的相容性原則</span><span class="sxs-lookup"><span data-stu-id="3b379-135">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="3b379-136">為了保護公司資料無法在已越獄的 iOS 裝置上存取，我們建議您在 Intune 上設定下列符合性原則。</span><span class="sxs-lookup"><span data-stu-id="3b379-136">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="3b379-137">目前，jailbreak 的 Microsoft Defender for iOS Endpoint 偵測是在預覽中。</span><span class="sxs-lookup"><span data-stu-id="3b379-137">At this time jailbreak detection by Microsoft Defender for Endpoint on iOS is in preview.</span></span> <span data-ttu-id="3b379-138">建議您將此原則設定為其他防禦層級，以防禦 jailbreak 案例。</span><span class="sxs-lookup"><span data-stu-id="3b379-138">We recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="3b379-139">請遵循下列步驟，建立對已越獄裝置的相容性原則。</span><span class="sxs-lookup"><span data-stu-id="3b379-139">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="3b379-140">在 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，移至 [**裝置**  ->  **規範原則**] [  ->  **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="3b379-140">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="3b379-141">選取 "iOS/iPadOS" 作為平臺，然後按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="3b379-141">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3b379-142">![建立原則](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="3b379-142">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="3b379-143">指定原則的名稱，例如「Jailbreak 的合規性原則」。</span><span class="sxs-lookup"><span data-stu-id="3b379-143">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="3b379-144">在 [規範設定] 頁面上，按一下以展開 [**裝置健全**] 區段，然後按一下 [封鎖 **裝置** 的 **封鎖**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="3b379-144">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3b379-145">![原則設定](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="3b379-145">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="3b379-146">在 [不 *符合之動作* ] 區段中，根據您的需求選取動作，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b379-146">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="3b379-147">![原則動作](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="3b379-147">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="3b379-148">在 [ *工作分派* ] 區段中，選取您要包含此原則的使用者群組，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b379-148">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="3b379-149">在 [ **複查 + 建立** ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="3b379-149">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="3b379-150">設定自訂指示器</span><span class="sxs-lookup"><span data-stu-id="3b379-150">Configure custom indicators</span></span>

<span data-ttu-id="3b379-151">IOS 上的 Defender for Endpoint 可讓系統管理員也在 iOS 裝置上設定自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="3b379-151">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="3b379-152">如需如何設定自訂指示器的詳細資訊，請參閱 [管理指示器](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="3b379-152">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="3b379-153">IOS 上的 Defender for Endpoint 支援只為 IP 位址和 URLs/網域建立自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="3b379-153">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="3b379-154">報告不安全的網站</span><span class="sxs-lookup"><span data-stu-id="3b379-154">Report unsafe site</span></span>

<span data-ttu-id="3b379-155">網路釣魚網站會為了取得您的個人或財務資訊，模仿可信的網站。</span><span class="sxs-lookup"><span data-stu-id="3b379-155">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="3b379-156">如果您想要報告可能是網路釣魚網站的網站，請造訪 [ [提供有關網路保護的意見](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 反應] 頁面。</span><span class="sxs-lookup"><span data-stu-id="3b379-156">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="3b379-157">安裝 Microsoft Defender for Endpoint 時 iOS 的電池消耗問題</span><span class="sxs-lookup"><span data-stu-id="3b379-157">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="3b379-158">應用程式的電池使用量是根據許多因素（包括 CPU 和網路使用量）計算而來。</span><span class="sxs-lookup"><span data-stu-id="3b379-158">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="3b379-159">Microsoft Defender for Endpoint 會在背景中使用本機/環路傳回 VPN，檢查任何惡意網站或連線的網頁流量。</span><span class="sxs-lookup"><span data-stu-id="3b379-159">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="3b379-160">任何應用程式的網路封包都會進行此項檢查，從而導致無法準確計算 Microsoft Defender for Endpoint 的電池使用量。</span><span class="sxs-lookup"><span data-stu-id="3b379-160">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="3b379-161">這為使用者提供了錯誤的印象。</span><span class="sxs-lookup"><span data-stu-id="3b379-161">This gives a false impression to the user.</span></span> <span data-ttu-id="3b379-162">Microsoft Defender for Endpoint 的實際電池消耗小於裝置上的 [電池設定] 頁面上顯示的數目。</span><span class="sxs-lookup"><span data-stu-id="3b379-162">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="3b379-163">這是以 Microsoft Defender for Endpoint app 所進行的測試為基礎，以瞭解電池消耗。</span><span class="sxs-lookup"><span data-stu-id="3b379-163">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="3b379-164">此外，使用的 VPN 也是本機 VPN，與傳統的 vpn 不同的是，網路流量不會傳送到裝置外。</span><span class="sxs-lookup"><span data-stu-id="3b379-164">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
