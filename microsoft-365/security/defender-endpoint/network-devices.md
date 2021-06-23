---
title: 網路裝置探索和弱點管理
description: 現在，安全性建議和弱點偵測可供交換器、路由器、WLAN 控制器及防火牆的作業系統使用。
keywords: 網路裝置、網路裝置弱點偵測、交換器的作業系統、路由器、WLAN 控制器及防火牆
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 86b8a37fd6b2d6f9906321b5d74de0e21c45fca3
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062138"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="e472d-104">網路裝置探索和弱點管理</span><span class="sxs-lookup"><span data-stu-id="e472d-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e472d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e472d-105">**Applies to:**</span></span>

- [<span data-ttu-id="e472d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e472d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e472d-107">威脅及弱點管理</span><span class="sxs-lookup"><span data-stu-id="e472d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="e472d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e472d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e472d-109">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="e472d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e472d-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e472d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="e472d-111">「 [網路設備探索」和「安全性漏洞評估](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) 」博客 \( 發佈 \) 的04-13-2021 可深入瞭解如何在適用于 Endpoint 的 Defender 中進行新的 **網路設備探索** 功能。</span><span class="sxs-lookup"><span data-stu-id="e472d-111">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="e472d-112">本文提供 **網路裝置探索** 的設計目的問題，以及如何開始使用這些新功能的詳細資訊的概述。</span><span class="sxs-lookup"><span data-stu-id="e472d-112">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="e472d-113">網路探索功能可在「Microsoft 365 安全性中心」和「Microsoft Defender 資訊安全中心主控台」的 [**裝置庫存**] 區段中取得。</span><span class="sxs-lookup"><span data-stu-id="e472d-113">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="e472d-114">會在每個網段上使用指定的 Microsoft Defender for Endpoint 裝置，對預先設定的網路裝置執行定期驗證掃描。</span><span class="sxs-lookup"><span data-stu-id="e472d-114">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="e472d-115">一旦探索，Defender 的威脅與弱點管理功能會提供整合式工作流程，以保護探索到的交換器、路由器、WLAN 控制器、防火牆和 VPN 閘道。</span><span class="sxs-lookup"><span data-stu-id="e472d-115">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="e472d-116">一旦發現網路裝置並分類，安全性系統管理員就能接收最新的安全性建議，並在其組織中的網路裝置上回顧最近發現的漏洞。</span><span class="sxs-lookup"><span data-stu-id="e472d-116">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="e472d-117">方法</span><span class="sxs-lookup"><span data-stu-id="e472d-117">Approach</span></span>

<span data-ttu-id="e472d-118">由於 Endpoint 的 Defender 沒有內置於網路裝置中的感應器，因此不會將網路裝置當作標準端點進行管理。</span><span class="sxs-lookup"><span data-stu-id="e472d-118">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="e472d-119">這些類型的裝置需要一種無代理的方式，遠端掃描會從裝置取得所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="e472d-119">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="e472d-120">根據網路拓撲及特性，架至 Microsoft Defender for Endpoint 的單一裝置或少數裝置會使用 SNMP (唯讀) 來執行網路裝置的驗證掃描。</span><span class="sxs-lookup"><span data-stu-id="e472d-120">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="e472d-121">有兩種類型的裝置需要謹記：</span><span class="sxs-lookup"><span data-stu-id="e472d-121">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="e472d-122">**評估裝置**：已架的裝置，可供您用來掃描網路裝置。</span><span class="sxs-lookup"><span data-stu-id="e472d-122">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="e472d-123">**網路裝置**：您要掃描和上架的網路裝置。</span><span class="sxs-lookup"><span data-stu-id="e472d-123">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="e472d-124">網路裝置的弱點管理</span><span class="sxs-lookup"><span data-stu-id="e472d-124">Vulnerability management for network devices</span></span> 

<span data-ttu-id="e472d-125">一旦發現網路裝置並分類，安全性系統管理員就能接收最新的安全性建議，並在其組織中的網路裝置上回顧最近發現的漏洞。</span><span class="sxs-lookup"><span data-stu-id="e472d-125">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="e472d-126">支援的作業系統</span><span class="sxs-lookup"><span data-stu-id="e472d-126">Operating systems that are supported</span></span>

<span data-ttu-id="e472d-127">目前支援下列作業系統：</span><span class="sxs-lookup"><span data-stu-id="e472d-127">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="e472d-128">Cisco IOS，IOS-XE，NX-OS</span><span class="sxs-lookup"><span data-stu-id="e472d-128">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="e472d-129">刺柏 JUNOS</span><span class="sxs-lookup"><span data-stu-id="e472d-129">Juniper JUNOS</span></span>
- <span data-ttu-id="e472d-130">HPE ArubaOS，Procurve 切換軟體</span><span class="sxs-lookup"><span data-stu-id="e472d-130">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="e472d-131">Palo Alto 網路 PAN-OS</span><span class="sxs-lookup"><span data-stu-id="e472d-131">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="e472d-132">更多的網路廠商和作業系統會隨著時間而新增，根據客戶的使用量收集的資料而定。</span><span class="sxs-lookup"><span data-stu-id="e472d-132">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="e472d-133">因此，您建議您設定所有網路裝置，即使這些裝置未在此清單中指定也是一樣。</span><span class="sxs-lookup"><span data-stu-id="e472d-133">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="e472d-134">如何開始使用</span><span class="sxs-lookup"><span data-stu-id="e472d-134">How to get started</span></span>

<span data-ttu-id="e472d-135">第一步是選取將執行已驗證網路掃描的裝置。</span><span class="sxs-lookup"><span data-stu-id="e472d-135">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="e472d-136">決定架裝置的 Defender for Endpoint 裝置 (用戶端或伺服器) ，其具有您規劃掃描之網路裝置的網路連線。</span><span class="sxs-lookup"><span data-stu-id="e472d-136">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="e472d-137">在端點評估裝置和目標網路裝置之間的 SNMP 流量必須 (例如，由防火牆) 使用。</span><span class="sxs-lookup"><span data-stu-id="e472d-137">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="e472d-138">決定要評估哪些網路裝置以取得漏洞 (例如： Cisco 交換器或 Palo Alto 網路防火牆) 。</span><span class="sxs-lookup"><span data-stu-id="e472d-138">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="e472d-139">確定所有設定之網路裝置上都已啟用 SNMP 唯讀功能，以允許 Endpoint Endpoint 評估裝置查詢已設定的網路裝置。</span><span class="sxs-lookup"><span data-stu-id="e472d-139">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="e472d-140">這項功能的適當功能不需要「SNMP 寫入」。</span><span class="sxs-lookup"><span data-stu-id="e472d-140">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="e472d-141">取得要掃描之網路裝置的 IP 位址 (或) 部署這些裝置的子網。</span><span class="sxs-lookup"><span data-stu-id="e472d-141">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="e472d-142">取得網路裝置的 SNMP 認證 (例如： Community String、noAuthNoPriv、authNoPriv、authPriv) 。</span><span class="sxs-lookup"><span data-stu-id="e472d-142">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="e472d-143">設定新的評估工作時，您必須提供認證。</span><span class="sxs-lookup"><span data-stu-id="e472d-143">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="e472d-144">Proxy 用戶端設定：除了 Defender for Endpoint 裝置 proxy 需求以外，不需要額外的設定。</span><span class="sxs-lookup"><span data-stu-id="e472d-144">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="e472d-145">若要允許網路掃描器驗證並正確運作，您必須新增下列網域/URLs：</span><span class="sxs-lookup"><span data-stu-id="e472d-145">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="e472d-146">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="e472d-146">login.windows.net</span></span>  
    - <span data-ttu-id="e472d-147">securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="e472d-147">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="e472d-148">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="e472d-148">login.microsoftonline.com</span></span>
    - <span data-ttu-id="e472d-149">\* blob.core.windows.net/networkscannerstable/\*</span><span class="sxs-lookup"><span data-stu-id="e472d-149">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="e472d-150">並非所有 URLs 都已在已記錄的 Endpoint 中指定允許的資料收集的清單。</span><span class="sxs-lookup"><span data-stu-id="e472d-150">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="e472d-151">權限</span><span class="sxs-lookup"><span data-stu-id="e472d-151">Permissions</span></span>

<span data-ttu-id="e472d-152">若要設定評估工作，需要下列使用者許可權選項： **管理安全性中心的安全性設定**。</span><span class="sxs-lookup"><span data-stu-id="e472d-152">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="e472d-153">您可以移至 **設定** 角色，以尋找許可權  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e472d-153">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="e472d-154">如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e472d-154">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="e472d-155">安裝網路掃描程式</span><span class="sxs-lookup"><span data-stu-id="e472d-155">Install the network scanner</span></span>

1. <span data-ttu-id="e472d-156">移至 **Microsoft 365 security**  >  **設定**  >    >  (**網路評估**) 的端點 **評估工作**。</span><span class="sxs-lookup"><span data-stu-id="e472d-156">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="e472d-157">在 Microsoft Defender 資訊安全中心中，移至設定 > 評估工作] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e472d-157">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="e472d-158">下載網路掃描程式，並將其安裝在「指定的 Defender for Endpoint 評估」裝置上。</span><span class="sxs-lookup"><span data-stu-id="e472d-158">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="e472d-159">![下載掃描器按鈕](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="e472d-159">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="e472d-160">網路掃描器安裝 & 註冊</span><span class="sxs-lookup"><span data-stu-id="e472d-160">Network scanner installation & registration</span></span>

