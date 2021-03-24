---
title: 使用 Microsoft Defender ATP 中的即時回應調查裝置上的實體
description: 使用安全的遠端命令介面連線存取裝置，以執行調查工作並即時立即對裝置採取回應動作。
keywords: remote，shell，connection，live，response，real，command，script，修正，搜尋，匯出，記錄，刪除，下載，檔案，
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
ms.openlocfilehash: d992d98b916f5b59b67706b310edefdb37f157b4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057475"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="f01dc-104">使用即時回應調查裝置上的實體</span><span class="sxs-lookup"><span data-stu-id="f01dc-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f01dc-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f01dc-105">**Applies to:**</span></span>
- [<span data-ttu-id="f01dc-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f01dc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f01dc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f01dc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f01dc-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f01dc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f01dc-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f01dc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f01dc-110">Live response 讓安全性運作小組能夠暫態存取裝置 (也稱為) 使用遠端命令介面連線的電腦。</span><span class="sxs-lookup"><span data-stu-id="f01dc-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="f01dc-111">這可讓您在深入調查工作中做為您的力量，並立即採取回應動作，及時包含已識別的威脅（即時）。</span><span class="sxs-lookup"><span data-stu-id="f01dc-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="f01dc-112">Live response 的設計目的是讓您的安全性作業小組收集法律資料、執行腳本、傳送可疑實體以進行分析、修正威脅，以及主動搜尋新興威脅，以加強調查。</span><span class="sxs-lookup"><span data-stu-id="f01dc-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="f01dc-113">使用 live response 時，分析員可以執行下列所有工作：</span><span class="sxs-lookup"><span data-stu-id="f01dc-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="f01dc-114">執行基本和高級命令，在裝置上執行調查工作。</span><span class="sxs-lookup"><span data-stu-id="f01dc-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="f01dc-115">下載檔案，例如惡意程式碼範例和 PowerShell 腳本的結果。</span><span class="sxs-lookup"><span data-stu-id="f01dc-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="f01dc-116">在背景 (new！ ) 中下載檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="f01dc-117">將 PowerShell 腳本或可執行檔上傳至文件庫，並在租使用者層級上的裝置上執行。</span><span class="sxs-lookup"><span data-stu-id="f01dc-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="f01dc-118">採取或撤銷修正動作。</span><span class="sxs-lookup"><span data-stu-id="f01dc-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f01dc-119">開始之前</span><span class="sxs-lookup"><span data-stu-id="f01dc-119">Before you begin</span></span>

<span data-ttu-id="f01dc-120">在裝置上啟動會話之前，請先確定您符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="f01dc-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="f01dc-121">**確認您正在執行支援的 Windows 版本**。</span><span class="sxs-lookup"><span data-stu-id="f01dc-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="f01dc-122">裝置必須執行下列其中一個 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="f01dc-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="f01dc-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="f01dc-123">**Windows 10**</span></span>
    - <span data-ttu-id="f01dc-124">[版本 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="f01dc-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="f01dc-125">[版本 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) 與 [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="f01dc-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="f01dc-126">[版本 1809 (RS 5) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) 與 [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="f01dc-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="f01dc-127">[版本 1803 (RS 4) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) 與 [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="f01dc-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="f01dc-128">[版本 1709 (RS 3) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 與 [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="f01dc-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="f01dc-129">**Windows Server 2019-僅適用于公開預覽**</span><span class="sxs-lookup"><span data-stu-id="f01dc-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="f01dc-130">版本1903或 (隨 [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) 更新版本</span><span class="sxs-lookup"><span data-stu-id="f01dc-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="f01dc-131">版本 1809 (，含 [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)) </span><span class="sxs-lookup"><span data-stu-id="f01dc-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="f01dc-132">**從 [高級設定] 頁面啟用即時回應**。</span><span class="sxs-lookup"><span data-stu-id="f01dc-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="f01dc-133">您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的 [即時回應] 功能。</span><span class="sxs-lookup"><span data-stu-id="f01dc-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f01dc-134">只有具有「管理安全性」或「全域系統管理員」角色的使用者可以編輯這些設定。</span><span class="sxs-lookup"><span data-stu-id="f01dc-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="f01dc-135">**從 [高級設定] 頁面啟用伺服器的即時回應** (建議) 。</span><span class="sxs-lookup"><span data-stu-id="f01dc-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="f01dc-136">只有具有「管理安全性」或「全域系統管理員」角色的使用者可以編輯這些設定。</span><span class="sxs-lookup"><span data-stu-id="f01dc-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="f01dc-137">**確定裝置具有指派的「自動化修正」層級**。</span><span class="sxs-lookup"><span data-stu-id="f01dc-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="f01dc-138">您必須至少啟用特定裝置群組的最低修正層級。</span><span class="sxs-lookup"><span data-stu-id="f01dc-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="f01dc-139">否則，您將無法為該群組的成員建立即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="f01dc-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="f01dc-140">您會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="f01dc-140">You'll receive the following error:</span></span>

    ![錯誤訊息影像](images/live-response-error.png)

- <span data-ttu-id="f01dc-142">**啟用 live response 未簽署的腳本執行** (選用) 。</span><span class="sxs-lookup"><span data-stu-id="f01dc-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="f01dc-143">允許使用未簽署的腳本可能會增加威脅的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="f01dc-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="f01dc-144">不建議執行未簽署的腳本，因為這樣可增加您對威脅的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="f01dc-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="f01dc-145">如果您必須使用它們，但是您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的設定。</span><span class="sxs-lookup"><span data-stu-id="f01dc-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="f01dc-146">**確定您具有適當的許可權**。</span><span class="sxs-lookup"><span data-stu-id="f01dc-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="f01dc-147">只有已使用適當許可權布建的使用者才能啟動會話。</span><span class="sxs-lookup"><span data-stu-id="f01dc-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="f01dc-148">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f01dc-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="f01dc-149">將檔案上傳至文件庫的選項只適用于具有適當 RBAC 許可權的選項。</span><span class="sxs-lookup"><span data-stu-id="f01dc-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="f01dc-150">只有委派許可權的使用者，此按鈕才會顯示為灰色。</span><span class="sxs-lookup"><span data-stu-id="f01dc-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="f01dc-151">您可以執行基本或高級 live 回應命令，視授與您的角色而定。</span><span class="sxs-lookup"><span data-stu-id="f01dc-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="f01dc-152">使用者許可權是由 RBAC 自訂角色所控制。</span><span class="sxs-lookup"><span data-stu-id="f01dc-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="f01dc-153">Live response 儀表板一覽</span><span class="sxs-lookup"><span data-stu-id="f01dc-153">Live response dashboard overview</span></span>
<span data-ttu-id="f01dc-154">當您在裝置上啟動即時回應會話時，儀表板會開啟。</span><span class="sxs-lookup"><span data-stu-id="f01dc-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="f01dc-155">儀表板提供會話的相關資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f01dc-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="f01dc-156">建立會話的人員</span><span class="sxs-lookup"><span data-stu-id="f01dc-156">Who created the session</span></span>
- <span data-ttu-id="f01dc-157">啟動會話時</span><span class="sxs-lookup"><span data-stu-id="f01dc-157">When the session started</span></span>
- <span data-ttu-id="f01dc-158">會話的持續時間</span><span class="sxs-lookup"><span data-stu-id="f01dc-158">The duration of the session</span></span>

<span data-ttu-id="f01dc-159">儀表板也可讓您存取：</span><span class="sxs-lookup"><span data-stu-id="f01dc-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="f01dc-160">中斷連線會話</span><span class="sxs-lookup"><span data-stu-id="f01dc-160">Disconnect session</span></span>
- <span data-ttu-id="f01dc-161">將檔案上傳至文件庫</span><span class="sxs-lookup"><span data-stu-id="f01dc-161">Upload files to the library</span></span> 
- <span data-ttu-id="f01dc-162">命令主控台</span><span class="sxs-lookup"><span data-stu-id="f01dc-162">Command console</span></span>
- <span data-ttu-id="f01dc-163">命令記錄檔</span><span class="sxs-lookup"><span data-stu-id="f01dc-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="f01dc-164">在裝置上啟動即時回應會話</span><span class="sxs-lookup"><span data-stu-id="f01dc-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="f01dc-165">登入 Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="f01dc-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="f01dc-166">流覽至 [裝置] 清單頁面，然後選取要調查的裝置。</span><span class="sxs-lookup"><span data-stu-id="f01dc-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="f01dc-167">隨即會開啟 [裝置] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f01dc-167">The devices page opens.</span></span>

3. <span data-ttu-id="f01dc-168">選取 [ **啟動即時回應會話**]，以啟動即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="f01dc-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="f01dc-169">隨即會顯示命令主控台。</span><span class="sxs-lookup"><span data-stu-id="f01dc-169">A command console is displayed.</span></span> <span data-ttu-id="f01dc-170">在會話連接至裝置時等候。</span><span class="sxs-lookup"><span data-stu-id="f01dc-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="f01dc-171">使用內建的命令執行調查工作。</span><span class="sxs-lookup"><span data-stu-id="f01dc-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="f01dc-172">如需詳細資訊，請參閱 [Live response 命令](#live-response-commands)。</span><span class="sxs-lookup"><span data-stu-id="f01dc-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="f01dc-173">完成調查後，請選取 **[中斷連線會話]**，然後選取 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="f01dc-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="f01dc-174">即時回應命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-174">Live response commands</span></span>

<span data-ttu-id="f01dc-175">您可以執行基本或高級 live 回應命令，視授與您的角色而定。</span><span class="sxs-lookup"><span data-stu-id="f01dc-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="f01dc-176">使用者權限是由 RBAC 自訂角色所控制。</span><span class="sxs-lookup"><span data-stu-id="f01dc-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="f01dc-177">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f01dc-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="f01dc-178">Live response 是雲端型互動命令介面，如此一來，特定的命令體驗可能會因回應時間而異，取決於使用者與目標裝置之間的網路品質和系統負載。</span><span class="sxs-lookup"><span data-stu-id="f01dc-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="f01dc-179">基本命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-179">Basic commands</span></span>

<span data-ttu-id="f01dc-180">下列命令適用于授與執行 **基本** live 回應命令之功能的使用者角色。</span><span class="sxs-lookup"><span data-stu-id="f01dc-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="f01dc-181">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f01dc-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="f01dc-182">命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-182">Command</span></span> | <span data-ttu-id="f01dc-183">描述</span><span class="sxs-lookup"><span data-stu-id="f01dc-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="f01dc-184">變更目前的目錄。</span><span class="sxs-lookup"><span data-stu-id="f01dc-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="f01dc-185">清除主控台畫面。</span><span class="sxs-lookup"><span data-stu-id="f01dc-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="f01dc-186">啟動裝置的即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="f01dc-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="f01dc-187">顯示所有使用中的連線。</span><span class="sxs-lookup"><span data-stu-id="f01dc-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="f01dc-188">顯示目錄中的檔案及子目錄清單。</span><span class="sxs-lookup"><span data-stu-id="f01dc-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="f01dc-189">會在背景中下載檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-189">Downloads a file in the background.</span></span> |
<span data-ttu-id="f01dc-190">司機</span><span class="sxs-lookup"><span data-stu-id="f01dc-190">drivers</span></span> |  <span data-ttu-id="f01dc-191">顯示裝置上安裝的所有驅動程式。</span><span class="sxs-lookup"><span data-stu-id="f01dc-191">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="f01dc-192">將檔案下載傳回前景。</span><span class="sxs-lookup"><span data-stu-id="f01dc-192">Returns a file download to the foreground.</span></span> |
|`fileinfo` | <span data-ttu-id="f01dc-193">取得檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f01dc-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="f01dc-194">以指定的名稱在裝置上尋找檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-194">Locates files by a given name on the device.</span></span> |
|`help` | <span data-ttu-id="f01dc-195">提供即時回應命令的説明資訊。</span><span class="sxs-lookup"><span data-stu-id="f01dc-195">Provides help information for live response commands.</span></span> |
|`persistence` | <span data-ttu-id="f01dc-196">顯示裝置上所有已知的持久性方法。</span><span class="sxs-lookup"><span data-stu-id="f01dc-196">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="f01dc-197">顯示裝置上執行的所有進程。</span><span class="sxs-lookup"><span data-stu-id="f01dc-197">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="f01dc-198">顯示登錄值。</span><span class="sxs-lookup"><span data-stu-id="f01dc-198">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="f01dc-199">顯示裝置上的所有排程任務。</span><span class="sxs-lookup"><span data-stu-id="f01dc-199">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="f01dc-200">顯示裝置上的所有服務。</span><span class="sxs-lookup"><span data-stu-id="f01dc-200">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="f01dc-201">設定終端的記錄模式進行調試。</span><span class="sxs-lookup"><span data-stu-id="f01dc-201">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="f01dc-202">Advanced 命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-202">Advanced commands</span></span>
<span data-ttu-id="f01dc-203">下列命令適用于授與執行「 **高級** 即時回應」命令功能的使用者角色。</span><span class="sxs-lookup"><span data-stu-id="f01dc-203">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="f01dc-204">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="f01dc-204">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="f01dc-205">命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-205">Command</span></span> | <span data-ttu-id="f01dc-206">描述</span><span class="sxs-lookup"><span data-stu-id="f01dc-206">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="f01dc-207">分析具有各種 incrimination 引擎的實體，以達到判定。</span><span class="sxs-lookup"><span data-stu-id="f01dc-207">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `getfile` | <span data-ttu-id="f01dc-208">從裝置取得檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-208">Gets a file from the device.</span></span> <br> <span data-ttu-id="f01dc-209">注意：此命令具有必要條件命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-209">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="f01dc-210">您可以搭配使用此 `-auto` 命令 `getfile` ，以自動執行必要條件命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-210">You can use the `-auto` command in conjunction with `getfile` to automatically run the prerequisite command.</span></span> |
| `run` | <span data-ttu-id="f01dc-211">從裝置上的文件庫執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="f01dc-211">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="f01dc-212">列出已上傳至 live response library 的檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-212">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="f01dc-213">將檔案從文件庫放入裝置。</span><span class="sxs-lookup"><span data-stu-id="f01dc-213">Puts a file from the library to the device.</span></span> <span data-ttu-id="f01dc-214">檔案儲存在工作資料夾中，而且會在預設重新開機裝置時刪除。</span><span class="sxs-lookup"><span data-stu-id="f01dc-214">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="f01dc-215">在裝置上 Remediates 實體。</span><span class="sxs-lookup"><span data-stu-id="f01dc-215">Remediates an entity on the device.</span></span> <span data-ttu-id="f01dc-216">修正動作會因實體類型而異：</span><span class="sxs-lookup"><span data-stu-id="f01dc-216">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="f01dc-217">-File： delete</span><span class="sxs-lookup"><span data-stu-id="f01dc-217">- File: delete</span></span><br><span data-ttu-id="f01dc-218">-進程：停止、刪除影像檔</span><span class="sxs-lookup"><span data-stu-id="f01dc-218">- Process: stop, delete image file</span></span><br><span data-ttu-id="f01dc-219">-服務：停止、刪除映射檔</span><span class="sxs-lookup"><span data-stu-id="f01dc-219">- Service: stop, delete image file</span></span><br><span data-ttu-id="f01dc-220">-登錄專案：刪除</span><span class="sxs-lookup"><span data-stu-id="f01dc-220">- Registry entry: delete</span></span><br><span data-ttu-id="f01dc-221">-排程任務：移除</span><span class="sxs-lookup"><span data-stu-id="f01dc-221">- Scheduled task: remove</span></span><br><span data-ttu-id="f01dc-222">-Startup 資料夾專案：刪除檔案</span><span class="sxs-lookup"><span data-stu-id="f01dc-222">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="f01dc-223">注意：此命令具有必要條件命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-223">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="f01dc-224">您可以搭配使用此 `-auto` 命令 `remediate` ，以自動執行必要條件命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-224">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="f01dc-225">還原已修正的實體。</span><span class="sxs-lookup"><span data-stu-id="f01dc-225">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="f01dc-226">使用即時回應命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-226">Use live response commands</span></span>

<span data-ttu-id="f01dc-227">您可以在主控台中使用的命令遵循與 [Windows 命令](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)類似的原則。</span><span class="sxs-lookup"><span data-stu-id="f01dc-227">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="f01dc-228">Advanced 命令提供一組更為強大的動作，可讓您採取更強大的動作，例如下載和上傳檔案、在裝置上執行腳本，以及對實體採取修正動作。</span><span class="sxs-lookup"><span data-stu-id="f01dc-228">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="f01dc-229">從裝置取得檔案</span><span class="sxs-lookup"><span data-stu-id="f01dc-229">Get a file from the device</span></span>

<span data-ttu-id="f01dc-230">例如，如果您想要從您正在調查的裝置取得檔案，您可以使用此 `getfile` 命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-230">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="f01dc-231">這可讓您儲存裝置中的檔案進行進一步調查。</span><span class="sxs-lookup"><span data-stu-id="f01dc-231">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="f01dc-232">適用下列檔案大小限制：</span><span class="sxs-lookup"><span data-stu-id="f01dc-232">The following file size limits apply:</span></span>
>- <span data-ttu-id="f01dc-233">`getfile` 限制： 3 GB</span><span class="sxs-lookup"><span data-stu-id="f01dc-233">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="f01dc-234">`fileinfo` 限制： 10 GB</span><span class="sxs-lookup"><span data-stu-id="f01dc-234">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="f01dc-235">`library` 限制： 250 MB</span><span class="sxs-lookup"><span data-stu-id="f01dc-235">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="f01dc-236">下載背景中的檔案</span><span class="sxs-lookup"><span data-stu-id="f01dc-236">Download a file in the background</span></span>

<span data-ttu-id="f01dc-237">若要讓您的安全性運作小組繼續調查受影響的裝置，現在可以在後臺下載檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-237">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="f01dc-238">若要在後臺下載檔案，請在 live response 命令主控台中輸入 `download <file_path> &` 。</span><span class="sxs-lookup"><span data-stu-id="f01dc-238">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="f01dc-239">如果您正在等候下載檔案，您可以使用 Ctrl+Z 將檔案移至背景。</span><span class="sxs-lookup"><span data-stu-id="f01dc-239">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="f01dc-240">若要將檔案下載移至前臺，請在 live response 命令主控台中輸入 `fg <command_id>` 。</span><span class="sxs-lookup"><span data-stu-id="f01dc-240">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="f01dc-241">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="f01dc-241">Here are some examples:</span></span>


|<span data-ttu-id="f01dc-242">命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-242">Command</span></span>  |<span data-ttu-id="f01dc-243">其用途</span><span class="sxs-lookup"><span data-stu-id="f01dc-243">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="f01dc-244">開始在背景中下載名為 *some_file.exe* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-244">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="f01dc-245">會傳回具有命令識別碼 *1234* 至前景的下載。</span><span class="sxs-lookup"><span data-stu-id="f01dc-245">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="f01dc-246">將檔案放入文件庫中</span><span class="sxs-lookup"><span data-stu-id="f01dc-246">Put a file in the library</span></span>

<span data-ttu-id="f01dc-247">Live response 具有可讓您存放盤案的文件庫。</span><span class="sxs-lookup"><span data-stu-id="f01dc-247">Live response has a library where you can put files into.</span></span> <span data-ttu-id="f01dc-248">文件庫儲存 (例如腳本) ，可在租使用者層級的即時回應會話中執行。</span><span class="sxs-lookup"><span data-stu-id="f01dc-248">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="f01dc-249">Live response 允許執行 PowerShell 腳本，但是您必須先將檔案放入文件庫中，才可執行這些檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-249">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="f01dc-250">您可以在用來啟動 live 回應會話的裝置上，使用可在其上執行的 PowerShell 腳本集合。</span><span class="sxs-lookup"><span data-stu-id="f01dc-250">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="f01dc-251">上傳文件庫中的檔案</span><span class="sxs-lookup"><span data-stu-id="f01dc-251">To upload a file in the library</span></span>

1. <span data-ttu-id="f01dc-252">按一下 **[將檔案上傳至文件庫**]。</span><span class="sxs-lookup"><span data-stu-id="f01dc-252">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="f01dc-253">按一下 **[流覽]** 並選取檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-253">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="f01dc-254">提供簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="f01dc-254">Provide a brief description.</span></span>

4. <span data-ttu-id="f01dc-255">指定您是否要覆寫具有相同名稱的檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-255">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="f01dc-256">如果您想要的話，請知道腳本所需的參數，然後選取 [腳本參數] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f01dc-256">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="f01dc-257">在 [文字] 欄位中，輸入範例和描述。</span><span class="sxs-lookup"><span data-stu-id="f01dc-257">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="f01dc-258">按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="f01dc-258">Click **Confirm**.</span></span> 

7. <span data-ttu-id="f01dc-259"> (選用) 若要確認已將檔案上傳至文件庫，請執行 `library` 命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-259">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="f01dc-260">取消命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-260">Cancel a command</span></span>
<span data-ttu-id="f01dc-261">在會話期間，您可以隨時按 CTRL+C 取消命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-261">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="f01dc-262">使用此快捷方式不會停止代理端中的命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-262">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="f01dc-263">它只會取消入口網站中的命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-263">It will only cancel the command in the portal.</span></span> <span data-ttu-id="f01dc-264">這樣一來，在取消變更時，"修正" 作業可能會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="f01dc-264">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="f01dc-265">自動執行必要條件命令</span><span class="sxs-lookup"><span data-stu-id="f01dc-265">Automatically run prerequisite commands</span></span>

<span data-ttu-id="f01dc-266">有些命令會執行必要條件命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-266">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="f01dc-267">如果您未執行必要條件命令，您會收到錯誤。</span><span class="sxs-lookup"><span data-stu-id="f01dc-267">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="f01dc-268">例如，執行此 `download` 命令但不 `fileinfo` 會傳回錯誤。</span><span class="sxs-lookup"><span data-stu-id="f01dc-268">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="f01dc-269">您可以使用自動旗標自動執行必要命令，例如：</span><span class="sxs-lookup"><span data-stu-id="f01dc-269">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="f01dc-270">執行 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="f01dc-270">Run a PowerShell script</span></span> 

<span data-ttu-id="f01dc-271">在您可以執行 PowerShell 腳本之前，您必須先將其上傳至文件庫。</span><span class="sxs-lookup"><span data-stu-id="f01dc-271">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="f01dc-272">將腳本上傳至文件庫之後，請使用 `run` 命令來執行腳本。</span><span class="sxs-lookup"><span data-stu-id="f01dc-272">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="f01dc-273">如果您想要在會話中使用未簽署的腳本，您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的設定。</span><span class="sxs-lookup"><span data-stu-id="f01dc-273">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="f01dc-274">允許使用未簽署的腳本可能會增加威脅的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="f01dc-274">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="f01dc-275">套用命令參數</span><span class="sxs-lookup"><span data-stu-id="f01dc-275">Apply command parameters</span></span>

- <span data-ttu-id="f01dc-276">若要瞭解命令參數的資訊，請參閱主控台説明。</span><span class="sxs-lookup"><span data-stu-id="f01dc-276">View the console help to learn about command parameters.</span></span> <span data-ttu-id="f01dc-277">若要瞭解個別命令，請執行：</span><span class="sxs-lookup"><span data-stu-id="f01dc-277">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="f01dc-278">對命令套用參數時，請注意，參數的處理方式取決於固定順序：</span><span class="sxs-lookup"><span data-stu-id="f01dc-278">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="f01dc-279">指定固定順序以外的參數時，在提供值之前，請使用連字號指定參數的名稱：</span><span class="sxs-lookup"><span data-stu-id="f01dc-279">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="f01dc-280">使用具有必要條件命令的命令時，您可以使用旗標：</span><span class="sxs-lookup"><span data-stu-id="f01dc-280">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="f01dc-281">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto` 。</span><span class="sxs-lookup"><span data-stu-id="f01dc-281">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="f01dc-282">支援的輸出類型</span><span class="sxs-lookup"><span data-stu-id="f01dc-282">Supported output types</span></span>

<span data-ttu-id="f01dc-283">Live response 支援表格和 JSON 格式的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="f01dc-283">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="f01dc-284">針對每個命令，都有預設的輸出行為。</span><span class="sxs-lookup"><span data-stu-id="f01dc-284">For each command, there's a default output behavior.</span></span> <span data-ttu-id="f01dc-285">您可以使用下列命令，修改您偏好輸出格式的輸出：</span><span class="sxs-lookup"><span data-stu-id="f01dc-285">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="f01dc-286">因為空間有限，所以表格格式會顯示較少的欄位。</span><span class="sxs-lookup"><span data-stu-id="f01dc-286">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="f01dc-287">若要查看輸出中的更多詳細資料，您可以使用 JSON 輸出命令，以顯示更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f01dc-287">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="f01dc-288">支援的輸出管道</span><span class="sxs-lookup"><span data-stu-id="f01dc-288">Supported output pipes</span></span>

<span data-ttu-id="f01dc-289">Live response 支援將輸出管道傳送至 CLI 和檔案。</span><span class="sxs-lookup"><span data-stu-id="f01dc-289">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="f01dc-290">CLI 是預設的輸出行為。</span><span class="sxs-lookup"><span data-stu-id="f01dc-290">CLI is the default output behavior.</span></span> <span data-ttu-id="f01dc-291">您可以使用下列命令，將輸出輸送至檔案： [命令] > [filename] .txt。</span><span class="sxs-lookup"><span data-stu-id="f01dc-291">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="f01dc-292">範例：</span><span class="sxs-lookup"><span data-stu-id="f01dc-292">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="f01dc-293">查看命令記錄檔</span><span class="sxs-lookup"><span data-stu-id="f01dc-293">View the command log</span></span>

<span data-ttu-id="f01dc-294">選取 [ **命令記錄** ] 索引標籤，以查看在會話期間用於裝置的命令。</span><span class="sxs-lookup"><span data-stu-id="f01dc-294">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="f01dc-295">每個命令都會以完整的詳細資料來追蹤：</span><span class="sxs-lookup"><span data-stu-id="f01dc-295">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="f01dc-296">ID</span><span class="sxs-lookup"><span data-stu-id="f01dc-296">ID</span></span>
- <span data-ttu-id="f01dc-297">命令列</span><span class="sxs-lookup"><span data-stu-id="f01dc-297">Command line</span></span>
- <span data-ttu-id="f01dc-298">持續時間</span><span class="sxs-lookup"><span data-stu-id="f01dc-298">Duration</span></span>
- <span data-ttu-id="f01dc-299">狀態和輸入或輸出側條</span><span class="sxs-lookup"><span data-stu-id="f01dc-299">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="f01dc-300">限制</span><span class="sxs-lookup"><span data-stu-id="f01dc-300">Limitations</span></span>

- <span data-ttu-id="f01dc-301">Live 回應會話一次僅限10個 live 回應會話。</span><span class="sxs-lookup"><span data-stu-id="f01dc-301">Live response sessions are limited to 10 live response sessions at a time.</span></span>
- <span data-ttu-id="f01dc-302">不支援大規模命令執行。</span><span class="sxs-lookup"><span data-stu-id="f01dc-302">Large-scale command execution is not supported.</span></span>
- <span data-ttu-id="f01dc-303">Live response session 非使用中超時值為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="f01dc-303">Live response session inactive timeout value is 5 minutes.</span></span> 
- <span data-ttu-id="f01dc-304">使用者一次只能啟動一個會話。</span><span class="sxs-lookup"><span data-stu-id="f01dc-304">A user can only initiate one session at a time.</span></span>
- <span data-ttu-id="f01dc-305">一個裝置一次只能在一個會話中。</span><span class="sxs-lookup"><span data-stu-id="f01dc-305">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="f01dc-306">適用下列檔案大小限制：</span><span class="sxs-lookup"><span data-stu-id="f01dc-306">The following file size limits apply:</span></span>
   - <span data-ttu-id="f01dc-307">`getfile` 限制： 3 GB</span><span class="sxs-lookup"><span data-stu-id="f01dc-307">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="f01dc-308">`fileinfo` 限制： 10 GB</span><span class="sxs-lookup"><span data-stu-id="f01dc-308">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="f01dc-309">`library` 限制： 250 MB</span><span class="sxs-lookup"><span data-stu-id="f01dc-309">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="f01dc-310">相關文章</span><span class="sxs-lookup"><span data-stu-id="f01dc-310">Related article</span></span>
- [<span data-ttu-id="f01dc-311">Live response 命令範例</span><span class="sxs-lookup"><span data-stu-id="f01dc-311">Live response command examples</span></span>](live-response-command-examples.md)
