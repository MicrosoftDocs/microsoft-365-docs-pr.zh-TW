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
ms.openlocfilehash: a3711018034bcabdde10c21b3c968c3e813d0565
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245251"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="8004c-104">在 iOS 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8004c-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8004c-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8004c-105">**Applies to:**</span></span>
- [<span data-ttu-id="8004c-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8004c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8004c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8004c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8004c-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="8004c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8004c-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="8004c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8004c-110">本主題說明如何在 Intune 公司入口網站註冊的裝置上的 iOS 上為端點部署 Defender。</span><span class="sxs-lookup"><span data-stu-id="8004c-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="8004c-111">如需 Intune 裝置註冊的詳細資訊，請參閱 [在 intune 中註冊 iOS/iPadOS 裝置](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll)。</span><span class="sxs-lookup"><span data-stu-id="8004c-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8004c-112">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="8004c-112">Before you begin</span></span>

- <span data-ttu-id="8004c-113">確定您可以存取 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="8004c-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="8004c-114">確定已為您的使用者執行 iOS 註冊。</span><span class="sxs-lookup"><span data-stu-id="8004c-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="8004c-115">使用者必須具有指派的 Defender for Endpoint 授權，才能在 iOS 上使用 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8004c-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="8004c-116">如需指派授權的相關指示，請參閱 [指派授權給使用者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) 。</span><span class="sxs-lookup"><span data-stu-id="8004c-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="8004c-117">現在，您可以在 [Apple App Store](https://aka.ms/mdatpiosappstore)中使用 iOS 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8004c-117">Microsoft Defender for Endpoint on iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="8004c-118">部署步驟</span><span class="sxs-lookup"><span data-stu-id="8004c-118">Deployment steps</span></span>

<span data-ttu-id="8004c-119">透過 Intune 公司入口網站在 iOS 上為端點部署 Defender。</span><span class="sxs-lookup"><span data-stu-id="8004c-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="8004c-120">新增 iOS 儲存應用程式</span><span class="sxs-lookup"><span data-stu-id="8004c-120">Add iOS store app</span></span>

1. <span data-ttu-id="8004c-121">在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 [**應用**  ->  **iOS/iPadOS**] [  ->  **新增**  ->  **iOS 儲存應用程式**]，然後按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-122">![Microsoft 端點管理員系統管理 Center1 的影像](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="8004c-123">在 [新增應用程式] 頁面上，按一下 [ **搜尋應用程式存放區** ]，然後在搜尋列中輸入 **Microsoft Defender 端點** 。</span><span class="sxs-lookup"><span data-stu-id="8004c-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="8004c-124">在 [搜尋結果] 區段中，按一下 [ *Microsoft Defender 端點* ]，然後按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="8004c-125">選取 [ **iOS 11.0** ] 做為最小作業系統。</span><span class="sxs-lookup"><span data-stu-id="8004c-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="8004c-126">查看應用程式的其餘資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8004c-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="8004c-127">在 [ *工作分派* ] 區段中，移至 [ **必要** ] 區段，然後選取 [ **新增群組**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="8004c-128">然後，您可以選擇 (s) 上的使用者群組，以 iOS app 上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8004c-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="8004c-129">按一下 [**選取**]，然後按一下 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="8004c-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8004c-130">選取的使用者群組應該包含 Intune 登記的使用者。</span><span class="sxs-lookup"><span data-stu-id="8004c-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-131">![Microsoft 端點管理員系統管理 Center2 的影像](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="8004c-132">在 [ *複查 + 建立* ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="8004c-133">在幾分鐘內，應順利建立端點應用程式，並且在頁面的右上角應該會顯示通知。</span><span class="sxs-lookup"><span data-stu-id="8004c-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="8004c-134">在顯示的 [應用程式資訊] 頁面中，選取 [ **監視** ] 區段中的 [ **裝置安裝狀態** ]，以確認裝置安裝已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8004c-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-135">![Microsoft 端點管理員系統管理 Center3 的影像](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="8004c-136">自動載入 VPN 設定檔 (簡化型架) </span><span class="sxs-lookup"><span data-stu-id="8004c-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

> [!NOTE]
> <span data-ttu-id="8004c-137">自動-載入 VPN 設定檔目前正在預覽中，此區段中所述的步驟在正式發行之前，可能會受到大量修改。</span><span class="sxs-lookup"><span data-stu-id="8004c-137">Auto-onboarding of VPN profile is currently in preview and the steps mentioned in this section may be substantially modified before it's commercially released.</span></span>

<span data-ttu-id="8004c-138">系統管理員可以設定 VPN 設定檔的自動設定。</span><span class="sxs-lookup"><span data-stu-id="8004c-138">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="8004c-139">這會自動設定 Defender for Endpoint VPN 設定檔，而不需要使用者在上架時執行此作業。</span><span class="sxs-lookup"><span data-stu-id="8004c-139">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="8004c-140">請注意，使用 VPN 是為了提供 Web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="8004c-140">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="8004c-141">這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。</span><span class="sxs-lookup"><span data-stu-id="8004c-141">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="8004c-142">在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 [**裝置** 設定  ->  **設定檔**  ->  **建立**  ->  **iOS 儲存應用程式**]，然後按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-142">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create** -> **iOS store app** and click **Select**.</span></span>
1. <span data-ttu-id="8004c-143">選擇 [ **平臺** 為 **iOS/iPadOS** ] 和 [ **配置檔案類型** 為 **VPN**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-143">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="8004c-144">按一下 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="8004c-144">Click **Create**.</span></span>
1. <span data-ttu-id="8004c-145">輸入設定檔的名稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="8004c-145">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="8004c-146">選取 [連線類型的 **自訂 VPN** ]，然後在 [ **基礎 VPN** ] 區段中，輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="8004c-146">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="8004c-147">Connection Name = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8004c-147">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="8004c-148">VPN 伺服器位址 = 127.0.0。1</span><span class="sxs-lookup"><span data-stu-id="8004c-148">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="8004c-149">Auth 方法 = 「使用者名稱與密碼」</span><span class="sxs-lookup"><span data-stu-id="8004c-149">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="8004c-150">分割隧道 = 停用</span><span class="sxs-lookup"><span data-stu-id="8004c-150">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="8004c-151">VPN 識別碼 = scmx</span><span class="sxs-lookup"><span data-stu-id="8004c-151">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="8004c-152">在 [索引鍵-值] 組中，輸入機碼 **AutoOnboard** ，然後將值設定為 **True**。</span><span class="sxs-lookup"><span data-stu-id="8004c-152">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="8004c-153">自動 VPN 的類型 = 隨選 VPN</span><span class="sxs-lookup"><span data-stu-id="8004c-153">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="8004c-154">針對 [**需求規則**] 按一下 [**新增**]，然後選取 **[我想要建立 VPN**]，**我想要限制為 [所有網域**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-154">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![VPN 設定檔設定的螢幕擷取畫面](images/ios-deploy-8.png)

1. <span data-ttu-id="8004c-156">按 [下一步] 並將設定檔指派給目標使用者。</span><span class="sxs-lookup"><span data-stu-id="8004c-156">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="8004c-157">在 [ *複查 + 建立* ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-157">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="8004c-158">完成上架和支票狀態</span><span class="sxs-lookup"><span data-stu-id="8004c-158">Complete onboarding and check status</span></span>

1. <span data-ttu-id="8004c-159">一旦裝置上已安裝 iOS 的 Endpoint for Endpoint，您就會看到應用程式圖示。</span><span class="sxs-lookup"><span data-stu-id="8004c-159">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![自動產生之智慧型電話描述的螢幕擷取畫面](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="8004c-161">點擊 [Defender for Endpoint app] 圖示，然後依照螢幕指示完成上架步驟。</span><span class="sxs-lookup"><span data-stu-id="8004c-161">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="8004c-162">詳細資料包括 iOS 使用者接受 iOS 上的 Defender for Endpoint 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="8004c-162">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="8004c-163">成功上架後，裝置會在 Microsoft Defender 資訊安全中心中的 [裝置] 清單上開始顯示。</span><span class="sxs-lookup"><span data-stu-id="8004c-163">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-164">![自動產生之儲存格電話描述的螢幕擷取畫面](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-164">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="8004c-165">針對監督模式設定 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8004c-165">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="8004c-166">在 iOS 應用程式上的 Microsoft Defender for Endpoint 具有 iOS/iPadOS 裝置的特殊能力，但前提是這些裝置類型的平臺已增加管理功能。</span><span class="sxs-lookup"><span data-stu-id="8004c-166">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="8004c-167">若要利用這些功能，終結點應用程式必須知道裝置是否處於監督模式。</span><span class="sxs-lookup"><span data-stu-id="8004c-167">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="8004c-168">透過 Intune 設定監督模式</span><span class="sxs-lookup"><span data-stu-id="8004c-168">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="8004c-169">Intune 可讓您透過應用程式設定原則設定 iOS 應用程式的 Defender。</span><span class="sxs-lookup"><span data-stu-id="8004c-169">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8004c-170">受監視裝置的此應用程式設定原則只適用于受管理的裝置，而且應針對所有受管理的 iOS 裝置做為最佳作法。</span><span class="sxs-lookup"><span data-stu-id="8004c-170">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="8004c-171">登入 Microsoft 端點管理員系統 [管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然後移至 [**新增應用** 程式] 設定  >  **原則**  >  \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8004c-171">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="8004c-172">按一下 [ **受管理的裝置**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-172">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-173">![Microsoft 端點管理員系統管理 Center4 的影像](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-173">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="8004c-174">在 [ *建立應用程式佈建原則* ] 頁面中，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="8004c-174">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="8004c-175">原則名稱</span><span class="sxs-lookup"><span data-stu-id="8004c-175">Policy Name</span></span>
    - <span data-ttu-id="8004c-176">平臺： Select iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="8004c-176">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="8004c-177">目標應用程式：從清單中選取 **Microsoft Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="8004c-177">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-178">![Microsoft 端點管理員系統管理 Center5 的影像](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-178">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="8004c-179">在下一個畫面中，選取 [ **使用 configuration designer** 做為格式]。</span><span class="sxs-lookup"><span data-stu-id="8004c-179">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="8004c-180">指定下列屬性：</span><span class="sxs-lookup"><span data-stu-id="8004c-180">Specify the following property:</span></span>
    - <span data-ttu-id="8004c-181">設定機碼： issupervised</span><span class="sxs-lookup"><span data-stu-id="8004c-181">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="8004c-182">數值型別：字串</span><span class="sxs-lookup"><span data-stu-id="8004c-182">Value type: String</span></span>
    - <span data-ttu-id="8004c-183">設定值： {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="8004c-183">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-184">![Microsoft 端點管理員系統管理 Center6 的影像](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-184">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="8004c-185">按 **[下一步]** 開啟 [ **範圍標記** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="8004c-185">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="8004c-186">範圍標記是選用的。</span><span class="sxs-lookup"><span data-stu-id="8004c-186">Scope tags are optional.</span></span> <span data-ttu-id="8004c-187">按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="8004c-187">Click **Next** to continue.</span></span>

1. <span data-ttu-id="8004c-188">在 [ **工作分派** ] 頁面上，選取將要接收此設定檔的群組。</span><span class="sxs-lookup"><span data-stu-id="8004c-188">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="8004c-189">針對此案例，最佳作法是針對 **所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="8004c-189">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="8004c-190">如需指派設定檔的詳細資訊，請參閱 [指派使用者和裝置設定檔](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="8004c-190">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="8004c-191">部署至使用者群組時，使用者必須先登入裝置，然後才能套用原則。</span><span class="sxs-lookup"><span data-stu-id="8004c-191">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="8004c-192">按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="8004c-192">Click **Next**.</span></span>

1. <span data-ttu-id="8004c-193">當您完成時，請在 [ **複查 + 建立** ] 頁面上，選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-193">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="8004c-194">新的設定檔會顯示在設定檔的清單中。</span><span class="sxs-lookup"><span data-stu-id="8004c-194">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="8004c-195">接下來，針對增強型防網路釣魚功能，您可以在監督的 iOS 裝置上部署自訂設定檔。</span><span class="sxs-lookup"><span data-stu-id="8004c-195">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="8004c-196">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8004c-196">Follow the steps below:</span></span>
    - <span data-ttu-id="8004c-197">從下載設定檔 [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="8004c-197">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="8004c-198">流覽至 **裝置**  ->  **iOS/iPadOS** 設定配置  ->  **檔**  ->  **建立設定檔**</span><span class="sxs-lookup"><span data-stu-id="8004c-198">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8004c-199">![Microsoft 端點管理員系統管理 Center7 的影像](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="8004c-199">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="8004c-200">提供設定檔的名稱。</span><span class="sxs-lookup"><span data-stu-id="8004c-200">Provide a name of the profile.</span></span> <span data-ttu-id="8004c-201">當系統提示您匯入設定設定檔檔案時，請選取上述下載的檔案。</span><span class="sxs-lookup"><span data-stu-id="8004c-201">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="8004c-202">在 [ **工作分派** ] 區段中，選取您要套用此設定檔的裝置群組。</span><span class="sxs-lookup"><span data-stu-id="8004c-202">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="8004c-203">最佳作法是將此套用至所有受管理的 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="8004c-203">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="8004c-204">按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="8004c-204">Click **Next**.</span></span>
    - <span data-ttu-id="8004c-205">當您完成時，請在 [ **複查 + 建立** ] 頁面上，選擇 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="8004c-205">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="8004c-206">新的設定檔會顯示在設定檔的清單中。</span><span class="sxs-lookup"><span data-stu-id="8004c-206">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8004c-207">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8004c-207">Next Steps</span></span>

[<span data-ttu-id="8004c-208">設定 iOS 功能上的端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="8004c-208">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
