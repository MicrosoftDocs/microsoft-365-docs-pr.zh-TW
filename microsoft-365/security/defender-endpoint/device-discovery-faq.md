---
title: 裝置探索常見問題
description: " (FAQs) 有關裝置探索的常見問題解答，請找出相關的常見問題解答。"
keywords: 裝置探索，探索，被動式，主動，網路，可視性，伺服器，工作站，板載，未受管理的裝置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c61e69b5c8d414ab229fa8bf64eb657a6e40304
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245957"
---
# <a name="device-discovery-frequently-asked-questions"></a><span data-ttu-id="12736-104">裝置探索常見問題</span><span class="sxs-lookup"><span data-stu-id="12736-104">Device discovery frequently asked questions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="12736-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="12736-105">**Applies to:**</span></span>
- [<span data-ttu-id="12736-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="12736-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="12736-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="12736-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="12736-108"> (FAQs) 有關裝置探索的詳細資訊，請找出常見問題的答案。</span><span class="sxs-lookup"><span data-stu-id="12736-108">Find answers to frequently asked questions (FAQs) about device discovery.</span></span>

## <a name="what-is-basic-discovery-mode"></a><span data-ttu-id="12736-109">何謂基本探索模式？</span><span class="sxs-lookup"><span data-stu-id="12736-109">What is Basic discovery mode?</span></span>
<span data-ttu-id="12736-110">這種模式可讓每個 Microsoft Defender for Endpoint 架裝置收集網路資料，並探索鄰居裝置。</span><span class="sxs-lookup"><span data-stu-id="12736-110">This mode allows every Microsoft Defender for Endpoint onboarded device to collect network data and discover neighboring devices.</span></span> <span data-ttu-id="12736-111">架端點會以被動方式收集網路中的事件，並從中抽取裝置資訊。</span><span class="sxs-lookup"><span data-stu-id="12736-111">Onboarded endpoints passively collect events in the network and extract device information from them.</span></span> <span data-ttu-id="12736-112">不會發起任何網路流量。</span><span class="sxs-lookup"><span data-stu-id="12736-112">No network traffic will be initiated.</span></span> <span data-ttu-id="12736-113">架端點只會從架裝置所看到的每個網路流量提取資料。</span><span class="sxs-lookup"><span data-stu-id="12736-113">Onboarded endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> <span data-ttu-id="12736-114">這項資料可用於列出您網路中未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="12736-114">This data used to list unmanaged devices in your network.</span></span>

## <a name="can-i-disable-basic-discovery"></a><span data-ttu-id="12736-115">可否停用基本探索？</span><span class="sxs-lookup"><span data-stu-id="12736-115">Can I disable Basic discovery?</span></span>
<span data-ttu-id="12736-116">您可以選擇透過 [ [高級功能](advanced-features.md) ] 頁面關閉裝置探索。</span><span class="sxs-lookup"><span data-stu-id="12736-116">You have the option to turn off device discovery through the [Advanced features](advanced-features.md) page.</span></span> <span data-ttu-id="12736-117">不過，您的網路中未受管理的裝置會失去可視性。</span><span class="sxs-lookup"><span data-stu-id="12736-117">However, you will lose visibility on unmanaged devices in your network.</span></span> 

## <a name="what-is-standard-discovery-mode"></a><span data-ttu-id="12736-118">何謂 Standard discovery mode？</span><span class="sxs-lookup"><span data-stu-id="12736-118">What is Standard discovery mode?</span></span>
 <span data-ttu-id="12736-119">在此模式中，架至 Microsoft Defender for Endpoint 的端點可以積極探查網路中的觀察裝置，以豐富網路流量) 所收集的資料 (。</span><span class="sxs-lookup"><span data-stu-id="12736-119">In this mode endpoints onboarded to Microsoft Defender for Endpoint can actively probe observed devices in the network to enrich collected data (with negligible amount of network traffic).</span></span> <span data-ttu-id="12736-120">強烈建議使用此模式來建立可靠且連貫的設備清查。</span><span class="sxs-lookup"><span data-stu-id="12736-120">This mode is highly recommended for building a reliable and coherent device inventory.</span></span> <span data-ttu-id="12736-121">如果您選擇停用此模式，並選取 [基本探索] 模式，您的網路中可能只會獲得有限的非受管理端點的可見度。</span><span class="sxs-lookup"><span data-stu-id="12736-121">If you choose to disable this mode, and select Basic discovery mode, you will likely only gain limited visibility of unmanaged endpoints in your network.</span></span>

## <a name="can-i-control-which-devices-perform-standard-discovery"></a><span data-ttu-id="12736-122">我可以控制哪些裝置會執行標準探索？</span><span class="sxs-lookup"><span data-stu-id="12736-122">Can I control which devices perform Standard discovery?</span></span>
 <span data-ttu-id="12736-123">您可以自訂用來執行標準探索的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="12736-123">You can customize the list of devices that are used to perform Standard discovery.</span></span> <span data-ttu-id="12736-124">您可以在所有也支援此功能的架裝置上啟用 Standard discovery， (目前 Windows 10 裝置只) 或透過指定裝置的裝置標籤選取裝置的子集或子集。</span><span class="sxs-lookup"><span data-stu-id="12736-124">You can either enable Standard discovery on all the onboarded devices that also support this capability (currently Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> <span data-ttu-id="12736-125">在此情況下，所有其他裝置將設定為只執行基本探索。</span><span class="sxs-lookup"><span data-stu-id="12736-125">In this case, all other devices will be configured to run Basic discovery only.</span></span> <span data-ttu-id="12736-126">設定可在 [裝置探索設定] 頁面中取得。</span><span class="sxs-lookup"><span data-stu-id="12736-126">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a><span data-ttu-id="12736-127">我是否可以從裝置庫存清單中排除未受管理的裝置？</span><span class="sxs-lookup"><span data-stu-id="12736-127">Can I exclude unmanaged devices from the device inventory list?</span></span>
<span data-ttu-id="12736-128">是的，您可以從裝置庫存清單套用篩選器以排除未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="12736-128">Yes, you can apply filters exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="12736-129">您也可以在 API 查詢上使用 [上架狀態] 欄，以篩選出未受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="12736-129">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 


## <a name="which-onboarded-devices-can-perform-discovery"></a><span data-ttu-id="12736-130">哪些架裝置可以執行探索？</span><span class="sxs-lookup"><span data-stu-id="12736-130">Which onboarded devices can perform discovery?</span></span>
 <span data-ttu-id="12736-131">在 Windows 10 版本1809或更新版本上執行的架裝置可以執行探索。</span><span class="sxs-lookup"><span data-stu-id="12736-131">Onboarded devices running on Windows 10 version 1809 or later can perform discovery.</span></span>

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a><span data-ttu-id="12736-132">如果我的架裝置連線到我的家用網路或公用存取點會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="12736-132">What happens if my onboarded devices is connected to my home network, or to public access point?</span></span>
 <span data-ttu-id="12736-133">探索引擎會區別公司網路中所接收的網路事件與公司網路以外的網路事件。</span><span class="sxs-lookup"><span data-stu-id="12736-133">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="12736-134">透過將網路識別碼關聯到所有租使用者的用戶端，事件會在從私人網路和公司網路接收的事件之間加以區別。</span><span class="sxs-lookup"><span data-stu-id="12736-134">By correlating network identifiers across all tenant's clients, events are differentiated between ones that were received from private networks and corporate networks.</span></span> <span data-ttu-id="12736-135">例如，如果網路中的大部分裝置報告其連線至相同的網路名稱，且其預設閘道和 DHCP 伺服器位址相同，則會假設此網路可能是公司網路。</span><span class="sxs-lookup"><span data-stu-id="12736-135">For example, if the majority of the devices in the network report that they are connected to the same network name, with the same default gateway and DHCP server address, it can be assumed that this network is likely a corporate network.</span></span> <span data-ttu-id="12736-136">私人網路裝置不會列在庫存中，也不會主動加以探測。</span><span class="sxs-lookup"><span data-stu-id="12736-136">Private network devices will not be listed in the inventory and will not be actively probed.</span></span>

## <a name="what-protocols-are-you-capturing-and-analyzing"></a><span data-ttu-id="12736-137">您在捕獲和分析哪些通訊協定？</span><span class="sxs-lookup"><span data-stu-id="12736-137">What protocols are you capturing and analyzing?</span></span>
 <span data-ttu-id="12736-138">根據預設，在 Windows 10 版本1809或更新版本上執行的所有架裝置都是在捕獲和分析下列通訊協定： ARP、CDP、DHCP、DHCPv6、IP (標頭) 、LLDP、LLMNR、mDNS、MNDP、NBNS、SSDP、TCP (標頭) 、UDP (標頭) 、WSD</span><span class="sxs-lookup"><span data-stu-id="12736-138">By default, all onboarded devices running on Windows 10 version 1809 or later are capturing and analyzing the following protocols: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD</span></span>

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a><span data-ttu-id="12736-139">您在 Standard discovery 中用於使用中探測的通訊協定為何？</span><span class="sxs-lookup"><span data-stu-id="12736-139">Which protocols do you use for active probing in Standard discovery?</span></span>
 <span data-ttu-id="12736-140">當裝置設定為執行標準探索時，會使用下列通訊協定來探測公開的服務： ARP、FTP、HTTP、ICMP、LLMNR、NBNS、RDP、SIP、SMTP、SNMP、SSH、Telnet、UPNP、WSD、SMB、NBSS、IPP、PJL</span><span class="sxs-lookup"><span data-stu-id="12736-140">When a device is configured to run Standard discovery, exposed services are being probed by using the following protocols: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL</span></span>

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a><span data-ttu-id="12736-141">如何排除目標，使其不會透過標準探索來探測？</span><span class="sxs-lookup"><span data-stu-id="12736-141">How can I exclude targets from being probed with Standard discovery?</span></span>
 <span data-ttu-id="12736-142">如果您的網路上有不應該主動探測的裝置，您也可以定義排除清單以避免掃描這些裝置。</span><span class="sxs-lookup"><span data-stu-id="12736-142">If there are devices on your network which should not be actively probed, you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="12736-143">設定可在 [裝置探索設定] 頁面中取得。</span><span class="sxs-lookup"><span data-stu-id="12736-143">The configuration is available in the device discovery settings page.</span></span>

## <a name="can-i-exclude-devices-from-being-discovered"></a><span data-ttu-id="12736-144">是否可以排除探索的裝置？</span><span class="sxs-lookup"><span data-stu-id="12736-144">Can I exclude devices from being discovered?</span></span>
 <span data-ttu-id="12736-145">隨著裝置探索使用被動式方法探索網路中的裝置，您可以在庫存中探索與架裝置通訊的任何裝置，並在庫存中列出。</span><span class="sxs-lookup"><span data-stu-id="12736-145">As device discovery uses passive methods to discover devices in the network, any device that communicates with your onboarded devices in the corporate network can be discovered and listed in the inventory.</span></span> <span data-ttu-id="12736-146">您可以只從作用中的探查排除裝置。</span><span class="sxs-lookup"><span data-stu-id="12736-146">You can exclude devices from active probing only.</span></span>

## <a name="how-frequent-is-the-active-probing"></a><span data-ttu-id="12736-147">使用中探查的頻率如何？</span><span class="sxs-lookup"><span data-stu-id="12736-147">How frequent is the active probing?</span></span>
 <span data-ttu-id="12736-148">當顯示裝置特性的變更時，將會主動探測裝置 (每1到3周) 以確定現有的資訊是最新的。</span><span class="sxs-lookup"><span data-stu-id="12736-148">Devices will actively be probed when changes in device characteristics are observed (every 1 to 3 weeks) to make sure the existing information is up-to-date.</span></span>

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a><span data-ttu-id="12736-149">我的安全性工具在其所啟動的 UnicastScanner.ps1 或埠掃描活動上發出警示，我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="12736-149">My security tool raised alert on UnicastScanner.ps1 or port scanning activity initiated by it, what should I do?</span></span>
 <span data-ttu-id="12736-150">使用中的探查腳本是由 Microsoft 簽署且安全的。</span><span class="sxs-lookup"><span data-stu-id="12736-150">The active probing scripts are signed by Microsoft and are safe.</span></span> <span data-ttu-id="12736-151">您可以將下列路徑新增至您的排除清單： `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span><span class="sxs-lookup"><span data-stu-id="12736-151">You can add the following path to your exclusion list: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`</span></span>


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a><span data-ttu-id="12736-152">標準探索使用中探查產生的流量量為何？</span><span class="sxs-lookup"><span data-stu-id="12736-152">What is the amount of traffic being generated by the Standard discovery active probe?</span></span>
 <span data-ttu-id="12736-153">作用中的探查可產生高達架裝置與已探測裝置之間的流量，每次探測嘗試</span><span class="sxs-lookup"><span data-stu-id="12736-153">Active probing can generate up to 5K of traffic between the onboarded device and the probed device, every probing attempt</span></span>

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a><span data-ttu-id="12736-154">為何裝置庫存中的「可以架」裝置有差異，以及儀表板磚中的「裝置到板載」的數目為何？</span><span class="sxs-lookup"><span data-stu-id="12736-154">Why is there a discrepancy between "can be onboarded" devices in the device inventory, and the number of "devices to onboard" in the dashboard tile?</span></span>
<span data-ttu-id="12736-155">您可能注意到裝置清查中的「可以架」的列出裝置數目、「Microsoft Defender for Endpoint」和「裝置上架」儀表板小工具之間的差異。</span><span class="sxs-lookup"><span data-stu-id="12736-155">You may notice differences between the number of listed devices under "can be onboarded" in the device inventory, "onboard to Microsoft Defender for Endpoint" security recommendation, and "devices to onboard" dashboard widget.</span></span>

 <span data-ttu-id="12736-156">安全性建議及儀表板小工具適用于網路上穩定的裝置。不包括短暫裝置、來賓裝置及其他。</span><span class="sxs-lookup"><span data-stu-id="12736-156">The security recommendation and the dashboard widget are for devices that are stable in the network; excluding ephemeral devices, guest devices and others.</span></span> <span data-ttu-id="12736-157">建議在持續性裝置上，這也是指組織的整體安全性分數。</span><span class="sxs-lookup"><span data-stu-id="12736-157">The idea is to recommend on persistent devices, that also imply on the overall security score of the organization.</span></span>

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a><span data-ttu-id="12736-158">是否可以板載找到的受管理裝置？</span><span class="sxs-lookup"><span data-stu-id="12736-158">Can I onboard unmanaged devices that were found?</span></span>
 <span data-ttu-id="12736-159">是。</span><span class="sxs-lookup"><span data-stu-id="12736-159">Yes.</span></span> <span data-ttu-id="12736-160">網路中未受管理的端點會向您的網路引進弱點和風險。</span><span class="sxs-lookup"><span data-stu-id="12736-160">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="12736-161">將其上架至服務可提高安全性。</span><span class="sxs-lookup"><span data-stu-id="12736-161">Onboarding them to the service can increase the security visibility on them.</span></span> 


