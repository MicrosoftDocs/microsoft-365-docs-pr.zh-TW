---
title: 自訂受控資料夾存取權
description: 新增其他應受「受控制的資料夾存取」保護的資料夾，或是允許未正確封鎖對重要檔案所做變更的應用程式。
keywords: 可控資料夾存取，windows 10，windows defender，勒索軟體，保護，檔案，資料夾，自訂，新增資料夾，新增應用程式，允許，新增可執行檔
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326522"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="69512-104">自訂受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="69512-104">Customize controlled folder access</span></span>

<span data-ttu-id="69512-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="69512-105">**Applies to:**</span></span>
- [<span data-ttu-id="69512-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="69512-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="69512-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="69512-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="69512-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="69512-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="69512-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="69512-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="69512-110">受控制的資料夾存取可協助您保護寶貴的資料，避免惡意應用程式和威脅（如勒索軟體）。</span><span class="sxs-lookup"><span data-stu-id="69512-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="69512-111">Windows Server 2019 和 Windows 10 用戶端支援受控資料夾存取。</span><span class="sxs-lookup"><span data-stu-id="69512-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="69512-112">本文說明如何自訂受管理的資料夾存取功能，並包含下列各節：</span><span class="sxs-lookup"><span data-stu-id="69512-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="69512-113">保護其他資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="69512-114">新增應允許存取受保護的資料夾的應用程式</span><span class="sxs-lookup"><span data-stu-id="69512-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="69512-115">允許簽署的可執行檔存取受保護的資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="69512-116">自訂通知</span><span class="sxs-lookup"><span data-stu-id="69512-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="69512-117">受管理的資料夾存取可監控偵測為惡意之活動的應用程式。</span><span class="sxs-lookup"><span data-stu-id="69512-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="69512-118">有時候會封鎖合法應用程式對您的檔案進行變更。</span><span class="sxs-lookup"><span data-stu-id="69512-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="69512-119">如果受控資料夾存取影響組織的生產力，您可以考慮在 [稽核模式](audit-windows-defender.md) 中執行這項功能，以完全評估影響。</span><span class="sxs-lookup"><span data-stu-id="69512-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="69512-120">保護其他資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-120">Protect additional folders</span></span>

<span data-ttu-id="69512-121">「受管理的資料夾存取」會套用至許多系統資料夾及預設位置，包括 **檔**、 **圖片** 和 **影片** 等資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="69512-122">您可以新增其他受保護的資料夾，但您無法移除預設清單中的預設資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="69512-123">將其他資料夾新增至 [受管理的資料夾存取] 在您未將檔案儲存在預設的 Windows 文件庫中時，或已變更文件庫的預設位置時，可能會很有説明。</span><span class="sxs-lookup"><span data-stu-id="69512-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="69512-124">您也可以指定網路共用和對應的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="69512-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="69512-125">支援環境變數和萬用字元。</span><span class="sxs-lookup"><span data-stu-id="69512-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="69512-126">如需使用萬用字元的詳細資訊，請參閱 [在檔案名和資料夾路徑或副檔名排除清單中使用萬用字元](configure-extension-file-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="69512-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="69512-127">您可以使用 Windows 安全性應用程式、群組原則、PowerShell Cmdlet 或行動裝置管理設定服務提供者來新增及移除受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="69512-128">使用 Windows 安全性應用程式來保護其他資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="69512-129">在工作列上選取盾牌圖示，或是在 [開始] 功能表中搜尋 *安全性*，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="69512-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="69512-130">選取 [ **病毒 & 威脅防護**]，然後向下滾動至 [ **勒索軟體防護** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="69512-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="69512-131">選取 [ **管理勒索軟體防護** ] 以開啟 [ **勒索軟體防護** ] 窗格。</span><span class="sxs-lookup"><span data-stu-id="69512-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="69512-132">在 [ **受管理的資料夾存取** ] 區段中，選取 [ **受保護的資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="69512-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="69512-133">在 [**使用者存取控制** 提示] 上選擇 [**是]** 。</span><span class="sxs-lookup"><span data-stu-id="69512-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="69512-134">[ **受保護的資料夾** ] 窗格隨即顯示。</span><span class="sxs-lookup"><span data-stu-id="69512-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="69512-135">選取 [ **新增受保護的資料夾** ]，然後依照提示新增資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="69512-136">使用群組原則來保護其他資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="69512-137">在您的群組原則管理電腦，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)。</span><span class="sxs-lookup"><span data-stu-id="69512-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="69512-138">以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="69512-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="69512-139">在您的 **群組原則管理編輯器** 中，移至 [**電腦** 設定原則] 「  >    >  **管理範本**」。</span><span class="sxs-lookup"><span data-stu-id="69512-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="69512-140">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Windows Defender Exploit Guard**  >  **控制的資料夾存取**。</span><span class="sxs-lookup"><span data-stu-id="69512-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="69512-141">**附注**：在舊版的 Windows 中，您可能會看到 **Windows Defender 防毒軟體** 而非 **Microsoft Defender 防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="69512-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="69512-142">按兩下 [ **已設定受保護的資料夾**]，然後將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="69512-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="69512-143">選取 [ **顯示**]，然後指定每個要保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="69512-144">像往常一樣部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="69512-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="69512-145">使用 PowerShell 來保護其他資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="69512-146">在 [開始] 功能表中輸入 **PowerShell** ，在 **Windows PowerShell** 上按一下滑鼠右鍵，然後選取 [以 **系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="69512-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="69512-147">輸入下列 PowerShell Cmdlet， `<the folder to be protected>` 並以資料夾路徑取代 (`"c:\apps\"`) ：</span><span class="sxs-lookup"><span data-stu-id="69512-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="69512-148">針對每個要保護的資料夾重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="69512-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="69512-149">受保護的資料夾在 Windows 安全性應用程式中是可見的。</span><span class="sxs-lookup"><span data-stu-id="69512-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="顯示 Cmdlet 的 PowerShell 視窗":::

