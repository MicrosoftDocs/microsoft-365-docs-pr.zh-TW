---
title: 開啟網路保護
description: 使用「群組原則」、「PowerShell」或「行動裝置管理」及 Configuration Manager 來啟用網路保護。
keywords: ANetwork protection，乘虛攻擊，惡意網站，ip，網域，網域，啟用，開啟
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bde97638a39eef4561b898b2cf49e51bed6e77a5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926652"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="57d19-104">開啟網路保護</span><span class="sxs-lookup"><span data-stu-id="57d19-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="57d19-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="57d19-105">**Applies to:**</span></span>
- [<span data-ttu-id="57d19-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="57d19-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="57d19-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57d19-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="57d19-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="57d19-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="57d19-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="57d19-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="57d19-110">[網路保護](network-protection.md) 可協助防止員工使用任何應用程式存取可能會在網際網路上主控網路釣魚詐騙、入侵和其他惡意內容的危險網域。</span><span class="sxs-lookup"><span data-stu-id="57d19-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="57d19-111">您可以在測試環境中 [審核網路保護](evaluate-network-protection.md) ，以查看在啟用之前將封鎖哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="57d19-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="57d19-112">深入瞭解網路篩選設定選項</span><span class="sxs-lookup"><span data-stu-id="57d19-112">Learn more about network filtering configuration options</span></span>](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="57d19-113">檢查是否已啟用網路保護</span><span class="sxs-lookup"><span data-stu-id="57d19-113">Check if network protection is enabled</span></span>

<span data-ttu-id="57d19-114">使用登錄編輯程式檢查是否已在本機裝置上啟用網路保護。</span><span class="sxs-lookup"><span data-stu-id="57d19-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="57d19-115">選取工作列中的 [ **開始** ] 按鈕，然後輸入 **regedit** 開啟登錄編輯程式</span><span class="sxs-lookup"><span data-stu-id="57d19-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>

2. <span data-ttu-id="57d19-116">選擇側邊功能表中的 [ **HKEY_LOCAL_MACHINE**</span><span class="sxs-lookup"><span data-stu-id="57d19-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>

3. <span data-ttu-id="57d19-117">透過嵌套功能表流覽至 **軟體**  >  **Microsoft**  >  **Windows Defender**  >  **Windows Defender 利用防護**  >  **網路保護**</span><span class="sxs-lookup"><span data-stu-id="57d19-117">Navigate through the nested menus to **SOFTWARE** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>

4. <span data-ttu-id="57d19-118">選取 [ **EnableNetworkProtection** ]，以查看裝置上目前的網路保護狀態。</span><span class="sxs-lookup"><span data-stu-id="57d19-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="57d19-119">0或 **關閉**</span><span class="sxs-lookup"><span data-stu-id="57d19-119">0, or **Off**</span></span>
    * <span data-ttu-id="57d19-120">1或 **開啟**</span><span class="sxs-lookup"><span data-stu-id="57d19-120">1, or **On**</span></span>
    * <span data-ttu-id="57d19-121">2或 **審計** 模式</span><span class="sxs-lookup"><span data-stu-id="57d19-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="57d19-123">啟用網路保護</span><span class="sxs-lookup"><span data-stu-id="57d19-123">Enable network protection</span></span>

<span data-ttu-id="57d19-124">使用下列任何一種方法來啟用網路保護：</span><span class="sxs-lookup"><span data-stu-id="57d19-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="57d19-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="57d19-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="57d19-126">移動裝置管理 (MDM) </span><span class="sxs-lookup"><span data-stu-id="57d19-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="57d19-127">Microsoft 端點管理員/Intune</span><span class="sxs-lookup"><span data-stu-id="57d19-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="57d19-128">群組原則</span><span class="sxs-lookup"><span data-stu-id="57d19-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="57d19-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="57d19-129">PowerShell</span></span>

1. <span data-ttu-id="57d19-130">在 [開始] 功能表中輸入 **powershell** ，以滑鼠右鍵按一下 **Windows PowerShell** 並選取 [以 **系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="57d19-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="57d19-131">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="57d19-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="57d19-132">選用：使用下列 Cmdlet 在稽核模式中啟用此功能：</span><span class="sxs-lookup"><span data-stu-id="57d19-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="57d19-133">使用 `Disabled` 代替 `AuditMode` 或 `Enabled` 關閉功能。</span><span class="sxs-lookup"><span data-stu-id="57d19-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="57d19-134">行動裝置管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="57d19-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="57d19-135">使用 [/Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) configuration service PROVIDER (CSP) 以啟用或停用網路保護或啟用稽核模式。</span><span class="sxs-lookup"><span data-stu-id="57d19-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="57d19-136">Microsoft 端點管理員 (以前的 Intune) </span><span class="sxs-lookup"><span data-stu-id="57d19-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="57d19-137">登入 Microsoft 端點管理員系統管理中心 (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="57d19-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="57d19-138">建立或編輯 [endpoint protection 設定檔](/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="57d19-138">Create or edit an [endpoint protection configuration profile](/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="57d19-139">在設定檔流程中的 [設定 **設定**] 底下，移至 **Microsoft Defender 惡意探索防護**  >  **網路篩選**  >  **網路保護**  >  **啟用** 或 **僅限審核**</span><span class="sxs-lookup"><span data-stu-id="57d19-139">Under **Configuration Settings** in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="57d19-140">群組原則</span><span class="sxs-lookup"><span data-stu-id="57d19-140">Group Policy</span></span>

<span data-ttu-id="57d19-141">使用下列程式可在已加入網域的電腦或獨立電腦上啟用網路保護。</span><span class="sxs-lookup"><span data-stu-id="57d19-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="57d19-142">在單機電腦上，移至 [ **開始** ]，然後輸入並選取 [ **編輯群組原則**]。</span><span class="sxs-lookup"><span data-stu-id="57d19-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="57d19-143">*或*</span><span class="sxs-lookup"><span data-stu-id="57d19-143">*-Or-*</span></span>

    <span data-ttu-id="57d19-144">在已加入網域的群組原則管理電腦上，開啟 [群組原則管理主控台](https://technet.microsoft.com/library/cc731212.aspx)，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="57d19-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="57d19-145">在 **[群組原則管理編輯器]** 中，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。</span><span class="sxs-lookup"><span data-stu-id="57d19-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="57d19-146">展開樹狀目錄，以 **Windows 元件**  >  **Microsoft Defender 防毒軟體**  >  **Windows Defender 利用防護**  >  **網路保護**。</span><span class="sxs-lookup"><span data-stu-id="57d19-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="57d19-147">在舊版的 Windows 中，群組原則路徑可以說「Windows Defender 防毒軟體」，而不是「Microsoft Defender 防毒軟體」。</span><span class="sxs-lookup"><span data-stu-id="57d19-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="57d19-148">按兩下 [ **防止使用者和應用程式存取危險的網站** ] 設定，並將此選項設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="57d19-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="57d19-149">在 [選項] 區段中，您必須指定下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="57d19-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="57d19-150">**封鎖** -使用者無法存取惡意的 IP 位址和網域</span><span class="sxs-lookup"><span data-stu-id="57d19-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="57d19-151">**停用 (預設)** -網路保護功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="57d19-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="57d19-152">使用者不會被封鎖存取惡意網域</span><span class="sxs-lookup"><span data-stu-id="57d19-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="57d19-153">**稽核模式**-如果使用者要走訪惡意的 IP 位址或網域，將會在 Windows 事件記錄檔中記錄事件。</span><span class="sxs-lookup"><span data-stu-id="57d19-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="57d19-154">不過，使用者不會被封鎖訪問位址。</span><span class="sxs-lookup"><span data-stu-id="57d19-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57d19-155">若要完全啟用網路保護，您必須將群組原則選項設定為 [ **啟用** ]，然後在 [選項] 下拉式功能表中選取 [ **封鎖** ]。</span><span class="sxs-lookup"><span data-stu-id="57d19-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="57d19-156">使用登錄編輯程式確認已在本機電腦上啟用網路保護：</span><span class="sxs-lookup"><span data-stu-id="57d19-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="57d19-157">選取 [ **啟動** ] 並輸入 **Regedit** 以開啟 **登錄編輯程式**。</span><span class="sxs-lookup"><span data-stu-id="57d19-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="57d19-158">流覽至 **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**</span><span class="sxs-lookup"><span data-stu-id="57d19-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**</span></span>

3. <span data-ttu-id="57d19-159">選取 **EnableNetworkProtection** 並確認值：</span><span class="sxs-lookup"><span data-stu-id="57d19-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="57d19-160">0 = 關閉</span><span class="sxs-lookup"><span data-stu-id="57d19-160">0=Off</span></span>
   * <span data-ttu-id="57d19-161">1 = 開啟</span><span class="sxs-lookup"><span data-stu-id="57d19-161">1=On</span></span>
   * <span data-ttu-id="57d19-162">2 = 審計</span><span class="sxs-lookup"><span data-stu-id="57d19-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="57d19-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="57d19-163">See also</span></span>

* [<span data-ttu-id="57d19-164">網路保護</span><span class="sxs-lookup"><span data-stu-id="57d19-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="57d19-165">評估網路保護</span><span class="sxs-lookup"><span data-stu-id="57d19-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="57d19-166">疑難排解網路保護</span><span class="sxs-lookup"><span data-stu-id="57d19-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
