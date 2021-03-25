---
title: 手動部署 macOS 的 Microsoft Defender ATP
description: 從命令列手動安裝 macOS 的 Microsoft Defender ATP。
keywords: microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamf，macos，catalina，mojave，高塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b2629eb3d13e6eb908644dfcade46a7ac2768637
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187442"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="39ad2-104">macOS 的 Microsoft Defender 端點的手動部署</span><span class="sxs-lookup"><span data-stu-id="39ad2-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39ad2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="39ad2-105">**Applies to:**</span></span>
- [<span data-ttu-id="39ad2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="39ad2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="39ad2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39ad2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="39ad2-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="39ad2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="39ad2-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="39ad2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="39ad2-110">本主題說明如何手動為 macOS 部署 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="39ad2-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="39ad2-111">成功的部署需要完成下列所有步驟：</span><span class="sxs-lookup"><span data-stu-id="39ad2-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="39ad2-112">下載安裝和上架套件</span><span class="sxs-lookup"><span data-stu-id="39ad2-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="39ad2-113">應用程式安裝 (macOS 10.15 和舊版) </span><span class="sxs-lookup"><span data-stu-id="39ad2-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="39ad2-114">應用程式安裝 (macOS 11 和更新版本) </span><span class="sxs-lookup"><span data-stu-id="39ad2-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="39ad2-115">用戶端設定</span><span class="sxs-lookup"><span data-stu-id="39ad2-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="39ad2-116">必要條件和系統需求</span><span class="sxs-lookup"><span data-stu-id="39ad2-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="39ad2-117">開始之前，請參閱 [macOS 頁面的主要 Microsoft Defender For Endpoint](microsoft-defender-endpoint-mac.md) ，以取得目前軟體版本之必要條件和系統需求的描述。</span><span class="sxs-lookup"><span data-stu-id="39ad2-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="39ad2-118">下載安裝和上架套件</span><span class="sxs-lookup"><span data-stu-id="39ad2-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="39ad2-119">從 Microsoft Defender Security Center 下載安裝和上架套件：</span><span class="sxs-lookup"><span data-stu-id="39ad2-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="39ad2-120">在 Microsoft Defender Security Center 中，移至 [ **設定] > 裝置管理 > 上架**]。</span><span class="sxs-lookup"><span data-stu-id="39ad2-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="39ad2-121">在頁面的區段1中，將 [作業系統] 設定為 **macOS** ，並將 Deployment 方法設定為 **本機腳本**。</span><span class="sxs-lookup"><span data-stu-id="39ad2-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="39ad2-122">在頁面的區段2中，選取 [ **下載安裝套件**]。</span><span class="sxs-lookup"><span data-stu-id="39ad2-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="39ad2-123">將其儲存為 wdav。 pkg 至本機目錄。</span><span class="sxs-lookup"><span data-stu-id="39ad2-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="39ad2-124">在頁面的區段2中，選取 [ **下載上架套件**]。</span><span class="sxs-lookup"><span data-stu-id="39ad2-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="39ad2-125">將它儲存成 WindowsDefenderATPOnboardingPackage.zip 相同的目錄。</span><span class="sxs-lookup"><span data-stu-id="39ad2-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Microsoft Defender 安全中心螢幕擷取畫面](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="39ad2-127">在命令提示字元中，確認您有兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="39ad2-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="39ad2-128">應用程式安裝 (macOS 10.15 和舊版) </span><span class="sxs-lookup"><span data-stu-id="39ad2-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="39ad2-129">若要完成此程式，您必須具有裝置的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="39ad2-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="39ad2-130">流覽至 Finder 中已下載的 wdav，然後開啟它。</span><span class="sxs-lookup"><span data-stu-id="39ad2-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![App 安裝 screenshot1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. <span data-ttu-id="39ad2-132">選取 [ **繼續**]，同意授權條款，然後在出現提示時輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="39ad2-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![App 安裝 screenshot2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > <span data-ttu-id="39ad2-134">系統會提示您允許安裝來自 Microsoft 的驅動程式， (「系統擴充封鎖」或「保留安裝」或兩者皆有）。</span><span class="sxs-lookup"><span data-stu-id="39ad2-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="39ad2-135">必須允許安裝驅動程式。</span><span class="sxs-lookup"><span data-stu-id="39ad2-135">The driver must be allowed to be installed.</span></span>

   ![App 安裝 screenshot3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. <span data-ttu-id="39ad2-137">選取 [ **開啟安全性** 設定] 或 [ **開啟系統偏好設定] > 安全性 & 隱私權**。</span><span class="sxs-lookup"><span data-stu-id="39ad2-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="39ad2-138">選取 [ **允許**]：</span><span class="sxs-lookup"><span data-stu-id="39ad2-138">Select **Allow**:</span></span>

    ![安全性和隱私權視窗螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   <span data-ttu-id="39ad2-140">安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="39ad2-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="39ad2-141">如果您未選取 [ **允許**]，安裝將在5分鐘之後繼續進行。</span><span class="sxs-lookup"><span data-stu-id="39ad2-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="39ad2-142">將會載入 Microsoft Defender for Endpoint，但某些功能（例如即時保護）將會停用。</span><span class="sxs-lookup"><span data-stu-id="39ad2-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="39ad2-143">如需如何解決此問題的資訊，請參閱 [內核擴充問題疑難排解](mac-support-kext.md) 。</span><span class="sxs-lookup"><span data-stu-id="39ad2-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="39ad2-144">在第一次安裝 Microsoft Defender for Endpoint 時，macOS 可能要求重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="39ad2-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="39ad2-145">在重新開機裝置之前，即時保護將無法使用。</span><span class="sxs-lookup"><span data-stu-id="39ad2-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="39ad2-146">應用程式安裝 (macOS 11 和更新版本) </span><span class="sxs-lookup"><span data-stu-id="39ad2-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="39ad2-147">若要完成此程式，您必須具有裝置的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="39ad2-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="39ad2-148">流覽至 Finder 中已下載的 wdav，然後開啟它。</span><span class="sxs-lookup"><span data-stu-id="39ad2-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![App 安裝 screenshot4](images/big-sur-install-1.png)

2. <span data-ttu-id="39ad2-150">選取 [ **繼續**]，同意授權條款，然後在出現提示時輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="39ad2-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="39ad2-151">在安裝程式結束時，您將會提升，以核准產品所用的系統擴充。</span><span class="sxs-lookup"><span data-stu-id="39ad2-151">At the end of the installation process, you will be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="39ad2-152">選取 [ **開啟安全性喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="39ad2-152">Select **Open Security Preferences**.</span></span>

    ![系統分機核准](images/big-sur-install-2.png)

4. <span data-ttu-id="39ad2-154">在 [ **安全性 & 隱私權** ] 視窗中，選取 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="39ad2-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![系統分機安全性 preferences1](images/big-sur-install-3.png)

5. <span data-ttu-id="39ad2-156">針對 Mac 的端點，針對所有隨 Microsoft Defender for Endpoint 發佈的系統擴充，重複步驟 3 & 4。</span><span class="sxs-lookup"><span data-stu-id="39ad2-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="39ad2-157">做為端點偵測和回應功能的一部分，Mac 版端點的 Microsoft Defender 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender Security Center 入口網站。</span><span class="sxs-lookup"><span data-stu-id="39ad2-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="39ad2-158">當系統提示您授與 Microsoft Defender for Endpoint 許可權以篩選網路流量時，請選取 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="39ad2-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![系統分機安全性 preferences2](images/big-sur-install-4.png)

7. <span data-ttu-id="39ad2-160">開啟 **系統偏好設定**  >  **安全性 & 隱私權** 及流覽至 **[隱私權**] 索引標籤。授與 **microsoft defender atp** 和 **microsoft defender atp Endpoint Security Extension** 的 **完整磁片存取** 許可權。</span><span class="sxs-lookup"><span data-stu-id="39ad2-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![完全磁片存取](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="39ad2-162">用戶端設定</span><span class="sxs-lookup"><span data-stu-id="39ad2-162">Client configuration</span></span>

1. <span data-ttu-id="39ad2-163">將 wdav pkg 和 MicrosoftDefenderATPOnboardingMacOs.py 複製到您為 macOS 部署 Microsoft Defender for Endpoint 的裝置。</span><span class="sxs-lookup"><span data-stu-id="39ad2-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="39ad2-164">用戶端裝置與 orgId 未關聯。</span><span class="sxs-lookup"><span data-stu-id="39ad2-164">The client device is not associated with orgId.</span></span> <span data-ttu-id="39ad2-165">請注意， *orgId* 屬性是空白的。</span><span class="sxs-lookup"><span data-stu-id="39ad2-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="39ad2-166">執行 Python 腳本以安裝設定檔：</span><span class="sxs-lookup"><span data-stu-id="39ad2-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="39ad2-167">請確認裝置現在與您的組織有關聯，並報告有效的 *orgId*：</span><span class="sxs-lookup"><span data-stu-id="39ad2-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="39ad2-168">安裝之後，您會在右上角的 macOS 狀態列中看到 Microsoft Defender 圖示。</span><span class="sxs-lookup"><span data-stu-id="39ad2-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![狀態列上的 Microsoft Defender 圖示螢幕擷取畫面](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="39ad2-170">如何允許完整磁片存取</span><span class="sxs-lookup"><span data-stu-id="39ad2-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="39ad2-171">macOS 10.15 (Catalina) 包含新的安全性和隱私權增強功能。</span><span class="sxs-lookup"><span data-stu-id="39ad2-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="39ad2-172">從這個版本開始，依預設，應用程式無法存取磁片 (上的某些位置，例如檔、下載、桌面等 ) 不經明確同意。</span><span class="sxs-lookup"><span data-stu-id="39ad2-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="39ad2-173">在缺少這種同意的情況下，Microsoft Defender for Endpoint 無法完全保護您的裝置。</span><span class="sxs-lookup"><span data-stu-id="39ad2-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="39ad2-174">若要授與同意，請開啟系統偏好設定-> 安全性 & 隱私權-> 隱私權-> 完整磁片存取。</span><span class="sxs-lookup"><span data-stu-id="39ad2-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="39ad2-175">按一下鎖定圖示，在對話方塊的底部 () 。</span><span class="sxs-lookup"><span data-stu-id="39ad2-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="39ad2-176">選取 [Microsoft Defender for Endpoint]。</span><span class="sxs-lookup"><span data-stu-id="39ad2-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="39ad2-177">記錄安裝問題</span><span class="sxs-lookup"><span data-stu-id="39ad2-177">Logging installation issues</span></span>

<span data-ttu-id="39ad2-178">如需詳細資訊，請參閱 [記錄安裝的問題](mac-resources.md#logging-installation-issues) ，以取得如何在錯誤發生時，尋找安裝程式所建立的自動產生記錄。</span><span class="sxs-lookup"><span data-stu-id="39ad2-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="39ad2-179">卸載</span><span class="sxs-lookup"><span data-stu-id="39ad2-179">Uninstallation</span></span>

<span data-ttu-id="39ad2-180">請參閱 [卸載](mac-resources.md#uninstalling) 以取得如何從用戶端裝置移除 Microsoft Defender For macOS 端點的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="39ad2-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
