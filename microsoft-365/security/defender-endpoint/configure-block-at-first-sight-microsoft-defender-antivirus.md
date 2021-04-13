---
title: 在第幾秒內啟用封鎖以偵測惡意程式碼
description: 開啟塊狀的「初次看到」功能，以在幾秒內偵測並封鎖惡意程式碼。
keywords: 掃描、BAFS、惡意程式碼、第一次查看、初次看到、雲端、defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 837b7899368e69b274323125c97169bbe4f823b7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690259"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="b5b0b-104">在初次看到時開啟組塊</span><span class="sxs-lookup"><span data-stu-id="b5b0b-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b5b0b-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b5b0b-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5b0b-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5b0b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b5b0b-107">在第一次看到的封鎖提供一種方法，可以在數秒內偵測並封鎖新的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="b5b0b-108">預設會在啟用某些先決條件設定時啟用此保護。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="b5b0b-109">這些設定包括雲端傳送保護、指定的範例提交超時 (例如50秒) 以及高的檔案封鎖層級。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="b5b0b-110">在大多數的企業組織中，預設會使用 Microsoft Defender 防病毒部署來啟用這些設定。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="b5b0b-111">您可以指定雲端式保護服務分析檔案時， [應防止檔案執行的時間長度](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="b5b0b-112">而且，您可以在封鎖檔時， [自訂使用者桌面上顯示的訊息](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="b5b0b-113">您可以變更公司名稱、連絡人資訊及消息 URL。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="b5b0b-114">請造訪 Microsoft Defender for Endpoint 示範網站， [以確認](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 功能是否正常運作，並查看其運作方式。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b5b0b-115">運作方式</span><span class="sxs-lookup"><span data-stu-id="b5b0b-115">How it works</span></span>

