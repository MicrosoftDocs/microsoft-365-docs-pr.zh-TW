---
title: 疑難排解 Microsoft Defender ATP live response 問題
description: 疑難排解在 Microsoft Defender ATP 中使用 live response 時可能發生的問題
keywords: 疑難排解即時回應、即時、回應、鎖定、檔
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
ms.openlocfilehash: 62525548be777a3187cea5ed4be622ac9d42079b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51183812"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="5b455-104">疑難排解 Microsoft Defender 的 Endpoint live 回應問題</span><span class="sxs-lookup"><span data-stu-id="5b455-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5b455-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="5b455-105">**Applies to:**</span></span>
- [<span data-ttu-id="5b455-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="5b455-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5b455-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5b455-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5b455-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="5b455-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5b455-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="5b455-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="5b455-110">此頁面提供疑難排解 live response 問題的詳細步驟。</span><span class="sxs-lookup"><span data-stu-id="5b455-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="5b455-111">在即時回應會話期間無法存取檔</span><span class="sxs-lookup"><span data-stu-id="5b455-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="5b455-112">當您嘗試在 live response session 期間採取動作時，您會遇到錯誤訊息，指出無法存取檔案，您必須使用下列步驟來解決問題。</span><span class="sxs-lookup"><span data-stu-id="5b455-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="5b455-113">複製下列腳本代碼片段，並將它儲存為 PS1 檔案：</span><span class="sxs-lookup"><span data-stu-id="5b455-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="5b455-114">將腳本新增至 live 回應文件庫。</span><span class="sxs-lookup"><span data-stu-id="5b455-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="5b455-115">以一個參數執行腳本：要複製之檔案的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="5b455-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="5b455-116">流覽至您的 TEMP 資料夾。</span><span class="sxs-lookup"><span data-stu-id="5b455-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="5b455-117">請執行您想要對複製的檔案採取的動作。</span><span class="sxs-lookup"><span data-stu-id="5b455-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="5b455-118">在初始連線期間緩慢即時回應會話或延遲</span><span class="sxs-lookup"><span data-stu-id="5b455-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="5b455-119">Live response 利用在 Windows 中的 WNS 服務，使用 Defender 進行 Endpoint 感應器註冊。</span><span class="sxs-lookup"><span data-stu-id="5b455-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="5b455-120">如果您有即時回應的連線問題，請確認下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="5b455-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="5b455-121">`notify.windows.com` 在您的環境中未遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="5b455-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="5b455-122">如需詳細資訊，請參閱 [Configure device proxy And Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。</span><span class="sxs-lookup"><span data-stu-id="5b455-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="5b455-123">WpnService (Windows 推入通知系統服務) 未停用。</span><span class="sxs-lookup"><span data-stu-id="5b455-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="5b455-124">請參閱下列文章，以完全瞭解 WpnService 服務的行為和需求：</span><span class="sxs-lookup"><span data-stu-id="5b455-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="5b455-125">Windows 推播通知服務 (WNS) 概述</span><span class="sxs-lookup"><span data-stu-id="5b455-125">Windows Push Notification Services (WNS) overview</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="5b455-126">支援 WNS 流量的企業防火牆和 Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="5b455-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="5b455-127">Microsoft 推播通知服務 (MPNS) 公用 IP 範圍</span><span class="sxs-lookup"><span data-stu-id="5b455-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

