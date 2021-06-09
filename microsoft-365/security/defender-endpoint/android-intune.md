---
title: 在 Android 上使用 Microsoft Intune 部署適用於端點的 Microsoft Defender
description: 說明如何在 Android 上使用 Microsoft Intune 部署 Microsoft Defender for Endpoint
keywords: microsoft、defender、Microsoft Defender for Endpoint、mde、android、安裝、部署、卸載、
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
ms.openlocfilehash: 1935533ad924b7589bdfee6f3119fb667fb60b73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841507"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="d1532-104">在 Android 上使用 Microsoft Intune 部署適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d1532-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d1532-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d1532-105">**Applies to:**</span></span>
- [<span data-ttu-id="d1532-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d1532-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d1532-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d1532-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d1532-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d1532-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d1532-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d1532-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="d1532-110">瞭解如何在 Intune 公司入口網站已註冊的裝置上，為 Android 上的端點部署 Defender。</span><span class="sxs-lookup"><span data-stu-id="d1532-110">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="d1532-111">如需 Intune 裝置註冊的詳細資訊，請參閱  [註冊裝置](/mem/intune/user-help/enroll-device-android-company-portal)。</span><span class="sxs-lookup"><span data-stu-id="d1532-111">For more information about Intune device enrollment, see  [Enroll your device](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="d1532-112">**Android 的 Defender 上的 Endpoint 現在可在 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)上使用**</span><span class="sxs-lookup"><span data-stu-id="d1532-112">**Defender for Endpoint on Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="d1532-113">您可以從 Intune 連線到 Google，以跨裝置管理員和 Android Enterprise entrollment 模式來部署適用于 Endpoint 應用程式的 Defender。</span><span class="sxs-lookup"><span data-stu-id="d1532-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="d1532-114">應用程式的更新是透過 Google Play 自動進行。</span><span class="sxs-lookup"><span data-stu-id="d1532-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="d1532-115">在裝置管理員註冊的裝置上部署</span><span class="sxs-lookup"><span data-stu-id="d1532-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="d1532-116">**在 Intune 公司入口網站裝置管理員註冊的裝置上，于 Android 上為端點部署 Defender**</span><span class="sxs-lookup"><span data-stu-id="d1532-116">**Deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="d1532-117">瞭解如何在 Intune 公司入口網站裝置管理員註冊的裝置上，為 Android 上的端點部署 Defender。</span><span class="sxs-lookup"><span data-stu-id="d1532-117">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="d1532-118">新增為 Android store 應用程式</span><span class="sxs-lookup"><span data-stu-id="d1532-118">Add as Android store app</span></span>

1. <span data-ttu-id="d1532-119">在 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，移至 **應用程式** \> **Android 應用** 程式 \> **新增 \> android store 應用程式**，然後選擇 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="d1532-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Microsoft 端點管理員系統管理中心的影像新增 android 應用程式儲存應用程式](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="d1532-121">在 [ **新增應用程式** ] 頁面上，于 [ *應用程式資訊* ] 區段中輸入：</span><span class="sxs-lookup"><span data-stu-id="d1532-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="d1532-122">**名稱**</span><span class="sxs-lookup"><span data-stu-id="d1532-122">**Name**</span></span> 
   - <span data-ttu-id="d1532-123">**描述**</span><span class="sxs-lookup"><span data-stu-id="d1532-123">**Description**</span></span>
   - <span data-ttu-id="d1532-124">**Publisher** 為 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d1532-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="d1532-125">**應用商店 url** 為 https://play.google.com/store/apps/details?id=com.microsoft.scmx 端點應用程式 GOOGLE Play Store url (Defender) </span><span class="sxs-lookup"><span data-stu-id="d1532-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="d1532-126">其他欄位是選用的。</span><span class="sxs-lookup"><span data-stu-id="d1532-126">Other fields are optional.</span></span> <span data-ttu-id="d1532-127">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1532-127">Select **Next**.</span></span>

   ![Microsoft 端點管理員系統管理中心的影像新增應用程式資訊](images/mda-addappinfo.png)

3. <span data-ttu-id="d1532-129">在 [ *工作分派* ] 區段中，移至 [ **必要** ] 區段，然後選取 [ **新增群組]。**</span><span class="sxs-lookup"><span data-stu-id="d1532-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="d1532-130">然後，您可以選擇要在 Android 應用程式上以其為 Defender for Endpoint 的使用者群組 () 。</span><span class="sxs-lookup"><span data-stu-id="d1532-130">You can then choose the user group(s) that you would like to target Defender for Endpoint on Android app.</span></span> <span data-ttu-id="d1532-131">選擇 [選取]，然後 **按一下** **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="d1532-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="d1532-132">選取的使用者群組應該包含 Intune 登記的使用者。</span><span class="sxs-lookup"><span data-stu-id="d1532-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![選取的 Microsoft 端點管理員系統管理中心之使用者群組的影像](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="d1532-134">在 [ **複查 + 建立** ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="d1532-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="d1532-135">在幾分鐘內，即可成功建立端點應用程式，並在頁面的右上角顯示通知。</span><span class="sxs-lookup"><span data-stu-id="d1532-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![defender 端點應用程式的 Microsoft 端點管理員系統管理員中心通知的影像](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="d1532-137">在顯示的 [應用程式資訊] 頁面中，選取 [ **監視** ] 區段中的 [ **裝置安裝狀態** ]，以確認裝置安裝已成功完成。</span><span class="sxs-lookup"><span data-stu-id="d1532-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-138">![Microsoft 端點管理員系統管理中心設備安裝的影像](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="d1532-139">完成上架和支票狀態</span><span class="sxs-lookup"><span data-stu-id="d1532-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="d1532-140">在 Android 上的 Endpoint for Endpoint 在裝置上安裝後，您會看到應用程式圖示。</span><span class="sxs-lookup"><span data-stu-id="d1532-140">Once Defender for Endpoint on Android has been installed on the device, you'll see the app icon.</span></span>

    ![移動裝置上的圖示](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="d1532-142">點擊 [Microsoft Defender for Endpoint app] 圖示，然後依照螢幕指示完成安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="d1532-142">Tap the Microsoft Defender for Endpoint app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="d1532-143">詳細資料包含使用者接收 Android 的 Defender for Endpoint 所需的 Android 許可權。</span><span class="sxs-lookup"><span data-stu-id="d1532-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint on Android.</span></span>

3. <span data-ttu-id="d1532-144">成功上架後，裝置會在 Microsoft Defender 資訊安全中心中的 [裝置] 清單上開始顯示。</span><span class="sxs-lookup"><span data-stu-id="d1532-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![用於端點入口網站的 Defender 中的裝置影像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="d1532-146">在 Android Enterprise 已註冊的裝置上部署</span><span class="sxs-lookup"><span data-stu-id="d1532-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="d1532-147">android 上的 Endpoint for android 支援 android Enterprise 已註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="d1532-147">Defender for Endpoint on Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="d1532-148">如需 Intune 支援之註冊選項的詳細資訊，請參閱 [註冊選項](/mem/intune/enrollment/android-enroll)。</span><span class="sxs-lookup"><span data-stu-id="d1532-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="d1532-149">**目前，具有工作設定檔和公司所擁有的完整管理使用者裝置註冊的個人擁有裝置可支援部署。**</span><span class="sxs-lookup"><span data-stu-id="d1532-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="d1532-150">在 Android 上將 Microsoft Defender for Endpoint 新增為受管理的 Google Play 應用程式</span><span class="sxs-lookup"><span data-stu-id="d1532-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="d1532-151">請遵循下列步驟，將 Microsoft Defender for Endpoint 應用程式新增至您的受管理 Google Play。</span><span class="sxs-lookup"><span data-stu-id="d1532-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="d1532-152">在 [Microsoft 端點管理員系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，移至 **應用程式** \> **Android 應用程式** \> **新增** 並選取 **受管理的 Google Play 應用程式**。</span><span class="sxs-lookup"><span data-stu-id="d1532-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-153">![Microsoft 端點管理員管理中心 managed google play 的影像](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="d1532-154">在隨後載入的 [受管理的 Google Play] 頁面上，移至 [搜尋] 方塊並查閱 **Microsoft Defender。**</span><span class="sxs-lookup"><span data-stu-id="d1532-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="d1532-155">您的搜尋應該會在受管理的 Google Play 中顯示 Microsoft Defender for Endpoint 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d1532-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="d1532-156">在 [應用程式搜尋結果] 中，按一下 [Microsoft Defender for Endpoint 應用程式]。</span><span class="sxs-lookup"><span data-stu-id="d1532-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Microsoft 端點管理員 admin center 應用程式搜尋的影像](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="d1532-158">在接下來的 [應用程式描述] 頁面中，您應該可以查看 Defender for Endpoint 上的應用程式詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d1532-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="d1532-159">複查頁面上的資訊，然後選取 [ **核准**]。</span><span class="sxs-lookup"><span data-stu-id="d1532-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-160">![受管理的 Google Play 的螢幕擷取畫面](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="d1532-161">您將會看到供該 Defender for Endpoint 取得的許可權，讓其能夠運作。</span><span class="sxs-lookup"><span data-stu-id="d1532-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="d1532-162">請加以檢查，然後選取 [ **核准**]。</span><span class="sxs-lookup"><span data-stu-id="d1532-162">Review them and then select **Approve**.</span></span>

    ![使用 Defender 進行端點預覽應用程式核准的螢幕擷取畫面](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="d1532-164">您將會看到 [核准設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d1532-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="d1532-165">頁面會確認您的喜好設定，以處理 Android 上的 Defender for Endpoint 可能要求的新應用程式許可權。</span><span class="sxs-lookup"><span data-stu-id="d1532-165">The page confirms your preference to handle new app permissions that Defender for Endpoint on Android might ask.</span></span> <span data-ttu-id="d1532-166">查看選項，然後選取您的喜好選項。</span><span class="sxs-lookup"><span data-stu-id="d1532-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="d1532-167">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d1532-167">Select **Done**.</span></span>

    <span data-ttu-id="d1532-168">依預設，受管理的 Google 播放會 *在應用程式要求新許可權時選取 [保留已核准*]</span><span class="sxs-lookup"><span data-stu-id="d1532-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-169">![[通知] 索引標籤](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="d1532-170">進行許可權處理選取之後，請選取 [ **同步** 處理]，將 Microsoft Defender for Endpoint 同步處理至您的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="d1532-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-171">![[同步處理] 頁面](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="d1532-172">同步處理會在幾分鐘內完成。</span><span class="sxs-lookup"><span data-stu-id="d1532-172">The sync will complete in a few minutes.</span></span>

    ![Android 應用程式的影像](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="d1532-174">選取 [Android 應用程式] 畫面中的 [重新整理 **] 按鈕，** [應用程式] 清單中應該會顯示 [Microsoft Defender for Endpoint]。</span><span class="sxs-lookup"><span data-stu-id="d1532-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender for Endpoint should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-175">![Android 應用程式清單的影像](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="d1532-176">適用于 Endpoint 的 Defender 可透過 Intune 支援受管理裝置的應用程式佈建原則。</span><span class="sxs-lookup"><span data-stu-id="d1532-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="d1532-177">您可以利用這項功能，autogrant) 適用的 Android (許可權，因此，使用者不需要接受這些許可權 (s) 。</span><span class="sxs-lookup"><span data-stu-id="d1532-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="d1532-178">在 [ **應用程式** ] 頁面中，移至 **Policy > App Configuration Policy > 新增 > 受管理的裝置**。</span><span class="sxs-lookup"><span data-stu-id="d1532-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Microsoft 端點管理員系統管理中心 android 受管理裝置的影像](images/android-mem.png)

    1. <span data-ttu-id="d1532-180">在 [ **建立應用程式佈建原則** ] 頁面中，輸入下列詳細資料：</span><span class="sxs-lookup"><span data-stu-id="d1532-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="d1532-181">名稱： Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d1532-181">Name: Microsoft Defender for Endpoint.</span></span>
        - <span data-ttu-id="d1532-182">選擇 [ **Android Enterprise** 為平臺]。</span><span class="sxs-lookup"><span data-stu-id="d1532-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="d1532-183">選擇 [ **僅工作設定檔** ] 做為配置檔案類型。</span><span class="sxs-lookup"><span data-stu-id="d1532-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="d1532-184">按一下 [**選取應用程式**]，然後選擇 [ **Microsoft Defender ATP**]，選取 **[確定]** ，然後選取 **[**</span><span class="sxs-lookup"><span data-stu-id="d1532-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d1532-185">![[建立應用程式佈建原則] 頁面的影像](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="d1532-186">在 [**設定**] 頁面中，移至 [許可權] 區段，按一下 [新增] 以查看支援的許可權清單。</span><span class="sxs-lookup"><span data-stu-id="d1532-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="d1532-187">在 [新增許可權] 區段中，選取下列許可權：</span><span class="sxs-lookup"><span data-stu-id="d1532-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="d1532-188">外部儲存體 (讀取) </span><span class="sxs-lookup"><span data-stu-id="d1532-188">External storage (read)</span></span>
       - <span data-ttu-id="d1532-189">外部儲存體 (寫入) </span><span class="sxs-lookup"><span data-stu-id="d1532-189">External storage (write)</span></span>

       <span data-ttu-id="d1532-190">然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d1532-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="d1532-191">![Android 的影像建立應用程式設定原則](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="d1532-192">現在您應該會看到列出的許可權，而且現在您可以在 **許可權狀態** 下拉式清單中選擇 [autogrant] 來 autogrant，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1532-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="d1532-193">![Android 自動授與的影像建立應用程式設定原則](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="d1532-194">在 [ **工作分派** ] 頁面中，選取要指派此應用程式佈建原則的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d1532-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="d1532-195">按一下 [ **選取要包含的群組** ]，然後選取適當的群組，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1532-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="d1532-196">在這裡選取的群組通常是您要為其指派 Microsoft Defender for Endpoint Android 應用程式的相同群組。</span><span class="sxs-lookup"><span data-stu-id="d1532-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="d1532-197">![建立應用程式佈建原則的影像](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="d1532-198">在 [ **複查** ] 接下來的 [建立] 頁面中，複查所有資訊，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="d1532-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="d1532-199">「用於 Defender for Endpoint autogranting 的應用程式設定原則」儲存許可權現在會指派給選取的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d1532-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="d1532-200">![Android 評審的影像建立應用程式佈建原則](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="d1532-201">在 [清單 \> **屬性** \> **指派**] \> **編輯** 中，選取 [Microsoft Defender ATP 應用程式]。</span><span class="sxs-lookup"><span data-stu-id="d1532-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![App 清單影像](images/mda-properties.png)


11. <span data-ttu-id="d1532-203">將 app 指派為 *所需* 的應用程式至使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d1532-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="d1532-204">它會在下一次同步裝置時透過公司入口網站 app 自動安裝在 *工作設定檔* 中。</span><span class="sxs-lookup"><span data-stu-id="d1532-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="d1532-205">若要完成此工作分派，請流覽至 *必要* 的區段 [ \> **新增群組]，** 選取 [使用者] 群組，然後按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="d1532-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-206">![[編輯應用程式] 頁面的圖像](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="d1532-207">在 [ **編輯應用程式** ] 頁面中，複查以上輸入的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="d1532-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="d1532-208">然後選取 [ **複查 + 儲存** ]，然後再次 **儲存** 以開始工作分派。</span><span class="sxs-lookup"><span data-stu-id="d1532-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="d1532-209">自動設定 Always on VPN</span><span class="sxs-lookup"><span data-stu-id="d1532-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="d1532-210">適用于 Endpoint 的 Defender 是透過 Intune 支援受管理裝置的裝置設定原則。</span><span class="sxs-lookup"><span data-stu-id="d1532-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="d1532-211">您可以利用這項功能，在 Android Enterprise 註冊的裝置上 **自動設定 Always on VPN** ，讓使用者在上架時不需要設定 vpn 服務。</span><span class="sxs-lookup"><span data-stu-id="d1532-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="d1532-212">在 [**裝置**] 上，選取 [設定配置 **檔**] [  >  **建立配置** 檔  >  **平臺**  >  **Android Enterprise** ]，根據您的裝置註冊類型，選取下列其中一項下的 **裝置限制**</span><span class="sxs-lookup"><span data-stu-id="d1532-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="d1532-213">**完全管理、專用及 Corporate-Owned 的工作設定檔**</span><span class="sxs-lookup"><span data-stu-id="d1532-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="d1532-214">**個人擁有的工作設定檔**</span><span class="sxs-lookup"><span data-stu-id="d1532-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="d1532-215">選取 [建立 **]**。</span><span class="sxs-lookup"><span data-stu-id="d1532-215">Select **Create**.</span></span>
 
   > ![裝置設定檔建立的影像](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="d1532-217">設定 **設定** 提供 **名稱** 和 **描述**，以唯一識別設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="d1532-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![裝置的影像設定設定檔名稱和描述](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="d1532-219">選取 **連通性** 及設定 VPN：</span><span class="sxs-lookup"><span data-stu-id="d1532-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="d1532-220">啟用 **Always ON vpn** 設定工作設定檔中的 vpn 用戶端，可在可能時自動連線並重新連接至 VPN。</span><span class="sxs-lookup"><span data-stu-id="d1532-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="d1532-221">在指定的裝置上，只有一個 VPN 用戶端可以設定為 always on VPN，所以請務必將一個以上的 [永不間斷] VPN 原則部署到單一裝置。</span><span class="sxs-lookup"><span data-stu-id="d1532-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="d1532-222">在 VPN 用戶端下拉式清單中選取 **自訂** vpn 在此案例中，是用來提供 Web 保護功能的 Endpoint VPN 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="d1532-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="d1532-223">使用者的裝置上必須安裝 Microsoft Defender for Endpoint 應用程式，才能運作此 VPN 的自動設定。</span><span class="sxs-lookup"><span data-stu-id="d1532-223">Microsoft Defender for Endpoint app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="d1532-224">為 Google Play store 中的 Microsoft Defender for Endpoint 應用程式輸入 **套件識別碼** 。</span><span class="sxs-lookup"><span data-stu-id="d1532-224">Enter **Package ID** of the Microsoft Defender for Endpoint app in Google Play store.</span></span> <span data-ttu-id="d1532-225">若為 Defender 應用程式 URL https://play.google.com/store/apps/details?id=com.microsoft.scmx ，PACKAGE ID 為 **.com。 scmx**</span><span class="sxs-lookup"><span data-stu-id="d1532-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="d1532-226">**鎖定模式** 未設定 (預設) </span><span class="sxs-lookup"><span data-stu-id="d1532-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![裝置的影像設定設定檔啟用 Alwayson VPN](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="d1532-228">**工作分派** 在 [ **工作分派**]   頁面中，選取要指派此應用程式佈建原則的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d1532-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="d1532-229">按一下 [選取要包含的 **群組** ]，然後選取適當的群組，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d1532-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="d1532-230">在這裡選取的群組通常是您要為其指派 Microsoft Defender for Endpoint Android 應用程式的相同群組。</span><span class="sxs-lookup"><span data-stu-id="d1532-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![裝置設定檔指派的影像](images/4autosetupofvpn.png)

5. <span data-ttu-id="d1532-232">在 [ **複查** ] 接下來的 [建立] 頁面中，複查所有資訊，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="d1532-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="d1532-233">裝置設定檔現在會指派給選取的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d1532-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![裝置的圖像設定設定檔檢查和建立](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="d1532-235">完成上架和支票狀態</span><span class="sxs-lookup"><span data-stu-id="d1532-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="d1532-236">按一下 [ **裝置安裝狀態**]，以確認 Android 上 Microsoft Defender for Endpoint 的安裝狀態。</span><span class="sxs-lookup"><span data-stu-id="d1532-236">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="d1532-237">驗證裝置是否顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="d1532-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1532-238">![裝置安裝狀態的影像](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="d1532-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="d1532-239">在裝置上，您可以前往 **工作設定檔** 來驗證上架狀態。</span><span class="sxs-lookup"><span data-stu-id="d1532-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="d1532-240">確認已提供 [Defender for Endpoint]，且您已 **使用工作設定檔對個人擁有的裝置** 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="d1532-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="d1532-241">如果您已註冊到 **公司所擁有的完整管理使用者裝置**，您可以在裝置上擁有單一設定檔，您可以在此裝置上確認可用的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d1532-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![移動裝置中的應用程式影像](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="d1532-243">安裝應用程式時，請開啟應用程式並接受許可權，然後您的上架應該會成功。</span><span class="sxs-lookup"><span data-stu-id="d1532-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![使用 Microsoft Defender for Endpoint 應用程式的行動裝置影像](images/mda-devicesafe.png)

4. <span data-ttu-id="d1532-245">在此階段，裝置成功架到 Android 上的 Endpoint for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="d1532-245">At this stage the device is successfully onboarded onto Defender for Endpoint on Android.</span></span> <span data-ttu-id="d1532-246">您可以流覽至 [**裝置**] 頁面，在 [Microsoft Defender 資訊安全中心](https://securitycenter.microsoft.com)上進行驗證。</span><span class="sxs-lookup"><span data-stu-id="d1532-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![端點入口網站的 Microsoft Defender 影像](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="d1532-248">相關主題</span><span class="sxs-lookup"><span data-stu-id="d1532-248">Related topics</span></span>
- [<span data-ttu-id="d1532-249">Android 上適用於端點的 Microsoft Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="d1532-249">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="d1532-250">在 Android 上設定適用於端點的 Microsoft Defender 功能</span><span class="sxs-lookup"><span data-stu-id="d1532-250">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
