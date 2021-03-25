---
title: 設定 Microsoft Defender ATP 部署
description: 瞭解如何設定 Microsoft Defender ATP 的部署
keywords: 部署、安裝、授權驗證、租使用者設定、網路設定
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4af84c21977e4b90c8b6d9ec4c785339ff229e7d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186146"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="e0e06-104">設定 Microsoft Defender for Endpoint 部署</span><span class="sxs-lookup"><span data-stu-id="e0e06-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e0e06-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e0e06-105">**Applies to:**</span></span>
- [<span data-ttu-id="e0e06-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e0e06-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e0e06-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0e06-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e0e06-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e0e06-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e0e06-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="e0e06-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e0e06-110">為端點部署 Defender 是三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="e0e06-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="e0e06-111">[![部署階段-準備](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="e0e06-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="e0e06-112">階段1：準備</span><span class="sxs-lookup"><span data-stu-id="e0e06-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![部署階段-安裝程式](images/phase-diagrams/setup.png)<br><span data-ttu-id="e0e06-114">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="e0e06-114">Phase 2: Setup</span></span> | <span data-ttu-id="e0e06-115">[![部署階段-板載](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="e0e06-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="e0e06-116">階段3：板載</span><span class="sxs-lookup"><span data-stu-id="e0e06-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="e0e06-117">*您在這裡！*</span><span class="sxs-lookup"><span data-stu-id="e0e06-117">*You are here!*</span></span>||

<span data-ttu-id="e0e06-118">您目前在設定階段。</span><span class="sxs-lookup"><span data-stu-id="e0e06-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="e0e06-119">在此部署案例中，您將會逐步指導您執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e0e06-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="e0e06-120">授權驗證</span><span class="sxs-lookup"><span data-stu-id="e0e06-120">Licensing validation</span></span>
- <span data-ttu-id="e0e06-121">租用戶設定</span><span class="sxs-lookup"><span data-stu-id="e0e06-121">Tenant configuration</span></span>
- <span data-ttu-id="e0e06-122">網路設定</span><span class="sxs-lookup"><span data-stu-id="e0e06-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="e0e06-123">為便於您透過一般部署，此案例只會涵蓋 Microsoft 端點 Configuration Manager 的使用。</span><span class="sxs-lookup"><span data-stu-id="e0e06-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e0e06-124">Defender for Endpoint 支援使用其他上架工具，但不會涵蓋部署指南中的那些案例。</span><span class="sxs-lookup"><span data-stu-id="e0e06-124">Defender for Endpoint supports the use of other onboarding tools but will not cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="e0e06-125">如需詳細資訊，請參閱 [在 Microsoft Defender For Endpoint 中的板載裝置](onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e06-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="e0e06-126">檢查授權狀態</span><span class="sxs-lookup"><span data-stu-id="e0e06-126">Check license state</span></span>

<span data-ttu-id="e0e06-127">檢查授權狀態以及是否已正確布建，可透過系統管理中心或 **Microsoft Azure 入口網站** 進行。</span><span class="sxs-lookup"><span data-stu-id="e0e06-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="e0e06-128">若要查看您的授權，請移至 **Microsoft azure 入口網站** ，並流覽至 [microsoft azure 入口網站授權區段](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)。</span><span class="sxs-lookup"><span data-stu-id="e0e06-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Azure 授權頁面影像](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="e0e06-130">或者，在系統管理中心中，流覽至 [**帳單**] [  >  **訂閱**]。</span><span class="sxs-lookup"><span data-stu-id="e0e06-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="e0e06-131">在螢幕上，您會看到所有已布建的授權及其目前的 **狀態**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-131">On the screen, you will see all the provisioned licenses and their current **Status**.</span></span>

    ![計費授權影像](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="e0e06-133">雲端服務提供者驗證</span><span class="sxs-lookup"><span data-stu-id="e0e06-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="e0e06-134">若要存取您公司所提供的授權，以及檢查授權的狀態，請移至系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e0e06-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="e0e06-135">從 **夥伴入口網站** 中，選取 [ **管理服務 > Office 365**]。</span><span class="sxs-lookup"><span data-stu-id="e0e06-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="e0e06-136">按一下 [ **合作夥伴入口網站** ] 連結時，將會自行開啟 [ **管理員** ] 選項，並可讓您存取客戶系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="e0e06-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![O365 管理入口網站的影像](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="e0e06-138">租使用者設定</span><span class="sxs-lookup"><span data-stu-id="e0e06-138">Tenant Configuration</span></span>

<span data-ttu-id="e0e06-139">第一次存取 Microsoft Defender Security Center 時，會有一個嚮導可引導您逐步完成一些初始步驟。</span><span class="sxs-lookup"><span data-stu-id="e0e06-139">When accessing Microsoft Defender Security Center for the first time, a wizard that will guide you through some initial steps.</span></span> <span data-ttu-id="e0e06-140">在安裝程式嚮導結束時，會為建立端點的 Defender 專用雲端實例。</span><span class="sxs-lookup"><span data-stu-id="e0e06-140">At the end of the setup wizard, there will be a dedicated cloud instance of Defender for Endpoint created.</span></span> <span data-ttu-id="e0e06-141">最簡單的方法是從 Windows 10 用戶端裝置執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="e0e06-141">The easiest method is to perform these steps from a Windows 10 client device.</span></span>

1. <span data-ttu-id="e0e06-142">在網頁瀏覽器中，流覽至 <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="e0e06-142">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

    ![設定 Microsoft Defender for Endpoint 的許可權的映射](images/atp-setup-permissions-wdatp-portal.png)

2. <span data-ttu-id="e0e06-144">若要透過試用許可證，請移至連結 (<https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x>) </span><span class="sxs-lookup"><span data-stu-id="e0e06-144">If going through a TRIAL license, go to the link (<https://signup.microsoft.com/Signup?OfferId=6033e4b5-c320-4008-a936-909c2825d83c&dl=WIN_DEF_ATP&pc=xxxxxxx-xxxxxx-xxx-x>)</span></span>

    <span data-ttu-id="e0e06-145">授權步驟完成後，就會顯示 [ **歡迎** ] 畫面。</span><span class="sxs-lookup"><span data-stu-id="e0e06-145">Once the authorization step is completed, the **Welcome** screen will be displayed.</span></span>
3. <span data-ttu-id="e0e06-146">請流覽驗證步驟。</span><span class="sxs-lookup"><span data-stu-id="e0e06-146">Go through the authorization steps.</span></span>

    ![設定入口網站的歡迎畫面影像](images/welcome1.png)

4. <span data-ttu-id="e0e06-148">設定偏好設定。</span><span class="sxs-lookup"><span data-stu-id="e0e06-148">Set up preferences.</span></span>

   <span data-ttu-id="e0e06-149">**資料儲存位置** -請務必正確設定。</span><span class="sxs-lookup"><span data-stu-id="e0e06-149">**Data storage location** - It's important to set this up correctly.</span></span> <span data-ttu-id="e0e06-150">決定客戶想要主要寄存的位置：美國、歐盟或 UK。</span><span class="sxs-lookup"><span data-stu-id="e0e06-150">Determine where the customer wants to be primarily hosted: US, EU, or UK.</span></span> <span data-ttu-id="e0e06-151">您無法變更此設定之後的位置，Microsoft 也不會從指定的地理位置傳輸資料。</span><span class="sxs-lookup"><span data-stu-id="e0e06-151">You cannot change the location after this set up and Microsoft will not transfer the data from the specified geolocation.</span></span> 

    <span data-ttu-id="e0e06-152">**資料保留** -預設值為六個月。</span><span class="sxs-lookup"><span data-stu-id="e0e06-152">**Data retention** - The default is six months.</span></span>

    <span data-ttu-id="e0e06-153">**啟用預覽功能** -預設值為 on，以後可以變更。</span><span class="sxs-lookup"><span data-stu-id="e0e06-153">**Enable preview features** - The default is on, can be changed later.</span></span>

    ![設定中的地理位置影像](images/setup-preferences.png)

5. <span data-ttu-id="e0e06-155">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="e0e06-155">Select **Next**.</span></span>

     ![最終喜好設定的影像](images/setup-preferences2.png)

6. <span data-ttu-id="e0e06-157">選取 [ **繼續**]。</span><span class="sxs-lookup"><span data-stu-id="e0e06-157">Select **Continue**.</span></span>


## <a name="network-configuration"></a><span data-ttu-id="e0e06-158">網路設定</span><span class="sxs-lookup"><span data-stu-id="e0e06-158">Network configuration</span></span>
<span data-ttu-id="e0e06-159">如果組織不需要端點使用 Proxy 來存取網際網路，請略過本節。</span><span class="sxs-lookup"><span data-stu-id="e0e06-159">If the organization does not require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="e0e06-160">適用於端點的 Microsoft Defender 感應器需要 Microsoft Windows HTTP (WinHTTP) 回報感應器資料，並與適用於端點的 Microsoft Defender 服務通訊。</span><span class="sxs-lookup"><span data-stu-id="e0e06-160">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="e0e06-161">內嵌的 Microsoft Defender for Endpoint 感應器會在使用 LocalSystem 帳戶的系統上下文中執行。</span><span class="sxs-lookup"><span data-stu-id="e0e06-161">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="e0e06-162">感應器使用 Microsoft Windows HTTP Services （WinHTTP）來啟用與適用於端點的 Microsoft Defender 雲端服務的通訊。</span><span class="sxs-lookup"><span data-stu-id="e0e06-162">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="e0e06-163">WinHTTP 設定設定與 Windows Internet (WinINet) Internet 流覽 proxy 設定無關，而且只能使用下列探索方法來探索 proxy 伺服器：</span><span class="sxs-lookup"><span data-stu-id="e0e06-163">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="e0e06-164">**自動探索方法：**</span><span class="sxs-lookup"><span data-stu-id="e0e06-164">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="e0e06-165">透明Proxy</span><span class="sxs-lookup"><span data-stu-id="e0e06-165">Transparent proxy</span></span>

-   <span data-ttu-id="e0e06-166">Web Proxy 自動探索通訊協定 (WPAD) </span><span class="sxs-lookup"><span data-stu-id="e0e06-166">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="e0e06-167">如果已在網路拓撲中執行透明 proxy 或 WPAD，則不需要特殊的設定。</span><span class="sxs-lookup"><span data-stu-id="e0e06-167">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="e0e06-168">如需 proxy 中 Microsoft Defender for Endpoint URL 排除專案的詳細資訊，請參閱本檔中的「附錄」區段中的 URLs 允許清單或 [Microsoft](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-proxy-internet-windows-defender-advanced-threat-protection#enable-access-to-windows-defender-atp-service-urls-in-the-proxy-server)檔。</span><span class="sxs-lookup"><span data-stu-id="e0e06-168">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the Appendix section in this document for the URLs allow list or on [Microsoft Docs](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-proxy-internet-windows-defender-advanced-threat-protection#enable-access-to-windows-defender-atp-service-urls-in-the-proxy-server).</span></span>

> [!NOTE]
> <span data-ttu-id="e0e06-169">如需需要允許的 URLs 詳細清單，請參閱 [本文](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="e0e06-169">For a detailed list of URLs that need to be allowed, please see [this article](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="e0e06-170">**手動靜態 Proxy 組態：**</span><span class="sxs-lookup"><span data-stu-id="e0e06-170">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="e0e06-171">以登錄為基礎的設定</span><span class="sxs-lookup"><span data-stu-id="e0e06-171">Registry-based configuration</span></span>

-   <span data-ttu-id="e0e06-172">使用 netsh 命令設定 WinHTTP</span><span class="sxs-lookup"><span data-stu-id="e0e06-172">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="e0e06-173">僅適用于穩定拓撲中的桌上型電腦 (例如，公司網路中位於相同 proxy 的桌面) </span><span class="sxs-lookup"><span data-stu-id="e0e06-173">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="e0e06-174">使用基於登錄的靜態 Proxy 手動設定 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="e0e06-174">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="e0e06-175">設定登錄型靜態 proxy，只允許 Microsoft Defender for Endpoint 感應器報告診斷資料，並在電腦不允許連線至網際網路時，與 Microsoft Defender for Endpoint service 通訊。</span><span class="sxs-lookup"><span data-stu-id="e0e06-175">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer is not permitted to connect to the Internet.</span></span> <span data-ttu-id="e0e06-176">靜態 Proxy 可以透過群組原則 (GP) 設定。</span><span class="sxs-lookup"><span data-stu-id="e0e06-176">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="e0e06-177">可以在以下位置找到群組原則：</span><span class="sxs-lookup"><span data-stu-id="e0e06-177">The group policy can be found under:</span></span>

 - <span data-ttu-id="e0e06-178">系統管理範本 \> Windows 元件 \> 資料收集和預覽組建 \> 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用方式</span><span class="sxs-lookup"><span data-stu-id="e0e06-178">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="e0e06-179">設定為 **啟用** ，並選取 [ **停用已驗證的 Proxy 使用**</span><span class="sxs-lookup"><span data-stu-id="e0e06-179">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="e0e06-180">開啟 [群組原則管理主控台]。</span><span class="sxs-lookup"><span data-stu-id="e0e06-180">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="e0e06-181">建立原則，或根據組織的作法來編輯現有的原則。</span><span class="sxs-lookup"><span data-stu-id="e0e06-181">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="e0e06-182">編輯群組原則並流覽至 [系統 **管理範本] \> Windows 元件 \> 資料收集和預覽組建 \> 設定連線使用者經驗和遙測服務的已驗證 Proxy 使用方式**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-182">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="e0e06-183">![群組原則設定的影像](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="e0e06-183">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="e0e06-184">選取 **已啟用**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-184">Select **Enabled**.</span></span>
5. <span data-ttu-id="e0e06-185">選取 [ **停用已驗證的 Proxy 使用**]。</span><span class="sxs-lookup"><span data-stu-id="e0e06-185">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="e0e06-186">流覽至系統 **管理範本 \> Windows 元件 \> 資料收集和預覽組建 \> 設定連線使用者經驗和遙測**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-186">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="e0e06-187">![群組原則設定設定的影像](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="e0e06-187">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="e0e06-188">選取 **已啟用**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-188">Select **Enabled**.</span></span>
8. <span data-ttu-id="e0e06-189">輸入 **Proxy 伺服器名稱**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-189">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="e0e06-190">原則將登錄機碼 `HKLM\Software\Policies\Microsoft\Windows\DataCollection` 下的兩個登錄值 `TelemetryProxyServer` 設定為 REG\u SZ，`DisableEnterpriseAuthProxy` 設定為 REG\u DWORD。</span><span class="sxs-lookup"><span data-stu-id="e0e06-190">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="e0e06-191">登錄值 `TelemetryProxyServer` 採用下列字串格式：</span><span class="sxs-lookup"><span data-stu-id="e0e06-191">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="e0e06-192">例如：10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="e0e06-192">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="e0e06-193">此登錄值 `DisableEnterpriseAuthProxy` 應當設定為 1。</span><span class="sxs-lookup"><span data-stu-id="e0e06-193">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="e0e06-194">使用 netsh 命令手動設定 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="e0e06-194">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="e0e06-195">使用 netsh 設定全系統的靜態 Proxy。</span><span class="sxs-lookup"><span data-stu-id="e0e06-195">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="e0e06-196">這將影響所有應用程式，包括使用帶預設 Proxy 之 WinHTTP 的 Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="e0e06-196">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="e0e06-197">變更拓撲的膝上型電腦 (例如：從 office 到 home) ，將無法使用 netsh。</span><span class="sxs-lookup"><span data-stu-id="e0e06-197">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="e0e06-198">使用基於登錄的靜態 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="e0e06-198">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="e0e06-199">開啟已提升許可權的命令列：</span><span class="sxs-lookup"><span data-stu-id="e0e06-199">Open an elevated command line:</span></span>

    1. <span data-ttu-id="e0e06-200">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-200">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="e0e06-201">以滑鼠右鍵按一下 **[命令提示字元]**，然後選取 **[以系統管理員身分執行]**。</span><span class="sxs-lookup"><span data-stu-id="e0e06-201">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="e0e06-202">輸入以下命令，再按 **Enter**：</span><span class="sxs-lookup"><span data-stu-id="e0e06-202">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="e0e06-203">例如：netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="e0e06-203">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="e0e06-204">底層裝置的 Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="e0e06-204">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="e0e06-205">Down-Level 裝置包含 windows 7 SP1 和 Windows 8.1 工作站，以及 windows server CB 2016 之前的 windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2 和 Windows Server 1803 版本。</span><span class="sxs-lookup"><span data-stu-id="e0e06-205">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="e0e06-206">這些作業系統會將 proxy 設定為 Microsoft Management Agent 的一部分，以處理從端點到 Azure 的通訊。</span><span class="sxs-lookup"><span data-stu-id="e0e06-206">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="e0e06-207">如需如何在這些裝置上設定 proxy 的詳細資訊，請參閱《 Microsoft Management Agent Fast Deployment 指南》。</span><span class="sxs-lookup"><span data-stu-id="e0e06-207">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="e0e06-208">Proxy 服務 URLs</span><span class="sxs-lookup"><span data-stu-id="e0e06-208">Proxy Service URLs</span></span>
<span data-ttu-id="e0e06-209">只有在您有 Windows 10、版本1803或更新版本的裝置時，才需要在其中包含 v20 的 URLs。</span><span class="sxs-lookup"><span data-stu-id="e0e06-209">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="e0e06-210">例如， ```us-v20.events.data.microsoft.com``` 只有當裝置在 Windows 10，版本1803或更新版本上時才需要。</span><span class="sxs-lookup"><span data-stu-id="e0e06-210">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="e0e06-211">如果 proxy 或防火牆封鎖匿名流量，當 Microsoft Defender for Endpoint 感應器從系統內容連線時，請確定所列的 URLs 允許匿名流量。</span><span class="sxs-lookup"><span data-stu-id="e0e06-211">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="e0e06-212">下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。</span><span class="sxs-lookup"><span data-stu-id="e0e06-212">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="e0e06-213">確定沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權，否則您可能需要建立專用的 *allow* 規則。</span><span class="sxs-lookup"><span data-stu-id="e0e06-213">Ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="e0e06-214">**網域清單的試算表**</span><span class="sxs-lookup"><span data-stu-id="e0e06-214">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="e0e06-215">**描述**</span><span class="sxs-lookup"><span data-stu-id="e0e06-215">**Description**</span></span>|
|:-----|:-----|
|![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/>  | <span data-ttu-id="e0e06-217">服務位置、地理位置和作業系統的特定 DNS 記錄試算表。</span><span class="sxs-lookup"><span data-stu-id="e0e06-217">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="e0e06-218">在這裡下載試算表。</span><span class="sxs-lookup"><span data-stu-id="e0e06-218">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-range"></a><span data-ttu-id="e0e06-219">Microsoft Defender for Endpoint service 後端 IP 範圍</span><span class="sxs-lookup"><span data-stu-id="e0e06-219">Microsoft Defender for Endpoint service backend IP range</span></span>

<span data-ttu-id="e0e06-220">如果網路裝置不支援上一節所列的 URLs，您可以使用下列資訊。</span><span class="sxs-lookup"><span data-stu-id="e0e06-220">If you network devices don't support the URLs listed in the prior section, you can use the following information.</span></span>

<span data-ttu-id="e0e06-221">在 Azure cloud 上建立端點的 Defender，部署于下列地區：</span><span class="sxs-lookup"><span data-stu-id="e0e06-221">Defender for Endpoint is built on Azure cloud, deployed in the following regions:</span></span>

- \+\<Region Name="uswestcentral">
- \+\<Region Name="useast2">
- \+\<Region Name="useast">
- \+\<Region Name="europenorth">
- \+\<Region Name="europewest">
- \+\<Region Name="uksouth">
- \+\<Region Name="ukwest">

<span data-ttu-id="e0e06-222">您可以在 [Microsoft Azure 資料中心 IP 範圍](https://www.microsoft.com/en-us/download/details.aspx?id=41653)上找到 Azure IP 範圍。</span><span class="sxs-lookup"><span data-stu-id="e0e06-222">You can find the Azure IP range on [Microsoft Azure Datacenter IP Ranges](https://www.microsoft.com/en-us/download/details.aspx?id=41653).</span></span>

> [!NOTE]
> <span data-ttu-id="e0e06-223">作為雲端式解決方案，IP 位址範圍可能會變更。</span><span class="sxs-lookup"><span data-stu-id="e0e06-223">As a cloud-based solution, the IP address range can change.</span></span> <span data-ttu-id="e0e06-224">建議您移至 DNS 解析設定。</span><span class="sxs-lookup"><span data-stu-id="e0e06-224">It's recommended you move to DNS resolving setting.</span></span>

## <a name="next-step"></a><span data-ttu-id="e0e06-225">下一步</span><span class="sxs-lookup"><span data-stu-id="e0e06-225">Next step</span></span>

<span data-ttu-id="e0e06-226">![* * 階段3：板載 * *](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="e0e06-226">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="e0e06-227">[階段3：板載](onboarding.md)：對服務的板載裝置，使 Microsoft Defender for Endpoint service 可以從這些裝置取得感應器資料。</span><span class="sxs-lookup"><span data-stu-id="e0e06-227">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
