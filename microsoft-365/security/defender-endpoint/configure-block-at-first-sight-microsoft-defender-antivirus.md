---
title: 在第幾秒內啟用封鎖以偵測惡意程式碼
description: 開啟塊狀的「初次看到」功能，以在幾秒內偵測並封鎖惡意程式碼。
keywords: 掃描、封鎖第一次看到、惡意程式碼、第一次看到、雲端、defender、防毒程式
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079200"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="bf147-104">第一次看見時開啟封鎖</span><span class="sxs-lookup"><span data-stu-id="bf147-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bf147-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="bf147-105">**Applies to:**</span></span>

- [<span data-ttu-id="bf147-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="bf147-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bf147-107">本文說明防毒軟體/反惡意軟體功能（稱為「初次看到時封鎖」），並說明如何在第一次看到的組織中啟用區塊。</span><span class="sxs-lookup"><span data-stu-id="bf147-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="bf147-108">本文適用于管理組織安全性設定的 enterprise admins 和 IT 專業人員。</span><span class="sxs-lookup"><span data-stu-id="bf147-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="bf147-109">如果您不是企業系統管理員或 IT 專業人員，但在初次看到時會有有關封鎖的問題，請參閱 [not enterprise admin OR It 專業人員？](#not-an-enterprise-admin-or-it-pro)。</span><span class="sxs-lookup"><span data-stu-id="bf147-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="bf147-110">「初次看到」為何？</span><span class="sxs-lookup"><span data-stu-id="bf147-110">What is "block at first sight"?</span></span>

<span data-ttu-id="bf147-111">「第一次看到的封鎖」是下一代保護的威脅防護功能，可偵測新的惡意程式碼並在幾秒內封鎖。</span><span class="sxs-lookup"><span data-stu-id="bf147-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="bf147-112">啟用某些安全性設定時，第一次看到的封鎖會啟用。</span><span class="sxs-lookup"><span data-stu-id="bf147-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="bf147-113">這些設定包含：</span><span class="sxs-lookup"><span data-stu-id="bf147-113">These settings include:</span></span>

- <span data-ttu-id="bf147-114">雲端提供的保護;</span><span class="sxs-lookup"><span data-stu-id="bf147-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="bf147-115">指定的範例提交超時 (例如50秒) ;和</span><span class="sxs-lookup"><span data-stu-id="bf147-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="bf147-116">高的檔封鎖層級。</span><span class="sxs-lookup"><span data-stu-id="bf147-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="bf147-117">在大多數企業組織中，第一次看到的啟用封鎖所需的設定是透過 Microsoft Defender 防病毒部署設定。</span><span class="sxs-lookup"><span data-stu-id="bf147-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="bf147-118">運作方式</span><span class="sxs-lookup"><span data-stu-id="bf147-118">How it works</span></span>

<span data-ttu-id="bf147-119">當 Microsoft Defender 防病毒遇到可疑但未偵測到的檔案時，它會查詢我們的雲端保護後端。</span><span class="sxs-lookup"><span data-stu-id="bf147-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="bf147-120">雲端後端套用檔的試探法、機器學習和自動分析，以判斷檔案是否惡意或不是威脅。</span><span class="sxs-lookup"><span data-stu-id="bf147-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="bf147-121">Microsoft Defender 防病毒會使用多個偵測及防護技術，以提供準確、智慧和即時的保護。</span><span class="sxs-lookup"><span data-stu-id="bf147-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Microsoft Defender AV 引擎清單](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="bf147-123">若要深入瞭解，請參閱下列博客： [深入瞭解 Microsoft Defender 的核心的高級技術，以供端點下一代保護](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。</span><span class="sxs-lookup"><span data-stu-id="bf147-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="bf147-124">在第一次看到區塊時，需要瞭解的一些事項</span><span class="sxs-lookup"><span data-stu-id="bf147-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="bf147-125">在 Windows 10 版本1803或更新版本中，第一次看到的封鎖可以封鎖不可移植的可執行檔 (例如 .JS、VBS 或宏) 和可執行檔。</span><span class="sxs-lookup"><span data-stu-id="bf147-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="bf147-126">在第一次看到時，封鎖只會對從網際網路下載的可執行檔和不可移植的可執行檔（從網際網路區域產生）使用雲端保護後端。</span><span class="sxs-lookup"><span data-stu-id="bf147-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="bf147-127">.Exe 檔案的雜湊值是透過雲端後端檢查，以判斷該檔案是否為先前未檢查過的檔案。</span><span class="sxs-lookup"><span data-stu-id="bf147-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="bf147-128">若 cloud 後端無法判斷，Microsoft Defender 防毒程式會鎖定檔案，並將副本上傳至雲端。</span><span class="sxs-lookup"><span data-stu-id="bf147-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="bf147-129">雲端會執行更多分析，以達到判斷，直到所有未來都能執行或封鎖該檔案，取決於它是否決定要成為惡意或不是威脅的檔案。</span><span class="sxs-lookup"><span data-stu-id="bf147-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="bf147-130">在許多情況下，此程式可將新惡意程式碼的回應時間從數小時縮短為秒。</span><span class="sxs-lookup"><span data-stu-id="bf147-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="bf147-131">您可以指定雲端式保護服務分析檔案時， [應防止檔案執行的時間長度](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 。</span><span class="sxs-lookup"><span data-stu-id="bf147-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="bf147-132">而且，您可以在封鎖檔時， [自訂使用者桌面上顯示的訊息](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 。</span><span class="sxs-lookup"><span data-stu-id="bf147-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="bf147-133">您可以變更公司名稱、連絡人資訊及消息 URL。</span><span class="sxs-lookup"><span data-stu-id="bf147-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="bf147-134">在初次看到 Microsoft Intune 時開啟區塊</span><span class="sxs-lookup"><span data-stu-id="bf147-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="bf147-135">Microsoft Intune 現在是 Microsoft 端點管理員的一部分。</span><span class="sxs-lookup"><span data-stu-id="bf147-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="bf147-136">在 Microsoft 端點管理員管理中心 () 中 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ，流覽至 [**裝置** 設定配置  >  **檔**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="bf147-137">使用 **裝置限制** 配置檔案類型選取或建立設定檔。</span><span class="sxs-lookup"><span data-stu-id="bf147-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="bf147-138">在裝置限制設定檔的 **設定設定** 中，在 [ **Microsoft Defender 防病毒**] 下設定或確認下列設定：</span><span class="sxs-lookup"><span data-stu-id="bf147-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="bf147-139">**雲端提供的保護**：已啟用</span><span class="sxs-lookup"><span data-stu-id="bf147-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="bf147-140">**檔封鎖層級**：高</span><span class="sxs-lookup"><span data-stu-id="bf147-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="bf147-141">**雲端的檔案掃描時間分機**：50</span><span class="sxs-lookup"><span data-stu-id="bf147-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="bf147-142">**在提交範例之前提示使用者**：不經提示傳送所有資料</span><span class="sxs-lookup"><span data-stu-id="bf147-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Intune config](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="bf147-144">儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="bf147-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="bf147-145">將檔封鎖層級設為 **高** 會套用強層次的偵測。</span><span class="sxs-lookup"><span data-stu-id="bf147-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="bf147-146">在發生不理想的情況下，由於檔封鎖導致合法檔案的誤報偵測，您的安全性作業小組可以 [還原隔離](./restore-quarantined-files-microsoft-defender-antivirus.md)的檔案。</span><span class="sxs-lookup"><span data-stu-id="bf147-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="bf147-147">如需在 Intune 中設定 Microsoft Defender 防病毒裝置限制的詳細資訊，請參閱 [在 Microsoft Intune 中設定裝置限制設定](/intune/device-restrictions-configure)。</span><span class="sxs-lookup"><span data-stu-id="bf147-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="bf147-148">如需 Intune 中 Microsoft Defender 防病毒裝置限制的清單，請參閱 [intune 中 Windows 10 (和更新) 設定的裝置限制](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="bf147-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="bf147-149">在初次看到 Microsoft 端點管理員時開啟區塊</span><span class="sxs-lookup"><span data-stu-id="bf147-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="bf147-150">如果您正在尋找 Microsoft 端點 Configuration Manager，它現在是 Microsoft 端點管理員的一部分。</span><span class="sxs-lookup"><span data-stu-id="bf147-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="bf147-151">在 Microsoft 端點管理員 ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 中，移至 **端點安全性**  >  **防病毒**。</span><span class="sxs-lookup"><span data-stu-id="bf147-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="bf147-152">選取現有的原則，或使用 **Microsoft Defender 防病毒** 配置檔案類型建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="bf147-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="bf147-153">設定或確認下列設定：</span><span class="sxs-lookup"><span data-stu-id="bf147-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="bf147-154">**開啟雲端傳送保護**：是</span><span class="sxs-lookup"><span data-stu-id="bf147-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="bf147-155">**雲端提供的保護層級**：高</span><span class="sxs-lookup"><span data-stu-id="bf147-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="bf147-156">**Defender Cloud 延伸超時秒**：50</span><span class="sxs-lookup"><span data-stu-id="bf147-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="端點管理員中首次看到的設定封鎖":::

4. <span data-ttu-id="bf147-158">將 Microsoft Defender 防病毒設定檔套用至群組，例如 **所有使用者**、 **所有裝置** 或 **所有使用者和裝置**。</span><span class="sxs-lookup"><span data-stu-id="bf147-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="bf147-159">在第一次使用群組原則時開啟區塊</span><span class="sxs-lookup"><span data-stu-id="bf147-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="bf147-160">我們建議您在第一次看到封鎖時，使用 Intune 或 Microsoft 端點管理員開啟封鎖。</span><span class="sxs-lookup"><span data-stu-id="bf147-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="bf147-161">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="bf147-162">使用 **群組原則管理編輯器** 移至 [**電腦設定] 系統**  >  **管理範本**  >  **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **對應**。</span><span class="sxs-lookup"><span data-stu-id="bf147-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="bf147-163">在 [對應] 區段中，按兩下 **[設定第一次看到的封鎖] 功能**，並將其設定為 [ **啟用**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bf147-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="bf147-164">設定為 **Always prompt (0)** 會降低裝置的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="bf147-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="bf147-165">設定為 **永不傳送 (2)** 表示第一次看到的區塊將無法運作。</span><span class="sxs-lookup"><span data-stu-id="bf147-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="bf147-166">在 [對應] 區段中，在 **需要進一步分析時**，按兩下 [傳送檔案範例]，並將其設定為 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="bf147-167">在 [ **需要進一步分析時傳送檔範例**] 底下，選取 [ **傳送所有範例**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bf147-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="bf147-168">以您通常的方式，在您的網路上重新部署群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="bf147-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="bf147-169">在個別用戶端裝置上啟用第一次看到時，確認封鎖</span><span class="sxs-lookup"><span data-stu-id="bf147-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="bf147-170">您可以在個別的用戶端裝置上使用 Windows 安全性應用程式，確認第一次看到的組塊已啟用。</span><span class="sxs-lookup"><span data-stu-id="bf147-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="bf147-171">只要已開啟 **雲端提供的保護** 和 **自動範例提交** ，便會自動啟用封鎖初次看到的功能。</span><span class="sxs-lookup"><span data-stu-id="bf147-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="bf147-172">開啟 [Windows 安全性應用程式]。</span><span class="sxs-lookup"><span data-stu-id="bf147-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="bf147-173">選取 [ **病毒 & 威脅防護**]，然後在 [ **病毒 & 威脅防護設定**] 底下，選取 [ **管理設定**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Windows 安全性應用程式中的病毒 & 威脅防護設定] 標籤的螢幕擷取畫面](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="bf147-175">確認已開啟 **雲端提供的保護** 和 **自動範例提交** 。</span><span class="sxs-lookup"><span data-stu-id="bf147-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="bf147-176">如果使用群組原則來設定及部署必要條件設定，本節中所述的設定將會變灰，且無法在個別端點上使用。</span><span class="sxs-lookup"><span data-stu-id="bf147-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="bf147-177">您必須先將透過「群組原則」物件所做的變更部署到個別的端點，然後才會在 [Windows 設定] 中更新設定。</span><span class="sxs-lookup"><span data-stu-id="bf147-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="bf147-178">第一次看到的驗證區塊運作正常</span><span class="sxs-lookup"><span data-stu-id="bf147-178">Validate block at first sight is working</span></span>

<span data-ttu-id="bf147-179">若要驗證功能是否正常運作，請遵循 [驗證網路與雲端之間](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)連線的指導方針。</span><span class="sxs-lookup"><span data-stu-id="bf147-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="bf147-180">在第一次看到封鎖時關閉封鎖</span><span class="sxs-lookup"><span data-stu-id="bf147-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="bf147-181">在第一次看到時關閉區塊，將會降低裝置 (s) 和您的網路的保護狀態。</span><span class="sxs-lookup"><span data-stu-id="bf147-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="bf147-182">如果您想要保留必要條件設定，而不實際在第一次看到保護時使用區塊，您可以選擇停用 [在第一次看到時封鎖]。</span><span class="sxs-lookup"><span data-stu-id="bf147-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="bf147-183">您可能會在第一次看到封鎖時暫時關閉封鎖，以查看此功能對您的網路有何影響。</span><span class="sxs-lookup"><span data-stu-id="bf147-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="bf147-184">不過，我們不建議您在初次看到保護時停用封鎖。</span><span class="sxs-lookup"><span data-stu-id="bf147-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="bf147-185">在第一次使用 Microsoft 端點管理員時關閉封鎖</span><span class="sxs-lookup"><span data-stu-id="bf147-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="bf147-186">移至 [Microsoft 端點管理員管理中心] ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) 並登入]。</span><span class="sxs-lookup"><span data-stu-id="bf147-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="bf147-187">請移至 **端點安全性**  >  **防病毒**，然後選取您的 Microsoft Defender 防病毒原則。</span><span class="sxs-lookup"><span data-stu-id="bf147-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="bf147-188">在 [ **管理**] 下，選擇 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="bf147-189">在 [ **設定設定**] 旁，選擇 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="bf147-190">變更一或多個下列設定：</span><span class="sxs-lookup"><span data-stu-id="bf147-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="bf147-191">將 **雲端傳送保護開啟** 為 [ **否** ] 或 [ **未設定**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="bf147-192">將 **雲端傳送的保護等級** 設為 [ **未設定**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="bf147-193">清除 [ **Defender Cloud 擴充超時的秒數**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bf147-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="bf147-194">檢查並儲存您的設定。</span><span class="sxs-lookup"><span data-stu-id="bf147-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="bf147-195">在第一次使用群組原則時關閉封鎖</span><span class="sxs-lookup"><span data-stu-id="bf147-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="bf147-196">在您的群組原則管理電腦上，開啟 [ [群組原則管理主控台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))]，以滑鼠右鍵按一下您要設定的群組原則物件，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="bf147-197">使用 **群組原則管理編輯器** 移至 [ **電腦** 設定]，然後選取 [ **管理範本**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="bf147-198">透過 **Windows 元件**  >  **Microsoft Defender 防病毒**  >  **對應** 展開樹狀目錄。</span><span class="sxs-lookup"><span data-stu-id="bf147-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="bf147-199">按兩下 [設定 **第一次看到的封鎖] 功能** ，並將此選項設定為 [ **停用**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf147-200">停用區塊初次看到時，不會停用或變更必要條件群組原則。</span><span class="sxs-lookup"><span data-stu-id="bf147-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="bf147-201">不是企業系統管理員或 IT 專業人員？</span><span class="sxs-lookup"><span data-stu-id="bf147-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="bf147-202">如果您不是企業系統管理員或 IT 專業人員，但您在第一次看到封鎖時有問題，請參閱本節。</span><span class="sxs-lookup"><span data-stu-id="bf147-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="bf147-203">「第一次看到的封鎖」是威脅防護功能，可在幾秒內偵測並封鎖惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="bf147-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="bf147-204">雖然在「初次看到時封鎖」沒有特定設定，但在裝置上設定某些設定時會啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="bf147-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="bf147-205">操作方法：在您自己的裝置上初次看到或關閉封鎖</span><span class="sxs-lookup"><span data-stu-id="bf147-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="bf147-206">如果您有未由組織管理的個人裝置，您可能想知道如何在第一次看到或關閉時關閉封鎖功能。</span><span class="sxs-lookup"><span data-stu-id="bf147-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="bf147-207">您可以使用 Windows 安全性應用程式，在初次看到時管理區塊。</span><span class="sxs-lookup"><span data-stu-id="bf147-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="bf147-208">在您的 Windows 10 電腦上，開啟 [Windows 安全性應用程式]。</span><span class="sxs-lookup"><span data-stu-id="bf147-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="bf147-209">選取 [ **病毒 & 威脅防護**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="bf147-210">在 [ **病毒 & 威脅防護設定**] 底下，選取 [ **管理設定**]。</span><span class="sxs-lookup"><span data-stu-id="bf147-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="bf147-211">請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="bf147-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="bf147-212">若要在初次看到時啟用封鎖，請確定已同時開啟 **雲端傳送保護** 和 **自動範例提交** 。</span><span class="sxs-lookup"><span data-stu-id="bf147-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="bf147-213">若要在第一次看到時停用封鎖，請關閉已 **提供雲端保護** 或 **自動範例提交**。</span><span class="sxs-lookup"><span data-stu-id="bf147-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="bf147-214">在初次看到時關閉區塊，會降低裝置的保護層級。</span><span class="sxs-lookup"><span data-stu-id="bf147-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="bf147-215">我們不建議您在初次看到時，永久停用區塊。</span><span class="sxs-lookup"><span data-stu-id="bf147-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="bf147-216">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bf147-216">See also</span></span>

- [<span data-ttu-id="bf147-217">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="bf147-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="bf147-218">啟用雲端傳送保護</span><span class="sxs-lookup"><span data-stu-id="bf147-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bf147-219">使用 Windows 安全性保持受保護</span><span class="sxs-lookup"><span data-stu-id="bf147-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)