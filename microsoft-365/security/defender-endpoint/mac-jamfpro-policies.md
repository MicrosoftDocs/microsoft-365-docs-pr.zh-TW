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
ms.openlocfilehash: 79f5837ae6bae6e6a9d952d90605f4cf7b31262e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765128"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>在 Jamf Pro 的 macOS 原則上設定 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [Mac 版端點的 Defender](microsoft-defender-endpoint-mac.md)

此頁面會引導您完成在 Jamf Pro 中設定 macOS 原則所需採取的步驟。

您必須採取下列步驟：

1. [取得 Microsoft Defender for Endpoint 上架套件](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [使用上架套件在 Jamf Pro 中建立設定檔](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [設定 Microsoft Defender for Endpoint 設定](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [設定 Microsoft Defender for Endpoint notification 設定](#step-4-configure-notifications-settings)

5. [設定 Microsoft AutoUpdate (MAU) ](#step-5-configure-microsoft-autoupdate-mau)

6. [授與 Microsoft Defender for Endpoint 的完整磁片存取權](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [核准 Microsoft Defender for Endpoint 的內核擴充](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [核准 Microsoft Defender for Endpoint 的系統擴充](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [設定網路擴充](#step-9-configure-network-extension)

10. [在 macOS 上使用 Microsoft Defender for Endpoint 排程掃描](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [在 macOS 上部署 Microsoft Defender for Endpoint](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>步驟1：取得 Microsoft Defender for Endpoint 上架套件

1. 在 [Microsoft Defender Security Center](https://securitycenter.microsoft.com )中，流覽至 [ **設定] > 上架**。 

2. 選取 [macOS 為作業系統] 和 [行動裝置管理/Microsoft Intune] 做為部署方法。

    ![Microsoft Defender 安全中心的影像](images/onboarding-macos.png)

3. 選取 [ (WindowsDefenderATPOnboardingPackage.zip) **下載上架套件** ]。

4. 解壓縮 `WindowsDefenderATPOnboardingPackage.zip` 。

5. 將檔案複製到您的慣用位置。 例如，  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`。


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>步驟2：使用上架套件在 Jamf Pro 中建立設定檔

1. `WindowsDefenderATPOnboarding.plist`從上一節中找出檔。

   ![WindowsDefenderATPOnboarding 檔案的影像](images/plist-onboarding-file.png)

 
2. 在 Jamf Pro 儀表板中，選取 [ **新增**]。

    ![建立新的 Jamf Pro 儀表板的影像](images/jamf-pro-configure-profile.png)

3. 輸入下列詳細資料：

   **一般**
   - 名稱： MDATP 上架 macOS
   - 描述： macOS 的 MDATP EDR 上架
   - 類別：無
   - 分配方法：自動安裝
   - 層級：電腦層級

4. 在 **應用程式 & 自訂設定** 中，選取 [ **設定**]。

    ![Configurate 應用程式和自訂設定的影像](images/jamfpro-mac-profile.png)

5. 選取 **[ (PLIST 檔案) 上傳** 檔案]，然後在 [ **喜好設定功能變數名稱** ] 中輸入： `com.microsoft.wdav.atp` 。 

    ![Jamfpro plist 上傳檔案的影像](images/jamfpro-plist-upload.png)

    ![上傳檔案屬性清單檔案的影像](images/jamfpro-plist-file.png)

7. 選取 [ **開啟** ]，然後選取上架檔案。

    ![上架檔案的影像](images/jamfpro-plist-file-onboard.png)

8. 選取 **[上傳**]。 

    ![上傳 plist 檔的影像](images/jamfpro-upload-plist.png)


9. 選取 [ **範圍** ] 索引標籤。

    ![範圍] 索引標籤的影像](images/jamfpro-scope-tab.png)

10. 選取目的電腦。

    ![目的電腦的影像](images/jamfpro-target-computer.png)

    ![目標影像](images/jamfpro-targets.png) 

11. 選取 **[儲存]**。

    ![部署目的電腦的映射](images/jamfpro-deployment-target.png)

    ![選取目的電腦的影像](images/jamfpro-target-selected.png)

12. 選取 **[完成]**。

    ![目標群組電腦的影像](images/jamfpro-target-group.png)

    ![配置檔案清單](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>步驟3：設定 Microsoft Defender for Endpoint 設定

1.  使用下列 Microsoft Defender for Endpoint configuration 設定：

    - enableRealTimeProtection
    - passiveMode
    
    >[!NOTE]
    >預設未開啟，如果您打算為 macOS 執行協力廠商 AV，請將其設為 `true` 。

    - 排除
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats
    
    >[!NOTE]
    >EICAR.TXT 位於範例上，如果您想要透過概念證明，請將它移除，尤其是在您測試 EICAR.TXT 時。
        
    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - 標籤
    - hideStatusMenuIcon
    
     如需詳細資訊，請參閱 [Jamf 設定檔的屬性清單](mac-preferences.md#property-list-for-jamf-configuration-profile)。

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

2. 將檔案儲存為 `MDATP_MDAV_configuration_settings.plist` 。


3.  在 Jamf Pro 儀表板中，選取 **[一般**]。

    ![新 Jamf Pro 儀表板的影像](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. 輸入下列詳細資料：

    **一般**
    
    - 名稱： MDATP MDAV 設定設定
    - 描述：\<blank\>
    - 類別：無 (預設) 
    - 分配方法：自動安裝 (預設) 
    - 層級：電腦層級 (預設) 

    ![MDATP MDAV 配置設定的影像](images/3160906404bc5a2edf84d1d015894e3b.png)

5. 在 **應用程式 & 自訂設定** 中，選取 [ **設定**]。

    ![應用程式和自訂設定的影像](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. 選取 **[上傳檔案 (PLIST** 檔案]) 。

    ![配置設定 plist 檔案的影像](images/6f85269276b2278eca4bce84f935f87b.png)

7. 在 [ **喜好設定網域**] 中，輸入 `com.microsoft.wdav` ，然後選取  **[上傳 PLIST** 檔案]。

    ![配置設定偏好設定網域的影像](images/db15f147dd959e872a044184711d7d46.png)

8. 選取 **[選擇檔**]。

    ![設定的配置圖像選擇 [檔案]](images/526e978761fc571cca06907da7b01fd6.png)

9. 選取 **MDATP_MDAV_configuration_settings plist**，然後選取 [ **開啟**]。

    ![Mdatpmdav 配置設定的影像](images/98acea3750113b8dbab334296e833003.png)

10. 選取 **[上傳**]。

    ![設定的配置圖像上載](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![配置設定上傳圖像的圖像](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >如果您要上傳 Intune 檔案，您會收到下列錯誤：<br>
    >![配置設定的映射 intune 檔案上傳](images/8e69f867664668796a3b2904896f0436.png)


11. 選取 **[儲存]**。 

    ![配置設定的影像儲存影像](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. 檔案上傳。

    ![設定檔上傳圖像的圖像](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![上傳的配置設定檔案影像](images/a422e57fe8d45689227e784443e51bd1.png)

13. 選取 [ **範圍** ] 索引標籤。

    ![設定的配置範圍影像](images/9fc17529e5577eefd773c658ec576a7d.png)

14. 選取 [ **Contoso 的電腦群組**]。 

15. 選取 [ **新增**]，然後選取 [ **儲存**]。

    ![配置設定 addsav 的影像](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![配置設定的影像儲存新增](images/6f093e42856753a3955cab7ee14f12d9.png)

16. 選取 **[完成]**。 您將會看到新的設定 **設定檔**。

    ![設定設定檔影像的影像](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a>步驟4：設定通知設定

這些步驟適用于 macOS 10.15 (Catalina) 或更新版本。

1. 在 Jamf Pro 儀表板中，選取 [ **電腦**]，然後選取 [設定 **設定檔**]。

2. 按一下 [ **新增**]，然後輸入下列 **選項** 的詳細資料：
    
    - 索引標籤 **一般**： 
        - **名稱**： MDATP MDAV 通知設定
        - **描述**： macOS 10.15 (Catalina) 或更新版本
        - **類別**：無 *(預設)*
        - **分配方法**：自動安裝 *(預設)*
        - **層級**：電腦層級 *(預設)*

        ![設定設定檔設定 mdatpmdav 的影像](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - [索引標籤 **通知**] 中，按一下 [ **新增**]，然後輸入下列值：
        - **束識別碼**： `com.microsoft.wdav.tray`
        - **嚴重警示**：按一下 [**停** 用]
        - **通知**：按一下 [**啟用**]
        - **橫幅警示類型**：選取 [ **包含** 與 **臨時** *(預設值])*
        - **鎖定畫面上的通知**：按一下 [**隱藏**]
        - **通知中心的通知**：按一下 [**顯示**]
        - **徽章應用程式圖示**：按一下 [**顯示**]

        ![設定 mdatpmdav 通知盤的配置設定影像](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - 索引標籤 **通知**，請按一下 [ **增加** 一次]，向下滾動至 **新的通知設定**
        - **束識別碼**： `com.microsoft.autoupdate2`
        - 將其餘設定設定為與上述值相同

        ![設定 mdatpmdav 通知 mau 的映射](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        請注意，現在有兩個「資料表」具有通知設定，一個用於 **捆綁 ID: wdav**，另一個用於 **ID: autoupdate2 的捆綁**。 雖然您可以根據您的需求來設定警示設定，但捆綁 IDs 必須與之前所述完全相同，且 **包含** 參數必須 **開啟** 以取得 **通知**。

3. 選取 [ **範圍** ] 索引標籤，然後選取 [ **新增**]。

    ![設定範圍新增的映射](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. 選取 [ **Contoso 的電腦群組**]。 

5. 選取 [ **新增**]，然後選取 [ **儲存**]。
    
    ![設定設定 contoso 機器 grp 儲存的影像](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![設定的配置圖像新增儲存](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. 選取 **[完成]**。 您將會看到新的設定 **設定檔**。
    ![設定的圖像配置設定完成 img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>步驟5：設定 Microsoft AutoUpdate (MAU) 

1. 使用下列 Microsoft Defender for Endpoint configuration 設定：

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

2. 將其儲存為 `MDATP_MDAV_MAU_settings.plist` 。

3. 在 Jamf Pro 儀表板中，選取 **[一般**]。 

    ![設定的圖像配置一般影像](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. 輸入下列詳細資料：

    **一般** 
    
    - 名稱： MDATP MDAV MAU 設定
    - 描述： macOS 的 MDATP 的 Microsoft AutoUpdate 設定
    - 類別：無 (預設) 
    - 分配方法：自動安裝 (預設) 
    - 層級：電腦層級 (預設) 

5. 在 **應用程式 & 自訂設定** 中，選取 [ **設定**]。

    ![設定的映射設定應用程式和自訂設定](images/1f72e9c15eaafcabf1504397e99be311.png)

6. 選取 **[上傳檔案 (PLIST** 檔案]) 。

    ![設定 plist 的影像](images/1213872db5833aa8be535da57653219f.png)  

7. 在 [ **喜好設定網域** ] 中輸入： `com.microsoft.autoupdate2` ，然後選取 **[上傳 PLIST** 檔案]。

    ![設定 pref 網域的配置圖像](images/1213872db5833aa8be535da57653219f.png)

8. 選取 **[選擇檔**]。

    ![設定 choosefile 的影像](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. 選取 **MDATP_MDAV_MAU_settings plist**。

    ![設定 mdatpmdavmau 設定的影像](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. 選取 **[上傳**]。
    ![設定 uplimage 的影像](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![設定 uplimg 的影像](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. 選取 **[儲存]**。

    ![設定 saveimg 的影像](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. 選取 [ **範圍** ] 索引標籤。
   
     ![設定 scopetab 的影像](images/10ab98358b2d602f3f67618735fa82fb.png)

13. 選取 [新增]。
    
    ![設定 addimg1 的影像](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![設定 addimg2 的影像](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![設定 addimg3 的影像](images/321ba245f14743c1d5d51c15e99deecc.png)

14. 選取 **[完成]**。
    
    ![設定 doneimage 的影像](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>步驟6：授與 Microsoft Defender for Endpoint 的完整磁片存取權

1. 在 Jamf Pro 儀表板中，選取 [設定 **設定檔**]。

    ![設定設定檔的映射](images/264493cd01e62c7085659d6fdc26dc91.png)

2. 選取 [ **+ 新增**]。 

3. 輸入下列詳細資料：

    **一般** 
    - 名稱： MDATP MDAV-對 EDR 和 AV 授與完整磁片存取權
    - 描述：在 macOS Catalina 或更新版本上，新增隱私權偏好設定原則控制
    - 類別：無
    - 分配方法：自動安裝
    - 層級：電腦層級


    ![一般的設定圖像配置](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. 在 [ **設定隱私權偏好設定原則控制** ] 中，選取 [ **設定**]。

    ![設定隱私權原則控制的影像](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. 在 [ **隱私權偏好設定原則**] 中，輸入下列詳細資料：

    - 識別碼： `com.microsoft.wdav`
    - 識別碼類型：束識別碼
    - 程式碼需求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![設定的圖像設定隱私權喜好原則控制詳細資料](images/22cb439de958101c0a12f3038f905b27.png)

6. 選取 **[+ 新增]**。

    ![設定的圖像設定新增系統原則所有檔案](images/bd93e78b74c2660a0541af4690dd9485.png)

    - 在應用程式或服務中：設定為 **SystemPolicyAllFiles**

    - 在 [access] 底下：設定為 **允許**

7. 選取 [ **儲存** (]，而不是位於右下方) 。

    ![設定的圖像配置儲存影像](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. 按一下 [ `+` **應用程式存取** ] 旁的符號，以加入新的專案。

    ![設定的配置圖像設定應用程式存取](images/tcc-add-entry.png)

9. 輸入下列詳細資料：

    - 識別碼： `com.microsoft.wdav.epsext`
    - 識別碼類型：束識別碼
    - 程式碼需求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. 選取 **[+ 新增]**。

    ![設定 tcc epsext 專案的影像](images/tcc-epsext-entry.png)

    - 在應用程式或服務中：設定為 **SystemPolicyAllFiles**

    - 在 [access] 底下：設定為 **允許**

11. 選取 [ **儲存** (]，而不是位於右下方) 。

    ![設定的圖像 tcc epsext image2](images/tcc-epsext-entry2.png)

12. 選取 [ **範圍** ] 索引標籤。

    ![設定設定範圍的影像](images/2c49b16cd112729b3719724f581e6882.png)

13. 選取 **[+ 新增]**。

    ![設定 addimage 的影像](images/57cef926d1b9260fb74a5f460cee887a.png)

14. 選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的 MachineGroup**]。 

    ![設定為 contoso machinegrp 的配置圖像](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. 選取 [新增]。 

16. 選取 **[儲存]**。 
    
17. 選取 **[完成]**。
    
    ![設定 donimg 的影像](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![設定 donimg2 的影像](images/6c8b406ee224335a8c65d06953dc756e.png)

或者，您也可以下載 [fulldisk](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) ，並將其上傳至 JAMF 設定檔，如 [使用 JAMF Pro 部署自訂設定設定檔中所述）。方法2：將設定檔上傳至 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>步驟7：核准 Microsoft Defender for Endpoint 的內核擴充

> [!CAUTION]
> Apple 矽 (M1) 裝置不支援 KEXT。 在這些裝置上安裝包含 KEXT 原則的設定檔將會失敗。

1. 在設定配置 **檔** 中，選取 [ **+ 新增**]。

    ![自動產生社交媒體發佈描述的螢幕擷取畫面](images/6c8b406ee224335a8c65d06953dc756e.png)

2. 輸入下列詳細資料：

    **一般** 
    
    - 名稱： MDATP MDAV 內核擴充
    - 描述： MDATP 內核擴充 (kext) 
    - 類別：無
    - 分配方法：自動安裝
    - 層級：電腦層級

    ![Mdatpmdav 內核的設定配置圖像](images/24e290f5fc309932cf41f3a280d22c14.png)

3. 在 [ **設定核准的核心擴充** ] 中，選取 [ **設定**]。

    ![已核准的內核分機的配置設定影像](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. 在 **核准的內核擴充** 輸入下列詳細資料：

    - 顯示名稱： Microsoft Corp。
    - 團隊 ID: UBF8T346G9

    ![Appr 內核擴充設定的配置設定映射](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. 選取 [ **範圍** ] 索引標籤。

    ![設定的 [設定範圍] 索引標籤 m 的影像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. 選取 **[+ 新增]**。

7. 選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的機器群組**]。

8. 選取 **[+ 新增]**。

    ![配置設定的影像新增影像](images/0dde8a4c41110dbc398c485433a81359.png)

9. 選取 **[儲存]**。

    ![配置設定 saveimag 的影像](images/0add8019b85a453b47fa5c402c72761b.png)

10. 選取 **[完成]**。

    ![配置設定 doneimag 的影像](images/1c9bd3f68db20b80193dac18f33c22d0.png)

或者，您也可以下載 [kext](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) ，並將其上傳至 JAMF 設定檔，如 [使用 JAMF Pro 部署自訂設定設定檔中所述）。方法2：將設定檔上傳至 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>步驟8：核准 Microsoft Defender for Endpoint 的系統擴充

1. 在設定配置 **檔** 中，選取 [ **+ 新增**]。

    ![自動產生社交媒體發佈描述的螢幕擷取畫面](images/6c8b406ee224335a8c65d06953dc756e.png)

2. 輸入下列詳細資料：

    **一般**
    
    - 名稱： MDATP MDAV 系統擴充
    - 描述： MDATP 系統擴充
    - 類別：無
    - 分配方法：自動安裝
    - 層級：電腦層級

    ![Sysext 新 prof 的配置設定影像](images/sysext-new-profile.png)

3. 在 [ **系統擴充** ] 中，選取 [ **設定**]。

   ![配置設定 sysext config 的影像](images/sysext-configure.png)

4. 在 [ **系統擴充** ] 中，輸入下列詳細資料：

   - 顯示名稱： Microsoft Corp. 系統擴充
   - 系統擴充類型：允許的系統擴充
   - 小組識別碼： UBF8T346G9
   - 允許的系統擴充：
     - **wdav epsext**
     - **wdav netext**

    ![配置設定 sysextconfig2 的影像](images/sysext-configure2.png)

5. 選取 [ **範圍** ] 索引標籤。

    ![配置設定 scopeimage 的影像](images/0df36fc308ba569db204ee32db3fb40a.png)

6. 選取 **[+ 新增]**。

7. 選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的機器群組**]。

8. 選取 **[+ 新增]**。

   ![配置設定 addima 的影像](images/0dde8a4c41110dbc398c485433a81359.png)

9. 選取 **[儲存]**。

   ![配置設定 sysext 範圍的影像](images/sysext-scope.png)

10. 選取 **[完成]**。

    ![Sysext-final 的配置設定影像](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>步驟9：設定網路擴充

在端點偵測和回應功能中，Microsoft Defender for Endpoint on macOS 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender Security Center 入口網站。 下列原則允許網路分機執行這項功能。

這些步驟適用于 macOS 10.15 (Catalina) 或更新版本。

1. 在 Jamf Pro 儀表板中，選取 [ **電腦**]，然後選取 [設定 **設定檔**]。

2. 按一下 [ **新增**]，然後輸入下列 **選項** 的詳細資料：

    - 索引標籤 **一般**： 
        - **名稱**： MICROSOFT Defender ATP 網路擴充
        - **描述**： macOS 10.15 (Catalina) 或更新版本
        - **類別**：無 *(預設)*
        - **分配方法**：自動安裝 *(預設)*
        - **層級**：電腦層級 *(預設)*

    - 索引標籤 **內容篩選**：
        - **篩選名稱**： MICROSOFT Defender ATP 內容篩選器
        - **識別碼**： `com.microsoft.wdav`
        - 保留 *未* 選取 **服務位址**、**組織**、**使用者名稱**、**密碼**、**憑證** 空白 (**包含**) 
        - **篩選順序**： Inspector
        - **通訊端篩選**： `com.microsoft.wdav.netext`
        - **通訊端篩選指定的需求**： `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - *不* 會選取 [**網路篩選** 欄位] [空白 (**包含**]) 

        請注意，「 **識別碼**」、「 **通訊端篩選** 」及「 **通訊端篩選」指定的需求** 會如上所指定的

        ![設定 mdatpmdav 的影像](images/netext-create-profile.png)

3. 選取 [ **範圍** ] 索引標籤。

   ![設定設定的圖像 [sco] 索引標籤](images/0df36fc308ba569db204ee32db3fb40a.png)

4. 選取 **[+ 新增]**。

5. 選取 [>**群組名稱**] 下的 [**電腦群組**] > 選取 [ **Contoso 的機器群組**]。

6. 選取 **[+ 新增]**。

    ![配置設定 adim 的影像](images/0dde8a4c41110dbc398c485433a81359.png)

7. 選取 **[儲存]**。

    ![設定 savimg netextscop 的映射](images/netext-scope.png)

8. 選取 **[完成]**。

    ![配置設定 netextfinal 的影像](images/netext-final.png)

或者，您也可以下載 [netfilter](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) ，並將其上傳至 JAMF 設定檔，如 [使用 JAMF Pro 部署自訂設定設定檔中所述）。方法2：將設定檔上傳至 Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro)。


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>步驟10：使用 macOS 上的 Microsoft Defender for Endpoint 排程掃描
依照 [macOS 上的 [Microsoft Defender For Endpoint] 進行排程掃描](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)的指示進行。


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>步驟11：在 macOS 上部署 Microsoft Defender for Endpoint

1. 流覽至您儲存的位置 `wdav.pkg` 。

    ![檔案瀏覽器 wdav 的影像 pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. 將其重新命名為 `wdav_MDM_Contoso_200329.pkg` 。

    ![檔 explorer1 的影像 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. 開啟 Jamf Pro 儀表板。

    ![配置設定 jamfpro 的影像](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. 選取您的電腦，然後按一下上方的齒輪圖示，然後選取 [ **電腦管理**]。

    ![配置設定 compmgmt 的影像](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. 在 [ **套件**] 中，選取 [ **+ 新增**]。 
    ![包含鳥描述的圖片會自動產生套件 new](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. 在 [ **新增套件** ] 中輸入下列詳細資料：

    **一般] 索引標籤**
    - 顯示名稱：現在請將它保留空白。 因為當您選擇 pkg 時，將會重設。
    - 類別：無 (預設) 
    - 檔案名：選擇檔案

    ![設定設定的圖像 [一般] 索引標籤](images/21de3658bf58b1b767a17358a3f06341.png)

    開啟檔，並將它指向 `wdav.pkg` 或 `wdav_MDM_Contoso_200329.pkg` 。
    
    ![自動產生電腦畫面描述的螢幕擷取畫面](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. 選取 [開啟]。 將 **顯示名稱** 設定為 **Microsoft Defender 高級威脅防護和 Microsoft defender 防病毒**。

    **資訊清單** 檔案不是必要的。 Microsoft Defender 高級威脅防護沒有資訊清單檔案。
    
    **[選項] 索引標籤**<br> 保留預設值。

    **限制] 索引標籤**<br> 保留預設值。
    
     ![[設定設定] [限制] 索引標籤的影像](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. 選取 **[儲存]**。 套件已上傳至 Jamf Pro。 

   ![Configuration settings pack upl jamf pro 映射](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   可能需要幾分鐘的時間才能部署套件。
   
   ![配置設定套件 upl 的影像](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. 流覽至 [ **原則** ] 頁面。

    ![配置設定 polocies 的影像](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. 選取 [ **+ 新增** ] 以建立新的原則。

    ![設定新原則的影像](images/847b70e54ed04787e415f5180414b310.png)


11. **一般說來** 請輸入下列詳細資料：

    - 顯示名稱： MDATP 上架 200329 v 100.86.92 或更新版本

    ![設定 settingsmdatponboard 的影像 ](images/625ba6d19e8597f05e4907298a454d28.png)

12. 選取 [ **週期性存回**]。 
    
    ![重複簽入設定設定的影像](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. 選取 **[儲存]**。 
 
14. 選取 **> 設定的套件**。
 
    ![配置設定套件設定的影像](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. 選取 [ **Microsoft Defender 高級威脅防護] 和 [Microsoft Defender 防毒軟體**] 旁邊的 [**新增**] 按鈕。

    ![設定 MDATP 和 MDA 新增的影像](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. 選取 **[儲存]**。

    ![設定 settingssavimg 的影像](images/9d6e5386e652e00715ff348af72671c6.png)

17. 選取 [ **範圍** ] 索引標籤。  

    ![配置設定 scptab 的影像](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. 選取目的電腦。

    ![配置設定 tgtcomp 的影像](images/6eda18a64a660fa149575454e54e7156.png)

    **Scope**
    
    選取 [新增]。
    
    ![配置設定 ad1img 的影像](images/1c08d097829863778d562c10c5f92b67.png)

    ![配置設定 ad2img 的影像](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **Self-Service**
    
    ![配置設定 selfservice 的影像](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. 選取 **[完成]**。 

    ![配置設定 do1img 的影像](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![配置設定 do2img 的影像](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




