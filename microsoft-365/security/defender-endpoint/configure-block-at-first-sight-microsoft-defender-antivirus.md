---
title: 啟用第一次看見時即封鎖功能，以在數秒內偵測到惡意程式碼
description: 第一見看見時即開啟封鎖之功能，以在數秒內偵測並封鎖惡意程式碼。
keywords: 掃描，第一次看見時即封鎖，惡意程式碼，第一次看見，雲端，防禦程式，防毒軟體
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ba0f2184ced21aea60b172d44936e3e2d36e5270
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274949"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="e43e4-104">第一次看見時即開啟封鎖</span><span class="sxs-lookup"><span data-stu-id="e43e4-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e43e4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e43e4-105">**Applies to:**</span></span>

- [<span data-ttu-id="e43e4-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e43e4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e43e4-107">本文會詳述名為「第一次看見時即封鎖」的防毒/反惡意軟體之功能，並說明如何為貴組織啟用第一次看見時即封鎖之功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="e43e4-108">本文適用于管理組織安全性設定的企業系統管理員和 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="e43e4-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="e43e4-109">如果您不是企業系統管理員或 IT 專業人員，但若您對 [第一次看見時即封鎖] 功能有疑問，請參閱 [不是企業系統管理員或 IT 專業人員？](#not-an-enterprise-admin-or-it-pro)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="e43e4-110">什麼是 [第一次看見時即封鎖]？</span><span class="sxs-lookup"><span data-stu-id="e43e4-110">What is "block at first sight"?</span></span>

<span data-ttu-id="e43e4-111">[第一次看見時即封鎖] 是新一代防護的威脅防護功能，可偵測到新的惡意程式碼，並能在幾秒內將之封鎖。</span><span class="sxs-lookup"><span data-stu-id="e43e4-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="e43e4-112">啟用特定安全性設定時，便會啟用 [第一次看見時即封鎖] 功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="e43e4-113">這些設定包含：</span><span class="sxs-lookup"><span data-stu-id="e43e4-113">These settings include:</span></span>

- <span data-ttu-id="e43e4-114">雲端提供的保護；</span><span class="sxs-lookup"><span data-stu-id="e43e4-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="e43e4-115">指定的樣本提交超時 (例如 50 秒)；和</span><span class="sxs-lookup"><span data-stu-id="e43e4-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="e43e4-116">高度檔案封鎖層級。</span><span class="sxs-lookup"><span data-stu-id="e43e4-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="e43e4-117">在大部分的企業組織中，啟用 [第一次看見時即封鎖] 功能需要使用 Microsoft Defender 防病毒軟體部署進行設定。</span><span class="sxs-lookup"><span data-stu-id="e43e4-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="e43e4-118">運作方式</span><span class="sxs-lookup"><span data-stu-id="e43e4-118">How it works</span></span>

<span data-ttu-id="e43e4-119">當 Microsoft Defender 防毒軟體遇到可疑但無法偵測的檔案時，它會查詢我們的雲端保護後端。</span><span class="sxs-lookup"><span data-stu-id="e43e4-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="e43e4-120">雲端後端會針對檔案進行啟發學習、機器學習和自動化分析，以判斷檔案是否為惡意檔案或者為威脅。</span><span class="sxs-lookup"><span data-stu-id="e43e4-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="e43e4-121">Microsoft Defender 防毒軟體使用多個偵測和防護技術，以提供準確、智慧型且即時的保護。</span><span class="sxs-lookup"><span data-stu-id="e43e4-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Microsoft Defender 防毒軟體工程清單](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="e43e4-123">若要深入瞭解，請參閱此部落格： [瞭解 Microsoft Defender 進階威脅防護新一代保護功能的核心](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="e43e4-124">關於 [第一次看見時即封鎖] 功能的一些資訊</span><span class="sxs-lookup"><span data-stu-id="e43e4-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="e43e4-125">在 Windows 10 版本 1803 或更新版本中，[第一次看見時即封鎖] 可以封鎖不可攜式可執行檔案 (例如 JS、VBS 或巨集) 和可執行檔案。</span><span class="sxs-lookup"><span data-stu-id="e43e4-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="e43e4-126">[第一次看見時即封鎖] 只會針對從網際網路下載或源自網際網路區域之可執行檔案和非可攜式可執行檔案使用雲端保護後端。</span><span class="sxs-lookup"><span data-stu-id="e43e4-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="e43e4-127">.exe 檔案的雜湊值會透過雲端後端檢查，以判斷檔案是否先前未被偵測到。</span><span class="sxs-lookup"><span data-stu-id="e43e4-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="e43e4-128">如果雲端後端無法判斷，Microsoft Defender 防毒軟體會鎖定檔案，並上傳副本至雲端。</span><span class="sxs-lookup"><span data-stu-id="e43e4-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="e43e4-129">雲端會執行更多分析以判斷是否允許檔案執行，或在未來遇到時阻擋該檔案，取決於它是否將檔案判定為惡意檔案或非威脅檔案。</span><span class="sxs-lookup"><span data-stu-id="e43e4-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="e43e4-130">在許多情況下，此程式可以將新惡意軟體的回應時間從小時縮短為秒鐘。</span><span class="sxs-lookup"><span data-stu-id="e43e4-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="e43e4-131">當雲端式保護服務分析檔案時，您可以 [指定防止檔案執行的時間長度](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="e43e4-132">此外，您也可以在檔案被封鎖時，[自訂使用者桌面上所顯示的訊息](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="e43e4-133">您可以變更公司名稱、連絡人資訊和郵件 URL。</span><span class="sxs-lookup"><span data-stu-id="e43e4-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="e43e4-134">使用 Microsoft Intune 開啟 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="e43e4-135">Microsoft Intune (現在是 Microsoft 端點管理員的一部分)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e43e4-136">在 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com))，瀏覽至 **[裝置]** > **[組態設定檔]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="e43e4-137">使用 **[裝置限制]** 設定檔類型，選取或建立設定檔。</span><span class="sxs-lookup"><span data-stu-id="e43e4-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="e43e4-138">在裝置限制設定檔的 **[組態設定]** 中，設定或確認以下 **Microsoft Defender 防毒軟體** 下方的設定：</span><span class="sxs-lookup"><span data-stu-id="e43e4-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="e43e4-139">**雲端提供的保護**：啟動</span><span class="sxs-lookup"><span data-stu-id="e43e4-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="e43e4-140">**檔案封鎖層級**：高</span><span class="sxs-lookup"><span data-stu-id="e43e4-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="e43e4-141">**雲端掃描檔案的時間延長**：50</span><span class="sxs-lookup"><span data-stu-id="e43e4-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="e43e4-142">**在提交範例之前提示使用者**：在不進行提示的情況下，傳送所有資料</span><span class="sxs-lookup"><span data-stu-id="e43e4-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune Config](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="e43e4-144">儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="e43e4-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="e43e4-145">將檔案封鎖層級設定為 **高** 會套用高偵測層級。</span><span class="sxs-lookup"><span data-stu-id="e43e4-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="e43e4-146">在某些意外情況下，檔案封鎖造成合法檔案被誤偵測為錯誤檔案類型，您的安全性作業小組可以 [還原隔離的檔案](./restore-quarantined-files-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="e43e4-147">如需更多在 Intune 中設定 Microsoft Denfender 防毒軟體裝置限制的相關資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="e43e4-148">有關 Intune 中 Microsoft Defender 防毒軟體裝置限制的清單，請參閱 [Intune 中的 Windows 10 (及更新版本) 的裝置限制設定](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="e43e4-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e43e4-149">使用 Microsoft 端點管理員開啟 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="e43e4-150">如果您要尋找 Microsoft Endpoint Configuration Manager，它現在是 Microsoft 端點管理員的一部分。</span><span class="sxs-lookup"><span data-stu-id="e43e4-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e43e4-151">在 Microsoft 端點管理員 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 中，移至 **端點安全性** > **防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="e43e4-152">選取現有的原則，或使用 **Microsoft Defender 防毒軟體** 設定檔類型建立新原則。</span><span class="sxs-lookup"><span data-stu-id="e43e4-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="e43e4-153">設定或確認下列組態設定：</span><span class="sxs-lookup"><span data-stu-id="e43e4-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="e43e4-154">**開啟雲端提供的保護**：是</span><span class="sxs-lookup"><span data-stu-id="e43e4-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="e43e4-155">**雲端提供的保護層級**：高</span><span class="sxs-lookup"><span data-stu-id="e43e4-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="e43e4-156">**Defender 雲端延伸逾時 (以秒為單位)**：50</span><span class="sxs-lookup"><span data-stu-id="e43e4-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="端點管理員中的 [第一次看見時即封鎖] 設定":::

4. <span data-ttu-id="e43e4-158">將 Microsoft Defender 防毒軟體設定檔套用到群組，例如 **[所有使用者]**、 **[所有裝置]** 或 **[所有使用者和裝置]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e43e4-159">使用群組原則開啟 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="e43e4-160">我們建議您使用 Intune 或 Microsoft 端點管理員來開啟 [第一次看見時即封鎖] 功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="e43e4-161">在您的群組原則管理電腦上，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="e43e4-162">使用 **群組原則管理編輯器**，移至 **[電腦設定]** > **[系統管理範本]** > **[Windows 元件]** > **[Microsoft Defender 防毒軟體]** > **[MAPS]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="e43e4-163">在 MAPS 區段中，按兩下 **[設定第一次看見時即封鎖功能]**，然後將它設定為 **[已啟用]**，並選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e43e4-164">設定為 **永遠提示 (0)** 將會降低裝置的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="e43e4-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="e43e4-165">設定為 **永不傳送 (2)** 表示第一次看見時即封鎖功能將無法運作。</span><span class="sxs-lookup"><span data-stu-id="e43e4-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="e43e4-166">在 MAPS 區段按兩下 **[在需要進一步分析時，傳送檔案樣本]**，並將其設定為 **[已啟用]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="e43e4-167">在 **[在需要進一步分析時，傳送檔案樣本]** 底下，選取 **[傳送所有樣本]**，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="e43e4-168">如常在整個網路中，重新部署您的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="e43e4-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="e43e4-169">確認個別用戶端裝置上已啟用 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="e43e4-170">您可以使用 Windows 安全性應用程式，確認個別用戶端裝置已啟用 [第一次看見時即封鎖] 功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="e43e4-171">只要開啟 **[雲端提供的保護]** 及 **[自動樣本提交]**，就會自動啟用「第一次看見時封鎖」。</span><span class="sxs-lookup"><span data-stu-id="e43e4-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="e43e4-172">開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e43e4-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="e43e4-173">選取 **[病毒與威脅防護]**，然後在 **[病毒與威脅防護設定]** 底下，選取 **[管理設定]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows 安全性應用程式中的病毒與威脅防護設定標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="e43e4-175">確認已開啟 **[雲端提供的保護]** 和 **[自動樣本提交]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="e43e4-176">如果先決條件設定是使用群組原則進行設定和部署，本節所述的設定會以灰色顯示，且無法用於個別端點。</span><span class="sxs-lookup"><span data-stu-id="e43e4-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="e43e4-177">必須先將透過群組原則物件進行的變更部署到個別端點，才能在 Windows 設定中更新設定。</span><span class="sxs-lookup"><span data-stu-id="e43e4-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="e43e4-178">驗證 [第一次看見時即封鎖] 功能是否有效</span><span class="sxs-lookup"><span data-stu-id="e43e4-178">Validate block at first sight is working</span></span>

<span data-ttu-id="e43e4-179">若要驗證該功能是否有效，請遵循 [[驗證您的網路與雲端網路間的連結]](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud) 指南。</span><span class="sxs-lookup"><span data-stu-id="e43e4-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="e43e4-180">關閉 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="e43e4-181">關閉 [第一次看見時即封鎖] 功能會降低裝置和網路的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="e43e4-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="e43e4-182">如果您想要保留先決條件設定而不實際使用 [第一次看見時即封鎖] 保護，您可以選擇停用 [第一次看見時即封鎖] 功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="e43e4-183">您可以暫時關閉 [第一次看見時即封鎖] 功能，以查看此功能對您的網路有何影響。</span><span class="sxs-lookup"><span data-stu-id="e43e4-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="e43e4-184">不過，我們不建議永久停用 [第一次看見時即封鎖] 保護。</span><span class="sxs-lookup"><span data-stu-id="e43e4-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e43e4-185">使用 Microsoft 端點管理員關閉 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="e43e4-186">移至 Microsoft 端點管理員系統管理中心 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入。</span><span class="sxs-lookup"><span data-stu-id="e43e4-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="e43e4-187">移至 **端點安全性** > **防毒軟體**，然後選取您的 Microsoft Defender 防毒軟體原則。</span><span class="sxs-lookup"><span data-stu-id="e43e4-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="e43e4-188">在 **[管理]** 底下，選擇 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="e43e4-189">在 **[組態設定]** 旁邊，選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="e43e4-190">變更下列其中一項或多項設定：</span><span class="sxs-lookup"><span data-stu-id="e43e4-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="e43e4-191">將 **[開啟雲端式保護]** 設定為 **[否]** 或 **[未設定]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="e43e4-192">將 **[雲端式保護層級]** 設定為 **[未設定]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="e43e4-193">取消勾選 **Defender 雲端延伸逾時 (以秒為單位)** 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e43e4-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="e43e4-194">檢視並儲存設定。</span><span class="sxs-lookup"><span data-stu-id="e43e4-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e43e4-195">使用群組原則關閉 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="e43e4-196">在您的群組原則管理電腦上，開啟 [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，以滑鼠右鍵按一下您要設定的群組原則物件，然後選擇 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="e43e4-197">使用 **[群組原則管理編輯器]**，移至 **[電腦設定]** 然後選取 **[系統管理範本]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="e43e4-198">展開 **Windows 元件** > **Microsoft Defender 防毒軟體** > **MAPS** 的整體樹狀結構。</span><span class="sxs-lookup"><span data-stu-id="e43e4-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="e43e4-199">按兩下 **設定 [第一次看見時即封鎖] 功能** ，然後設定選項為 **[停用]** 該設定。</span><span class="sxs-lookup"><span data-stu-id="e43e4-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e43e4-200">停用 [第一次看見時即封鎖] 功能不會停用或變更先決條件群組原則。</span><span class="sxs-lookup"><span data-stu-id="e43e4-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="e43e4-201">不是企業系統管理員或 IT 專業人員？</span><span class="sxs-lookup"><span data-stu-id="e43e4-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="e43e4-202">如果您不是企業系統管理員或 IT 專業人員，但若您對 [第一次看見時即封鎖] 功能有疑問，請參閱這一章節。</span><span class="sxs-lookup"><span data-stu-id="e43e4-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="e43e4-203">[第一次看見時即封鎖] 是威脅防護功能，可偵測到惡意程式碼，並能在幾秒內將之封鎖。</span><span class="sxs-lookup"><span data-stu-id="e43e4-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="e43e4-204">雖然沒有名為「第一次看見時即封鎖」的特定設定，但當您的裝置上設定了特定設定時，便會啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="e43e4-205">如何在您自己的裝置上管理 [第一次看見時即封鎖] 功能</span><span class="sxs-lookup"><span data-stu-id="e43e4-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="e43e4-206">如果您有非由組織管理的個人裝置，您可能會想知道如何開啟或關閉 [第一次看見時即封鎖] 功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="e43e4-207">您可以使用 Windows 安全性應用程式來管理 [第一次看見時即封鎖] 功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="e43e4-208">在 Windows 10 電腦上，開啟 Windows 安全性應用程式。</span><span class="sxs-lookup"><span data-stu-id="e43e4-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="e43e4-209">選取 **病毒與威脅防護**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="e43e4-210">在 **[病毒與威脅防護設定]** 下方，選取 **[管理設定]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="e43e4-211">請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="e43e4-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="e43e4-212">若要啟動 [第一次看見時即封鎖] 功能，請務必確定 **[雲端提供的保護]** 及 **[自動樣本提交]** 皆處於開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="e43e4-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="e43e4-213">若要停用 [第一次看見時即封鎖]，請關閉 **[雲端提供的保護]** 或 **[自動樣本提交]**。</span><span class="sxs-lookup"><span data-stu-id="e43e4-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="e43e4-214">關閉 [第一次看見時即封鎖] 會降低您裝置的保護層級。</span><span class="sxs-lookup"><span data-stu-id="e43e4-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="e43e4-215">我們不建議永久停用 [第一次看見時即封鎖] 功能。</span><span class="sxs-lookup"><span data-stu-id="e43e4-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="e43e4-216">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e43e4-216">See also</span></span>

- [<span data-ttu-id="e43e4-217">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="e43e4-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e43e4-218">啟動雲端提供的保護</span><span class="sxs-lookup"><span data-stu-id="e43e4-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e43e4-219">使用 Windows 安全性，隨時處於保護狀態</span><span class="sxs-lookup"><span data-stu-id="e43e4-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)