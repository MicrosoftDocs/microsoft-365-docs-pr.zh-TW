---
title: 使用行動裝置管理工具上線 Windows 10 電腦
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 使用行動裝置管理工具，在裝置上部署設定套件，使其可架至服務。
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917989"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="57f68-103">使用行動裝置管理工具上線 Windows 10 電腦</span><span class="sxs-lookup"><span data-stu-id="57f68-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="57f68-104">適用於：</span><span class="sxs-lookup"><span data-stu-id="57f68-104">**Applies to:**</span></span>

- [<span data-ttu-id="57f68-105">Microsoft 365 端點資料遺失防護 (DLP) </span><span class="sxs-lookup"><span data-stu-id="57f68-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="57f68-106">您可以使用 [行動裝置管理] (MDM) 解決方案來設定裝置。</span><span class="sxs-lookup"><span data-stu-id="57f68-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="57f68-107">Microsoft 365 端點資料遺失防護可提供 OMA-URIs 來建立管理裝置的原則，以支援 MDMs。</span><span class="sxs-lookup"><span data-stu-id="57f68-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="57f68-108">開始之前</span><span class="sxs-lookup"><span data-stu-id="57f68-108">Before you begin</span></span>
<span data-ttu-id="57f68-109">如果您使用的是 Microsoft Intune，則必須已註冊裝置 MDM。</span><span class="sxs-lookup"><span data-stu-id="57f68-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="57f68-110">否則，將不會成功套用設定。</span><span class="sxs-lookup"><span data-stu-id="57f68-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="57f68-111">如需使用 Microsoft Intune 啟用 MDM 的詳細資訊，請參閱 [Device 註冊名 (Microsoft intune) ](/mem/intune/enrollment/device-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="57f68-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="57f68-112">使用 Microsoft Intune 的板載裝置</span><span class="sxs-lookup"><span data-stu-id="57f68-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="57f68-113">遵循 [Intune](/intune/advanced-threat-protection)中的指示。</span><span class="sxs-lookup"><span data-stu-id="57f68-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="57f68-114">**架裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。</span><span class="sxs-lookup"><span data-stu-id="57f68-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="57f68-115">使用行動裝置管理工具下架及監視裝置</span><span class="sxs-lookup"><span data-stu-id="57f68-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="57f68-116">基於安全性的考慮，用來下架裝置的套件會在下載之日期之後的30天后到期。</span><span class="sxs-lookup"><span data-stu-id="57f68-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="57f68-117">傳送給裝置的已到期的脫離套件會遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="57f68-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="57f68-118">下載脫離套件時，系統會通知您套件到期日，也會包含在套件名稱中。</span><span class="sxs-lookup"><span data-stu-id="57f68-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="57f68-119">上架和脫離的原則不得同時部署在相同的裝置上，否則會造成無法預期的衝突。</span><span class="sxs-lookup"><span data-stu-id="57f68-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="57f68-120">從 [Microsoft 規範中心](https://compliance.microsoft.com/)取得脫離套件。</span><span class="sxs-lookup"><span data-stu-id="57f68-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="57f68-121">在功能窗格中，選取 [**設定**  >  **裝置上架**  >  **脫離**]。</span><span class="sxs-lookup"><span data-stu-id="57f68-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="57f68-122">在 [ **部署方法** ] 欄位中，選取 [行動 **裝置管理/Microsoft Intune**]。</span><span class="sxs-lookup"><span data-stu-id="57f68-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="57f68-123">按一下 [ **下載套件**]，然後儲存 .zip 檔案。</span><span class="sxs-lookup"><span data-stu-id="57f68-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="57f68-124">將 .zip 檔案的內容解壓至共用的唯讀位置，該位置可供將要部署此套件的網路系統管理員存取。</span><span class="sxs-lookup"><span data-stu-id="57f68-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="57f68-125">您應該會有一個名為 *DeviceCompliance_valid_until_YYYY-MM 的* 檔案名。</span><span class="sxs-lookup"><span data-stu-id="57f68-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="57f68-126">使用 Microsoft Intune 自訂設定原則部署下列支援的 OMA URI 設定。</span><span class="sxs-lookup"><span data-stu-id="57f68-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="57f68-127">OMA URI：./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="57f68-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="57f68-128">Date type： String</span><span class="sxs-lookup"><span data-stu-id="57f68-128">Date type: String</span></span>      
      <span data-ttu-id="57f68-129">值： [從 DeviceCompliance_valid_until_YYYY-DD 映射檔的內容複寫並貼上值]</span><span class="sxs-lookup"><span data-stu-id="57f68-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="57f68-130">如需 Microsoft Intune 原則設定的詳細資訊，請參閱 [Microsoft intune 中的 Windows 10 原則設定](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="57f68-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="57f68-131">**Offboarded 裝置原則的健全狀況狀態** 會使用唯讀屬性，而且無法補救。</span><span class="sxs-lookup"><span data-stu-id="57f68-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57f68-132">脫離會導致裝置停止將感應器資料傳送至入口網站，但是來自裝置的資料（包括對它所做的任何警示參考）將保留最多6個月。</span><span class="sxs-lookup"><span data-stu-id="57f68-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57f68-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="57f68-133">Related topics</span></span>
- [<span data-ttu-id="57f68-134">使用群組原則的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="57f68-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="57f68-135">使用 Microsoft Endpoint Configuration Manager 的板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="57f68-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="57f68-136">使用本機指令碼上線 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="57f68-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="57f68-137">上線非持續 Virtual Desktop Infrastructure (VDI) 裝置</span><span class="sxs-lookup"><span data-stu-id="57f68-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="57f68-138">疑難排解 Microsoft Defender 高級威脅防護上架問題</span><span class="sxs-lookup"><span data-stu-id="57f68-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)