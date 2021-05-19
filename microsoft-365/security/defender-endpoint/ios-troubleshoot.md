---
title: 疑難排解 iOS 上的 Microsoft Defender for Endpoint 上的問題
description: 疑難排解與常見問題-Microsoft Defender for Endpoint on iOS
keywords: microsoft，defender，Microsoft Defender for Endpoint，ios，疑難排解，常見問題，如何
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
ms.openlocfilehash: 82a3fcc58b97f53f584befae77c86e8a18952a23
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539292"
---
# <a name="troubleshoot-issues-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="6bb1e-104">疑難排解 iOS 上的 Microsoft Defender for Endpoint 上的問題</span><span class="sxs-lookup"><span data-stu-id="6bb1e-104">Troubleshoot issues on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6bb1e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="6bb1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="6bb1e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6bb1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6bb1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bb1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6bb1e-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6bb1e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6bb1e-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="6bb1e-110">本主題提供疑難排解資訊，可協助您處理當您在 iOS 上使用 Microsoft Defender for Endpoint 時可能發生的問題。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="6bb1e-111">IOS 上的 Defender for Endpoint 會使用 VPN，以便提供 Web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="6bb1e-112">這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="6bb1e-113">開啟 VPN 時，應用程式無法運作</span><span class="sxs-lookup"><span data-stu-id="6bb1e-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="6bb1e-114">偵測到主動 VPN 時，有些應用程式停止運作。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="6bb1e-115">您可以在使用這類應用程式時停用 VPN。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="6bb1e-116">根據預設，iOS 上的 Defender for Endpoint 會包含並啟用 web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="6bb1e-117">[Web 保護](web-protection-overview.md) 可協助保護裝置免受網頁威脅，並保護使用者免受網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="6bb1e-118">IOS 上的 Defender for Endpoint 會使用 VPN，以提供此保護。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="6bb1e-119">請注意，這是本機 VPN，與傳統 VPN 不同，網路流量不會傳送到裝置外。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="6bb1e-120">預設為啟用時，可能需要停用 VPN。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="6bb1e-121">例如，當設定 VPN 時，您想要執行一些無法運作的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="6bb1e-122">在這種情況下，您可以依照下列步驟，從裝置上的應用程式中選擇停用 VPN：</span><span class="sxs-lookup"><span data-stu-id="6bb1e-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="6bb1e-123">在您的 iOS 裝置上，開啟 **設定** 應用程式，按一下或點擊 **[一般**]，然後再按一下 [ **VPN**]。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="6bb1e-124">按一下或點擊 Microsoft Defender for Endpoint 的「i」按鈕。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="6bb1e-125">關閉連線停用 VPN 的 **要求**。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6bb1e-126">![需要時 VPN 設定連接](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="6bb1e-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="6bb1e-127">停用 VPN 時，將無法使用 Web 保護。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="6bb1e-128">若要重新啟用 Web 保護，請開啟裝置上的 Microsoft Defender for Endpoint app，然後按一下或點擊 [ **啟動 VPN**]。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="6bb1e-129">多個 VPN 設定檔的問題</span><span class="sxs-lookup"><span data-stu-id="6bb1e-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="6bb1e-130">Apple iOS 不支援多個全裝置的 Vpn 同時作用中。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="6bb1e-131">雖然裝置上可以有多個 VPN 設定檔，但一次只能有一個 VPN 可用。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="6bb1e-132">電池消耗</span><span class="sxs-lookup"><span data-stu-id="6bb1e-132">Battery consumption</span></span>

<span data-ttu-id="6bb1e-133">應用程式的電池使用量是根據許多因素（包括 CPU 和網路使用量）計算而來。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="6bb1e-134">Microsoft Defender for Endpoint 會在背景中使用本機/環路傳回 VPN，檢查任何惡意網站或連線的網頁流量。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="6bb1e-135">任何應用程式的網路封包都會進行此項檢查，從而導致無法準確計算 Microsoft Defender for Endpoint 的電池使用量。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="6bb1e-136">這為使用者提供了錯誤的印象。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-136">This gives a false impression to the user.</span></span> <span data-ttu-id="6bb1e-137">Microsoft Defender for Endpoint 的實際電池消耗小於裝置上的 [電池設定] 頁面上顯示的數目。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="6bb1e-138">這是以 Microsoft Defender for Endpoint app 所進行的測試為基礎，以瞭解電池消耗。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="6bb1e-139">此外，使用的 VPN 也是本機 VPN，與傳統的 VPN 不同的是，網路流量不會傳送到裝置外。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="6bb1e-140">資料使用量</span><span class="sxs-lookup"><span data-stu-id="6bb1e-140">Data usage</span></span>

<span data-ttu-id="6bb1e-141">Microsoft Defender for Endpoint 會使用本機/回送 VPN，檢查任何惡意網站或連線的網頁流量。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="6bb1e-142">由於這個原因，Apple 帳戶資料使用量對 Microsoft Defender for Endpoint 是不准確的。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="6bb1e-143">Microsoft Defender for Endpoint 的實際資料使用量並不大，且遠遠小於裝置上的資料使用量設定所顯示的內容。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="6bb1e-144">報告不安全的網站</span><span class="sxs-lookup"><span data-stu-id="6bb1e-144">Report unsafe site</span></span>

<span data-ttu-id="6bb1e-145">網路釣魚網站會為了取得您的個人或財務資訊，模仿可信的網站。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="6bb1e-146">就診「 [提供網路保護的意見](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 反應」頁面，以報告可能是仿冒網站的網站。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="6bb1e-147">偵測到惡意網站</span><span class="sxs-lookup"><span data-stu-id="6bb1e-147">Malicious site detected</span></span>

<span data-ttu-id="6bb1e-148">Microsoft Defender for Endpoint 會保護您免受網路釣魚或其他網路型攻擊。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="6bb1e-149">如果偵測到惡意的網站，將會封鎖連線，並會將警示傳送至組織的安全性中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="6bb1e-150">警示包括 connection 的功能變數名稱、遠端 IP 位址和裝置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="6bb1e-151">此外，在 iOS 裝置上會顯示通知。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="6bb1e-152">在通知上敲擊會開啟下列畫面，讓使用者複查詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6bb1e-153">![報告為不安全通知的網站影像](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="6bb1e-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="6bb1e-154">資料和隱私權</span><span class="sxs-lookup"><span data-stu-id="6bb1e-154">Data and Privacy</span></span>

<span data-ttu-id="6bb1e-155">如需收集資料與隱私權的詳細資訊，請參閱 [隱私權資訊-Microsoft Defender For Endpoint on iOS](ios-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="6bb1e-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

