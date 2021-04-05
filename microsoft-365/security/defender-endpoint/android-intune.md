---
title: 使用 Microsoft Intune 部署 Android 版適用於端點的 Microsoft Defender
description: 說明如何使用 Microsoft Intune 為 Android 部署 Microsoft Defender
keywords: microsoft、defender、atp、mde、android、安裝、部署、卸載
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fdfc6e63945e15ce2d1f1a293c377f641eeb9bc4
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587692"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-android-with-microsoft-intune"></a>使用 Microsoft Intune 部署 Android 版適用於端點的 Microsoft Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

瞭解如何在 Intune 公司入口網站註冊的裝置上部署適用于 Android 的 Endpoint 的 Defender。 如需 Intune 裝置註冊的詳細資訊，請參閱  [註冊裝置](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)。

> [!NOTE]
> **適用于 Android 的 Endpoint 的 Defender 現在已可在 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)上使用** <br>
> 您可以從 Intune 連線到 Google，以跨裝置管理員和 Android Enterprise entrollment 模式，為端點應用程式部署 Defender。
應用程式的更新是透過 Google Play 自動進行。

## <a name="deploy-on-device-administrator-enrolled-devices"></a>在裝置管理員註冊的裝置上部署

**在 Intune 公司入口網站上部署適用于 Android 的 Endpoint 的 Defender-裝置管理員註冊裝置**

瞭解如何在 Intune 公司入口網站上為 Android 部署 Defender （裝置管理員註冊的裝置）。 

### <a name="add-as-android-store-app"></a>新增為 Android store 應用程式

1. 在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431) 管理員系統管理中心中，移至 [ **應用程式** \> **Android 應用** 程式 \> **新增 \> android store app** ]，然後選擇 [ **選取**]。

   ![Microsoft 端點管理員系統管理中心的圖像新增 android 應用程式](images/mda-addandroidstoreapp.png)

2. 在 [ **新增應用程式** ] 頁面上，于 [ *應用程式資訊* ] 區段中輸入： 

   - **名稱** 
   - **描述**
   - **發行者** 為 Microsoft。
   - **應用商店 url** 為 https://play.google.com/store/apps/details?id=com.microsoft.scmx 端點應用程式 GOOGLE Play Store url (Defender)  

   其他欄位是選用的。 選取 **[下一步]**。

   ![Microsoft 端點管理員系統管理中心的圖像新增應用程式資訊](images/mda-addappinfo.png)