> [!IMPORTANT]
> <span data-ttu-id="69512-151">用於 `Add-MpPreference` 在清單中附加或新增應用程式 `Set-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="69512-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="69512-152">使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。</span><span class="sxs-lookup"><span data-stu-id="69512-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="69512-153">使用 MDM Csp 來保護其他資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="69512-154">使用 [/Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service PROVIDER (CSP) 以允許應用程式變更受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="69512-155">允許特定的應用程式變更受管理的資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="69512-156">您可以指定某些應用程式是否一定會被視為安全，並對受保護的資料夾中的檔案提供寫入存取權。</span><span class="sxs-lookup"><span data-stu-id="69512-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="69512-157">如果您知道和信任的特定應用程式被受控資料夾存取功能封鎖，則允許應用程式會非常有用。</span><span class="sxs-lookup"><span data-stu-id="69512-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="69512-158">根據預設，Windows 會將視為友好的應用程式新增至允許的清單。</span><span class="sxs-lookup"><span data-stu-id="69512-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="69512-159">這類應用程式會自動新增，不會記錄在 Windows 安全性應用程式或使用相關 PowerShell Cmdlet 所顯示的清單中。</span><span class="sxs-lookup"><span data-stu-id="69512-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="69512-160">您不需要新增大多數的應用程式。</span><span class="sxs-lookup"><span data-stu-id="69512-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="69512-161">僅新增應用程式（若已被封鎖，您可以驗證其可信度）。</span><span class="sxs-lookup"><span data-stu-id="69512-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="69512-162">當您新增應用程式時，您必須指定應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="69512-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="69512-163">只有該位置中的應用程式才能存取受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="69512-164">如果使用相同名稱的應用程式 () 位於不同的位置，則不會將它新增至 allowlist，也不會被受控資料夾存取權封鎖。</span><span class="sxs-lookup"><span data-stu-id="69512-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="69512-165">在啟動後，允許的應用程式或服務只具有受管理的資料夾的寫入權限。</span><span class="sxs-lookup"><span data-stu-id="69512-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="69512-166">例如，更新服務會在允許事件後繼續觸發事件，直到它停止並重新啟動為止。</span><span class="sxs-lookup"><span data-stu-id="69512-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="69512-167">使用 Windows Defender 的安全性應用程式來允許特定的應用程式</span><span class="sxs-lookup"><span data-stu-id="69512-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="69512-168">在 [**安全性**] 的 [開始] 功能表上搜尋，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="69512-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="69512-169">在左功能表列上選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示) 然後選取 [ **管理勒索軟體防護**]。</span><span class="sxs-lookup"><span data-stu-id="69512-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="69512-170">在 [**受管理的資料夾存取**] 區段中，選取 [**允許透過可控資料夾存取的應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="69512-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="69512-171">選取 [ **新增允許的應用程式** ]，然後依照提示新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="69512-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="[新增允許的應用程式] 按鈕":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="69512-173">使用群組原則允許特定的應用程式</span><span class="sxs-lookup"><span data-stu-id="69512-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="69512-174">在您的群組原則管理裝置上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="69512-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="69512-175">在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。</span><span class="sxs-lookup"><span data-stu-id="69512-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="69512-176">展開樹狀目錄， **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Windows Defender Exploit Guard**  >  **控制的資料夾存取**。</span><span class="sxs-lookup"><span data-stu-id="69512-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="69512-177">按兩下 [ **設定允許的應用程式** ] 設定，並將選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="69512-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="69512-178">選取 [ **顯示** ]，然後輸入每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="69512-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="69512-179">使用 PowerShell 允許特定的應用程式</span><span class="sxs-lookup"><span data-stu-id="69512-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="69512-180">在 [開始] 功能表中輸入 **PowerShell** ，在 **Windows PowerShell** 上按一下滑鼠右鍵，然後選取 [以 **系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="69512-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="69512-181">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="69512-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="69512-182">例如，若要新增位於 *C:\apps* 資料夾中的可執行 *test.exe* ，此 Cmdlet 如下所示：</span><span class="sxs-lookup"><span data-stu-id="69512-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="69512-183">繼續使用將 `Add-MpPreference -ControlledFolderAccessAllowedApplications` 更多應用程式新增至清單。</span><span class="sxs-lookup"><span data-stu-id="69512-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="69512-184">使用此 Cmdlet 新增的應用程式會出現在 Windows 安全性應用程式中。</span><span class="sxs-lookup"><span data-stu-id="69512-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="允許應用程式的 PowerShell Cmdlet":::

> [!IMPORTANT]
> <span data-ttu-id="69512-186">用於 `Add-MpPreference` 附加或新增應用程式至清單。</span><span class="sxs-lookup"><span data-stu-id="69512-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="69512-187">使用此 `Set-MpPreference` Cmdlet 將會覆寫現有清單。</span><span class="sxs-lookup"><span data-stu-id="69512-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="69512-188">使用 MDM Csp 以允許特定的應用程式</span><span class="sxs-lookup"><span data-stu-id="69512-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="69512-189">使用 [/Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service PROVIDER (CSP) 以允許應用程式變更受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="69512-190">允許簽署的可執行檔存取受保護的資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="69512-191">Microsoft Defender for Endpoint 憑證和檔指示器可允許簽署的可執行檔存取受保護的資料夾。</span><span class="sxs-lookup"><span data-stu-id="69512-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="69512-192">如需有關執行的詳細資訊，請參閱 [建立以憑證為基礎的指示器](indicator-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="69512-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="69512-193">這不會套用至腳本掃描引擎，包括 Powershell</span><span class="sxs-lookup"><span data-stu-id="69512-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="69512-194">自訂通知</span><span class="sxs-lookup"><span data-stu-id="69512-194">Customize the notification</span></span>

<span data-ttu-id="69512-195">如需在觸發規則時自訂通知並封鎖應用程式或檔案的詳細資訊，請參閱 [在 Microsoft Defender For Endpoint 中設定警示通知](configure-email-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="69512-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69512-196">請參閱</span><span class="sxs-lookup"><span data-stu-id="69512-196">See also</span></span>

- [<span data-ttu-id="69512-197">使用受控資料夾存取權來保護重要資料夾</span><span class="sxs-lookup"><span data-stu-id="69512-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="69512-198">啟用受控資料夾存取權</span><span class="sxs-lookup"><span data-stu-id="69512-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="69512-199">評估受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="69512-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
