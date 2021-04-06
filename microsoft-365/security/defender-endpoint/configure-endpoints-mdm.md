---
title: 使用行動裝置管理工具上線 Windows 10 電腦
description: 使用行動裝置管理工具，在裝置上部署設定套件，使其可架至服務。
keywords: 使用 mdm 的板載裝置，裝置管理，板載 Windows ATP 裝置，板載 Microsoft Defender for Endpoint 裝置，mdm
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 85dd6b50280f54b9d39bbb134e466171fc6268ff
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166146"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="f526f-104">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="f526f-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f526f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f526f-105">**Applies to:**</span></span>
- [<span data-ttu-id="f526f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f526f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f526f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f526f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f526f-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f526f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f526f-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f526f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="f526f-110">您可以使用 [行動裝置管理] (MDM) 解決方案來設定裝置。</span><span class="sxs-lookup"><span data-stu-id="f526f-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="f526f-111">Endpoint for Endpoint 支援 MDMs，方法是提供建立原則來管理裝置的 OMA-URIs。</span><span class="sxs-lookup"><span data-stu-id="f526f-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="f526f-112">如需使用 Defender for Endpoint CSP 的詳細資訊，請參閱 [WINDOWSADVANCEDTHREATPROTECTION CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)檔案。</span><span class="sxs-lookup"><span data-stu-id="f526f-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f526f-113">開始之前</span><span class="sxs-lookup"><span data-stu-id="f526f-113">Before you begin</span></span>
<span data-ttu-id="f526f-114">如果您使用的是 Microsoft Intune，則必須已註冊裝置 MDM。</span><span class="sxs-lookup"><span data-stu-id="f526f-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="f526f-115">否則，將不會成功套用設定。</span><span class="sxs-lookup"><span data-stu-id="f526f-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="f526f-116">如需使用 Microsoft Intune 啟用 MDM 的詳細資訊，請參閱 [Device 註冊名 (Microsoft intune) ](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="f526f-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="f526f-117">使用 Microsoft Intune 的板載裝置</span><span class="sxs-lookup"><span data-stu-id="f526f-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="f526f-118">[![顯示使用 Microsoft Intune ](images/onboard-intune.png) 之 Endpoint To Defender 上架裝置的 PDF 影像 ](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f526f-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="f526f-119">請取出 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  或  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Defender for Endpoint 的各種路徑。</span><span class="sxs-lookup"><span data-stu-id="f526f-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="f526f-120">遵循 [Intune](https://docs.microsoft.com/intune/advanced-threat-protection)中的指示。</span><span class="sxs-lookup"><span data-stu-id="f526f-120">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="f526f-121">如需使用 Defender for Endpoint CSP 的詳細資訊，請參閱 [WINDOWSADVANCEDTHREATPROTECTION CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 和 [WindowsAdvancedThreatProtection DDF](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)檔案。</span><span class="sxs-lookup"><span data-stu-id="f526f-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="f526f-122">**架裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。</span><span class="sxs-lookup"><span data-stu-id="f526f-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="f526f-123">設定診斷資料包告頻率只適用于 Windows 10，版本1703上的裝置。</span><span class="sxs-lookup"><span data-stu-id="f526f-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="f526f-124">在裝置上架後，您可以選擇執行偵測測試，以確認裝置已正確架至服務。</span><span class="sxs-lookup"><span data-stu-id="f526f-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="f526f-125">如需詳細資訊，請參閱 [在新架的 Microsoft Defender For Endpoint 裝置上執行偵測測試](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="f526f-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="f526f-126">請取出 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  或  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) ，以查看部署 Microsoft Defender ATP 中的各種路徑。</span><span class="sxs-lookup"><span data-stu-id="f526f-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender ATP.</span></span> 

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="f526f-127">使用行動裝置管理工具下架及監視裝置</span><span class="sxs-lookup"><span data-stu-id="f526f-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="f526f-128">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="f526f-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="f526f-129">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="f526f-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="f526f-130">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="f526f-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="f526f-131">上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。</span><span class="sxs-lookup"><span data-stu-id="f526f-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="f526f-132">從 [Microsoft Defender Security Center](https://securitycenter.windows.com/)取得脫離套件：</span><span class="sxs-lookup"><span data-stu-id="f526f-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="f526f-133">在功能窗格中，選取 [**設定**  >  **脫離**]。</span><span class="sxs-lookup"><span data-stu-id="f526f-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="f526f-134">選取 [Windows 10] 做為作業系統。</span><span class="sxs-lookup"><span data-stu-id="f526f-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="f526f-135">在 [ **部署方法** ] 欄位中，選取 [行動 **裝置管理/Microsoft Intune**]。</span><span class="sxs-lookup"><span data-stu-id="f526f-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="f526f-136">按一下 [ **下載套件**]，然後儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="f526f-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="f526f-137">將 .zip 檔案的內容解壓至共用的唯讀位置，該位置可供將要部署此套件的網路系統管理員存取。</span><span class="sxs-lookup"><span data-stu-id="f526f-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="f526f-138">您應該會有一個名為 *WindowsDefenderATP_valid_until_YYYY-MM 的* 檔案名。</span><span class="sxs-lookup"><span data-stu-id="f526f-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="f526f-139">使用 Microsoft Intune 自訂設定原則部署下列支援的 OMA URI 設定。</span><span class="sxs-lookup"><span data-stu-id="f526f-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="f526f-140">OMA URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="f526f-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="f526f-141">Date type： String</span><span class="sxs-lookup"><span data-stu-id="f526f-141">Date type: String</span></span><br/>
      <span data-ttu-id="f526f-142">值： [從 WindowsDefenderATP_valid_until_YYYY-DD 映射檔的內容複寫並貼上值]</span><span class="sxs-lookup"><span data-stu-id="f526f-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="f526f-143">如需 Microsoft Intune 原則設定的詳細資訊，請參閱 [Microsoft intune 中的 Windows 10 原則設定](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="f526f-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="f526f-144">**Offboarded 裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。</span><span class="sxs-lookup"><span data-stu-id="f526f-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f526f-145">脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。</span><span class="sxs-lookup"><span data-stu-id="f526f-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f526f-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="f526f-146">Related topics</span></span>
- [<span data-ttu-id="f526f-147">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="f526f-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="f526f-148">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="f526f-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="f526f-149">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="f526f-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="f526f-150">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="f526f-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="f526f-151">在新架的 Microsoft Defender for Endpoint 裝置上執行偵測測試</span><span class="sxs-lookup"><span data-stu-id="f526f-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="f526f-152">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="f526f-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)