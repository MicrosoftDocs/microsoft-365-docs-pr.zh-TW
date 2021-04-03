---
title: 啟用受控資料夾存取權
keywords: 可控資料夾存取、windows 10、windows defender、勒索軟體、保護、檔案、資料夾、啟用、開啟、使用
description: 瞭解如何透過啟用「控制資料夾存取」來保護您的重要檔案
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: ee87ac3bdfe88596a5f1625904af53499488f35f
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571005"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="2e12f-104">啟用受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="2e12f-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2e12f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2e12f-105">**Applies to:**</span></span>
- [<span data-ttu-id="2e12f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2e12f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2e12f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e12f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2e12f-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2e12f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2e12f-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2e12f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="2e12f-110">[受控制的資料夾存取](controlled-folders.md) 可協助您保護寶貴的資料，避免惡意應用程式和威脅（如勒索軟體）。</span><span class="sxs-lookup"><span data-stu-id="2e12f-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="2e12f-111">Windows 10 和 Windows Server 2019 隨附的受管理資料夾存取。</span><span class="sxs-lookup"><span data-stu-id="2e12f-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="2e12f-112">您可以使用下列任何一種方法來啟用受控資料夾存取：</span><span class="sxs-lookup"><span data-stu-id="2e12f-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="2e12f-113">Windows 安全性應用程式</span><span class="sxs-lookup"><span data-stu-id="2e12f-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="2e12f-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2e12f-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="2e12f-115">移動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="2e12f-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="2e12f-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2e12f-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="2e12f-117">群組原則</span><span class="sxs-lookup"><span data-stu-id="2e12f-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="2e12f-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e12f-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="2e12f-119">[稽核模式](evaluate-controlled-folder-access.md) 可讓您測試功能 (和審閱事件) 的運作方式，而不會影響裝置的正常使用。</span><span class="sxs-lookup"><span data-stu-id="2e12f-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="2e12f-120">停用本機管理員清單合併的群組原則設定會覆寫「控制的資料夾存取」設定。</span><span class="sxs-lookup"><span data-stu-id="2e12f-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="2e12f-121">它們也會覆寫受保護的資料夾，以及由本機系統管理員透過「可控資料夾存取」所設定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="2e12f-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="2e12f-122">這些原則包括：</span><span class="sxs-lookup"><span data-stu-id="2e12f-122">These policies include:</span></span>

* <span data-ttu-id="2e12f-123">Microsoft Defender 防病毒 **設定清單的本機系統管理員合併行為**</span><span class="sxs-lookup"><span data-stu-id="2e12f-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="2e12f-124">System Center Endpoint Protection **允許使用者新增排除和覆寫**</span><span class="sxs-lookup"><span data-stu-id="2e12f-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="2e12f-125">如需停用本機清單合併的詳細資訊，請參閱 [防止或允許使用者從本機修改 Microsoft DEFENDER AV 原則設定](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)。</span><span class="sxs-lookup"><span data-stu-id="2e12f-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="2e12f-126">Windows 安全性應用程式</span><span class="sxs-lookup"><span data-stu-id="2e12f-126">Windows Security app</span></span>

1. <span data-ttu-id="2e12f-127">選取工作列中的盾牌圖示，以開啟 [Windows 安全性] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="2e12f-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="2e12f-128">您也可以搜尋 **Defender** 的 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="2e12f-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="2e12f-129">在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [ **勒索軟體防護**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="2e12f-130">將「 **受控資料夾存取** 」的參數設為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="2e12f-131">如果已使用群組原則、PowerShell 或 MDM Csp 設定受管理的資料夾存取，則在重新開機裝置後，系統會在 Windows 安全性應用程式中變更狀態。</span><span class="sxs-lookup"><span data-stu-id="2e12f-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="2e12f-132">如果使用任何工具將功能設定為 [ **稽核模式]** ，Windows 安全性應用程式就會顯示狀態為 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="2e12f-133">如果您要保護使用者設定檔資料，建議使用者設定檔應位於預設 Windows 安裝磁片磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="2e12f-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="2e12f-134">Intune</span><span class="sxs-lookup"><span data-stu-id="2e12f-134">Intune</span></span>

1. <span data-ttu-id="2e12f-135">登入 [Azure 入口網站](https://portal.azure.com) 並開啟 Intune。</span><span class="sxs-lookup"><span data-stu-id="2e12f-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="2e12f-136">移至 **裝置配置**  >  **檔**  >  **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="2e12f-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="2e12f-137">命名設定檔，請選擇 [ **Windows 10 和更新版本** ] 和 [ **Endpoint protection**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="2e12f-138">![建立 endpoint protection 設定檔](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="2e12f-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="2e12f-139">移至 **設定**  >  **Windows Defender exploit Guard**  >  **受控制的資料夾存取**  >  **啟用**。</span><span class="sxs-lookup"><span data-stu-id="2e12f-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="2e12f-140">輸入可存取受保護資料夾之每個應用程式的路徑，以及任何需要保護之其他資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="2e12f-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="2e12f-141">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-141">Select **Add**.</span></span><br/> <span data-ttu-id="2e12f-142">![啟用 Intune 中的可控資料夾存取](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="2e12f-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="2e12f-143">Wilcard 支援應用程式，但不適用於資料夾。</span><span class="sxs-lookup"><span data-stu-id="2e12f-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="2e12f-144">子資料夾不受保護。</span><span class="sxs-lookup"><span data-stu-id="2e12f-144">Subfolders are not protected.</span></span> <span data-ttu-id="2e12f-145">允許的應用程式會繼續觸發事件，直到重新開機為止。</span><span class="sxs-lookup"><span data-stu-id="2e12f-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="2e12f-146">選取 **[確定]** 以儲存每個開啟的刀片式伺服器並 **建立**。</span><span class="sxs-lookup"><span data-stu-id="2e12f-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="2e12f-147">選取設定檔 **指派**，並指派給 **所有使用者 & 所有裝置** 及 **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="2e12f-148">移動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="2e12f-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="2e12f-149">使用 [/Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service PROVIDER (CSP) 以允許應用程式變更受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="2e12f-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="2e12f-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="2e12f-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="2e12f-151">在 Microsoft 端點 Configuration Manager 中，移至 [**資產和合規性**  >  **端點防護**] 「  >  **Windows Defender 利用防護**」。</span><span class="sxs-lookup"><span data-stu-id="2e12f-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="2e12f-152">選取 [**首頁**  >  **建立 Exploit Guard 原則**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="2e12f-153">輸入名稱和描述，選取 [ **受管理的資料夾存取**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2e12f-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="2e12f-154">選擇封鎖或審核變更、允許其他應用程式或新增其他資料夾，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="2e12f-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="2e12f-155">Wilcard 支援應用程式，但不適用於資料夾。</span><span class="sxs-lookup"><span data-stu-id="2e12f-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="2e12f-156">子資料夾不受保護。</span><span class="sxs-lookup"><span data-stu-id="2e12f-156">Subfolders are not protected.</span></span> <span data-ttu-id="2e12f-157">允許的應用程式會繼續觸發事件，直到重新開機為止。</span><span class="sxs-lookup"><span data-stu-id="2e12f-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="2e12f-158">複查設定，然後選取 **[下一步]** 建立原則。</span><span class="sxs-lookup"><span data-stu-id="2e12f-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="2e12f-159">建立原則之後， **關閉**。</span><span class="sxs-lookup"><span data-stu-id="2e12f-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="2e12f-160">群組原則</span><span class="sxs-lookup"><span data-stu-id="2e12f-160">Group Policy</span></span>

1. <span data-ttu-id="2e12f-161">在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="2e12f-162">在 [**群組原則管理編輯器**] 中，移至 [電腦設定]，然後選取 [**系統\*\*\*\*管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="2e12f-163">在 **Microsoft Defender 防病毒 > Windows Defender Exploit Guard > 可控資料夾存取 >** 中，展開 [windows 元件] 的樹狀目錄。</span><span class="sxs-lookup"><span data-stu-id="2e12f-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="2e12f-164">按兩下 [ **設定受控資料夾存取** 設定]，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="2e12f-165">在 [選項] 區段中，您必須指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="2e12f-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="2e12f-166">**Enable** -不允許惡意和可疑應用程式對受保護資料夾中的檔案進行變更。</span><span class="sxs-lookup"><span data-stu-id="2e12f-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="2e12f-167">Windows 事件記錄檔中會提供通知。</span><span class="sxs-lookup"><span data-stu-id="2e12f-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="2e12f-168">**停用 (預設)** -「受管理的資料夾存取」功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="2e12f-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="2e12f-169">所有應用程式都可對受保護資料夾中的檔案進行變更。</span><span class="sxs-lookup"><span data-stu-id="2e12f-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="2e12f-170">「**審計模式**」-如果惡意或可疑應用程式嘗試對受保護資料夾中的檔案進行變更，便允許變更。</span><span class="sxs-lookup"><span data-stu-id="2e12f-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="2e12f-171">不過，它會記錄在 Windows 事件記錄檔中，您可以在此記錄中評估對組織的影響。</span><span class="sxs-lookup"><span data-stu-id="2e12f-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="2e12f-172">**僅封鎖磁片修改** ：在 Windows 事件記錄檔中，將不受信任的應用程式嘗試寫入磁片磁區。</span><span class="sxs-lookup"><span data-stu-id="2e12f-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="2e12f-173">您可以在 Microsoft > Windows > Windows Defender > 作業 > ID 1123 中 **，于應用程式及服務 > 記錄** 檔中找到這些記錄檔。</span><span class="sxs-lookup"><span data-stu-id="2e12f-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="2e12f-174">**僅限審核磁片修改只** 會在 [**應用程式及服務記錄**] [  >  **Microsoft**  >  **windows**  >  **windows Defender**  >  **運作**  >  **識別碼 1124**) ] 底下的 [Windows 事件 (記錄檔] 中，記錄寫入受保護的磁片磁區的企圖。</span><span class="sxs-lookup"><span data-stu-id="2e12f-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="2e12f-175">不會記錄在 [受保護的資料夾] 中修改或刪除檔的嘗試。</span><span class="sxs-lookup"><span data-stu-id="2e12f-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![已啟用群組原則選項的螢幕擷取畫面和下拉式清單中選取的審計模式](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="2e12f-177">若要完全啟用可控資料夾存取，您必須將群組原則選項設定為 [ **啟用** ]，然後在 [選項] 下拉式功能表中選取 [ **封鎖** ]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="2e12f-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e12f-178">PowerShell</span></span>

1. <span data-ttu-id="2e12f-179">在 [開始] 功能表中 **，以滑鼠** 按右鍵 [ **Windows PowerShell** ]，然後選取 [ **以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="2e12f-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="2e12f-180">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2e12f-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="2e12f-181">您可以指定代替來啟用 [審計模式] 中的功能 `AuditMode` `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="2e12f-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="2e12f-182">用 `Disabled` 來關閉功能。</span><span class="sxs-lookup"><span data-stu-id="2e12f-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e12f-183">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2e12f-183">See also</span></span>

* [<span data-ttu-id="2e12f-184">使用受控資料夾存取權來保護重要資料夾</span><span class="sxs-lookup"><span data-stu-id="2e12f-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="2e12f-185">自訂受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="2e12f-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="2e12f-186">評估適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2e12f-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
