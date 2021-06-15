---
title: 啟用受控資料夾存取權
keywords: 可控資料夾存取、windows 10、windows defender、勒索軟體、保護、檔案、資料夾、啟用、開啟、使用
description: 瞭解如何透過啟用「控制資料夾存取」來保護您的重要檔案
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ed0859e6018d171b48aac83d394eacbd2163c37b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924680"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="40405-104">啟用受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="40405-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40405-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="40405-105">**Applies to:**</span></span>
- [<span data-ttu-id="40405-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="40405-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="40405-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40405-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="40405-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="40405-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="40405-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="40405-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="40405-110">[受控制的資料夾存取](controlled-folders.md) 可協助您保護寶貴的資料，避免惡意應用程式和威脅（如勒索軟體）。</span><span class="sxs-lookup"><span data-stu-id="40405-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="40405-111">[受管理的資料夾存取] 包含在 Windows 10 和 Windows Server 2019。</span><span class="sxs-lookup"><span data-stu-id="40405-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="40405-112">您可以使用下列任何一種方法來啟用受控資料夾存取：</span><span class="sxs-lookup"><span data-stu-id="40405-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="40405-113">Windows 安全性應用程式</span><span class="sxs-lookup"><span data-stu-id="40405-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="40405-114">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="40405-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="40405-115">移動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="40405-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="40405-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="40405-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="40405-117">群組原則</span><span class="sxs-lookup"><span data-stu-id="40405-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="40405-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="40405-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="40405-119">[稽核模式](evaluate-controlled-folder-access.md) 可讓您測試功能 (和審閱事件) 的運作方式，而不會影響裝置的正常使用。</span><span class="sxs-lookup"><span data-stu-id="40405-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="40405-120">停用本機管理員清單合併的群組原則設定會覆寫「控制的資料夾存取」設定。</span><span class="sxs-lookup"><span data-stu-id="40405-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="40405-121">它們也會覆寫受保護的資料夾，以及由本機系統管理員透過「可控資料夾存取」所設定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="40405-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="40405-122">這些原則包括：</span><span class="sxs-lookup"><span data-stu-id="40405-122">These policies include:</span></span>

* <span data-ttu-id="40405-123">Microsoft Defender 防毒軟體 **設定清單的本機系統管理員合併行為**</span><span class="sxs-lookup"><span data-stu-id="40405-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="40405-124">System Center Endpoint Protection **允許使用者新增排除和覆寫**</span><span class="sxs-lookup"><span data-stu-id="40405-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="40405-125">如需停用本機清單合併的詳細資訊，請參閱 [防止或允許使用者從本機修改 Microsoft DEFENDER AV 原則設定](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="40405-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="40405-126">Windows 安全性應用程式</span><span class="sxs-lookup"><span data-stu-id="40405-126">Windows Security app</span></span>

1. <span data-ttu-id="40405-127">選取工作列中的盾牌圖示，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="40405-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="40405-128">您也可以搜尋 **Defender** 的 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="40405-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="40405-129">在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [ **勒索軟體防護**]。</span><span class="sxs-lookup"><span data-stu-id="40405-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="40405-130">將「 **受控資料夾存取** 」的參數設為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="40405-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="40405-131">如果已使用群組原則、PowerShell 或 MDM csp 設定受管理的資料夾存取，則在重新開機裝置後，該狀態會在 Windows 安全性應用程式中變更。</span><span class="sxs-lookup"><span data-stu-id="40405-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="40405-132">如果使用任何工具將功能設定為 [**審計模式]** ，Windows 安全性應用程式會顯示狀態為 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="40405-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="40405-133">如果您要保護使用者設定檔資料，建議使用者設定檔應位於預設的 Windows 安裝磁片磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="40405-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="40405-134">端點管理員</span><span class="sxs-lookup"><span data-stu-id="40405-134">Endpoint Manager</span></span>

1. <span data-ttu-id="40405-135">登入 [端點管理員](https://endpoint.microsoft.com)，然後開啟 **端點安全性**。</span><span class="sxs-lookup"><span data-stu-id="40405-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="40405-136">移至 **攻擊面減少**  >  **原則**。</span><span class="sxs-lookup"><span data-stu-id="40405-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="40405-137">選取 [**平臺**]，選擇 [ **Windows 10 和更新版本**]，然後選取 [設定檔 **攻擊面減少規則**  >  **建立**]。</span><span class="sxs-lookup"><span data-stu-id="40405-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="40405-138">命名原則並新增描述。</span><span class="sxs-lookup"><span data-stu-id="40405-138">Name the policy and add a description.</span></span> <span data-ttu-id="40405-139">選取 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="40405-139">Select **Next**.</span></span>

5.  <span data-ttu-id="40405-140">向下滾動至底部，選取 [ **啟用資料夾保護** ] 下拉式清單，然後選擇 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="40405-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="40405-141">選取 **需要受保護之其他資料夾的清單** ，並新增需要保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="40405-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="40405-142">選取 **具有受保護資料夾存取權的應用程式清單** ，並新增具有受保護資料夾存取權的應用程式。</span><span class="sxs-lookup"><span data-stu-id="40405-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="40405-143">選取 [ **從攻擊面減少規則排除檔案和路徑** ]，並新增需要從攻擊面減少規則中排除的檔案和路徑。</span><span class="sxs-lookup"><span data-stu-id="40405-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="40405-144">選取設定檔 **指派**，並指派給 **所有使用者 & 所有裝置**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="40405-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="40405-145">選取 **[下一步]** 儲存每個開啟的刀片式伺服器，然後 **建立**。</span><span class="sxs-lookup"><span data-stu-id="40405-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="40405-146">應用程式支援萬用字元，但不適用於資料夾。</span><span class="sxs-lookup"><span data-stu-id="40405-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="40405-147">子資料夾不受保護。</span><span class="sxs-lookup"><span data-stu-id="40405-147">Subfolders are not protected.</span></span> <span data-ttu-id="40405-148">允許的應用程式會繼續觸發事件，直到重新開機為止。</span><span class="sxs-lookup"><span data-stu-id="40405-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="40405-149">移動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="40405-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="40405-150">使用 [/Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) configuration service PROVIDER (CSP) 以允許應用程式變更受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="40405-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="40405-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="40405-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="40405-152">在 Microsoft Endpoint Configuration Manager 中，移至 **資產及規範**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**。</span><span class="sxs-lookup"><span data-stu-id="40405-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="40405-153">選取 [**首頁**  >  **建立 Exploit Guard 原則**]。</span><span class="sxs-lookup"><span data-stu-id="40405-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="40405-154">輸入名稱和描述，選取 [ **受管理的資料夾存取**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="40405-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="40405-155">選擇封鎖或審核變更、允許其他應用程式或新增其他資料夾，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="40405-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="40405-156">Wilcard 支援應用程式，但不適用於資料夾。</span><span class="sxs-lookup"><span data-stu-id="40405-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="40405-157">子資料夾不受保護。</span><span class="sxs-lookup"><span data-stu-id="40405-157">Subfolders are not protected.</span></span> <span data-ttu-id="40405-158">允許的應用程式會繼續觸發事件，直到重新開機為止。</span><span class="sxs-lookup"><span data-stu-id="40405-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="40405-159">複查設定，然後選取 **[下一步]** 建立原則。</span><span class="sxs-lookup"><span data-stu-id="40405-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="40405-160">建立原則之後， **關閉**。</span><span class="sxs-lookup"><span data-stu-id="40405-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="40405-161">群組原則</span><span class="sxs-lookup"><span data-stu-id="40405-161">Group Policy</span></span>

1. <span data-ttu-id="40405-162">在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="40405-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="40405-163">在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。</span><span class="sxs-lookup"><span data-stu-id="40405-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="40405-164">展開樹狀目錄， **Windows 元件 > Microsoft Defender 防毒軟體 > Windows Defender Exploit Guard > 受控制的資料夾存取**。</span><span class="sxs-lookup"><span data-stu-id="40405-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="40405-165">按兩下 [ **設定受控資料夾存取** 設定]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="40405-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="40405-166">在 [選項] 區段中，您必須指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="40405-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="40405-167">**Enable** -不允許惡意和可疑應用程式對受保護資料夾中的檔案進行變更。</span><span class="sxs-lookup"><span data-stu-id="40405-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="40405-168">在 Windows 事件記錄檔中會提供通知。</span><span class="sxs-lookup"><span data-stu-id="40405-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="40405-169">**停用 (預設)** -「受管理的資料夾存取」功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="40405-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="40405-170">所有應用程式都可對受保護資料夾中的檔案進行變更。</span><span class="sxs-lookup"><span data-stu-id="40405-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="40405-171">「**審計模式**」-如果惡意或可疑應用程式嘗試對受保護資料夾中的檔案進行變更，便允許變更。</span><span class="sxs-lookup"><span data-stu-id="40405-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="40405-172">不過，它會記錄在 Windows 事件記錄檔中，您可以在其中評估對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="40405-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="40405-173">**僅封鎖磁片修改**：在 Windows 事件記錄檔中，會記錄不受信任應用程式對磁片區的嘗試。</span><span class="sxs-lookup"><span data-stu-id="40405-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="40405-174">在 [**應用程式及服務記錄**] 中，可以找到這些記錄檔 > Microsoft > Windows > Windows Defender > 作業 > ID 1123。</span><span class="sxs-lookup"><span data-stu-id="40405-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="40405-175">**僅限審核磁片修改只** 會在 [**應用程式及服務 Windows 記錄** 檔] 下的 [Windows 事件記錄 (中記錄寫入受保護的磁片磁區，  >    >    >  **Windows Defender**  >  **運作**  >  **識別碼 1124**) 。</span><span class="sxs-lookup"><span data-stu-id="40405-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="40405-176">不會記錄在 [受保護的資料夾] 中修改或刪除檔的嘗試。</span><span class="sxs-lookup"><span data-stu-id="40405-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![已啟用群組原則選項的螢幕擷取畫面和下拉式清單中選取的審計模式](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="40405-178">若要完全啟用可控資料夾存取，您必須將群組原則選項設定為 [ **啟用** ]，然後在 [選項] 下拉式功能表中選取 [ **封鎖** ]。</span><span class="sxs-lookup"><span data-stu-id="40405-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="40405-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="40405-179">PowerShell</span></span>

1. <span data-ttu-id="40405-180">在 [開始] 功能表中 **，以滑鼠** 按右鍵 [ **Windows PowerShell** ]，然後選取 [以 **系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="40405-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="40405-181">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="40405-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="40405-182">您可以指定代替來啟用 [審計模式] 中的功能 `AuditMode` `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="40405-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="40405-183">用 `Disabled` 來關閉功能。</span><span class="sxs-lookup"><span data-stu-id="40405-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="40405-184">另請參閱</span><span class="sxs-lookup"><span data-stu-id="40405-184">See also</span></span>

* [<span data-ttu-id="40405-185">使用受控資料夾存取權來保護重要資料夾</span><span class="sxs-lookup"><span data-stu-id="40405-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="40405-186">自訂受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="40405-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="40405-187">評估適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="40405-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
