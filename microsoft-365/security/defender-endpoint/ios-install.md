---
title: 在 iOS 上以應用程式為基礎的 Microsoft Defender for Endpoint 部署
ms.reviewer: ''
description: 說明如何使用應用程式在 iOS 上部署 Microsoft Defender for Endpoint
keywords: microsoft，defender，Microsoft Defender for Endpoint，ios，應用程式，安裝，部署，卸載，intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842282"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="b0a1a-104">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0a1a-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b0a1a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b0a1a-105">**Applies to:**</span></span>
- [<span data-ttu-id="b0a1a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b0a1a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b0a1a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0a1a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b0a1a-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="b0a1a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b0a1a-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b0a1a-110">本主題說明如何在 Intune 公司入口網站註冊的裝置上的 iOS 上為端點部署 Defender。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="b0a1a-111">如需 Intune 裝置註冊的詳細資訊，請參閱 [在 intune 中註冊 iOS/iPadOS 裝置](/mem/intune/enrollment/ios-enroll)。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b0a1a-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="b0a1a-112">Before you begin</span></span>

- <span data-ttu-id="b0a1a-113">確定您可以存取 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="b0a1a-114">確定已為您的使用者執行 iOS 註冊。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="b0a1a-115">使用者必須具有指派的 Defender for Endpoint 授權，才能在 iOS 上使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="b0a1a-116">如需指派授權的相關指示，請參閱 [指派授權給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign) 。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="b0a1a-117">IOS 上的 Microsoft Defender for Endpoint 可用於 [Apple 應用程式存放區](https://aka.ms/mdatpiosappstore)。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="b0a1a-118">部署步驟</span><span class="sxs-lookup"><span data-stu-id="b0a1a-118">Deployment steps</span></span>

<span data-ttu-id="b0a1a-119">透過 Intune 公司入口網站在 iOS 上為端點部署 Defender。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="b0a1a-120">新增 iOS 儲存應用程式</span><span class="sxs-lookup"><span data-stu-id="b0a1a-120">Add iOS store app</span></span>

1. <span data-ttu-id="b0a1a-121">在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 [**應用**  ->  **iOS/iPadOS**] [  ->  **新增**  ->  **iOS 儲存應用程式**]，然後按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-122">![Microsoft 端點管理員系統管理 Center1 的影像](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="b0a1a-123">在 [新增應用程式] 頁面上，按一下 [ **搜尋應用程式存放區** ]，然後在搜尋列中輸入 **Microsoft Defender 端點** 。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="b0a1a-124">在 [搜尋結果] 區段中，按一下 [ *Microsoft Defender 端點* ]，然後按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="b0a1a-125">選取 [ **iOS 11.0** ] 做為最小作業系統。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="b0a1a-126">查看應用程式的其餘資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="b0a1a-127">在 [ *工作分派* ] 區段中，移至 [ **必要** ] 區段，然後選取 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="b0a1a-128">然後，您可以選擇 (s) 上的使用者群組，以 iOS app 上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="b0a1a-129">按一下 [**選取**]，然後按一下 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="b0a1a-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0a1a-130">選取的使用者群組應該包含 Intune 登記的使用者。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-131">![Microsoft 端點管理員系統管理 Center2 的影像](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="b0a1a-132">在 [ *複查 + 建立* ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="b0a1a-133">在幾分鐘內，應順利建立端點應用程式，並且在頁面的右上角應該會顯示通知。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="b0a1a-134">在顯示的 [應用程式資訊] 頁面中，選取 [ **監視** ] 區段中的 [ **裝置安裝狀態** ]，以確認裝置安裝已成功完成。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-135">![Microsoft 端點管理員系統管理 Center3 的影像](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="b0a1a-136">自動載入 VPN 設定檔 (簡化型架) </span><span class="sxs-lookup"><span data-stu-id="b0a1a-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="b0a1a-137">系統管理員可以設定 VPN 設定檔的自動設定。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="b0a1a-138">這會自動設定 Defender for Endpoint VPN 設定檔，而不需要使用者在上架時執行此作業。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="b0a1a-139">請注意，使用 VPN 是為了提供 Web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="b0a1a-140">這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="b0a1a-141">在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 [**裝置** 設定配置  ->  **檔**  ->  **建立設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="b0a1a-142">選擇 [ **平臺** 為 **iOS/iPadOS** ] 和 [ **配置檔案類型** 為 **VPN**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="b0a1a-143">按一下 \*\*\*\*[建立]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-143">Click **Create**.</span></span>
1. <span data-ttu-id="b0a1a-144">輸入設定檔的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="b0a1a-145">選取 [連線類型的 **自訂 VPN** ]，然後在 [ **基礎 VPN** ] 區段中，輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="b0a1a-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="b0a1a-146">Connection Name = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0a1a-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="b0a1a-147">VPN 伺服器位址 = 127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="b0a1a-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="b0a1a-148">Auth 方法 = 「使用者名稱與密碼」</span><span class="sxs-lookup"><span data-stu-id="b0a1a-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="b0a1a-149">分割隧道 = 停用</span><span class="sxs-lookup"><span data-stu-id="b0a1a-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="b0a1a-150">VPN 識別碼 = scmx</span><span class="sxs-lookup"><span data-stu-id="b0a1a-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="b0a1a-151">在 [索引鍵-值] 組中，輸入機碼 **AutoOnboard** ，然後將值設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="b0a1a-152">自動 VPN 的類型 = 隨選 VPN</span><span class="sxs-lookup"><span data-stu-id="b0a1a-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="b0a1a-153">針對 [**需求規則**] 按一下 [**新增**]，然後選取 **[我想要建立 VPN**]，**我想要限制為 [所有網域**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![VPN 設定檔設定的螢幕擷取畫面](images/ios-deploy-8.png)

1. <span data-ttu-id="b0a1a-155">按 [下一步] 並將設定檔指派給目標使用者。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="b0a1a-156">在 [ *複查 + 建立* ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="b0a1a-157">完成上架和支票狀態</span><span class="sxs-lookup"><span data-stu-id="b0a1a-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="b0a1a-158">一旦裝置上已安裝 iOS 的 Endpoint for Endpoint，您就會看到應用程式圖示。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![自動產生之智慧型電話描述的螢幕擷取畫面](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="b0a1a-160">點擊 [Defender for Endpoint 應用程式] 圖示 (MSDefender) 並依照螢幕指示完成上架步驟。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="b0a1a-161">詳細資料包括 iOS 使用者接受 iOS 上的 Defender for Endpoint 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="b0a1a-162">成功上架後，裝置會在 Microsoft Defender 資訊安全中心中的 [裝置] 清單上開始顯示。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-163">![自動產生之儲存格電話描述的螢幕擷取畫面](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="b0a1a-164">針對監督模式設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b0a1a-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="b0a1a-165">在 iOS 應用程式上的 Microsoft Defender for Endpoint 具有 iOS/iPadOS 裝置的特殊能力，但前提是這些裝置類型的平臺已增加管理功能。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="b0a1a-166">若要利用這些功能，終結點應用程式必須知道裝置是否處於監督模式。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="b0a1a-167">透過 Intune 設定監督模式</span><span class="sxs-lookup"><span data-stu-id="b0a1a-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="b0a1a-168">Intune 可讓您透過應用程式設定原則設定 iOS 應用程式的 Defender。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b0a1a-169">受監視裝置的此應用程式設定原則只適用于受管理的裝置，而且應針對所有受管理的 iOS 裝置做為最佳作法。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="b0a1a-170">登入 Microsoft 端點管理員系統 [管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然後移至 [**新增應用** 程式] 設定  >  **原則**  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="b0a1a-171">按一下 [ **受管理的裝置**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-172">![Microsoft 端點管理員系統管理 Center4 的影像](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="b0a1a-173">在 [ *建立應用程式佈建原則* ] 頁面中，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b0a1a-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="b0a1a-174">原則名稱</span><span class="sxs-lookup"><span data-stu-id="b0a1a-174">Policy Name</span></span>
    - <span data-ttu-id="b0a1a-175">平臺： Select iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="b0a1a-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="b0a1a-176">目標應用程式：從清單中選取 [ **Microsoft Defender 端點** ]</span><span class="sxs-lookup"><span data-stu-id="b0a1a-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-177">![Microsoft 端點管理員系統管理 Center5 的影像](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="b0a1a-178">在下一個畫面中，選取 [ **使用 configuration designer** 做為格式]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="b0a1a-179">指定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="b0a1a-179">Specify the following property:</span></span>
    - <span data-ttu-id="b0a1a-180">設定機碼： issupervised</span><span class="sxs-lookup"><span data-stu-id="b0a1a-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="b0a1a-181">數值型別：字串</span><span class="sxs-lookup"><span data-stu-id="b0a1a-181">Value type: String</span></span>
    - <span data-ttu-id="b0a1a-182">設定值： {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="b0a1a-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-183">![Microsoft 端點管理員系統管理 Center6 的影像](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="b0a1a-184">按 **[下一步]** 開啟 [ **範圍標記** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="b0a1a-185">範圍標記是選用的。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-185">Scope tags are optional.</span></span> <span data-ttu-id="b0a1a-186">按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="b0a1a-187">在 [ **工作分派** ] 頁面上，選取將要接收此設定檔的群組。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="b0a1a-188">針對此案例，最佳作法是針對 **所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="b0a1a-189">如需指派設定檔的詳細資訊，請參閱 [指派使用者和裝置設定檔](/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="b0a1a-190">部署至使用者群組時，使用者必須先登入裝置，然後才能套用原則。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="b0a1a-191">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-191">Click **Next**.</span></span>

1. <span data-ttu-id="b0a1a-192">當您完成時，請在 [ **複查 + 建立** ] 頁面上，選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="b0a1a-193">新的設定檔會顯示在設定檔的清單中。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="b0a1a-194">接下來，針對增強型防網路釣魚功能，您可以在監督的 iOS 裝置上部署自訂設定檔。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="b0a1a-195">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b0a1a-195">Follow the steps below:</span></span>
    - <span data-ttu-id="b0a1a-196">從下載設定檔 [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="b0a1a-197">流覽至 **裝置**  ->  **iOS/iPadOS** 設定配置  ->  **檔**  ->  **建立設定檔**</span><span class="sxs-lookup"><span data-stu-id="b0a1a-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b0a1a-198">![Microsoft 端點管理員系統管理 Center7 的影像](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="b0a1a-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="b0a1a-199">提供設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-199">Provide a name of the profile.</span></span> <span data-ttu-id="b0a1a-200">當系統提示您匯入設定設定檔檔案時，請選取上述下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="b0a1a-201">在 [ **工作分派** ] 區段中，選取您要套用此設定檔的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="b0a1a-202">最佳作法是將此套用至所有受管理的 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="b0a1a-203">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-203">Click **Next**.</span></span>
    - <span data-ttu-id="b0a1a-204">當您完成時，請在 [ **複查 + 建立** ] 頁面上，選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="b0a1a-205">新的設定檔會顯示在設定檔的清單中。</span><span class="sxs-lookup"><span data-stu-id="b0a1a-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0a1a-206">後續步驟</span><span class="sxs-lookup"><span data-stu-id="b0a1a-206">Next Steps</span></span>

[<span data-ttu-id="b0a1a-207">設定 iOS 功能上的端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="b0a1a-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
