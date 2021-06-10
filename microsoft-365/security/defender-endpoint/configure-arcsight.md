---
title: 設定微焦點 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測
description: 設定從 Microsoft Defender 資訊安全中心接收及提取偵測的微焦點 ArcSight
keywords: 設定微焦點 ArcSight、安全性資訊和事件管理工具、ArcSight
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
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166182"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="32fca-104">設定微焦點 ArcSight 以拉入 Defender for Endpoint 偵測</span><span class="sxs-lookup"><span data-stu-id="32fca-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="32fca-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="32fca-105">**Applies to:**</span></span>
- [<span data-ttu-id="32fca-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="32fca-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="32fca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32fca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="32fca-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="32fca-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="32fca-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="32fca-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="32fca-110">您將需要安裝及設定部分檔案和工具，以使用微型焦點 ArcSight，以便讓其能夠拉入 Defender 以進行端點偵測。</span><span class="sxs-lookup"><span data-stu-id="32fca-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="32fca-111">從一或多個偵測中組成[的 Defender For Endpoint Alert](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="32fca-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="32fca-112">[Endpoint 偵測的 Defender](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。</span><span class="sxs-lookup"><span data-stu-id="32fca-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="32fca-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="32fca-113">Before you begin</span></span>

<span data-ttu-id="32fca-114">設定微型聚焦 ArcSight Connector 工具需要數個設定檔，才能從您的 Azure Active Directory (AAD) 應用程式中拉入和分析偵測。</span><span class="sxs-lookup"><span data-stu-id="32fca-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="32fca-115">本節會引導您取得正確設定及使用必要設定檔的必要資訊。</span><span class="sxs-lookup"><span data-stu-id="32fca-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="32fca-116">請確認您已從 **設定** 功能表啟用 SIEM 整合功能。</span><span class="sxs-lookup"><span data-stu-id="32fca-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="32fca-117">如需詳細資訊，請參閱 [ENABLE SIEM integration In Defender For Endpoint](enable-siem-integration.md)。</span><span class="sxs-lookup"><span data-stu-id="32fca-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="32fca-118">讓您儲存的檔案啟用 SIEM 整合功能。</span><span class="sxs-lookup"><span data-stu-id="32fca-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="32fca-119">您必須取得下列值：</span><span class="sxs-lookup"><span data-stu-id="32fca-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="32fca-120">OAuth 2.0 Token 重新整理 URL</span><span class="sxs-lookup"><span data-stu-id="32fca-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="32fca-121">OAuth 2.0 用戶端識別碼</span><span class="sxs-lookup"><span data-stu-id="32fca-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="32fca-122">OAuth 2.0 用戶端密碼</span><span class="sxs-lookup"><span data-stu-id="32fca-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="32fca-123">已準備好下列設定檔：</span><span class="sxs-lookup"><span data-stu-id="32fca-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="32fca-124">WDATP-連接器。屬性</span><span class="sxs-lookup"><span data-stu-id="32fca-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="32fca-125">WDATP-connector.jsonparser 屬性</span><span class="sxs-lookup"><span data-stu-id="32fca-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="32fca-126">當您選擇微焦點 ArcSight 做為您在組織中使用的 SIEM 類型時，您就會儲存一個包含這兩個檔案的 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="32fca-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="32fca-127">請確定您產生下列標記並準備好：</span><span class="sxs-lookup"><span data-stu-id="32fca-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="32fca-128">存取權杖</span><span class="sxs-lookup"><span data-stu-id="32fca-128">Access token</span></span>
  - <span data-ttu-id="32fca-129">重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="32fca-129">Refresh token</span></span>

  <span data-ttu-id="32fca-130">您可以從入口網站的 [ **SIEM 整合** 設定] 區段中產生這些權杖。</span><span class="sxs-lookup"><span data-stu-id="32fca-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="32fca-131">安裝和設定微型焦點 ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="32fca-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="32fca-132">下列步驟假設您已在 [開始之前](#before-you-begin)完成所有必要步驟。</span><span class="sxs-lookup"><span data-stu-id="32fca-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="32fca-133">安裝最新的32位 Windows FlexConnector 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="32fca-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="32fca-134">您可以在 HPE 軟體中心找到這種情況。</span><span class="sxs-lookup"><span data-stu-id="32fca-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="32fca-135">工具通常安裝在下列預設位置： `C:\Program Files\ArcSightFlexConnectors\current\bin` 。</span><span class="sxs-lookup"><span data-stu-id="32fca-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="32fca-136">您可以選擇儲存工具的位置，例如 C： \\ *folder_location*\current\bin，其中 *folder_location* 代表安裝位置。</span><span class="sxs-lookup"><span data-stu-id="32fca-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="32fca-137">依照下列工作執行安裝精靈：</span><span class="sxs-lookup"><span data-stu-id="32fca-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="32fca-138">簡介</span><span class="sxs-lookup"><span data-stu-id="32fca-138">Introduction</span></span>
   - <span data-ttu-id="32fca-139">選擇 [安裝資料夾]</span><span class="sxs-lookup"><span data-stu-id="32fca-139">Choose Install Folder</span></span>
   - <span data-ttu-id="32fca-140">選擇安裝集</span><span class="sxs-lookup"><span data-stu-id="32fca-140">Choose Install Set</span></span>
   - <span data-ttu-id="32fca-141">選擇快捷方式資料夾</span><span class="sxs-lookup"><span data-stu-id="32fca-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="32fca-142">安裝前摘要</span><span class="sxs-lookup"><span data-stu-id="32fca-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="32fca-143">安裝。。。</span><span class="sxs-lookup"><span data-stu-id="32fca-143">Installing...</span></span>

   <span data-ttu-id="32fca-144">您可以保留每個任務的預設值，或修改選取範圍以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="32fca-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="32fca-145">開啟 [檔案瀏覽器]，並找到啟用 SIEM 整合功能時所儲存的兩個設定檔。</span><span class="sxs-lookup"><span data-stu-id="32fca-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="32fca-146">將這兩個檔案放在 FlexConnector 安裝位置，例如：</span><span class="sxs-lookup"><span data-stu-id="32fca-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="32fca-147">WDATP-connector.jsonparser。屬性： C： \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="32fca-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="32fca-148">WDATP-連接器。屬性： C： \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="32fca-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="32fca-149">您必須將設定檔放在此位置，其中 *folder_location* 代表您安裝工具的位置。</span><span class="sxs-lookup"><span data-stu-id="32fca-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="32fca-150">在核心連接器安裝完成後，[連接器設定] 視窗隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="32fca-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="32fca-151">在 [連接器設定] 視窗中，選取 [ **新增連接器**]。</span><span class="sxs-lookup"><span data-stu-id="32fca-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="32fca-152">選取 [類型： **ArcSight FLEXCONNECTOR REST** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="32fca-153">在 [參數詳細資料] 表單中輸入下列資訊。</span><span class="sxs-lookup"><span data-stu-id="32fca-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="32fca-154">表單中的所有其他值都是選用的，而且可以保留空白。</span><span class="sxs-lookup"><span data-stu-id="32fca-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="32fca-155">欄位</span><span class="sxs-lookup"><span data-stu-id="32fca-155">Field</span></span></th>
    <th><span data-ttu-id="32fca-156">值</span><span class="sxs-lookup"><span data-stu-id="32fca-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="32fca-157">設定檔</span><span class="sxs-lookup"><span data-stu-id="32fca-157">Configuration File</span></span></td>
    <td><span data-ttu-id="32fca-158">輸入用戶端屬性檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="32fca-158">Type in the name of the client property file.</span></span> <span data-ttu-id="32fca-159">此名稱必須符合您所下載的 .zip 所提供的檔案。</span><span class="sxs-lookup"><span data-stu-id="32fca-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="32fca-160">例如，如果 flexagent 目錄中的配置 &quot; 檔 &quot; 命名為 &quot;WDATP-Connector.jsonparser 屬性 &quot; ，您必須輸入 &quot; WDATP 連接器 &quot; 做為用戶端屬性檔案名的名稱。</span><span class="sxs-lookup"><span data-stu-id="32fca-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="32fca-161">事件 URL</span><span class="sxs-lookup"><span data-stu-id="32fca-161">Events URL</span></span></td>
    <td><span data-ttu-id="32fca-162">根據資料中心的位置，選取歐盟或 US URL:</span><span class="sxs-lookup"><span data-stu-id="32fca-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="32fca-163"><b>適用于 EU</b>： HTTPs:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc = $START _AT_TIME</span><span class="sxs-lookup"><span data-stu-id="32fca-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="32fca-164"><b>美國：</b> HTTPs:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc = $START _AT_TIME</span><span class="sxs-lookup"><span data-stu-id="32fca-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="32fca-165">若<b>為 UK</b>： HTTPs:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc = $START _AT_TIME</span><span class="sxs-lookup"><span data-stu-id="32fca-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="32fca-166">驗證類型</span><span class="sxs-lookup"><span data-stu-id="32fca-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="32fca-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="32fca-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="32fca-168">OAuth 2 用戶端屬性檔</span><span class="sxs-lookup"><span data-stu-id="32fca-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="32fca-169">流覽至 <em>wdatp-connector</em> 的位置。</span><span class="sxs-lookup"><span data-stu-id="32fca-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="32fca-170">此名稱必須符合您所下載的 .zip 所提供的檔案。</span><span class="sxs-lookup"><span data-stu-id="32fca-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="32fca-171">重新整理權杖</span><span class="sxs-lookup"><span data-stu-id="32fca-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="32fca-172">您可以透過兩種方式取得重新整理權杖：透過從 [ <b>SIEM 設定</b> ] 頁面產生重新整理權杖，或使用 restutil 工具來取得更新。</span><span class="sxs-lookup"><span data-stu-id="32fca-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="32fca-173">如需從 <b>偏好設定</b> 中產生重新整理權杖的詳細資訊，請參閱 <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration In Defender for Endpoint</a>。</span><span class="sxs-lookup"><span data-stu-id="32fca-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="32fca-174"><b>使用 restutil 工具取得您的重新整理權杖：</b> </span><span class="sxs-lookup"><span data-stu-id="32fca-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="32fca-175">a.</span><span class="sxs-lookup"><span data-stu-id="32fca-175">a.</span></span> <span data-ttu-id="32fca-176">開啟命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="32fca-176">Open a command prompt.</span></span> <span data-ttu-id="32fca-177">流覽至 C：\<em>folder_location</em>\current\bin，其中 <em>folder_location</em> 代表您安裝工具的位置。</span><span class="sxs-lookup"><span data-stu-id="32fca-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="32fca-178">b.</span><span class="sxs-lookup"><span data-stu-id="32fca-178">b.</span></span> <span data-ttu-id="32fca-179">類型： <code>arcsight restutil token -config</code> 從 bin 目錄。例如： <b>arcsight restutil boxtoken-proxy proxy.location.hp.com:8080</b> 隨即會開啟網頁瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="32fca-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="32fca-180">c.</span><span class="sxs-lookup"><span data-stu-id="32fca-180">c.</span></span> <span data-ttu-id="32fca-181">輸入您的認證，然後按一下 [密碼] 欄位，讓頁面重新導向。</span><span class="sxs-lookup"><span data-stu-id="32fca-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="32fca-182">在 [登入] 提示中，輸入您的認證。</span><span class="sxs-lookup"><span data-stu-id="32fca-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="32fca-183">d.</span><span class="sxs-lookup"><span data-stu-id="32fca-183">d.</span></span> <span data-ttu-id="32fca-184">重新整理權杖會顯示在命令提示字元中。</span><span class="sxs-lookup"><span data-stu-id="32fca-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="32fca-185">e.</span><span class="sxs-lookup"><span data-stu-id="32fca-185">e.</span></span> <span data-ttu-id="32fca-186">複製並貼到 [重新整理 <b>權杖</b> ] 欄位。</span><span class="sxs-lookup"><span data-stu-id="32fca-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="32fca-187">由連接器開啟瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="32fca-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="32fca-188">使用您的應用程式認證登入。</span><span class="sxs-lookup"><span data-stu-id="32fca-188">Login with your application credentials.</span></span> <span data-ttu-id="32fca-189">登入後，系統會要求您將許可權授與您的 OAuth2 用戶端。</span><span class="sxs-lookup"><span data-stu-id="32fca-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="32fca-190">您必須授與 OAuth 2 用戶端的許可權，讓連接器設定可以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="32fca-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="32fca-191">如果 <code>redirect_uri</code> 是 HTTPS URL，則會重新導向至本機主機上的 URL。</span><span class="sxs-lookup"><span data-stu-id="32fca-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="32fca-192">您會看到一個頁面，要求您信任本機主機上執行之連接器所提供的憑證。</span><span class="sxs-lookup"><span data-stu-id="32fca-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="32fca-193">如果 redirect_uri 為 HTTPs，您必須信任此憑證。</span><span class="sxs-lookup"><span data-stu-id="32fca-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="32fca-194">不過，如果您指定 redirect_uri 的 HTTP URL，則不需要在信任憑證時提供同意。</span><span class="sxs-lookup"><span data-stu-id="32fca-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="32fca-195">透過返回 [微焦點 ArcSight Connector Setup] 視窗，繼續執行連接器設定。</span><span class="sxs-lookup"><span data-stu-id="32fca-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="32fca-196">選取 **ArcSight 管理員 (加密)** 做為目的地，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="32fca-197">在 **管理員主機名稱** 中輸入目的地 IP/主機名稱，並在 [參數] 表單中輸入您的認證。</span><span class="sxs-lookup"><span data-stu-id="32fca-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="32fca-198">表單中的所有其他值都應該以預設值保留。</span><span class="sxs-lookup"><span data-stu-id="32fca-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="32fca-199">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-199">Click **Next**.</span></span>

11. <span data-ttu-id="32fca-200">在 [連接器詳細資料] 表單中輸入連接器的名稱。</span><span class="sxs-lookup"><span data-stu-id="32fca-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="32fca-201">表單中的所有其他值都是選用的，而且可以保留空白。</span><span class="sxs-lookup"><span data-stu-id="32fca-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="32fca-202">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-202">Click **Next**.</span></span>

12. <span data-ttu-id="32fca-203">[ESM 管理員匯入憑證] 視窗會顯示。</span><span class="sxs-lookup"><span data-stu-id="32fca-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="32fca-204">選取 **[將憑證匯入連接器從目的地** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="32fca-205">隨即會顯示 [ **新增連接器摘要** ] 視窗，並匯入該憑證。</span><span class="sxs-lookup"><span data-stu-id="32fca-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="32fca-206">確認 [ **新增連接器摘要** ] 視窗中的詳細資訊正確無誤，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="32fca-207">選取 [ **安裝為服務** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="32fca-208">在 [ **服務內部名稱** ] 欄位中輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="32fca-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="32fca-209">表單中的所有其他值都可以保留預設值或保留空白。</span><span class="sxs-lookup"><span data-stu-id="32fca-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="32fca-210">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-210">Click **Next**.</span></span>

16. <span data-ttu-id="32fca-211">輸入服務參數，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="32fca-212">顯示「 **安裝服務摘要** 」的視窗。</span><span class="sxs-lookup"><span data-stu-id="32fca-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="32fca-213">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-213">Click **Next**.</span></span>

17. <span data-ttu-id="32fca-214">**選取 [** 結束] 和 **[下一步**]，完成安裝。</span><span class="sxs-lookup"><span data-stu-id="32fca-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="32fca-215">安裝和設定微型焦點 ArcSight 主控台</span><span class="sxs-lookup"><span data-stu-id="32fca-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="32fca-216">依照下列工作執行安裝精靈：</span><span class="sxs-lookup"><span data-stu-id="32fca-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="32fca-217">簡介</span><span class="sxs-lookup"><span data-stu-id="32fca-217">Introduction</span></span>
   - <span data-ttu-id="32fca-218">授權合約</span><span class="sxs-lookup"><span data-stu-id="32fca-218">License Agreement</span></span>
   - <span data-ttu-id="32fca-219">特殊注意事項</span><span class="sxs-lookup"><span data-stu-id="32fca-219">Special Notice</span></span>
   - <span data-ttu-id="32fca-220">選擇 [ArcSight 安裝目錄]</span><span class="sxs-lookup"><span data-stu-id="32fca-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="32fca-221">選擇快捷方式資料夾</span><span class="sxs-lookup"><span data-stu-id="32fca-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="32fca-222">安裝前摘要</span><span class="sxs-lookup"><span data-stu-id="32fca-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="32fca-223">按一下 **[安裝]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-223">Click **Install**.</span></span> <span data-ttu-id="32fca-224">安裝完成之後，ArcSight 主控台設定向導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="32fca-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="32fca-225">在 manager 的 [ **主機名稱** ] 和 8443 **In** **[下一步]** 中輸入 localhost。</span><span class="sxs-lookup"><span data-stu-id="32fca-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="32fca-226">選取 [ **使用直接** 連線]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="32fca-227">選取 [ **基於密碼的驗證**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="32fca-228">選取 [ **這是單一使用者安裝。 (建議)**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32fca-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="32fca-229">按一下 [ **完成] 結束** 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="32fca-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="32fca-230">登入微焦 ArcSight 主控台。</span><span class="sxs-lookup"><span data-stu-id="32fca-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="32fca-231">流覽至 [**現用通道集**]  >  **新的條件**  >  **裝置**  >  **裝置產品**。</span><span class="sxs-lookup"><span data-stu-id="32fca-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="32fca-232">設定 **裝置產品 = Microsoft Defender ATP**。</span><span class="sxs-lookup"><span data-stu-id="32fca-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="32fca-233">當您驗證事件已流過工具時，請停止此程式，然後移至 Windows 服務]，然後啟動 ArcSight FlexConnector REST。</span><span class="sxs-lookup"><span data-stu-id="32fca-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="32fca-234">您現在可以在 [微焦點 ArcSight] 主控台中執行查詢。</span><span class="sxs-lookup"><span data-stu-id="32fca-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="32fca-235">Endpoint 偵測的 Defender 會顯示為獨立的事件，並使用 "Microsoft" 作為廠商，而 "Windows Defender ATP" 為裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="32fca-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="32fca-236">疑難排解微型聚焦 ArcSight connection</span><span class="sxs-lookup"><span data-stu-id="32fca-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="32fca-237">**問題：** 無法重新整理權杖。</span><span class="sxs-lookup"><span data-stu-id="32fca-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="32fca-238">您可以在 C： folder_location \current\logs 中找到記錄檔 \\ \*\*， *folder_location* 代表安裝此工具的位置。</span><span class="sxs-lookup"><span data-stu-id="32fca-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="32fca-239">開啟 _代理程式 .log_ 和尋找 `ERROR/FATAL/WARN` 。</span><span class="sxs-lookup"><span data-stu-id="32fca-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="32fca-240">**症狀：** 您會收到下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="32fca-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="32fca-241">**解決 方案：**</span><span class="sxs-lookup"><span data-stu-id="32fca-241">**Solution:**</span></span>

1. <span data-ttu-id="32fca-242">按一下 [連接器] 視窗上的 [Ctrl+C]，以停止此程式。</span><span class="sxs-lookup"><span data-stu-id="32fca-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="32fca-243">當要求「終止批次處理工作 Y/N？」時，請按一下 **Y** 。</span><span class="sxs-lookup"><span data-stu-id="32fca-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="32fca-244">流覽至儲存 WDATP-connector 的資料夾，然後編輯該檔案，以新增下列值： `reauthenticate=true` 。</span><span class="sxs-lookup"><span data-stu-id="32fca-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="32fca-245">執行下列命令，以重新開機連接器： `arcsight.bat connectors` 。</span><span class="sxs-lookup"><span data-stu-id="32fca-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="32fca-246">瀏覽器視窗隨即出現。</span><span class="sxs-lookup"><span data-stu-id="32fca-246">A browser window appears.</span></span> <span data-ttu-id="32fca-247">允許它執行，應該會消失，連接器現在應該正在執行。</span><span class="sxs-lookup"><span data-stu-id="32fca-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="32fca-248">請停止此程式，以確認連接器是否正在執行。</span><span class="sxs-lookup"><span data-stu-id="32fca-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="32fca-249">然後再啟動連接器，不應出現瀏覽器視窗。</span><span class="sxs-lookup"><span data-stu-id="32fca-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32fca-250">相關主題</span><span class="sxs-lookup"><span data-stu-id="32fca-250">Related topics</span></span>
- [<span data-ttu-id="32fca-251">在 Defender for Endpoint 中啟用 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="32fca-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="32fca-252">向 SIEM 工具提取偵測</span><span class="sxs-lookup"><span data-stu-id="32fca-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="32fca-253">使用 REST API 的端點偵測的拉取 Defender</span><span class="sxs-lookup"><span data-stu-id="32fca-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="32fca-254">為 SIEM 工具整合問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="32fca-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