<span data-ttu-id="b5b0b-116">當 Microsoft Defender 防病毒遇到可疑但未偵測到的檔案時，它會查詢我們的雲端保護後端。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="b5b0b-117">雲端後端套用檔的試探法、機器學習和自動分析，以判斷檔案是否惡意或不是威脅。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="b5b0b-118">Microsoft Defender 防病毒會使用多個偵測及防護技術，以提供準確、智慧和即時的保護。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="b5b0b-119">若要深入瞭解，請參閱下列博客： [深入瞭解 Microsoft Defender 的核心的高級技術，以供端點下一代保護](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="b5b0b-120">![Microsoft Defender AV 引擎清單](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="b5b0b-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="b5b0b-121">在 Windows 10 版本1803或更新版本中，第一次看到的封鎖可以封鎖不可移植的可執行檔 (例如 .JS、VBS 或宏) 以及可執行檔。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="b5b0b-122">在第一次看到時，封鎖只會對從網際網路下載的可執行檔和不可移植的可執行檔（從網際網路區域產生）使用雲端保護後端。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="b5b0b-123">.Exe 檔案的雜湊值是透過雲端後端檢查，以判斷該檔案是否為先前未檢查過的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="b5b0b-124">若 cloud 後端無法判斷，Microsoft Defender 防毒程式會鎖定檔案，並將副本上傳至雲端。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="b5b0b-125">雲端會執行額外的分析，以達到判斷，讓檔案在未來所有的情況下都能執行或封鎖它，取決於它是否決定要成為惡意或安全的檔。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="b5b0b-126">在許多情況下，此程式可將新惡意程式碼的回應時間從數小時縮短為秒。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="b5b0b-127">在初次看到 Microsoft Intune 時開啟區塊</span><span class="sxs-lookup"><span data-stu-id="b5b0b-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="b5b0b-128">Microsoft Intune 現在是 Microsoft 端點管理員的一部分。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="b5b0b-129">在 Microsoft 端點管理員管理中心 () 中 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ，流覽至 [**裝置** 設定配置  >  **檔**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="b5b0b-130">使用 **裝置限制** 配置檔案類型選取或建立設定檔。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="b5b0b-131">在裝置限制設定檔的 **設定設定** 中，在 [ **Microsoft Defender 防病毒**] 下設定或確認下列設定：</span><span class="sxs-lookup"><span data-stu-id="b5b0b-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="b5b0b-132">**雲端提供的保護**：已啟用</span><span class="sxs-lookup"><span data-stu-id="b5b0b-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="b5b0b-133">**檔封鎖層級**：高</span><span class="sxs-lookup"><span data-stu-id="b5b0b-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="b5b0b-134">**雲端的檔案掃描時間分機**：50</span><span class="sxs-lookup"><span data-stu-id="b5b0b-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="b5b0b-135">**在提交範例之前提示使用者**：不經提示傳送所有資料</span><span class="sxs-lookup"><span data-stu-id="b5b0b-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune config](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="b5b0b-137">儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="b5b0b-138">將檔封鎖層級設為 **高** 會套用強層次的偵測。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="b5b0b-139">在發生不理想的情況下，由於 file 封鎖導致合法檔案的誤報偵測，您可以 [還原隔離](./restore-quarantined-files-microsoft-defender-antivirus.md)的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="b5b0b-140">如需在 Intune 中設定 Microsoft Defender 防病毒裝置限制的詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="b5b0b-141">如需 Intune 中 Microsoft Defender 防病毒裝置限制的清單，請參閱 [intune 中 Windows 10 (和更新) 設定的裝置限制](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="b5b0b-142">在初次看到 Microsoft 端點管理員時開啟區塊</span><span class="sxs-lookup"><span data-stu-id="b5b0b-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="b5b0b-143">如果您正在尋找 Microsoft 端點 Configuration Manager，它現在是 Microsoft 端點管理員的一部分。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="b5b0b-144">在 Microsoft 端點管理員 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 中，移至 **端點安全性**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="b5b0b-145">選取現有的原則，或使用 **Microsoft Defender 防病毒** 配置檔案類型建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="b5b0b-146">設定或確認下列設定：</span><span class="sxs-lookup"><span data-stu-id="b5b0b-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="b5b0b-147">**開啟雲端傳送保護**：是</span><span class="sxs-lookup"><span data-stu-id="b5b0b-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="b5b0b-148">**雲端提供的保護層級**：高</span><span class="sxs-lookup"><span data-stu-id="b5b0b-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="b5b0b-149">**Defender Cloud 延伸超時秒**：50</span><span class="sxs-lookup"><span data-stu-id="b5b0b-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="端點管理員中首次看到的設定封鎖":::

4. <span data-ttu-id="b5b0b-151">將 Microsoft Defender 防病毒設定檔套用至群組，例如 **所有使用者**、 **所有裝置** 或 **所有使用者和裝置**。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="b5b0b-152">在第一次使用群組原則時開啟區塊</span><span class="sxs-lookup"><span data-stu-id="b5b0b-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="b5b0b-153">我們建議您在第一次看到封鎖時，使用 Intune 或 Microsoft 端點管理員開啟封鎖。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="b5b0b-154">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="b5b0b-155">使用 **群組原則管理編輯器** 移至 [**電腦設定] 系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **對應**。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="b5b0b-156">在 [對應] 區段中，按兩下 **[設定第一次看到的封鎖] 功能**，並將其設定為 [ **啟用**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b5b0b-157">設定為 **Always prompt (0)** 會降低裝置的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="b5b0b-158">設定為 **永不傳送 (2)** 表示第一次看到的區塊將無法運作。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="b5b0b-159">在 [對應] 區段中，在 **需要進一步分析時**，按兩下 [傳送檔案範例]，並將其設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="b5b0b-160">在 [ **需要進一步分析時傳送檔範例**] 底下，選取 [ **傳送所有範例**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="b5b0b-161">如果您變更任何設定，請在您的網路上重新部署群組原則物件，以確保涵蓋所有端點。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="b5b0b-162">在個別用戶端上啟用第一次看到時，確認已啟用區塊</span><span class="sxs-lookup"><span data-stu-id="b5b0b-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="b5b0b-163">您可以在使用 Windows 安全性設定的個別用戶端上，確認第一次看到的組塊已啟用。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="b5b0b-164">只要已開啟 **雲端提供的保護** 和 **自動範例提交** ，便會自動啟用封鎖初次看到的功能。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="b5b0b-165">開啟 [Windows 安全性應用程式]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="b5b0b-166">選取 [ **病毒 & 威脅防護**]，然後在 [ **病毒 & 威脅防護設定**] 底下，選取 [ **管理設定**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows 安全性應用程式中的病毒 & 威脅防護設定] 標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="b5b0b-168">確認已開啟 **雲端提供的保護** 和 **自動範例提交** 。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="b5b0b-169">如果使用群組原則來設定及部署必要條件設定，本節中所述的設定將會變灰，且無法在個別端點上使用。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="b5b0b-170">您必須先將透過「群組原則」物件所做的變更部署到個別的端點，然後才會在 [Windows 設定] 中更新設定。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="b5b0b-171">第一次看到的驗證區塊運作正常</span><span class="sxs-lookup"><span data-stu-id="b5b0b-171">Validate block at first sight is working</span></span>

<span data-ttu-id="b5b0b-172">若要驗證功能是否正常運作，請遵循 [驗證網路與雲端之間](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)連線的指導方針。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="b5b0b-173">在第一次看到封鎖時關閉封鎖</span><span class="sxs-lookup"><span data-stu-id="b5b0b-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="b5b0b-174">在第一次看到時關閉區塊，將會降低裝置 (s) 和您的網路的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="b5b0b-175">如果您想要保留必要條件設定，而不實際在第一次看到保護時使用區塊，您可以選擇停用 [在第一次看到時封鎖]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="b5b0b-176">如果您遇到延遲問題，或您想要測試功能對您網路的影響，則第一次看到封鎖時，您可能會暫時關閉區塊。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="b5b0b-177">不過，我們不建議您在初次看到保護時停用封鎖。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="b5b0b-178">在第一次使用 Microsoft 端點管理員時關閉封鎖</span><span class="sxs-lookup"><span data-stu-id="b5b0b-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="b5b0b-179">移至 [Microsoft 端點管理員管理中心] ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="b5b0b-180">請移至 **端點安全性**  >  **防病毒**，然後選取您的 Microsoft Defender 防病毒原則。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="b5b0b-181">在 [ **管理**] 下，選擇 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="b5b0b-182">在 [ **設定設定**] 旁，選擇 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="b5b0b-183">變更一或多個下列設定：</span><span class="sxs-lookup"><span data-stu-id="b5b0b-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="b5b0b-184">將 **雲端傳送保護開啟** 為 [ **否** ] 或 [ **未設定**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="b5b0b-185">將 **雲端傳送的保護等級** 設為 [ **未設定**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="b5b0b-186">清除 [ **Defender Cloud 擴充超時（秒）** ] 方塊。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="b5b0b-187">檢查並儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="b5b0b-188">在第一次使用群組原則時關閉封鎖</span><span class="sxs-lookup"><span data-stu-id="b5b0b-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="b5b0b-189">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後按一下 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="b5b0b-190">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]，然後按一下 [系統 **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="b5b0b-191">透過 **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **對應** 展開樹狀目錄。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="b5b0b-192">按兩下 [設定 **第一次看到的封鎖] 功能** ，並將此選項設定為 [ **停用**]。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b5b0b-193">停用區塊初次看到時，不會停用或變更必要條件群組原則。</span><span class="sxs-lookup"><span data-stu-id="b5b0b-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5b0b-194">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b5b0b-194">See also</span></span>

- [<span data-ttu-id="b5b0b-195">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="b5b0b-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="b5b0b-196">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="b5b0b-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)