3. 在 [ *工作分派* ] 區段中，移至 [ **必要** ] 區段，然後選取 [ **新增群組]。** 然後，您可以選擇要將其設定為適用于 Android 應用程式的 Defender for Endpoint 的使用者群組 (s) 。 選擇 [選取]，然後 **按一下** **[下一步]**

    >[!NOTE]
    >選取的使用者群組應該包含 Intune 登記的使用者。

    > [!div class="mx-imgBorder"]

    > ![選取的使用者群組的 Microsoft 端點管理員管理中心圖像](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. 在 [ **複查 + 建立** ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。

    在幾分鐘內，即可成功建立端點應用程式，並在頁面的右上角顯示通知。

    ![Defender 端點應用程式之 Microsoft 端點管理員系統管理中心通知的影像](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. 在顯示的 [應用程式資訊] 頁面中，選取 [ **監視** ] 區段中的 [ **裝置安裝狀態** ]，以確認裝置安裝已成功完成。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理中心設備安裝的影像](images/513cf5d59eaaef5d2b5bc122715b5844.png)

### <a name="complete-onboarding-and-check-status"></a>完成上架和支票狀態

1. 一旦已在裝置上安裝適用于 Android 的 Endpoint 的 Defender，您就會看到應用程式圖示。

    ![移動裝置上的圖示](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. 點擊 [Microsoft Defender ATP 應用程式] 圖示，然後依照螢幕指示完成安裝應用程式。 詳細資料包含使用者對 Android 的 Defender for Endpoint 所需的 Android 許可權的使用者認可。

3. 成功上架後，裝置會在 Microsoft Defender 安全中心的 [裝置] 清單上開始顯示。

    ![用於端點入口網站的 Defender 中的裝置影像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>在 Android 企業註冊裝置上部署

適用于 Android 的 Defender for Android 支援 Android 企業註冊裝置。

如需 Intune 支援之註冊選項的詳細資訊，請參閱 [註冊選項](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)。

**目前，具有工作設定檔和公司所擁有的完整管理使用者裝置註冊的個人擁有裝置可支援部署。**

## <a name="add-microsoft-defender-for-endpoint-for-android-as-a-managed-google-play-app"></a>將適用于 Android 的 Microsoft Defender 端點新增為受管理的 Google Play 應用程式

請遵循下列步驟，將 Microsoft Defender for Endpoint 應用程式新增至您的受管理 Google Play。

1. 在 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431) 中，移至 [ **應用程式** \> **Android 應用** 程式] [ \> **新增** 並選取 **受管理的 Google Play app**]。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理中心 managed google play 的影像](images/579ff59f31f599414cedf63051628b2e.png)

2. 在隨後載入的 [受管理的 Google Play] 頁面上，移至 [搜尋] 方塊並查閱 **Microsoft Defender。** 您的搜尋應該會在受管理的 Google Play 中顯示 Microsoft Defender for Endpoint 應用程式。 在 [應用程式搜尋結果] 中，按一下 [Microsoft Defender for Endpoint 應用程式]。

    ![Microsoft 端點管理員系統管理中心應用程式搜尋的影像](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. 在接下來的 [應用程式描述] 頁面中，您應該可以查看 Defender for Endpoint 上的應用程式詳細資料。 複查頁面上的資訊，然後選取 [ **核准**]。

    > [!div class="mx-imgBorder"]
    > ![受管理的 Google Play 的螢幕擷取畫面](images/07e6d4119f265037e3b80a20a73b856f.png)

4. 您將會看到供該 Defender for Endpoint 取得的許可權，讓其能夠運作。 請加以檢查，然後選取 [ **核准**]。

    ![使用 Defender 進行端點預覽應用程式核准的螢幕擷取畫面](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. 您將會看到 [核准設定] 頁面。 頁面會確認您的喜好設定，以處理適用于 Android 的 Defender for Endpoint 的新應用程式許可權可能要求。 查看選項，然後選取您的喜好選項。 選取 **[完成]**。

    依預設，受管理的 Google 播放會 *在應用程式要求新許可權時選取 [保留已核准*]

    > [!div class="mx-imgBorder"]
    > ![[通知] 索引標籤](images/ffecfdda1c4df14148f1526c22cc0236.png)

6. 進行許可權處理選取之後，請選取 [ **同步** 處理]，將 Microsoft Defender for Endpoint 同步處理至您的應用程式清單。

    > [!div class="mx-imgBorder"]
    > ![[同步處理] 頁面](images/34e6b9a0dae125d085c84593140180ed.png)

7. 同步處理會在幾分鐘內完成。

    ![Android 應用程式的影像](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. 在 [Android 應用程式] 畫面中選取 [重新整理 **] 按鈕，** 並在 [應用程式] 清單中顯示 MICROSOFT Defender ATP。

    > [!div class="mx-imgBorder"]
    > ![Android 應用程式清單的影像](images/fa4ac18a6333335db3775630b8e6b353.png)

9. 適用于 Endpoint 的 Defender 可透過 Intune 支援受管理裝置的應用程式佈建原則。 您可以利用這項功能，autogrant) 適用的 Android (許可權，因此，使用者不需要接受這些許可權 (s) 。

    1. 在 [ **應用程式** ] 頁面中，移至 **Policy > App Configuration Policy > 新增 > 受管理的裝置**。

       ![Microsoft 端點管理員系統管理中心 android 受管理裝置的影像](images/android-mem.png)

    1. 在 [ **建立應用程式佈建原則** ] 頁面中，輸入下列詳細資料：
    
        - 名稱： Microsoft Defender ATP。
        - 選擇 [ **Android 企業** ] 做為 [平臺]。
        - 選擇 [ **僅工作設定檔** ] 做為配置檔案類型。
        - 按一下 [**選取應用程式**]，選擇 [ **Microsoft Defender ATP**]，然後選取 **[確定]** ，然後按一下 **[**
    
        > [!div class="mx-imgBorder"]
        > ![[建立應用程式佈建原則] 頁面的影像](images/android-create-app.png)

    1. 在 [ **設定** ] 頁面中，移至 [許可權] 區段，按一下 [新增] 以查看支援的許可權清單。 在 [新增許可權] 區段中，選取下列許可權：

       - 外部儲存體 (讀取) 
       - 外部儲存體 (寫入) 

       然後選取 **[確定]**。

       > [!div class="mx-imgBorder"]
      > ![Android 的影像建立應用程式設定原則](images/android-create-app-config.png)

    1. 現在您應該會看到列出的許可權，而且現在您可以在 **許可權狀態** 下拉式清單中選擇 [autogrant] 來 autogrant，然後選取 **[下一步]**。

       > [!div class="mx-imgBorder"]
       > ![Android 自動授與的影像建立應用程式設定原則](images/android-auto-grant.png)

    1. 在 [ **工作分派** ] 頁面中，選取要指派此應用程式佈建原則的使用者群組。 按一下 [ **選取要包含的群組** ]，然後選取適當的群組，然後選取 **[下一步]**。  在這裡選取的群組通常是您要為其指派 Microsoft Defender for Endpoint Android 應用程式的相同群組。 

       > [!div class="mx-imgBorder"]
       > ![建立應用程式佈建原則的影像](images/android-select-group.png)
    

     1. 在 [ **複查** ] 接下來的 [建立] 頁面中，複查所有資訊，然後選取 [ **建立**]。 <br>
    
        「用於 Defender for Endpoint autogranting 的應用程式設定原則」儲存許可權現在會指派給選取的使用者群組。

        > [!div class="mx-imgBorder"]
        > ![Android 評審的影像建立應用程式佈建原則](images/android-review-create.png)


10. 在 [ \> **屬性** \> **指派** \> **編輯**] 清單中，選取 [Microsoft Defender ATP 應用程式]。

    ![App 清單影像](images/mda-properties.png)


11. 將 app 指派為 *所需* 的應用程式至使用者群組。 在下一次透過公司入口網站進行裝置同步處理期間，會自動將其安裝在 *工作設定檔* 中。 若要完成此工作分派，請流覽至 *必要* 的區段 [ \> **新增群組]，** 選取 [使用者] 群組，然後按一下 [ **選取**]。

    > [!div class="mx-imgBorder"]
    > ![[編輯應用程式] 頁面的圖像](images/ea06643280075f16265a596fb9a96042.png)


12. 在 [ **編輯應用程式** ] 頁面中，複查以上輸入的所有資訊。 然後選取 [ **複查 + 儲存** ]，然後再次 **儲存** 以開始工作分派。

### <a name="auto-setup-of-always-on-vpn"></a>自動設定 Always on VPN 
適用于 Endpoint 的 Defender 是透過 Intune 支援受管理裝置的裝置設定原則。 這項功能可用於在 Android 企業註冊的裝置上 **自動安裝 Always ON VPN** ，因此使用者在上架時，不需要設定 vpn 服務。
1.  在 [**裝置**] 上，根據您的裝置註冊類型，選取 [設定配置 **檔**]，根據您的  >    >    >  裝置註冊類型，**在** 下列其中一項下建立設定檔平臺 
- **完全管理、專用及 Corporate-Owned 的工作設定檔**
- **個人擁有的工作設定檔**

選取 [建立]。
 
   > ![裝置設定檔建立的影像](images/1autosetupofvpn.png)
    
2. **配置設定** 提供 **名稱** 和 **描述** ，以唯一識別設定設定檔。 

   > ![裝置的影像設定設定檔名稱和描述](images/2autosetupofvpn.png)
   
 3. 選取 **連通性** 及設定 VPN：
- 啟用 **Always ON vpn** 設定工作設定檔中的 vpn 用戶端，可在可能時自動連線並重新連接至 VPN。 在指定的裝置上，只有一個 VPN 用戶端可以設定為 always on VPN，所以請務必將一個以上的 [永不間斷] VPN 原則部署到單一裝置。 
- 在 VPN 用戶端下拉式清單中選取 **自訂** vpn 在此案例中，是用來提供 Web 保護功能的 Endpoint VPN 的 Defender。 
    > [!NOTE]
    > 為了能夠運作此 VPN 的自動設定，必須在使用者的裝置上安裝 Microsoft Defender ATP 應用程式。

- 輸入 Google Play store 中 Microsoft Defender ATP 應用程式的 **套件識別碼** 。 若為 Defender 應用程式 URL https://play.google.com/store/apps/details?id=com.microsoft.scmx ，PACKAGE ID 為 **.com。 scmx**  
- **鎖定模式** 未設定 (預設)  

     ![裝置的影像設定設定檔啟用 Alwayson VPN](images/3autosetupofvpn.png)
   
4. **工作分派** 在 [ **工作分派**]   頁面中，選取要指派此應用程式佈建原則的使用者群組。 按一下 [選取要包含的 **群組** ]，然後選取適當的群組，然後按 **[下一步]**。 在這裡選取的群組通常是您要為其指派 Microsoft Defender for Endpoint Android 應用程式的相同群組。 

     ![裝置設定檔指派的影像](images/4autosetupofvpn.png)

5. 在 [ **複查** ] 接下來的 [建立] 頁面中，複查所有資訊，然後選取 [ **建立**]。 裝置設定檔現在會指派給選取的使用者群組。    

    ![裝置的圖像設定設定檔檢查和建立](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a>完成上架和支票狀態

1. 按一下 [ **裝置安裝狀態**]，以確認 Android 的 Microsoft Defender 端點的安裝狀態。 驗證裝置是否顯示在這裡。

    > [!div class="mx-imgBorder"]
    > ![裝置安裝狀態的影像](images/900c0197aa59f9b7abd762ab2b32e80c.png)


2. 在裝置上，您可以前往 **工作設定檔** 來驗證上架狀態。 確認已提供 [Defender for Endpoint]，且您已 **使用工作設定檔對個人擁有的裝置** 進行註冊。  如果您已註冊到 **公司所擁有的完整管理使用者裝置**，您可以在裝置上擁有單一設定檔，您可以在此裝置上確認可用的 Defender for Endpoint。

    ![移動裝置中的應用程式影像](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. 安裝應用程式時，請開啟應用程式並接受許可權，然後您的上架應該會成功。

    ![使用 Microsoft Defender for Endpoint 應用程式的行動裝置影像](images/mda-devicesafe.png)

4. 在此階段，裝置成功架到適用于 Android 的 Endpoint for Defender。 您可以流覽至 [**裝置**] 頁面，以在 [Microsoft Defender Security Center](https://securitycenter.microsoft.com)上驗證這一點。

    ![端點入口網站的 Microsoft Defender 影像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a>相關主題
- [Android 版適用於端點的 Microsoft Defender 概觀](microsoft-defender-endpoint-android.md)
- [設定 Android 版適用於端點的 Microsoft Defender 功能](android-configure.md)