<span data-ttu-id="e472d-161">您可以在指定的評估裝置自身或任何其他裝置上完成登入程式，例如，您的個人用戶端裝置)  (。</span><span class="sxs-lookup"><span data-stu-id="e472d-161">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="e472d-162">若要完成網路掃描程式註冊程式：</span><span class="sxs-lookup"><span data-stu-id="e472d-162">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="e472d-163">複製並追蹤出現在命令列上的 URL，並使用提供的安裝程式碼完成註冊程式。</span><span class="sxs-lookup"><span data-stu-id="e472d-163">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e472d-164">您可能需要變更命令提示字元設定，才能複製 URL。</span><span class="sxs-lookup"><span data-stu-id="e472d-164">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="e472d-165">使用「管理安全性中心的安全性設定」許可權的 Microsoft 帳戶輸入程式碼並登入。</span><span class="sxs-lookup"><span data-stu-id="e472d-165">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="e472d-166">完成後，您應該會看到一則確認已登入的郵件。</span><span class="sxs-lookup"><span data-stu-id="e472d-166">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="e472d-167">設定新的評估工作</span><span class="sxs-lookup"><span data-stu-id="e472d-167">Configure a new assessment job</span></span>  

<span data-ttu-id="e472d-168">在 **設定** 的 [評估工作] 頁面中，選取 [**新增網路評估工作**]。</span><span class="sxs-lookup"><span data-stu-id="e472d-168">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="e472d-169">依照設定程式選擇要定期掃描的網路裝置，並將其新增至設備清查。</span><span class="sxs-lookup"><span data-stu-id="e472d-169">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="e472d-170">若要防止網路設備清查中的裝置重複，請確定每個 IP 位址在多個評估裝置中只設定一次。</span><span class="sxs-lookup"><span data-stu-id="e472d-170">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e472d-171">![新增網路評估工作按鈕](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="e472d-171">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="e472d-172">新增網路評估工作步驟：</span><span class="sxs-lookup"><span data-stu-id="e472d-172">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="e472d-173">選擇「評估工作」名稱和安裝網路掃描器的「評估裝置」。</span><span class="sxs-lookup"><span data-stu-id="e472d-173">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="e472d-174">此裝置會執行定期驗證掃描。</span><span class="sxs-lookup"><span data-stu-id="e472d-174">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="e472d-175">新增要掃描的目標網路裝置的 IP 位址 (或) 部署這些裝置的子網。</span><span class="sxs-lookup"><span data-stu-id="e472d-175">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="e472d-176">新增目標網路裝置所需的 SNMP 認證。</span><span class="sxs-lookup"><span data-stu-id="e472d-176">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="e472d-177">儲存新設定的網路評估工作，以啟動定期網路掃描。</span><span class="sxs-lookup"><span data-stu-id="e472d-177">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="e472d-178">掃描及新增網路裝置</span><span class="sxs-lookup"><span data-stu-id="e472d-178">Scan and add network devices</span></span>

<span data-ttu-id="e472d-179">在設定過程中，您可以執行一次測試掃描，以確認：</span><span class="sxs-lookup"><span data-stu-id="e472d-179">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="e472d-180">在端點評估裝置和設定的目標網路裝置之間，有連線能力。</span><span class="sxs-lookup"><span data-stu-id="e472d-180">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="e472d-181">設定的 SNMP 認證正確無誤。</span><span class="sxs-lookup"><span data-stu-id="e472d-181">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="e472d-182">每個評估裝置可支援最多1500個成功的 IP 位址掃描。</span><span class="sxs-lookup"><span data-stu-id="e472d-182">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="e472d-183">例如，如果您掃描10個不同的子網，其中只有 100 IP 位址會傳回成功的結果，您就可以從相同評估裝置上的其他子網掃描 1400 IP 其他位址。</span><span class="sxs-lookup"><span data-stu-id="e472d-183">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="e472d-184">如果有多個 IP 位址範圍/子網可供掃描，測試掃描結果將需要數分鐘的時間才能顯示。</span><span class="sxs-lookup"><span data-stu-id="e472d-184">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="e472d-185">測試掃描可用於最多1024個位址。</span><span class="sxs-lookup"><span data-stu-id="e472d-185">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="e472d-186">結果顯示後，您可以選擇要包含在定期掃描中的裝置。</span><span class="sxs-lookup"><span data-stu-id="e472d-186">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="e472d-187">如果您略過查看掃描結果，不論裝置的回應) 為何，所有設定的 IP 位址都會新增至網路評估工作 (。</span><span class="sxs-lookup"><span data-stu-id="e472d-187">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="e472d-188">也可以匯出掃描結果。</span><span class="sxs-lookup"><span data-stu-id="e472d-188">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="e472d-189">裝置清單</span><span class="sxs-lookup"><span data-stu-id="e472d-189">Device inventory</span></span>

<span data-ttu-id="e472d-190">新發現的裝置會顯示在 [**裝置庫存**] 頁面的 [新增 **網路裝置**] 索引標籤底下。</span><span class="sxs-lookup"><span data-stu-id="e472d-190">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="e472d-191">在新增評估工作之前，可能需要長達兩小時，直到裝置更新為止。</span><span class="sxs-lookup"><span data-stu-id="e472d-191">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e472d-192">![裝置庫存中的 [網路裝置] 區段](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="e472d-192">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e472d-193">疑難排解</span><span class="sxs-lookup"><span data-stu-id="e472d-193">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="e472d-194">網路掃描器安裝失敗</span><span class="sxs-lookup"><span data-stu-id="e472d-194">Network scanner installation has failed</span></span>

<span data-ttu-id="e472d-195">確認所需的 URLs 已新增至防火牆設定中的允許網域。</span><span class="sxs-lookup"><span data-stu-id="e472d-195">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="e472d-196">此外，請確定已依照 [設定裝置 proxy 和網際網路連線設定](configure-proxy-internet.md)中所述的方式來設定 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="e472d-196">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="e472d-197">未顯示 Microsoft.com/devicelogin 網頁</span><span class="sxs-lookup"><span data-stu-id="e472d-197">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="e472d-198">確認所需的 URLs 已新增至防火牆中的允許網域。</span><span class="sxs-lookup"><span data-stu-id="e472d-198">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="e472d-199">此外，請確定已依照 [設定裝置 proxy 和網際網路連線設定](configure-proxy-internet.md)中所述的方式來設定 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="e472d-199">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="e472d-200">在幾個小時後，網路裝置不會顯示在設備清查中</span><span class="sxs-lookup"><span data-stu-id="e472d-200">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="e472d-201">在完成評估工作設定之後所發生的初始掃描後，應在幾小時之後更新掃描結果。</span><span class="sxs-lookup"><span data-stu-id="e472d-201">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="e472d-202">如果仍未顯示裝置，請確認服務 ' MdatpNetworkScanService ' 已在您安裝網路掃描程式的評估裝置上執行，並在相關的評估工作設定中執行「執行掃描」。</span><span class="sxs-lookup"><span data-stu-id="e472d-202">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="e472d-203">如果5分鐘之後仍未取得結果，請重新開機服務。</span><span class="sxs-lookup"><span data-stu-id="e472d-203">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="e472d-204">裝置上次看到時間超過24小時</span><span class="sxs-lookup"><span data-stu-id="e472d-204">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="e472d-205">驗證掃描器是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="e472d-205">Validate that the scanner is running properly.</span></span> <span data-ttu-id="e472d-206">然後移至 [掃描定義]，然後選取 [執行測試]。</span><span class="sxs-lookup"><span data-stu-id="e472d-206">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="e472d-207">檢查相關 IP 位址傳回的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="e472d-207">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="e472d-208">必要威脅與弱點管理使用者許可權</span><span class="sxs-lookup"><span data-stu-id="e472d-208">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="e472d-209">註冊完成時出現錯誤：「似乎您沒有足夠的許可權可以新增代理程式。</span><span class="sxs-lookup"><span data-stu-id="e472d-209">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="e472d-210">必要的許可權是「管理安全性中心的安全性設定」。</span><span class="sxs-lookup"><span data-stu-id="e472d-210">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="e472d-211">按任意鍵退出。</span><span class="sxs-lookup"><span data-stu-id="e472d-211">Press any key to exit.</span></span>

<span data-ttu-id="e472d-212">請系統管理員為您指派必要的許可權。</span><span class="sxs-lookup"><span data-stu-id="e472d-212">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="e472d-213">或者，您可以透過提供登入程式碼和連結，讓另一個相關成員協助您進行登入處理常式。</span><span class="sxs-lookup"><span data-stu-id="e472d-213">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="e472d-214">註冊程式在註冊程式的命令列中使用提供的連結失敗</span><span class="sxs-lookup"><span data-stu-id="e472d-214">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="e472d-215">嘗試其他瀏覽器或將登入連結和程式碼複製到不同的裝置。</span><span class="sxs-lookup"><span data-stu-id="e472d-215">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="e472d-216">文字太小或無法從命令列複製文字</span><span class="sxs-lookup"><span data-stu-id="e472d-216">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="e472d-217">變更裝置上的命令列設定，以允許複製及變更文字大小。</span><span class="sxs-lookup"><span data-stu-id="e472d-217">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e472d-218">相關文章</span><span class="sxs-lookup"><span data-stu-id="e472d-218">Related articles</span></span>

- [<span data-ttu-id="e472d-219">裝置清單</span><span class="sxs-lookup"><span data-stu-id="e472d-219">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="e472d-220">設定進階功能</span><span class="sxs-lookup"><span data-stu-id="e472d-220">Configure advanced features</span></span>](advanced-features.md)
