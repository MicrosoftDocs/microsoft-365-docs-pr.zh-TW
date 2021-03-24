---
title: 在 Jamf Pro 中為 macOS 原則設定 Microsoft Defender ATP
description: 瞭解如何在 Jamf Pro 中設定 Microsoft Defender ATP 以取得 macOS 原則
keywords: 原則，microsoft，defender，atp，mac，安裝，部署，卸載，intune，jamfpro，macos，catalina，mojave，高塞拉里昂
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
ms.openlocfilehash: 1559d8dca6b6909f22473c5a8f4d25d4bac501d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057388"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a><span data-ttu-id="cf765-104">在 Jamf Pro 中設定 macOS 原則的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cf765-104">Set up the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cf765-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="cf765-105">**Applies to:**</span></span>

- [<span data-ttu-id="cf765-106">Mac 版端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="cf765-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="cf765-107">此頁面會引導您完成在 Jamf Pro 中設定 macOS 原則所需採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="cf765-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="cf765-108">您必須採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cf765-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="cf765-109">取得 Microsoft Defender for Endpoint 上架套件</span><span class="sxs-lookup"><span data-stu-id="cf765-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="cf765-110">使用上架套件在 Jamf Pro 中建立設定檔</span><span class="sxs-lookup"><span data-stu-id="cf765-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="cf765-111">設定 Microsoft Defender for Endpoint 設定</span><span class="sxs-lookup"><span data-stu-id="cf765-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="cf765-112">設定 Microsoft Defender for Endpoint notification 設定</span><span class="sxs-lookup"><span data-stu-id="cf765-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="cf765-113">設定 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="cf765-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="cf765-114">授與 Microsoft Defender for Endpoint 的完整磁片存取權</span><span class="sxs-lookup"><span data-stu-id="cf765-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="cf765-115">核准 Microsoft Defender for Endpoint 的內核擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="cf765-116">核准 Microsoft Defender for Endpoint 的系統擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="cf765-117">設定網路擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="cf765-118">使用 Mac 的 Microsoft Defender 端點排程掃描</span><span class="sxs-lookup"><span data-stu-id="cf765-118">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="cf765-119">為 macOS 部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cf765-119">Deploy Microsoft Defender for Endpoint for macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="cf765-120">步驟1：取得 Microsoft Defender for Endpoint 上架套件</span><span class="sxs-lookup"><span data-stu-id="cf765-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="cf765-121">在 [Microsoft Defender Security Center](https://securitycenter.microsoft.com )中，流覽至 [ **設定] > 上架**。</span><span class="sxs-lookup"><span data-stu-id="cf765-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="cf765-122">選取 [macOS 為作業系統] 和 [行動裝置管理/Microsoft Intune] 做為部署方法。</span><span class="sxs-lookup"><span data-stu-id="cf765-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Microsoft Defender 安全中心的影像](images/onboarding-macos.png)

3. <span data-ttu-id="cf765-124">選取 [ (WindowsDefenderATPOnboardingPackage.zip) **下載上架套件** ]。</span><span class="sxs-lookup"><span data-stu-id="cf765-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="cf765-125">解壓縮 `WindowsDefenderATPOnboardingPackage.zip` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="cf765-126">將檔案複製到您的慣用位置。</span><span class="sxs-lookup"><span data-stu-id="cf765-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="cf765-127">例如，  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。</span><span class="sxs-lookup"><span data-stu-id="cf765-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="cf765-128">步驟2：使用上架套件在 Jamf Pro 中建立設定檔</span><span class="sxs-lookup"><span data-stu-id="cf765-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="cf765-129">`WindowsDefenderATPOnboarding.plist`從上一節中找出檔。</span><span class="sxs-lookup"><span data-stu-id="cf765-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![WindowsDefenderATPOnboarding 檔案的影像](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="cf765-131">在 Jamf Pro 儀表板中，選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![建立新的 Jamf Pro 儀表板的影像](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="cf765-133">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-133">Enter the following details:</span></span>

   <span data-ttu-id="cf765-134">**一般**</span><span class="sxs-lookup"><span data-stu-id="cf765-134">**General**</span></span>
   - <span data-ttu-id="cf765-135">名稱： MDATP 上架 macOS</span><span class="sxs-lookup"><span data-stu-id="cf765-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="cf765-136">描述： macOS 的 MDATP EDR 上架</span><span class="sxs-lookup"><span data-stu-id="cf765-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="cf765-137">類別：無</span><span class="sxs-lookup"><span data-stu-id="cf765-137">Category: None</span></span>
   - <span data-ttu-id="cf765-138">分配方法：自動安裝</span><span class="sxs-lookup"><span data-stu-id="cf765-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="cf765-139">層級：電腦層級</span><span class="sxs-lookup"><span data-stu-id="cf765-139">Level: Computer Level</span></span>

4. <span data-ttu-id="cf765-140">在 **應用程式 & 自訂設定** 中，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Configurate 應用程式和自訂設定的影像](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="cf765-142">選取 **[ (PLIST 檔案) 上傳** 檔案]，然後在 [ **喜好設定功能變數名稱** ] 中輸入： `com.microsoft.wdav.atp` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Jamfpro plist 上傳檔案的影像](images/jamfpro-plist-upload.png)

    ![上傳檔案屬性清單檔案的影像](images/jamfpro-plist-file.png)

7. <span data-ttu-id="cf765-145">選取 [ **開啟** ]，然後選取上架檔案。</span><span class="sxs-lookup"><span data-stu-id="cf765-145">Select **Open** and select the onboarding file.</span></span>

    ![上架檔案的影像](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="cf765-147">選取 **[上傳**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-147">Select **Upload**.</span></span> 

    ![上傳 plist 檔的影像](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="cf765-149">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-149">Select the **Scope** tab.</span></span>

    ![範圍] 索引標籤的影像](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="cf765-151">選取目的電腦。</span><span class="sxs-lookup"><span data-stu-id="cf765-151">Select the target computers.</span></span>

    ![目的電腦的影像](images/jamfpro-target-computer.png)

    ![目標影像](images/jamfpro-targets.png) 

11. <span data-ttu-id="cf765-154">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-154">Select **Save**.</span></span>

    ![部署目的電腦的映射](images/jamfpro-deployment-target.png)

    ![選取目的電腦的影像](images/jamfpro-target-selected.png)

12. <span data-ttu-id="cf765-157">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-157">Select **Done**.</span></span>

    ![目標群組電腦的影像](images/jamfpro-target-group.png)

    ![配置檔案清單](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="cf765-160">步驟3：設定 Microsoft Defender for Endpoint 設定</span><span class="sxs-lookup"><span data-stu-id="cf765-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="cf765-161">使用下列 Microsoft Defender for Endpoint configuration 設定：</span><span class="sxs-lookup"><span data-stu-id="cf765-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="cf765-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="cf765-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="cf765-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="cf765-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="cf765-164">預設未開啟，如果您打算為 macOS 執行協力廠商 AV，請將其設為 `true` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="cf765-165">排除</span><span class="sxs-lookup"><span data-stu-id="cf765-165">exclusions</span></span>
    - <span data-ttu-id="cf765-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="cf765-166">excludedPath</span></span>
    - <span data-ttu-id="cf765-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="cf765-167">excludedFileExtension</span></span>
    - <span data-ttu-id="cf765-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="cf765-168">excludedFileName</span></span>
    - <span data-ttu-id="cf765-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="cf765-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="cf765-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="cf765-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="cf765-171">EICAR.TXT 位於範例上，如果您想要透過概念證明，請將它移除，尤其是在您測試 EICAR.TXT 時。</span><span class="sxs-lookup"><span data-stu-id="cf765-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="cf765-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="cf765-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="cf765-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="cf765-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="cf765-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="cf765-174">archive_bomb</span></span>
    - <span data-ttu-id="cf765-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="cf765-175">cloudService</span></span>
    - <span data-ttu-id="cf765-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="cf765-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="cf765-177">標籤</span><span class="sxs-lookup"><span data-stu-id="cf765-177">tags</span></span>
    - <span data-ttu-id="cf765-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="cf765-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="cf765-179">如需詳細資訊，請參閱 [Jamf 設定檔的屬性清單](mac-preferences.md#property-list-for-jamf-configuration-profile)。</span><span class="sxs-lookup"><span data-stu-id="cf765-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="cf765-180">將檔案儲存為 `MDATP_MDAV_configuration_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="cf765-181">在 Jamf Pro 儀表板中，選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![新 Jamf Pro 儀表板的影像](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="cf765-183">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-183">Enter the following details:</span></span>

    <span data-ttu-id="cf765-184">**一般**</span><span class="sxs-lookup"><span data-stu-id="cf765-184">**General**</span></span>
    
    - <span data-ttu-id="cf765-185">名稱： MDATP MDAV 設定設定</span><span class="sxs-lookup"><span data-stu-id="cf765-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="cf765-186">描述：\<blank\></span><span class="sxs-lookup"><span data-stu-id="cf765-186">Description:\<blank\></span></span>
    - <span data-ttu-id="cf765-187">類別：無 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-187">Category: None (default)</span></span>
    - <span data-ttu-id="cf765-188">分配方法：自動安裝 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="cf765-189">層級：電腦層級 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-189">Level: Computer Level(default)</span></span>

    ![MDATP MDAV 配置設定的影像](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="cf765-191">在 **應用程式 & 自訂設定** 中，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![應用程式和自訂設定的影像](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="cf765-193">選取 **[上傳檔案 (PLIST** 檔案]) 。</span><span class="sxs-lookup"><span data-stu-id="cf765-193">Select **Upload File (PLIST file)**.</span></span>

    ![配置設定 plist 檔案的影像](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="cf765-195">在 [ **喜好設定網域**] 中，輸入 `com.microsoft.wdav` ，然後選取  **[上傳 PLIST** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="cf765-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![配置設定偏好設定網域的影像](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="cf765-197">選取 **[選擇檔**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-197">Select **Choose File**.</span></span>

    ![設定的配置圖像選擇 [檔案]](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="cf765-199">選取 **MDATP_MDAV_configuration_settings plist**，然後選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Mdatpmdav 配置設定的影像](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="cf765-201">選取 **[上傳**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-201">Select **Upload**.</span></span>

    ![設定的配置圖像上載](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![配置設定上傳圖像的圖像](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="cf765-204">如果您要上傳 Intune 檔案，您會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="cf765-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="cf765-205">![配置設定的映射 intune 檔案上傳](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="cf765-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="cf765-206">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-206">Select **Save**.</span></span> 

    ![配置設定的影像儲存影像](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="cf765-208">檔案上傳。</span><span class="sxs-lookup"><span data-stu-id="cf765-208">The file is uploaded.</span></span>

    ![設定檔上傳圖像的圖像](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![上傳的配置設定檔案影像](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="cf765-211">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-211">Select the **Scope** tab.</span></span>

    ![設定的配置範圍影像](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="cf765-213">選取 [ **Contoso 的電腦群組**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="cf765-214">選取 [ **新增**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-214">Select **Add**, then select **Save**.</span></span>

    ![配置設定 addsav 的影像](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![配置設定的影像儲存新增](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="cf765-217">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-217">Select **Done**.</span></span> <span data-ttu-id="cf765-218">您將會看到新的設定 **設定檔**。</span><span class="sxs-lookup"><span data-stu-id="cf765-218">You'll see the new **Configuration profile**.</span></span>

    ![設定設定檔影像的影像](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="cf765-220">步驟4：設定通知設定</span><span class="sxs-lookup"><span data-stu-id="cf765-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="cf765-221">這些步驟適用于 macOS 10.15 (Catalina) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="cf765-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="cf765-222">`notif.mobileconfig`從[我們的 GitHub 存放庫](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)下載</span><span class="sxs-lookup"><span data-stu-id="cf765-222">Download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span></span>

2. <span data-ttu-id="cf765-223">將其儲存為 `MDATP_MDAV_notification_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-223">Save it as `MDATP_MDAV_notification_settings.plist`.</span></span>

3. <span data-ttu-id="cf765-224">在 Jamf Pro 儀表板中，選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-224">In the Jamf Pro dashboard, select **General**.</span></span> 
       
4. <span data-ttu-id="cf765-225">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-225">Enter the following details:</span></span>

    <span data-ttu-id="cf765-226">**一般**</span><span class="sxs-lookup"><span data-stu-id="cf765-226">**General**</span></span> 
    
    - <span data-ttu-id="cf765-227">名稱： MDATP MDAV 通知設定</span><span class="sxs-lookup"><span data-stu-id="cf765-227">Name: MDATP MDAV Notification settings</span></span>
    - <span data-ttu-id="cf765-228">描述： macOS 10.15 (Catalina) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="cf765-228">Description: macOS 10.15 (Catalina) or newer</span></span>
    - <span data-ttu-id="cf765-229">類別：無 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-229">Category: None (default)</span></span>
    - <span data-ttu-id="cf765-230">分配方法：自動安裝 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-230">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="cf765-231">層級：電腦層級 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-231">Level: Computer Level(default)</span></span>

    ![配置設定 mdatpmdav 的影像](images/c9820a5ff84aaf21635c04a23a97ca93.png)


5. <span data-ttu-id="cf765-233">選取 **[上傳檔案 (PLIST** 檔案]) 。</span><span class="sxs-lookup"><span data-stu-id="cf765-233">Select **Upload File (PLIST file)**.</span></span>

    ![上傳 plistfile 的配置設定影像](images/7f9138053dbcbf928e5182ee7b295ebe.png)
 

6. <span data-ttu-id="cf765-235">選取 **[選擇** 檔案  >  **MDATP_MDAV_Notification_Settings。 plist**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-235">Select **Choose File** > **MDATP_MDAV_Notification_Settings.plist**.</span></span>


    ![設定 mdatpmdav notsettings 的映射](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)


    ![設定 mdatpmdav notifsettings 的映射](images/20e33b98eb54447881dc6c89e58b890f.png)

7. <span data-ttu-id="cf765-238">選取  >  **[開啟上傳**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-238">Select **Open** > **Upload**.</span></span>

    ![Upl img 的配置設定影像](images/7697c33b9fd376ae5a8023d01f9d3857.png)


    ![配置設定 upl 影像的影像](images/2bda9244ec25d1526811da4ea91b1c86.png)

8. <span data-ttu-id="cf765-241">選取 [ **範圍** ] 索引標籤，然後選取 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-241">Select the **Scope** tab, then select **Add**.</span></span>

    ![設定範圍新增的映射](images/441aa2ecd36abadcdd8aed03556080b5.png)


9. <span data-ttu-id="cf765-243">選取 [ **Contoso 的電腦群組**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-243">Select **Contoso's Machine Group**.</span></span> 

10. <span data-ttu-id="cf765-244">選取 [ **新增**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-244">Select **Add**, then select **Save**.</span></span>
    
    ![設定設定 contoso 機器 grp 儲存的影像](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    
    ![設定的配置圖像新增儲存](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

11. <span data-ttu-id="cf765-247">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-247">Select **Done**.</span></span> <span data-ttu-id="cf765-248">您將會看到新的設定 **設定檔**。</span><span class="sxs-lookup"><span data-stu-id="cf765-248">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="cf765-249">![設定的圖像配置設定完成 img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="cf765-249">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="cf765-250">步驟5：設定 Microsoft AutoUpdate (MAU) </span><span class="sxs-lookup"><span data-stu-id="cf765-250">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="cf765-251">使用下列 Microsoft Defender for Endpoint configuration 設定：</span><span class="sxs-lookup"><span data-stu-id="cf765-251">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="cf765-252">將其儲存為 `MDATP_MDAV_MAU_settings.plist` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-252">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="cf765-253">在 Jamf Pro 儀表板中，選取 **[一般**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-253">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![設定的圖像配置一般影像](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="cf765-255">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-255">Enter the following details:</span></span>

    <span data-ttu-id="cf765-256">**一般**</span><span class="sxs-lookup"><span data-stu-id="cf765-256">**General**</span></span> 
    
    - <span data-ttu-id="cf765-257">名稱： MDATP MDAV MAU 設定</span><span class="sxs-lookup"><span data-stu-id="cf765-257">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="cf765-258">描述： macOS 的 MDATP 的 Microsoft AutoUpdate 設定</span><span class="sxs-lookup"><span data-stu-id="cf765-258">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="cf765-259">類別：無 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-259">Category: None (default)</span></span>
    - <span data-ttu-id="cf765-260">分配方法：自動安裝 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-260">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="cf765-261">層級：電腦層級 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-261">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="cf765-262">在 **應用程式 & 自訂設定** 中，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-262">In **Application & Custom Settings** select **Configure**.</span></span>

    ![設定的映射設定應用程式和自訂設定](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="cf765-264">選取 **[上傳檔案 (PLIST** 檔案]) 。</span><span class="sxs-lookup"><span data-stu-id="cf765-264">Select **Upload File (PLIST file)**.</span></span>

    ![設定 plist 的影像](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="cf765-266">在 [ **喜好設定網域** ] 中輸入： `com.microsoft.autoupdate2` ，然後選取 **[上傳 PLIST** 檔案]。</span><span class="sxs-lookup"><span data-stu-id="cf765-266">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![設定 pref 網域的配置圖像](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="cf765-268">選取 **[選擇檔**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-268">Select **Choose File**.</span></span>

    ![設定 choosefile 的影像](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="cf765-270">選取 **MDATP_MDAV_MAU_settings plist**。</span><span class="sxs-lookup"><span data-stu-id="cf765-270">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![設定 mdatpmdavmau 設定的影像](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="cf765-272">選取 **[上傳**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-272">Select **Upload**.</span></span>
    <span data-ttu-id="cf765-273">![設定 uplimage 的影像](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="cf765-273">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![設定 uplimg 的影像](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="cf765-275">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-275">Select **Save**.</span></span>

    ![設定 saveimg 的影像](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="cf765-277">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-277">Select the **Scope** tab.</span></span>
   
     ![設定 scopetab 的影像](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="cf765-279">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="cf765-279">Select **Add**.</span></span>
    
    ![設定 addimg1 的影像](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![設定 addimg2 的影像](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![設定 addimg3 的影像](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="cf765-283">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-283">Select **Done**.</span></span>
    
    ![設定 doneimage 的影像](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="cf765-285">步驟6：授與 Microsoft Defender for Endpoint 的完整磁片存取權</span><span class="sxs-lookup"><span data-stu-id="cf765-285">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="cf765-286">在 Jamf Pro 儀表板中，選取 [設定 **設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-286">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![設定設定檔的映射](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="cf765-288">選取 [ **+ 新增**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-288">Select **+ New**.</span></span> 

3. <span data-ttu-id="cf765-289">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-289">Enter the following details:</span></span>

    <span data-ttu-id="cf765-290">**一般**</span><span class="sxs-lookup"><span data-stu-id="cf765-290">**General**</span></span> 
    - <span data-ttu-id="cf765-291">名稱： MDATP MDAV-對 EDR 和 AV 授與完整磁片存取權</span><span class="sxs-lookup"><span data-stu-id="cf765-291">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="cf765-292">描述：在 macOS Catalina 或更新版本上，新增隱私權偏好設定原則控制</span><span class="sxs-lookup"><span data-stu-id="cf765-292">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="cf765-293">類別：無</span><span class="sxs-lookup"><span data-stu-id="cf765-293">Category: None</span></span>
    - <span data-ttu-id="cf765-294">分配方法：自動安裝</span><span class="sxs-lookup"><span data-stu-id="cf765-294">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="cf765-295">層級：電腦層級</span><span class="sxs-lookup"><span data-stu-id="cf765-295">Level: Computer level</span></span>


    ![一般的設定圖像配置](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="cf765-297">在 [ **設定隱私權偏好設定原則控制** ] 中，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-297">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![設定隱私權原則控制的影像](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="cf765-299">在 [ **隱私權偏好設定原則**] 中，輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-299">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="cf765-300">識別碼： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="cf765-300">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="cf765-301">識別碼類型：束識別碼</span><span class="sxs-lookup"><span data-stu-id="cf765-301">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="cf765-302">程式碼需求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="cf765-302">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![設定的圖像設定隱私權喜好原則控制詳細資料](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="cf765-304">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-304">Select **+ Add**.</span></span>

    ![設定的圖像設定新增系統原則所有檔案](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="cf765-306">在應用程式或服務中：設定為 **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="cf765-306">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="cf765-307">在 [access] 底下：設定為 **允許**</span><span class="sxs-lookup"><span data-stu-id="cf765-307">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="cf765-308">選取 [ **儲存** (]，而不是位於右下方) 。</span><span class="sxs-lookup"><span data-stu-id="cf765-308">Select **Save** (not the one at the bottom right).</span></span>

    ![設定的圖像配置儲存影像](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="cf765-310">按一下 [ `+` **應用程式存取** ] 旁的符號，以加入新的專案。</span><span class="sxs-lookup"><span data-stu-id="cf765-310">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![設定的配置圖像設定應用程式存取](images/tcc-add-entry.png)

9. <span data-ttu-id="cf765-312">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-312">Enter the following details:</span></span>

    - <span data-ttu-id="cf765-313">識別碼： `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="cf765-313">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="cf765-314">識別碼類型：束識別碼</span><span class="sxs-lookup"><span data-stu-id="cf765-314">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="cf765-315">程式碼需求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="cf765-315">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="cf765-316">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-316">Select **+ Add**.</span></span>

    ![設定 tcc epsext 專案的影像](images/tcc-epsext-entry.png)

    - <span data-ttu-id="cf765-318">在應用程式或服務中：設定為 **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="cf765-318">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="cf765-319">在 [access] 底下：設定為 **允許**</span><span class="sxs-lookup"><span data-stu-id="cf765-319">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="cf765-320">選取 [ **儲存** (]，而不是位於右下方) 。</span><span class="sxs-lookup"><span data-stu-id="cf765-320">Select **Save** (not the one at the bottom right).</span></span>

    ![設定的圖像 tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="cf765-322">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-322">Select the **Scope** tab.</span></span>

    ![設定設定範圍的影像](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="cf765-324">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-324">Select **+ Add**.</span></span>

    ![設定 addimage 的影像](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="cf765-326">選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的 MachineGroup**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-326">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![設定為 contoso machinegrp 的配置圖像](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="cf765-328">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="cf765-328">Select **Add**.</span></span> 

16. <span data-ttu-id="cf765-329">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-329">Select **Save**.</span></span> 
    
17. <span data-ttu-id="cf765-330">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-330">Select **Done**.</span></span>
    
    ![設定 donimg 的影像](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![設定 donimg2 的影像](images/6c8b406ee224335a8c65d06953dc756e.png)


## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="cf765-333">步驟7：核准 Microsoft Defender for Endpoint 的內核擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-333">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="cf765-334">在設定配置 **檔** 中，選取 [ **+ 新增**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-334">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自動產生社交媒體發佈描述的螢幕擷取畫面](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="cf765-336">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-336">Enter the following details:</span></span>

    <span data-ttu-id="cf765-337">**一般**</span><span class="sxs-lookup"><span data-stu-id="cf765-337">**General**</span></span> 
    
    - <span data-ttu-id="cf765-338">名稱： MDATP MDAV 內核擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-338">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="cf765-339">描述： MDATP 內核擴充 (kext) </span><span class="sxs-lookup"><span data-stu-id="cf765-339">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="cf765-340">類別：無</span><span class="sxs-lookup"><span data-stu-id="cf765-340">Category: None</span></span>
    - <span data-ttu-id="cf765-341">分配方法：自動安裝</span><span class="sxs-lookup"><span data-stu-id="cf765-341">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="cf765-342">層級：電腦層級</span><span class="sxs-lookup"><span data-stu-id="cf765-342">Level: Computer Level</span></span>

    ![Mdatpmdav 內核的設定配置圖像](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="cf765-344">在 [ **設定核准的核心擴充** ] 中，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-344">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![已核准的內核分機的配置設定影像](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="cf765-346">在 **核准的內核擴充** 輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-346">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="cf765-347">顯示名稱： Microsoft Corp。</span><span class="sxs-lookup"><span data-stu-id="cf765-347">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="cf765-348">團隊 ID: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="cf765-348">Team ID: UBF8T346G9</span></span>

    ![Appr 內核擴充設定的配置設定映射](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="cf765-350">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-350">Select the **Scope** tab.</span></span>

    ![設定的 [設定範圍] 索引標籤 m 的影像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="cf765-352">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-352">Select **+ Add**.</span></span>

7. <span data-ttu-id="cf765-353">選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的機器群組**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-353">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="cf765-354">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-354">Select **+ Add**.</span></span>

    ![配置設定的影像新增影像](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="cf765-356">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-356">Select **Save**.</span></span>

    ![配置設定 saveimag 的影像](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="cf765-358">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-358">Select **Done**.</span></span>

    ![配置設定 doneimag 的影像](images/1c9bd3f68db20b80193dac18f33c22d0.png)


## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="cf765-360">步驟8：核准 Microsoft Defender for Endpoint 的系統擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-360">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="cf765-361">在設定配置 **檔** 中，選取 [ **+ 新增**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-361">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![自動產生社交媒體發佈描述的螢幕擷取畫面](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="cf765-363">輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-363">Enter the following details:</span></span>

    <span data-ttu-id="cf765-364">**一般**</span><span class="sxs-lookup"><span data-stu-id="cf765-364">**General**</span></span>
    
    - <span data-ttu-id="cf765-365">名稱： MDATP MDAV 系統擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-365">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="cf765-366">描述： MDATP 系統擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-366">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="cf765-367">類別：無</span><span class="sxs-lookup"><span data-stu-id="cf765-367">Category: None</span></span>
    - <span data-ttu-id="cf765-368">分配方法：自動安裝</span><span class="sxs-lookup"><span data-stu-id="cf765-368">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="cf765-369">層級：電腦層級</span><span class="sxs-lookup"><span data-stu-id="cf765-369">Level: Computer Level</span></span>

    ![Sysext 新 prof 的配置設定影像](images/sysext-new-profile.png)

3. <span data-ttu-id="cf765-371">在 [ **系統擴充** ] 中，選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-371">In **System Extensions** select **Configure**.</span></span>

   ![配置設定 sysext config 的影像](images/sysext-configure.png)

4. <span data-ttu-id="cf765-373">在 [ **系統擴充** ] 中，輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-373">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="cf765-374">顯示名稱： Microsoft Corp. 系統擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-374">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="cf765-375">系統擴充類型：允許的系統擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-375">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="cf765-376">小組識別碼： UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="cf765-376">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="cf765-377">允許的系統擴充：</span><span class="sxs-lookup"><span data-stu-id="cf765-377">Allowed System Extensions:</span></span>
     - <span data-ttu-id="cf765-378">**wdav epsext**</span><span class="sxs-lookup"><span data-stu-id="cf765-378">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="cf765-379">**wdav netext**</span><span class="sxs-lookup"><span data-stu-id="cf765-379">**com.microsoft.wdav.netext**</span></span>

    ![配置設定 sysextconfig2 的影像](images/sysext-configure2.png)

5. <span data-ttu-id="cf765-381">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-381">Select the **Scope** tab.</span></span>

    ![配置設定 scopeimage 的影像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="cf765-383">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-383">Select **+ Add**.</span></span>

7. <span data-ttu-id="cf765-384">選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的機器群組**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-384">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="cf765-385">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-385">Select **+ Add**.</span></span>

   ![配置設定 addima 的影像](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="cf765-387">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-387">Select **Save**.</span></span>

   ![配置設定 sysext 範圍的影像](images/sysext-scope.png)

10. <span data-ttu-id="cf765-389">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-389">Select **Done**.</span></span>

    ![Sysext-final 的配置設定影像](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="cf765-391">步驟9：設定網路擴充</span><span class="sxs-lookup"><span data-stu-id="cf765-391">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="cf765-392">做為端點偵測和回應功能的一部分，Mac 版端點的 Microsoft Defender 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender Security Center 入口網站。</span><span class="sxs-lookup"><span data-stu-id="cf765-392">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="cf765-393">下列原則允許網路分機執行這項功能。</span><span class="sxs-lookup"><span data-stu-id="cf765-393">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="cf765-394">JAMF 不具備內容篩選原則的內建支援，這些是可讓 Microsoft Defender Endpoint for Mac 在裝置上安裝的網路分機之前的必要條件。</span><span class="sxs-lookup"><span data-stu-id="cf765-394">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint for Mac installs on the device.</span></span> <span data-ttu-id="cf765-395">此外，JAMF 有時會變更所要部署之原則的內容。</span><span class="sxs-lookup"><span data-stu-id="cf765-395">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="cf765-396">如此一來，下列步驟會提供對設定設定檔進行簽章的解決方法。</span><span class="sxs-lookup"><span data-stu-id="cf765-396">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="cf765-397">`netfilter.mobileconfig`從[我們的 GitHub 存放庫](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)下載至您的裝置，並將它儲存為`com.microsoft.network-extension.mobileconfig`</span><span class="sxs-lookup"><span data-stu-id="cf765-397">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) to your device and save it as `com.microsoft.network-extension.mobileconfig`</span></span>

2. <span data-ttu-id="cf765-398">遵循 [此頁面](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) 上的指示，以使用 JAMF 的內建憑證授權單位建立簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="cf765-398">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority</span></span>

3. <span data-ttu-id="cf765-399">在建立憑證並將其安裝至裝置後，請從 macOS 裝置的終端執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cf765-399">After the certificate is created and installed to your device, run the following command from the Terminal from a macOS device:</span></span>

   ```bash
   $ security cms -S -N "<certificate name>" -i com.microsoft.network-extension.mobileconfig -o com.microsoft.network-extension.signed.mobileconfig
   ```

   ![使用命令建立已簽署設定的終端視窗](images/netext-create-profile.png)

4. <span data-ttu-id="cf765-401">在 JAMF 入口網站中，流覽至 [設定 **設定檔** ]，然後按一下 [ **上傳** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="cf765-401">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> 

   ![上傳視窗的影像](images/netext-upload-file.png)

5. <span data-ttu-id="cf765-403">選取 **[選擇** 檔案]，然後選取 `microsoft.network-extension.signed.mobileconfig` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-403">Select **Choose File** and select `microsoft.network-extension.signed.mobileconfig`.</span></span>

   ![上傳視窗的圖像 netext 選擇檔案](images/netext-choose-file.png)

6. <span data-ttu-id="cf765-405">選取 **[上傳**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-405">Select **Upload**.</span></span>

   ![上傳視窗的圖像 netext 上傳 file2](images/netext-upload-file2.png)

7. <span data-ttu-id="cf765-407">上傳檔案之後，您會被重新導向至新的頁面，以完成此設定檔的建立。</span><span class="sxs-lookup"><span data-stu-id="cf765-407">After uploading the file, you are redirected to a new page to finalize the creation of this profile.</span></span>

   ![新設定檔 netext 設定檔頁面面的圖像](images/netext-profile-page.png)

8. <span data-ttu-id="cf765-409">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-409">Select the **Scope** tab.</span></span>

   ![設定設定的圖像 [sco] 索引標籤](images/0df36fc308ba569db204ee32db3fb40a.png)

9. <span data-ttu-id="cf765-411">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-411">Select **+ Add**.</span></span>

10. <span data-ttu-id="cf765-412">選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的機器群組**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-412">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

11. <span data-ttu-id="cf765-413">選取 **[+ 新增]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-413">Select **+ Add**.</span></span>

    ![配置設定 adim 的影像](images/0dde8a4c41110dbc398c485433a81359.png)

12. <span data-ttu-id="cf765-415">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-415">Select **Save**.</span></span>

    ![設定 savimg netextscop 的映射](images/netext-scope.png)

13. <span data-ttu-id="cf765-417">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-417">Select **Done**.</span></span>

    ![配置設定 netextfinal 的影像](images/netext-final.png)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="cf765-419">步驟10：使用 Mac 的 Microsoft Defender 端點排程掃描</span><span class="sxs-lookup"><span data-stu-id="cf765-419">Step 10: Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>
<span data-ttu-id="cf765-420">依照 [Microsoft Defender For Mac 的排程掃描](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)的指示。</span><span class="sxs-lookup"><span data-stu-id="cf765-420">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="cf765-421">步驟11：為 macOS 部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cf765-421">Step 11: Deploy Microsoft Defender for Endpoint for macOS</span></span>

1. <span data-ttu-id="cf765-422">流覽至您儲存的位置 `wdav.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-422">Navigate to where you saved `wdav.pkg`.</span></span>

    ![檔案瀏覽器 wdav 的影像 pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="cf765-424">將其重新命名為 `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-424">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![檔 explorer1 的影像 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="cf765-426">開啟 Jamf Pro 儀表板。</span><span class="sxs-lookup"><span data-stu-id="cf765-426">Open the Jamf Pro dashboard.</span></span>

    ![配置設定 jamfpro 的影像](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="cf765-428">選取您的電腦，然後按一下上方的齒輪圖示，然後選取 [ **電腦管理**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-428">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![配置設定 compmgmt 的影像](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="cf765-430">在 [ **套件**] 中，選取 [ **+ 新增**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-430">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="cf765-431">![包含鳥描述的圖片會自動產生套件 new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="cf765-431">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="cf765-432">在 [ **新增套件** ] 中輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-432">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="cf765-433">**一般] 索引標籤**</span><span class="sxs-lookup"><span data-stu-id="cf765-433">**General tab**</span></span>
    - <span data-ttu-id="cf765-434">顯示名稱：現在請將它保留空白。</span><span class="sxs-lookup"><span data-stu-id="cf765-434">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="cf765-435">因為當您選擇 pkg 時，將會重設。</span><span class="sxs-lookup"><span data-stu-id="cf765-435">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="cf765-436">類別：無 (預設) </span><span class="sxs-lookup"><span data-stu-id="cf765-436">Category: None (default)</span></span>
    - <span data-ttu-id="cf765-437">檔案名：選擇檔案</span><span class="sxs-lookup"><span data-stu-id="cf765-437">Filename: Choose File</span></span>

    ![設定設定的圖像 [一般] 索引標籤](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="cf765-439">開啟檔，並將它指向 `wdav.pkg` 或 `wdav_MDM_Contoso_200329.pkg` 。</span><span class="sxs-lookup"><span data-stu-id="cf765-439">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![自動產生電腦畫面描述的螢幕擷取畫面](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="cf765-441">選取 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="cf765-441">Select **Open**.</span></span> <span data-ttu-id="cf765-442">將 **顯示名稱** 設定為 **Microsoft Defender 高級威脅防護和 Microsoft defender 防病毒**。</span><span class="sxs-lookup"><span data-stu-id="cf765-442">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="cf765-443">**資訊清單** 檔案不是必要的。</span><span class="sxs-lookup"><span data-stu-id="cf765-443">**Manifest File** is not required.</span></span> <span data-ttu-id="cf765-444">Microsoft Defender 高級威脅防護沒有資訊清單檔案。</span><span class="sxs-lookup"><span data-stu-id="cf765-444">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="cf765-445">**[選項] 索引標籤**</span><span class="sxs-lookup"><span data-stu-id="cf765-445">**Options tab**</span></span><br> <span data-ttu-id="cf765-446">保留預設值。</span><span class="sxs-lookup"><span data-stu-id="cf765-446">Keep default values.</span></span>

    <span data-ttu-id="cf765-447">**限制] 索引標籤**</span><span class="sxs-lookup"><span data-stu-id="cf765-447">**Limitations tab**</span></span><br> <span data-ttu-id="cf765-448">保留預設值。</span><span class="sxs-lookup"><span data-stu-id="cf765-448">Keep default values.</span></span>
    
     ![[設定設定] [限制] 索引標籤的影像](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="cf765-450">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-450">Select **Save**.</span></span> <span data-ttu-id="cf765-451">套件已上傳至 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="cf765-451">The package is uploaded to Jamf Pro.</span></span> 

   ![Configuration settings pack upl jamf pro 映射](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="cf765-453">可能需要幾分鐘的時間才能部署套件。</span><span class="sxs-lookup"><span data-stu-id="cf765-453">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![配置設定套件 upl 的影像](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="cf765-455">流覽至 [ **原則** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="cf765-455">Navigate to the **Policies** page.</span></span>

    ![配置設定 polocies 的影像](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="cf765-457">選取 [ **+ 新增** ] 以建立新的原則。</span><span class="sxs-lookup"><span data-stu-id="cf765-457">Select **+ New** to create a new policy.</span></span>

    ![設定新原則的影像](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="cf765-459">**一般說來** 請輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="cf765-459">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="cf765-460">顯示名稱： MDATP 上架 200329 v 100.86.92 或更新版本</span><span class="sxs-lookup"><span data-stu-id="cf765-460">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="cf765-461">設定 settingsmdatponboard 的影像</span><span class="sxs-lookup"><span data-stu-id="cf765-461">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="cf765-462">選取 [ **週期性存回**]。</span><span class="sxs-lookup"><span data-stu-id="cf765-462">Select **Recurring Check-in**.</span></span> 
    
    ![重複簽入設定設定的影像](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="cf765-464">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-464">Select **Save**.</span></span> 
 
14. <span data-ttu-id="cf765-465">選取 **> 設定的套件**。</span><span class="sxs-lookup"><span data-stu-id="cf765-465">Select **Packages > Configure**.</span></span>
 
    ![配置設定套件設定的影像](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="cf765-467">選取 [ **Microsoft Defender 高級威脅防護] 和 [Microsoft Defender 防毒軟體**] 旁邊的 [**新增**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="cf765-467">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![設定 MDATP 和 MDA 新增的影像](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="cf765-469">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-469">Select **Save**.</span></span>

    ![設定 settingssavimg 的影像](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="cf765-471">選取 [ **範圍** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cf765-471">Select the **Scope** tab.</span></span>  

    ![配置設定 scptab 的影像](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="cf765-473">選取目的電腦。</span><span class="sxs-lookup"><span data-stu-id="cf765-473">Select the target computers.</span></span>

    ![配置設定 tgtcomp 的影像](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="cf765-475">**Scope**</span><span class="sxs-lookup"><span data-stu-id="cf765-475">**Scope**</span></span>
    
    <span data-ttu-id="cf765-476">選取 [新增]。</span><span class="sxs-lookup"><span data-stu-id="cf765-476">Select **Add**.</span></span>
    
    ![配置設定 ad1img 的影像](images/1c08d097829863778d562c10c5f92b67.png)

    ![配置設定 ad2img 的影像](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="cf765-479">**Self-Service**</span><span class="sxs-lookup"><span data-stu-id="cf765-479">**Self-Service**</span></span>
    
    ![配置設定 selfservice 的影像](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="cf765-481">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cf765-481">Select **Done**.</span></span> 

    ![配置設定 do1img 的影像](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![配置設定 do2img 的影像](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




