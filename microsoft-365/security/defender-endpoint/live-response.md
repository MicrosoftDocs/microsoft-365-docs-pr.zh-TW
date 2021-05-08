---
title: 使用 Microsoft Defender for Endpoint 中的即時回應調查裝置上的實體
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
ms.openlocfilehash: fc1c1e0d3f68016651c04521e04ce348e5ab9a65
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246462"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="ac783-104">使用即時回應調查裝置上的實體</span><span class="sxs-lookup"><span data-stu-id="ac783-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ac783-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ac783-105">**Applies to:**</span></span>
- [<span data-ttu-id="ac783-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ac783-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ac783-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac783-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ac783-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ac783-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ac783-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="ac783-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="ac783-110">Live response 讓安全性運作小組能夠暫態存取裝置 (也稱為) 使用遠端命令介面連線的電腦。</span><span class="sxs-lookup"><span data-stu-id="ac783-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="ac783-111">這可讓您在深入調查工作中做為您的力量，並立即採取回應動作，及時包含已識別的威脅（即時）。</span><span class="sxs-lookup"><span data-stu-id="ac783-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="ac783-112">Live response 的設計目的是讓您的安全性作業小組收集法律資料、執行腳本、傳送可疑實體以進行分析、修正威脅，以及主動搜尋新興威脅，以加強調查。</span><span class="sxs-lookup"><span data-stu-id="ac783-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="ac783-113">使用 live response 時，分析員可以執行下列所有工作：</span><span class="sxs-lookup"><span data-stu-id="ac783-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="ac783-114">執行基本和高級命令，在裝置上執行調查工作。</span><span class="sxs-lookup"><span data-stu-id="ac783-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="ac783-115">下載檔案，例如惡意程式碼範例和 PowerShell 腳本的結果。</span><span class="sxs-lookup"><span data-stu-id="ac783-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="ac783-116">在背景 (new！ ) 中下載檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="ac783-117">Upload PowerShell 腳本或可執行檔至文件庫，並在租使用者層級上的裝置上執行該腳本。</span><span class="sxs-lookup"><span data-stu-id="ac783-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="ac783-118">採取或撤銷修正動作。</span><span class="sxs-lookup"><span data-stu-id="ac783-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ac783-119">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="ac783-119">Before you begin</span></span>

<span data-ttu-id="ac783-120">在裝置上啟動會話之前，請先確定您符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="ac783-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="ac783-121">**請確認您執行的是支援的 Windows 版本**。</span><span class="sxs-lookup"><span data-stu-id="ac783-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="ac783-122">裝置必須執行下列其中一個 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="ac783-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="ac783-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="ac783-123">**Windows 10**</span></span>
    - <span data-ttu-id="ac783-124">[版本 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="ac783-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="ac783-125">[版本 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) 與 [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="ac783-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="ac783-126">[版本 1809 (RS 5) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) 與 [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="ac783-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="ac783-127">[版本 1803 (RS 4) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) 與 [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="ac783-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="ac783-128">[版本 1709 (RS 3) ](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 與 [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="ac783-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="ac783-129">**Windows伺服器 2019-僅適用于公開預覽**</span><span class="sxs-lookup"><span data-stu-id="ac783-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="ac783-130">版本1903或 (隨 [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) 更新版本</span><span class="sxs-lookup"><span data-stu-id="ac783-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="ac783-131">版本 1809 (，含 [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)) </span><span class="sxs-lookup"><span data-stu-id="ac783-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="ac783-132">**從 [高級設定] 頁面啟用即時回應**。</span><span class="sxs-lookup"><span data-stu-id="ac783-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="ac783-133">您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的 [即時回應] 功能。</span><span class="sxs-lookup"><span data-stu-id="ac783-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="ac783-134">只有具有「管理安全性」或「全域系統管理員」角色的使用者可以編輯這些設定。</span><span class="sxs-lookup"><span data-stu-id="ac783-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="ac783-135">**從 [高級設定] 頁面啟用伺服器的即時回應** (建議) 。</span><span class="sxs-lookup"><span data-stu-id="ac783-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="ac783-136">只有具有「管理安全性」或「全域系統管理員」角色的使用者可以編輯這些設定。</span><span class="sxs-lookup"><span data-stu-id="ac783-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="ac783-137">**確定裝置具有指派的「自動化修正」層級**。</span><span class="sxs-lookup"><span data-stu-id="ac783-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="ac783-138">您必須至少啟用特定裝置群組的最低修正層級。</span><span class="sxs-lookup"><span data-stu-id="ac783-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="ac783-139">否則，您將無法為該群組的成員建立即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="ac783-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="ac783-140">您會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="ac783-140">You'll receive the following error:</span></span>

    ![錯誤訊息影像](images/live-response-error.png)

- <span data-ttu-id="ac783-142">**啟用 live response 未簽署的腳本執行** (選用) 。</span><span class="sxs-lookup"><span data-stu-id="ac783-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="ac783-143">允許使用未簽署的腳本可能會增加威脅的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="ac783-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="ac783-144">不建議執行未簽署的腳本，因為這樣可增加您對威脅的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="ac783-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="ac783-145">如果您必須使用它們，但是您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的設定。</span><span class="sxs-lookup"><span data-stu-id="ac783-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="ac783-146">**確定您具有適當的許可權**。</span><span class="sxs-lookup"><span data-stu-id="ac783-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="ac783-147">只有已使用適當許可權布建的使用者才能啟動會話。</span><span class="sxs-lookup"><span data-stu-id="ac783-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="ac783-148">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ac783-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="ac783-149">將檔案上傳至文件庫的選項只適用于具有適當 RBAC 許可權的選項。</span><span class="sxs-lookup"><span data-stu-id="ac783-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="ac783-150">只有委派許可權的使用者，此按鈕才會顯示為灰色。</span><span class="sxs-lookup"><span data-stu-id="ac783-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="ac783-151">您可以執行基本或高級 live 回應命令，視授與您的角色而定。</span><span class="sxs-lookup"><span data-stu-id="ac783-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="ac783-152">使用者許可權是由 RBAC 自訂角色所控制。</span><span class="sxs-lookup"><span data-stu-id="ac783-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="ac783-153">Live response 儀表板一覽</span><span class="sxs-lookup"><span data-stu-id="ac783-153">Live response dashboard overview</span></span>
<span data-ttu-id="ac783-154">當您在裝置上啟動即時回應會話時，儀表板會開啟。</span><span class="sxs-lookup"><span data-stu-id="ac783-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="ac783-155">儀表板提供會話的相關資訊，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ac783-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="ac783-156">神秘建立會話</span><span class="sxs-lookup"><span data-stu-id="ac783-156">Who created the session</span></span>
- <span data-ttu-id="ac783-157">啟動會話時</span><span class="sxs-lookup"><span data-stu-id="ac783-157">When the session started</span></span>
- <span data-ttu-id="ac783-158">會話的持續時間</span><span class="sxs-lookup"><span data-stu-id="ac783-158">The duration of the session</span></span>

<span data-ttu-id="ac783-159">儀表板也可讓您存取：</span><span class="sxs-lookup"><span data-stu-id="ac783-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="ac783-160">中斷連線會話</span><span class="sxs-lookup"><span data-stu-id="ac783-160">Disconnect session</span></span>
- <span data-ttu-id="ac783-161">Upload 檔案至文件庫</span><span class="sxs-lookup"><span data-stu-id="ac783-161">Upload files to the library</span></span> 
- <span data-ttu-id="ac783-162">命令主控台</span><span class="sxs-lookup"><span data-stu-id="ac783-162">Command console</span></span>
- <span data-ttu-id="ac783-163">命令記錄檔</span><span class="sxs-lookup"><span data-stu-id="ac783-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="ac783-164">在裝置上啟動即時回應會話</span><span class="sxs-lookup"><span data-stu-id="ac783-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="ac783-165">登入 Microsoft Defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="ac783-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="ac783-166">流覽至 [裝置] 清單頁面，然後選取要調查的裝置。</span><span class="sxs-lookup"><span data-stu-id="ac783-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="ac783-167">隨即會開啟 [裝置] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ac783-167">The devices page opens.</span></span>

3. <span data-ttu-id="ac783-168">選取 [ **啟動即時回應會話**]，以啟動即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="ac783-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="ac783-169">隨即會顯示命令主控台。</span><span class="sxs-lookup"><span data-stu-id="ac783-169">A command console is displayed.</span></span> <span data-ttu-id="ac783-170">在會話連接至裝置時等候。</span><span class="sxs-lookup"><span data-stu-id="ac783-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="ac783-171">使用內建的命令執行調查工作。</span><span class="sxs-lookup"><span data-stu-id="ac783-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="ac783-172">如需詳細資訊，請參閱 [Live response 命令](#live-response-commands)。</span><span class="sxs-lookup"><span data-stu-id="ac783-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="ac783-173">完成調查後，請選取 **[中斷連線會話]**，然後選取 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="ac783-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="ac783-174">即時回應命令</span><span class="sxs-lookup"><span data-stu-id="ac783-174">Live response commands</span></span>

<span data-ttu-id="ac783-175">您可以執行基本或高級 live 回應命令，視授與您的角色而定。</span><span class="sxs-lookup"><span data-stu-id="ac783-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="ac783-176">使用者權限是由 RBAC 自訂角色所控制。</span><span class="sxs-lookup"><span data-stu-id="ac783-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="ac783-177">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ac783-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="ac783-178">Live response 是雲端型互動命令介面，如此一來，特定的命令體驗可能會因回應時間而異，取決於使用者與目標裝置之間的網路品質和系統負載。</span><span class="sxs-lookup"><span data-stu-id="ac783-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="ac783-179">基本命令</span><span class="sxs-lookup"><span data-stu-id="ac783-179">Basic commands</span></span>

<span data-ttu-id="ac783-180">下列命令適用于授與執行 **基本** live 回應命令之功能的使用者角色。</span><span class="sxs-lookup"><span data-stu-id="ac783-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="ac783-181">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ac783-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="ac783-182">命令</span><span class="sxs-lookup"><span data-stu-id="ac783-182">Command</span></span> | <span data-ttu-id="ac783-183">描述</span><span class="sxs-lookup"><span data-stu-id="ac783-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="ac783-184">變更目前的目錄。</span><span class="sxs-lookup"><span data-stu-id="ac783-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="ac783-185">清除主控台畫面。</span><span class="sxs-lookup"><span data-stu-id="ac783-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="ac783-186">啟動裝置的即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="ac783-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="ac783-187">顯示所有使用中的連線。</span><span class="sxs-lookup"><span data-stu-id="ac783-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="ac783-188">顯示目錄中的檔案及子目錄清單。</span><span class="sxs-lookup"><span data-stu-id="ac783-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="ac783-189">顯示裝置上安裝的所有驅動程式。</span><span class="sxs-lookup"><span data-stu-id="ac783-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="ac783-190">將指定的工作置於前臺，使其成為目前工作。</span><span class="sxs-lookup"><span data-stu-id="ac783-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="ac783-191">附注： fg 採用工作中提供的「命令識別碼」，而不是 PID</span><span class="sxs-lookup"><span data-stu-id="ac783-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="ac783-192">取得檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ac783-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="ac783-193">以指定的名稱在裝置上尋找檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="ac783-194">下載檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="ac783-195">提供即時回應命令的説明資訊。</span><span class="sxs-lookup"><span data-stu-id="ac783-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="ac783-196">顯示目前執行中的工作、其識別碼和狀態。</span><span class="sxs-lookup"><span data-stu-id="ac783-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="ac783-197">顯示裝置上所有已知的持久性方法。</span><span class="sxs-lookup"><span data-stu-id="ac783-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="ac783-198">顯示裝置上執行的所有進程。</span><span class="sxs-lookup"><span data-stu-id="ac783-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="ac783-199">顯示登錄值。</span><span class="sxs-lookup"><span data-stu-id="ac783-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="ac783-200">顯示裝置上的所有排程任務。</span><span class="sxs-lookup"><span data-stu-id="ac783-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="ac783-201">顯示裝置上的所有服務。</span><span class="sxs-lookup"><span data-stu-id="ac783-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="ac783-202">設定終端的記錄模式進行調試。</span><span class="sxs-lookup"><span data-stu-id="ac783-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="ac783-203">Advanced 命令</span><span class="sxs-lookup"><span data-stu-id="ac783-203">Advanced commands</span></span>
<span data-ttu-id="ac783-204">下列命令適用于授與執行「 **高級** 即時回應」命令功能的使用者角色。</span><span class="sxs-lookup"><span data-stu-id="ac783-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="ac783-205">如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="ac783-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="ac783-206">命令</span><span class="sxs-lookup"><span data-stu-id="ac783-206">Command</span></span> | <span data-ttu-id="ac783-207">描述</span><span class="sxs-lookup"><span data-stu-id="ac783-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="ac783-208">分析具有各種 incrimination 引擎的實體，以達到判定。</span><span class="sxs-lookup"><span data-stu-id="ac783-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="ac783-209">從裝置上的文件庫執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="ac783-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="ac783-210">列出已上傳至 live response library 的檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="ac783-211">將檔案從文件庫放入裝置。</span><span class="sxs-lookup"><span data-stu-id="ac783-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="ac783-212">檔案儲存在工作資料夾中，而且會在預設重新開機裝置時刪除。</span><span class="sxs-lookup"><span data-stu-id="ac783-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="ac783-213">在裝置上 Remediates 實體。</span><span class="sxs-lookup"><span data-stu-id="ac783-213">Remediates an entity on the device.</span></span> <span data-ttu-id="ac783-214">修正動作會因實體類型而異：</span><span class="sxs-lookup"><span data-stu-id="ac783-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="ac783-215">-File： delete</span><span class="sxs-lookup"><span data-stu-id="ac783-215">- File: delete</span></span><br><span data-ttu-id="ac783-216">-進程：停止、刪除影像檔</span><span class="sxs-lookup"><span data-stu-id="ac783-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="ac783-217">-服務：停止、刪除映射檔</span><span class="sxs-lookup"><span data-stu-id="ac783-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="ac783-218">-登錄專案：刪除</span><span class="sxs-lookup"><span data-stu-id="ac783-218">- Registry entry: delete</span></span><br><span data-ttu-id="ac783-219">-排程任務：移除</span><span class="sxs-lookup"><span data-stu-id="ac783-219">- Scheduled task: remove</span></span><br><span data-ttu-id="ac783-220">-Startup 資料夾專案：刪除檔案</span><span class="sxs-lookup"><span data-stu-id="ac783-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="ac783-221">注意：此命令具有必要條件命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="ac783-222">您可以搭配使用此 `-auto` 命令 `remediate` ，以自動執行必要條件命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="ac783-223">還原已修正的實體。</span><span class="sxs-lookup"><span data-stu-id="ac783-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="ac783-224">使用即時回應命令</span><span class="sxs-lookup"><span data-stu-id="ac783-224">Use live response commands</span></span>

<span data-ttu-id="ac783-225">您可以在主控台中使用的命令遵循與[Windows 命令](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)類似的原則。</span><span class="sxs-lookup"><span data-stu-id="ac783-225">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="ac783-226">Advanced 命令提供一組更為強大的動作，可讓您採取更強大的動作，例如下載和上傳檔案、在裝置上執行腳本，以及對實體採取修正動作。</span><span class="sxs-lookup"><span data-stu-id="ac783-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="ac783-227">從裝置取得檔案</span><span class="sxs-lookup"><span data-stu-id="ac783-227">Get a file from the device</span></span>

<span data-ttu-id="ac783-228">例如，如果您想要從您正在調查的裝置取得檔案，您可以使用此 `getfile` 命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="ac783-229">這可讓您儲存裝置中的檔案進行進一步調查。</span><span class="sxs-lookup"><span data-stu-id="ac783-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="ac783-230">適用下列檔案大小限制：</span><span class="sxs-lookup"><span data-stu-id="ac783-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="ac783-231">`getfile` 限制： 3 GB</span><span class="sxs-lookup"><span data-stu-id="ac783-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="ac783-232">`fileinfo` 限制： 10 GB</span><span class="sxs-lookup"><span data-stu-id="ac783-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="ac783-233">`library` 限制： 250 MB</span><span class="sxs-lookup"><span data-stu-id="ac783-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="ac783-234">下載背景中的檔案</span><span class="sxs-lookup"><span data-stu-id="ac783-234">Download a file in the background</span></span>

<span data-ttu-id="ac783-235">若要讓您的安全性運作小組繼續調查受影響的裝置，現在可以在後臺下載檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="ac783-236">若要在後臺下載檔案，請在 live response 命令主控台中輸入 `download <file_path> &` 。</span><span class="sxs-lookup"><span data-stu-id="ac783-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="ac783-237">如果您正在等候下載檔案，您可以使用 Ctrl+Z 將檔案移至背景。</span><span class="sxs-lookup"><span data-stu-id="ac783-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="ac783-238">若要將檔案下載移至前臺，請在 live response 命令主控台中輸入 `fg <command_id>` 。</span><span class="sxs-lookup"><span data-stu-id="ac783-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="ac783-239">以下為一些範例：</span><span class="sxs-lookup"><span data-stu-id="ac783-239">Here are some examples:</span></span>


|<span data-ttu-id="ac783-240">命令</span><span class="sxs-lookup"><span data-stu-id="ac783-240">Command</span></span>  |<span data-ttu-id="ac783-241">功能</span><span class="sxs-lookup"><span data-stu-id="ac783-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="ac783-242">開始在背景中下載名為 *some_file.exe* 的檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="ac783-243">會傳回具有命令識別碼 *1234* 至前景的下載。</span><span class="sxs-lookup"><span data-stu-id="ac783-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="ac783-244">將檔案放入文件庫中</span><span class="sxs-lookup"><span data-stu-id="ac783-244">Put a file in the library</span></span>

<span data-ttu-id="ac783-245">Live response 具有可讓您存放盤案的文件庫。</span><span class="sxs-lookup"><span data-stu-id="ac783-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="ac783-246">文件庫儲存 (例如腳本) ，可在租使用者層級的即時回應會話中執行。</span><span class="sxs-lookup"><span data-stu-id="ac783-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="ac783-247">Live response 允許執行 PowerShell 腳本，但是您必須先將檔案放入文件庫中，才可執行這些檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="ac783-248">您可以在用來啟動 live 回應會話的裝置上，使用可在其上執行的 PowerShell 腳本集合。</span><span class="sxs-lookup"><span data-stu-id="ac783-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="ac783-249">上傳文件庫中的檔案</span><span class="sxs-lookup"><span data-stu-id="ac783-249">To upload a file in the library</span></span>

1. <span data-ttu-id="ac783-250">按一下 [ **Upload 檔案至文件庫**]。</span><span class="sxs-lookup"><span data-stu-id="ac783-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="ac783-251">按一下 **[流覽]** 並選取檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="ac783-252">提供簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="ac783-252">Provide a brief description.</span></span>

4. <span data-ttu-id="ac783-253">指定您是否要覆寫具有相同名稱的檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="ac783-254">如果您想要的話，請知道腳本所需的參數，然後選取 [腳本參數] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ac783-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="ac783-255">在 [文字] 欄位中，輸入範例和描述。</span><span class="sxs-lookup"><span data-stu-id="ac783-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="ac783-256">按一下 [ **確認**]。</span><span class="sxs-lookup"><span data-stu-id="ac783-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="ac783-257"> (選用) 若要確認已將檔案上傳至文件庫，請執行 `library` 命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="ac783-258">取消命令</span><span class="sxs-lookup"><span data-stu-id="ac783-258">Cancel a command</span></span>
<span data-ttu-id="ac783-259">在會話期間，您可以隨時按 CTRL+C 取消命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="ac783-260">使用此快捷方式不會停止代理端中的命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="ac783-261">它只會取消入口網站中的命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="ac783-262">這樣一來，在取消變更時，"修正" 作業可能會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="ac783-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="ac783-263">執行 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="ac783-263">Run a PowerShell script</span></span> 

<span data-ttu-id="ac783-264">在您可以執行 PowerShell 腳本之前，您必須先將其上傳至文件庫。</span><span class="sxs-lookup"><span data-stu-id="ac783-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="ac783-265">將腳本上傳至文件庫之後，請使用 `run` 命令來執行腳本。</span><span class="sxs-lookup"><span data-stu-id="ac783-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="ac783-266">如果您想要在會話中使用未簽署的腳本，您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的設定。</span><span class="sxs-lookup"><span data-stu-id="ac783-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="ac783-267">允許使用未簽署的腳本可能會增加威脅的暴露程度。</span><span class="sxs-lookup"><span data-stu-id="ac783-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="ac783-268">套用命令參數</span><span class="sxs-lookup"><span data-stu-id="ac783-268">Apply command parameters</span></span>

- <span data-ttu-id="ac783-269">若要瞭解命令參數的資訊，請參閱主控台説明。</span><span class="sxs-lookup"><span data-stu-id="ac783-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="ac783-270">若要瞭解個別命令，請執行：</span><span class="sxs-lookup"><span data-stu-id="ac783-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="ac783-271">對命令套用參數時，請注意，參數的處理方式取決於固定順序：</span><span class="sxs-lookup"><span data-stu-id="ac783-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="ac783-272">指定固定順序以外的參數時，在提供值之前，請使用連字號指定參數的名稱：</span><span class="sxs-lookup"><span data-stu-id="ac783-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="ac783-273">使用具有必要條件命令的命令時，您可以使用旗標：</span><span class="sxs-lookup"><span data-stu-id="ac783-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="ac783-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto` 。</span><span class="sxs-lookup"><span data-stu-id="ac783-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="ac783-275">支援的輸出類型</span><span class="sxs-lookup"><span data-stu-id="ac783-275">Supported output types</span></span>

<span data-ttu-id="ac783-276">Live response 支援表格和 JSON 格式的輸出類型。</span><span class="sxs-lookup"><span data-stu-id="ac783-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="ac783-277">針對每個命令，都有預設的輸出行為。</span><span class="sxs-lookup"><span data-stu-id="ac783-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="ac783-278">您可以使用下列命令，修改您偏好輸出格式的輸出：</span><span class="sxs-lookup"><span data-stu-id="ac783-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="ac783-279">因為空間有限，所以表格格式會顯示較少的欄位。</span><span class="sxs-lookup"><span data-stu-id="ac783-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="ac783-280">若要查看輸出中的更多詳細資料，您可以使用 JSON 輸出命令，以顯示更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ac783-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="ac783-281">支援的輸出管道</span><span class="sxs-lookup"><span data-stu-id="ac783-281">Supported output pipes</span></span>

<span data-ttu-id="ac783-282">Live response 支援將輸出管道傳送至 CLI 和檔案。</span><span class="sxs-lookup"><span data-stu-id="ac783-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="ac783-283">CLI 是預設的輸出行為。</span><span class="sxs-lookup"><span data-stu-id="ac783-283">CLI is the default output behavior.</span></span> <span data-ttu-id="ac783-284">您可以使用下列命令，將輸出輸送至檔案： [命令] > [filename] .txt。</span><span class="sxs-lookup"><span data-stu-id="ac783-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="ac783-285">範例：</span><span class="sxs-lookup"><span data-stu-id="ac783-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="ac783-286">查看命令記錄檔</span><span class="sxs-lookup"><span data-stu-id="ac783-286">View the command log</span></span>

<span data-ttu-id="ac783-287">選取 [ **命令記錄** ] 索引標籤，以查看在會話期間用於裝置的命令。</span><span class="sxs-lookup"><span data-stu-id="ac783-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="ac783-288">每個命令都會以完整的詳細資料來追蹤：</span><span class="sxs-lookup"><span data-stu-id="ac783-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="ac783-289">ID</span><span class="sxs-lookup"><span data-stu-id="ac783-289">ID</span></span>
- <span data-ttu-id="ac783-290">命令列</span><span class="sxs-lookup"><span data-stu-id="ac783-290">Command line</span></span>
- <span data-ttu-id="ac783-291">持續時間</span><span class="sxs-lookup"><span data-stu-id="ac783-291">Duration</span></span>
- <span data-ttu-id="ac783-292">狀態和輸入或輸出側條</span><span class="sxs-lookup"><span data-stu-id="ac783-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="ac783-293">限制</span><span class="sxs-lookup"><span data-stu-id="ac783-293">Limitations</span></span>

- <span data-ttu-id="ac783-294">Live 回應會話一次僅限25個即時回應會話。</span><span class="sxs-lookup"><span data-stu-id="ac783-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="ac783-295">Live response session 非使用中超時值為30分鐘。</span><span class="sxs-lookup"><span data-stu-id="ac783-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="ac783-296">使用者最多可以啟動10個同時會話。</span><span class="sxs-lookup"><span data-stu-id="ac783-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="ac783-297">一個裝置一次只能在一個會話中。</span><span class="sxs-lookup"><span data-stu-id="ac783-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="ac783-298">適用下列檔案大小限制：</span><span class="sxs-lookup"><span data-stu-id="ac783-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="ac783-299">`getfile` 限制： 3 GB</span><span class="sxs-lookup"><span data-stu-id="ac783-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="ac783-300">`fileinfo` 限制： 10 GB</span><span class="sxs-lookup"><span data-stu-id="ac783-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="ac783-301">`library` 限制： 250 MB</span><span class="sxs-lookup"><span data-stu-id="ac783-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="ac783-302">相關文章</span><span class="sxs-lookup"><span data-stu-id="ac783-302">Related article</span></span>
- [<span data-ttu-id="ac783-303">即時回應命令範例</span><span class="sxs-lookup"><span data-stu-id="ac783-303">Live response command examples</span></span>](live-response-command-examples.md)
