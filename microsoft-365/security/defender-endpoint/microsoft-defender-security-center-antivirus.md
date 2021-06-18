---
title: Windows 安全性應用程式中的 Microsoft Defender 防毒軟體
description: 透過 Microsoft Defender 防毒軟體現在已包含在 Windows 安全性應用程式中，您可以檢查、比較及執行常見工作。
keywords: wdav，防毒程式，防火牆，安全性，windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: c15e68a74c9bf518822fce211d6c7d5c4dbc3f2c
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007440"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="e3912-104">Windows 安全性應用程式中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="e3912-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

<span data-ttu-id="e3912-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e3912-105">**Applies to:**</span></span>

- [<span data-ttu-id="e3912-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e3912-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e3912-107">在 Windows 10 版本1703和更新版本中，Windows Defender 應用程式是 Windows 安全性的一部分。</span><span class="sxs-lookup"><span data-stu-id="e3912-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="e3912-108">先前屬於 Windows Defender 用戶端和主 Windows 設定的設定已合併並移至新的應用程式，此應用程式預設會在 Windows 10 版本1703中安裝。</span><span class="sxs-lookup"><span data-stu-id="e3912-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3912-109">停用 Windows 安全性 Center 服務不會停用 Microsoft Defender 防毒軟體或[Windows Defender 防火牆](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。</span><span class="sxs-lookup"><span data-stu-id="e3912-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="e3912-110">在安裝協力廠商防病毒或防火牆產品並保持最新狀態時，會自動停用這些功能。</span><span class="sxs-lookup"><span data-stu-id="e3912-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="e3912-111">如果您停用 Windows 安全性 Center 服務，或設定其相關聯的群組原則設定，以防止其啟動或執行，則 Windows 安全性應用程式可能會顯示您已在裝置上安裝之任何防毒軟體或防火牆產品的陳舊或不正確的資訊。</span><span class="sxs-lookup"><span data-stu-id="e3912-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="e3912-112">如果您有舊的或過時的協力廠商防病毒，或是卸載任何可能先前安裝的協力廠商防病毒產品，也會使 Microsoft Defender 防毒軟體無法自行啟用。</span><span class="sxs-lookup"><span data-stu-id="e3912-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="e3912-113">這會大幅降低保護您的裝置，並可能導致惡意程式碼感染。</span><span class="sxs-lookup"><span data-stu-id="e3912-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="e3912-114">如需其他可在應用程式中監控的 Windows 安全性功能的詳細資訊，請參閱[Windows 安全性文章](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="e3912-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="e3912-115">Windows 安全性應用程式是 Windows 10 版本1703和更新版本上的用戶端介面。</span><span class="sxs-lookup"><span data-stu-id="e3912-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="e3912-116">這不是用來複查及管理[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)的 Microsoft Defender 資訊安全中心網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="e3912-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="e3912-117">在 Windows 安全性應用程式中審閱病毒和威脅防護設定</span><span class="sxs-lookup"><span data-stu-id="e3912-117">Review virus and threat protection settings in the Windows Security app</span></span>

:::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Windows 安全性應用程式中的病毒和威脅防護設定":::

1. <span data-ttu-id="e3912-119">按一下工作列中的盾牌圖示，或搜尋 **Defender** 的 [開始] 功能表，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3912-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="e3912-120">在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e3912-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="e3912-121">下列各節說明如何在查看或與 Windows 安全性應用程式中 Microsoft Defender 防毒軟體所提供的威脅防護進行互動時執行一些最常見的工作。</span><span class="sxs-lookup"><span data-stu-id="e3912-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="e3912-122">如果使用群組原則來設定及部署這些設定，本節中所述的設定將會變灰，且無法在個別端點上使用。</span><span class="sxs-lookup"><span data-stu-id="e3912-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="e3912-123">必須先將透過群組原則物件進行的變更部署到個別端點，才能在 Windows 設定中更新設定。</span><span class="sxs-lookup"><span data-stu-id="e3912-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="e3912-124">「[設定使用者與 Microsoft Defender 防毒軟體互動](configure-end-user-interaction-microsoft-defender-antivirus.md)」主題說明如何設定本機原則覆寫設定。</span><span class="sxs-lookup"><span data-stu-id="e3912-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="e3912-125">使用 Windows 安全性 app 執行掃描</span><span class="sxs-lookup"><span data-stu-id="e3912-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="e3912-126">搜尋 [**安全性**] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3912-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="e3912-127">在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e3912-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="e3912-128">選取 [ **快速掃描**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-128">Select **Quick scan**.</span></span> <span data-ttu-id="e3912-129">或者，若要執行完整掃描，請選取 [ **掃描選項**]，然後選取選項，例如 **完整掃描**。</span><span class="sxs-lookup"><span data-stu-id="e3912-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="e3912-130">檢查安全性智慧更新版本，並在 Windows 安全性應用程式中下載最新的更新</span><span class="sxs-lookup"><span data-stu-id="e3912-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

:::image type="content" source="../../media/wdav-wdsc-defs.png" alt-text="安全性智慧版本號碼":::

1. <span data-ttu-id="e3912-132">搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3912-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="e3912-133">在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e3912-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="e3912-134">選取 [ **病毒 & 威脅防護更新**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="e3912-135">目前安裝的版本會顯示，以及下載時的部分資訊。</span><span class="sxs-lookup"><span data-stu-id="e3912-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="e3912-136">您可以查看最新版本的最新版本，以供手動下載，或查看該版本的變更記錄檔。</span><span class="sxs-lookup"><span data-stu-id="e3912-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="e3912-137">請參閱[安全性情報更新的 Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="e3912-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="e3912-138">如果有任何) ，請選取 [ **檢查更新** 以下載新的保護更新 (。</span><span class="sxs-lookup"><span data-stu-id="e3912-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="e3912-139">確定 Windows 安全性應用程式中已啟用 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="e3912-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="e3912-140">搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3912-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="e3912-141">在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e3912-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="e3912-142">選取 [ **病毒 & 威脅防護設定**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="e3912-143">將 **即時保護** 開關切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3912-144">如果您切換 **即時保護** ，它會在一段短暫的延遲之後自動重新開啟。</span><span class="sxs-lookup"><span data-stu-id="e3912-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="e3912-145">這是為了確保您免受惡意程式碼和威脅的侵擾。</span><span class="sxs-lookup"><span data-stu-id="e3912-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="e3912-146">如果您安裝其他防病毒產品，Microsoft Defender 防毒軟體會在 Windows 安全性應用程式中自動停用自身，並以這種方式指示。</span><span class="sxs-lookup"><span data-stu-id="e3912-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="e3912-147">會出現一個設定，讓您啟用有限的 [定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e3912-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="e3912-148">在 Windows 安全性應用程式中新增 Microsoft Defender 防毒軟體的排除專案</span><span class="sxs-lookup"><span data-stu-id="e3912-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="e3912-149">搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3912-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="e3912-150">在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e3912-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="e3912-151">在 [ **管理設定**] 底下，選取 [ **病毒 & 威脅防護設定**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="e3912-152">在 [ **排除** ] 設定下，選取 [ **新增或移除排除**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="e3912-153">選取加號圖示 (**+**) 選擇 [類型]，然後為每個排除專案設定選項。</span><span class="sxs-lookup"><span data-stu-id="e3912-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="e3912-154">下表摘要列出排除類型以及所發生的情況：</span><span class="sxs-lookup"><span data-stu-id="e3912-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="e3912-155">排除類型</span><span class="sxs-lookup"><span data-stu-id="e3912-155">Exclusion type</span></span>  |<span data-ttu-id="e3912-156">定義者</span><span class="sxs-lookup"><span data-stu-id="e3912-156">Defined by</span></span>  |<span data-ttu-id="e3912-157">會發生什麼事</span><span class="sxs-lookup"><span data-stu-id="e3912-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e3912-158">**檔案**</span><span class="sxs-lookup"><span data-stu-id="e3912-158">**File**</span></span> |<span data-ttu-id="e3912-159">位置</span><span class="sxs-lookup"><span data-stu-id="e3912-159">Location</span></span> <br/><span data-ttu-id="e3912-160">範例：`c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="e3912-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="e3912-161">Microsoft Defender 防毒軟體會略過特定檔案。</span><span class="sxs-lookup"><span data-stu-id="e3912-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="e3912-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="e3912-162">**Folder**</span></span>    |<span data-ttu-id="e3912-163">位置</span><span class="sxs-lookup"><span data-stu-id="e3912-163">Location</span></span> <br/><span data-ttu-id="e3912-164">範例：`c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="e3912-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="e3912-165">Microsoft Defender 防毒軟體會略過指定資料夾中的所有專案。</span><span class="sxs-lookup"><span data-stu-id="e3912-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="e3912-166">**檔案類型**</span><span class="sxs-lookup"><span data-stu-id="e3912-166">**File type**</span></span>   |<span data-ttu-id="e3912-167">副檔名</span><span class="sxs-lookup"><span data-stu-id="e3912-167">File extension</span></span> <br/><span data-ttu-id="e3912-168">範例：`.test`</span><span class="sxs-lookup"><span data-stu-id="e3912-168">Example: `.test`</span></span> |<span data-ttu-id="e3912-169">`.test`您裝置上任何地方副檔名的所有檔案都會受到 Microsoft Defender 防毒軟體略過。</span><span class="sxs-lookup"><span data-stu-id="e3912-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="e3912-170">**程序**</span><span class="sxs-lookup"><span data-stu-id="e3912-170">**Process**</span></span>     |<span data-ttu-id="e3912-171">可執行檔路徑</span><span class="sxs-lookup"><span data-stu-id="e3912-171">Executable file path</span></span> <br><span data-ttu-id="e3912-172">範例：`c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="e3912-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="e3912-173">Microsoft Defender 防毒軟體會略過此程式所開啟的特定程式和任何檔案。</span><span class="sxs-lookup"><span data-stu-id="e3912-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="e3912-174">若要深入了解，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="e3912-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="e3912-175">根據副檔名和資料夾位置，設定及驗證排除</span><span class="sxs-lookup"><span data-stu-id="e3912-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="e3912-176">設定處理常式開啟之檔案的排除專案</span><span class="sxs-lookup"><span data-stu-id="e3912-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="e3912-177">在 Windows Defender 的安全性中心應用程式中審閱威脅偵測歷程記錄</span><span class="sxs-lookup"><span data-stu-id="e3912-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="e3912-178">搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3912-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="e3912-179">在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e3912-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="e3912-180">選取 [ **保護歷程記錄**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-180">Select **Protection history**.</span></span> <span data-ttu-id="e3912-181">已列出任何最近的專案。</span><span class="sxs-lookup"><span data-stu-id="e3912-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="e3912-182">設定勒索軟體防護和修復選項</span><span class="sxs-lookup"><span data-stu-id="e3912-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="e3912-183">搜尋 [*安全性*] 的 [開始] 功能表，然後選取 [ **Windows 安全性**]，以開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3912-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="e3912-184">在左功能表列) 上，選取 [ **病毒 & 威脅防護** 磚 (] 或 [盾牌] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e3912-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="e3912-185">在 [ **勒索軟體防護**] 底下，選取 [ **管理勒索軟體防護**]。</span><span class="sxs-lookup"><span data-stu-id="e3912-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="e3912-186">若要變更 **控制的資料夾存取** 設定，請參閱 [使用可控資料夾存取權保護重要資料夾](/microsoft-365/security/defender-endpoint/controlled-folders)。</span><span class="sxs-lookup"><span data-stu-id="e3912-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="e3912-187">若要設定勒索軟體恢復選項，請選取 [在 **勒索軟體資料** 復原] 底下的 [**設定**]，並依照連結或設定 OneDrive 帳戶的指示進行，讓您能輕鬆地從勒索軟體攻擊復原。</span><span class="sxs-lookup"><span data-stu-id="e3912-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3912-188">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e3912-188">See also</span></span>
- [<span data-ttu-id="e3912-189">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="e3912-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)