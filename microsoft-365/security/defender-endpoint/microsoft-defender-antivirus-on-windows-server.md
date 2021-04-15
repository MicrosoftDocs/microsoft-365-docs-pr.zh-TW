---
title: Windows Server 上的 Microsoft Defender 防病毒
description: 瞭解如何在 Windows Server 2016 和 Windows Server 2019 上啟用和設定 Microsoft Defender 防毒軟體。
keywords: windows defender、伺服器、scep、system center endpoint protection、伺服器2016、目前分支、伺服器2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d9452b6d2eeaad3880894b9ec66c8bc71797b429
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764600"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="61138-104">Windows Server 上的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="61138-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="61138-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="61138-105">**Applies to:**</span></span>

- [<span data-ttu-id="61138-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="61138-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="61138-107">您可以在下列 Windows Server 版本上使用 Microsoft Defender 防毒程式：</span><span class="sxs-lookup"><span data-stu-id="61138-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="61138-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="61138-108">Windows Server 2019</span></span>
- <span data-ttu-id="61138-109">Windows Server，版本1803或更新版本</span><span class="sxs-lookup"><span data-stu-id="61138-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="61138-110">Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="61138-110">Windows Server 2016.</span></span> 

<span data-ttu-id="61138-111">在某些情況下，Microsoft Defender 防毒程式稱為 *Endpoint Protection*;不過，保護引擎是相同的。</span><span class="sxs-lookup"><span data-stu-id="61138-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="61138-112">雖然 [windows 10 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)程式的功能、設定和管理基本相同，但在 windows Server 上有一些重要差異：</span><span class="sxs-lookup"><span data-stu-id="61138-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="61138-113">在 Windows Server 中，會根據您定義的伺服器角色套用 [自動排除](configure-server-exclusions-microsoft-defender-antivirus.md) 。</span><span class="sxs-lookup"><span data-stu-id="61138-113">In Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
- <span data-ttu-id="61138-114">在 Windows Server 中，當您執行其他防病毒產品時，Microsoft Defender 防毒程式不會自動停用自身。</span><span class="sxs-lookup"><span data-stu-id="61138-114">In Windows Server, Microsoft Defender Antivirus does not automatically disable itself if you are running another antivirus product.</span></span>

## <a name="the-process-at-a-glance"></a><span data-ttu-id="61138-115">程序概覽</span><span class="sxs-lookup"><span data-stu-id="61138-115">The process at a glance</span></span>

<span data-ttu-id="61138-116">在伺服器平臺上安裝及執行 Microsoft Defender 防毒程式的套裝程式含數個步驟：</span><span class="sxs-lookup"><span data-stu-id="61138-116">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="61138-117">[啟用介面](#enable-the-user-interface-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="61138-117">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="61138-118">[安裝 Microsoft Defender 防毒軟體](#install-microsoft-defender-antivirus-on-windows-server)。</span><span class="sxs-lookup"><span data-stu-id="61138-118">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="61138-119">[驗證 Microsoft Defender 防病毒是否正在](#verify-microsoft-defender-antivirus-is-running)執行中。</span><span class="sxs-lookup"><span data-stu-id="61138-119">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="61138-120">[更新您的反惡意程式碼安全性情報](#update-antimalware-security-intelligence)。</span><span class="sxs-lookup"><span data-stu-id="61138-120">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="61138-121"> (視需要) [提交範例](#submit-samples)。</span><span class="sxs-lookup"><span data-stu-id="61138-121">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="61138-122"> (視需要) [設定自動排除](#configure-automatic-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="61138-122">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="61138-123">只有在必要時) [將 Microsoft Defender 防毒軟體設定為被動模式](#need-to-set-microsoft-defender-antivirus-to-passive-mode)，才 (。</span><span class="sxs-lookup"><span data-stu-id="61138-123">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="61138-124">在 Windows Server 上啟用使用者介面</span><span class="sxs-lookup"><span data-stu-id="61138-124">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="61138-125">根據預設，Windows Server 上已安裝 Microsoft Defender 防毒軟體，且運作正常。</span><span class="sxs-lookup"><span data-stu-id="61138-125">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="61138-126">預設會在某些 SKUs 上安裝使用者介面 (GUI) ，但不是必要的，因為您可以使用 PowerShell 或其他方法來管理 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="61138-126">The user interface (GUI) is installed by default on some SKUs, but is not required because you can use PowerShell or other methods to manage Microsoft Defender Antivirus.</span></span> <span data-ttu-id="61138-127">如果您的伺服器上未安裝 GUI，您可以使用 [ **新增角色及功能** ] 嚮導或使用 PowerShell Cmdlet 來新增 GUI。</span><span class="sxs-lookup"><span data-stu-id="61138-127">If the GUI is not installed on your server, you can add it by using the **Add Roles and Features** wizard, or by using PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="61138-128">使用 [新增角色及功能] 嚮導開啟 GUI</span><span class="sxs-lookup"><span data-stu-id="61138-128">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="61138-129">請參閱 [使用 [新增角色及功能] 嚮導安裝角色、角色服務和功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)，然後使用 [ **新增角色及功能] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="61138-129">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="61138-130">當您到達嚮導的 [ **功能** ] 步驟時，請在 [ **windows defender 功能**] 底下，選取 [ **windows defender 的 GUI** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="61138-130">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="61138-131">在 Windows Server 2016 中，[ **新增角色及功能] 嚮導** 看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="61138-131">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![新增角色和功能嚮導顯示 Windows Defender 的 GUI 選項](images/server-add-gui.png)

   <span data-ttu-id="61138-133">在 Windows Server 2019 中，[ **新增角色及功能] 嚮導** 是類似的。</span><span class="sxs-lookup"><span data-stu-id="61138-133">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="61138-134">使用 PowerShell 開啟 GUI</span><span class="sxs-lookup"><span data-stu-id="61138-134">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="61138-135">下列 PowerShell Cmdlet 會啟用介面：</span><span class="sxs-lookup"><span data-stu-id="61138-135">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="61138-136">在 Windows Server 上安裝 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="61138-136">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="61138-137">您可以使用 [ **新增角色及功能] 嚮導** 或 PowerShell 來安裝 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="61138-137">You can use either the **Add Roles and Features Wizard** or PowerShell to install Microsoft Defender Antivirus.</span></span>

### <a name="use-the-add-roles-and-features-wizard"></a><span data-ttu-id="61138-138">使用 [新增角色及功能] 嚮導</span><span class="sxs-lookup"><span data-stu-id="61138-138">Use the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="61138-139">請參閱 [本文](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)，並使用 [ **新增角色及功能] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="61138-139">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="61138-140">當您到達嚮導的 [ **功能** ] 步驟時，請選取 [Microsoft Defender 防病毒] 選項。</span><span class="sxs-lookup"><span data-stu-id="61138-140">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="61138-141">同時選取 [ **Windows Defender 的 GUI** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="61138-141">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="61138-142">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="61138-142">Use PowerShell</span></span>

<span data-ttu-id="61138-143">若要使用 PowerShell 來安裝 Microsoft Defender 防毒軟體，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="61138-143">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="61138-144">Microsoft defender AV 事件中包含的反惡意軟體引擎的事件訊息可以在 [Microsoft defender AV 事件](troubleshoot-microsoft-defender-antivirus.md)中找到。</span><span class="sxs-lookup"><span data-stu-id="61138-144">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="61138-145">驗證 Microsoft Defender 防病毒是否正在執行中</span><span class="sxs-lookup"><span data-stu-id="61138-145">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="61138-146">若要確認您的伺服器上正在執行 Microsoft Defender 防毒程式，請執行下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="61138-146">To verify that Microsoft Defender Antivirus is running on your server, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="61138-147">若要確認已開啟防火牆保護，請執行下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="61138-147">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="61138-148">除了 PowerShell 之外，您還可以使用命令提示字元來驗證 Microsoft Defender 防病毒是否正在執行中。</span><span class="sxs-lookup"><span data-stu-id="61138-148">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="61138-149">若要這麼做，請從命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="61138-149">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="61138-150">命令會傳回 `sc query` Microsoft Defender 防病毒服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="61138-150">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="61138-151">當 Microsoft Defender 防病毒執行時，會 `STATE` 顯示此值 `RUNNING` 。</span><span class="sxs-lookup"><span data-stu-id="61138-151">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="61138-152">更新反惡意程式碼安全性情報</span><span class="sxs-lookup"><span data-stu-id="61138-152">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="61138-153">若要取得更新的反惡意程式碼安全性情報，您必須執行 Windows Update 服務。</span><span class="sxs-lookup"><span data-stu-id="61138-153">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="61138-154">如果您使用更新管理服務（如 Windows Server Update Services (WSUS) ），請確定已針對您管理的電腦核准 Microsoft Defender 防病毒安全性情報的更新。</span><span class="sxs-lookup"><span data-stu-id="61138-154">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="61138-155">依預設，Windows Update 不會在 Windows Server 2019 或 Windows Server 2016 上自動下載並安裝更新。</span><span class="sxs-lookup"><span data-stu-id="61138-155">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="61138-156">您可以使用下列其中一種方法來變更此設定：</span><span class="sxs-lookup"><span data-stu-id="61138-156">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="61138-157">方法	</span><span class="sxs-lookup"><span data-stu-id="61138-157">Method</span></span>  |<span data-ttu-id="61138-158">描述</span><span class="sxs-lookup"><span data-stu-id="61138-158">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="61138-159">控制台中的 **Windows 更新**</span><span class="sxs-lookup"><span data-stu-id="61138-159">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="61138-160">- **自動安裝更新** ，會自動安裝所有更新，包括 Windows Defender 安全性情報更新。</span><span class="sxs-lookup"><span data-stu-id="61138-160">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="61138-161">- **下載更新，但讓我選擇是否安裝這些更新** ，可讓 Windows Defender 自動下載並安裝安全性智慧更新，但不會自動安裝其他更新。</span><span class="sxs-lookup"><span data-stu-id="61138-161">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="61138-162">**群組原則**</span><span class="sxs-lookup"><span data-stu-id="61138-162">**Group Policy**</span></span>     | <span data-ttu-id="61138-163">您可以使用 [群組原則] 中的可用設定來設定及管理 Windows 更新，其路徑如下：系統 **管理 \Windows 元件 \Windows Update\Configure 自動更新**</span><span class="sxs-lookup"><span data-stu-id="61138-163">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="61138-164">**AUOptions** 登錄機碼</span><span class="sxs-lookup"><span data-stu-id="61138-164">The **AUOptions** registry key</span></span>     |<span data-ttu-id="61138-165">下列兩個值允許 Windows Update 自動下載並安裝安全性情報更新：</span><span class="sxs-lookup"><span data-stu-id="61138-165">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="61138-166">- **4**  - **自動安裝更新**。</span><span class="sxs-lookup"><span data-stu-id="61138-166">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="61138-167">這個值會導致自動安裝所有更新，包括 Windows Defender 安全性情報更新。</span><span class="sxs-lookup"><span data-stu-id="61138-167">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="61138-168">- **3**  - **下載更新，但讓我選擇是否要安裝這些更新**。</span><span class="sxs-lookup"><span data-stu-id="61138-168">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="61138-169">這個值可讓 Windows Defender 自動下載並安裝安全性智慧更新，但不會自動安裝其他更新。</span><span class="sxs-lookup"><span data-stu-id="61138-169">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="61138-170">為了確保維護惡意程式碼保護，建議您啟用下列服務：</span><span class="sxs-lookup"><span data-stu-id="61138-170">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="61138-171">Windows 錯誤報告服務</span><span class="sxs-lookup"><span data-stu-id="61138-171">Windows Error Reporting service</span></span>

- <span data-ttu-id="61138-172">Windows Update 服務</span><span class="sxs-lookup"><span data-stu-id="61138-172">Windows Update service</span></span>

<span data-ttu-id="61138-173">下表列出 Microsoft Defender 防病毒和相依服務的服務。</span><span class="sxs-lookup"><span data-stu-id="61138-173">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="61138-174">服務名稱</span><span class="sxs-lookup"><span data-stu-id="61138-174">Service Name</span></span>|<span data-ttu-id="61138-175">檔案位置</span><span class="sxs-lookup"><span data-stu-id="61138-175">File Location</span></span>|<span data-ttu-id="61138-176">描述</span><span class="sxs-lookup"><span data-stu-id="61138-176">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="61138-177">Windows Defender 服務 (WinDefend) </span><span class="sxs-lookup"><span data-stu-id="61138-177">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="61138-178">這是主要的 Microsoft Defender 防病毒服務，必須在任何時間執行。</span><span class="sxs-lookup"><span data-stu-id="61138-178">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="61138-179">Windows 錯誤報告服務 (Wersvc) </span><span class="sxs-lookup"><span data-stu-id="61138-179">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="61138-180">此服務會將錯誤報表傳送回 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="61138-180">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="61138-181">Windows Defender 防火牆 (MpsSvc) </span><span class="sxs-lookup"><span data-stu-id="61138-181">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="61138-182">建議您保留啟用 Windows Defender 防火牆服務。</span><span class="sxs-lookup"><span data-stu-id="61138-182">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="61138-183">Windows Update (Wuauserv) </span><span class="sxs-lookup"><span data-stu-id="61138-183">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="61138-184">需要有 Windows Update 才能取得安全性情報更新和反惡意程式碼引擎更新</span><span class="sxs-lookup"><span data-stu-id="61138-184">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="61138-185">提交範例</span><span class="sxs-lookup"><span data-stu-id="61138-185">Submit samples</span></span>

<span data-ttu-id="61138-186">範例提交可讓 Microsoft 收集可能惡意軟體的範例。</span><span class="sxs-lookup"><span data-stu-id="61138-186">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="61138-187">為了協助提供持續且最新的保護，Microsoft 研究員使用這些範例來分析可疑活動，並產生更新的反惡意軟體安全性情報。</span><span class="sxs-lookup"><span data-stu-id="61138-187">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="61138-188">我們會收集程式的可執行檔，例如 .exe 檔案和 .dll 檔案。</span><span class="sxs-lookup"><span data-stu-id="61138-188">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="61138-189">我們不會收集包含個人資料的檔案，像是 Microsoft Word 檔和 PDF 檔案。</span><span class="sxs-lookup"><span data-stu-id="61138-189">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="61138-190">提交檔案</span><span class="sxs-lookup"><span data-stu-id="61138-190">Submit a file</span></span>

1. <span data-ttu-id="61138-191">查看 [提交指南](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="61138-191">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="61138-192">請造訪 [範例提交入口網站](https://www.microsoft.com/wdsi/filesubmission)，並提交您的檔案。</span><span class="sxs-lookup"><span data-stu-id="61138-192">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="61138-193">啟用自動範例提交</span><span class="sxs-lookup"><span data-stu-id="61138-193">Enable automatic sample submission</span></span>

<span data-ttu-id="61138-194">若要啟用自動範例提交，請以系統管理員身分啟動 Windows PowerShell 主控台，然後根據下列其中一個設定來設定 **SubmitSamplesConsent** 值資料：</span><span class="sxs-lookup"><span data-stu-id="61138-194">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="61138-195">設定</span><span class="sxs-lookup"><span data-stu-id="61138-195">Setting</span></span>  |<span data-ttu-id="61138-196">描述</span><span class="sxs-lookup"><span data-stu-id="61138-196">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="61138-197">**0**  - **Always prompt**</span><span class="sxs-lookup"><span data-stu-id="61138-197">**0** - **Always prompt**</span></span>     |<span data-ttu-id="61138-198">Microsoft Defender 防病毒服務會提示您確認是否提交所有必要的檔案。</span><span class="sxs-lookup"><span data-stu-id="61138-198">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="61138-199">這是 Microsoft Defender 防毒軟體的預設設定，但是不建議在未使用 GUI 的 Windows Server 2016 或2019上進行安裝。</span><span class="sxs-lookup"><span data-stu-id="61138-199">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="61138-200">**1**   - **自動傳送安全的範例**</span><span class="sxs-lookup"><span data-stu-id="61138-200">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="61138-201">Microsoft Defender 防病毒服務會傳送所有標示為「安全」的檔案，並提示您輸入檔案的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="61138-201">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="61138-202">**2**  - **從不傳送**</span><span class="sxs-lookup"><span data-stu-id="61138-202">**2** - **Never send**</span></span>      |<span data-ttu-id="61138-203">Microsoft Defender 防病毒服務不會提示，也不會傳送任何檔案。</span><span class="sxs-lookup"><span data-stu-id="61138-203">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="61138-204">**3**  - **自動傳送所有範例**</span><span class="sxs-lookup"><span data-stu-id="61138-204">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="61138-205">Microsoft Defender 防病毒服務會不經提示確認即傳送所有檔案。</span><span class="sxs-lookup"><span data-stu-id="61138-205">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="61138-206">設定自動排除</span><span class="sxs-lookup"><span data-stu-id="61138-206">Configure automatic exclusions</span></span>

<span data-ttu-id="61138-207">為了協助確保安全性和效能，會根據您在 Windows Server 2016 或2019上使用 Microsoft Defender 防毒程式時所安裝的角色和功能，自動新增某些排除。</span><span class="sxs-lookup"><span data-stu-id="61138-207">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="61138-208">請參閱 [在 Windows Server 上設定 Microsoft Defender 防毒軟體中的排除](configure-server-exclusions-microsoft-defender-antivirus.md)專案。</span><span class="sxs-lookup"><span data-stu-id="61138-208">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="61138-209">需要將 Microsoft Defender 防毒程式設為被動模式？</span><span class="sxs-lookup"><span data-stu-id="61138-209">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="61138-210">如果您使用非 Microsoft 防病毒產品作為主要防病毒方案，請將 Microsoft Defender 防病毒產品設定為被動模式。</span><span class="sxs-lookup"><span data-stu-id="61138-210">If you are using a non-Microsoft antivirus product as your primary antivirus solution, set Microsoft Defender Antivirus to passive mode.</span></span>  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="61138-211">使用登錄機碼將 Microsoft Defender 防毒程式設定為被動模式</span><span class="sxs-lookup"><span data-stu-id="61138-211">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="61138-212">如果您使用的是 Windows Server，版本1803或 Windows Server 2019，您可以設定下列登錄機碼，將 Microsoft Defender 防毒軟體設定為被動式模式：</span><span class="sxs-lookup"><span data-stu-id="61138-212">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="61138-213">路徑： `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="61138-213">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="61138-214">名稱：`ForcePassiveMode`</span><span class="sxs-lookup"><span data-stu-id="61138-214">Name: `ForcePassiveMode`</span></span>
- <span data-ttu-id="61138-215">類型： `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="61138-215">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="61138-216">值：`1`</span><span class="sxs-lookup"><span data-stu-id="61138-216">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="61138-217">使用移除角色和功能嚮導停用 Microsoft Defender 防毒程式</span><span class="sxs-lookup"><span data-stu-id="61138-217">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="61138-218">請參閱 [安裝或卸載角色、角色服務或功能](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)，並使用 **移除角色和功能嚮導**。</span><span class="sxs-lookup"><span data-stu-id="61138-218">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="61138-219">當您到達嚮導的 [ **功能** ] 步驟時，請清除 [ **Windows Defender 功能** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="61138-219">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="61138-220">[！提示] 如果您在 [ **Windows Defender 功能**] 區段下清除 [ **windows defender** ]，系統會提示您移除 **windows defender** 的 [介面] 選項 GUI。</span><span class="sxs-lookup"><span data-stu-id="61138-220">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="61138-221">在沒有使用者介面的情況下，Microsoft Defender 防病毒仍會正常執行，但是如果您停用核心 **Windows Defender** 功能，則無法啟用使用者介面。</span><span class="sxs-lookup"><span data-stu-id="61138-221">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="61138-222">使用 PowerShell 關閉 Microsoft Defender 防病毒使用者介面</span><span class="sxs-lookup"><span data-stu-id="61138-222">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="61138-223">若要關閉 Microsoft Defender 防病毒 GUI，請使用下列 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="61138-223">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="61138-224">您使用的是 Windows Server 2016 嗎？</span><span class="sxs-lookup"><span data-stu-id="61138-224">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="61138-225">如果您使用的是 Windows Server 2016，且是 Microsoft 未提供或開發的協力廠商反惡意軟體/防病毒產品，您必須停用/卸載 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="61138-225">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="61138-226">您無法卸載 Windows 安全性 app，但是您可以使用這些指示來停用此介面。</span><span class="sxs-lookup"><span data-stu-id="61138-226">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="61138-227">下列 PowerShell Cmdlet 會在 Windows Server 2016 上卸載 Microsoft Defender 防毒程式：</span><span class="sxs-lookup"><span data-stu-id="61138-227">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a><span data-ttu-id="61138-228">另請參閱</span><span class="sxs-lookup"><span data-stu-id="61138-228">See also</span></span>

- [<span data-ttu-id="61138-229">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="61138-229">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="61138-230">Microsoft Defender 防毒程式相容性</span><span class="sxs-lookup"><span data-stu-id="61138-230">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)