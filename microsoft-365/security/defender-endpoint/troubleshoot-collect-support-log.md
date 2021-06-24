---
title: 使用即時回應在 Microsoft Defender 中為端點收集支援記錄
description: 瞭解如何使用即時回應收集記錄，以疑難排解 Microsoft Defender 的端點問題
keywords: 支援、記錄、收集、疑難排解、live response、liveanalyzer、analyzer、live、response
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 0e7634177e58b558381fdc230533b55cade9dc13
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108508"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="9be68-104">使用 live 回應收集 Microsoft Defender for Endpoint 中的支援記錄</span><span class="sxs-lookup"><span data-stu-id="9be68-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="9be68-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9be68-105">**Applies to:**</span></span>
- [<span data-ttu-id="9be68-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="9be68-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9be68-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9be68-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9be68-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="9be68-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9be68-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="9be68-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="9be68-110">當您聯繫支援時，可能會要求您提供 Microsoft Defender for Endpoint Client Analyzer 工具的輸出套件。</span><span class="sxs-lookup"><span data-stu-id="9be68-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="9be68-111">本主題提供如何透過即時回應來執行工具的指示。</span><span class="sxs-lookup"><span data-stu-id="9be68-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="9be68-112">下載適當的腳本</span><span class="sxs-lookup"><span data-stu-id="9be68-112">Download the appropriate script</span></span>
    * <span data-ttu-id="9be68-113">僅適用于 Endpoint 用戶端感應器記錄的 Microsoft Defender： [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer)。</span><span class="sxs-lookup"><span data-stu-id="9be68-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="9be68-114">結果套件大致大小： ~ 100Kb</span><span class="sxs-lookup"><span data-stu-id="9be68-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="9be68-115">Microsoft Defender for Endpoint 用戶端感應器和防病毒記錄： [LiveAnalyzer +MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV)。</span><span class="sxs-lookup"><span data-stu-id="9be68-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="9be68-116">結果套件大致大小：大約10Mb</span><span class="sxs-lookup"><span data-stu-id="9be68-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="9be68-117">在您需要調查的機器上啟動 [即時回應會話](live-response.md#initiate-a-live-response-session-on-a-device) 。</span><span class="sxs-lookup"><span data-stu-id="9be68-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="9be68-118">選取 [ **Upload 檔案至文件庫**]。</span><span class="sxs-lookup"><span data-stu-id="9be68-118">Select **Upload file to library**.</span></span>

    ![上傳檔案的影像](images/upload-file.png)

4. <span data-ttu-id="9be68-120">選取 **[選擇檔**]。</span><span class="sxs-lookup"><span data-stu-id="9be68-120">Select **Choose file**.</span></span>

    ![選擇檔 button1 的影像](images/choose-file.png)

5. <span data-ttu-id="9be68-122">選取名為 MDELiveAnalyzer.ps1 的下載檔案，然後按一下 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="9be68-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![選擇檔案 button2 的影像](images/analyzer-file.png)


6. <span data-ttu-id="9be68-124">仍在 LiveResponse 會話中，請使用下列命令執行 analyzer，並收集結果檔案：</span><span class="sxs-lookup"><span data-stu-id="9be68-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip"
    ```

    <span data-ttu-id="9be68-125">[![命令 ](images/analyzer-commands.png) 圖像](images/analyzer-commands.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9be68-125">[ ![Image of commands](images/analyzer-commands.png) ](images/analyzer-commands.png#lightbox)</span></span>


>[!NOTE]
> - <span data-ttu-id="9be68-126">MDEClientAnalyzer 的最新預覽版本可于以下下載： [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) 。</span><span class="sxs-lookup"><span data-stu-id="9be68-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="9be68-127">LiveAnalyzer 腳本會從：中下載目的地機器上的疑難排解套件 https://mdatpclientanalyzer.blob.core.windows.net 。</span><span class="sxs-lookup"><span data-stu-id="9be68-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="9be68-128">如果您無法允許機器到達上述 URL，請在執行 LiveAnalyzer 腳本之前，先將 MDEClientAnalyzerPreview.zip 檔案上傳至文件庫：</span><span class="sxs-lookup"><span data-stu-id="9be68-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" 
>   ```
> 
> - <span data-ttu-id="9be68-129">如需在機器本機上收集資料的詳細資訊，以防機器未與 Microsoft Defender for Endpoint 雲端服務通訊，或未如預期顯示在 Microsoft Defender for Endpoint portal，請參閱 [Verify client connectivity to connectivity To Microsoft defender For endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)。</span><span class="sxs-lookup"><span data-stu-id="9be68-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).</span></span>
