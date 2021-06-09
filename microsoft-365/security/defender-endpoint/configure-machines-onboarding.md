---
title: 取得架至 Microsoft Defender for Endpoint 的裝置
description: 追蹤 Intune 管理裝置的上架至 Microsoft Defender for Endpoint，並增加上架速率。
keywords: 板載，Intune management，microsoft defender for Endpoint，microsoft defender，Windows Defender，設定管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7798f3b6bd2f99d48a8fa85ecf088023f4629b7b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841567"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="d4ae1-104">取得架至 Microsoft Defender for Endpoint 的裝置</span><span class="sxs-lookup"><span data-stu-id="d4ae1-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d4ae1-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d4ae1-105">**Applies to:**</span></span>
- [<span data-ttu-id="d4ae1-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d4ae1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d4ae1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4ae1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d4ae1-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d4ae1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d4ae1-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="d4ae1-110">每個架裝置會在您的網路中新增額外的端點偵測偵測和回應 (EDR) 感應器，並增加對侵犯活動的知名度。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="d4ae1-111">上架也可讓您檢查裝置是否有易受攻擊的元件，以及安全性設定問題，並可在攻擊期間接收重要的修復動作。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="d4ae1-112">在您可以追蹤和管理裝置的上架之前：</span><span class="sxs-lookup"><span data-stu-id="d4ae1-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="d4ae1-113">將裝置註冊到 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="d4ae1-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="d4ae1-114">確定您具備必要的許可權</span><span class="sxs-lookup"><span data-stu-id="d4ae1-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="d4ae1-115">探索並追蹤未受保護的裝置</span><span class="sxs-lookup"><span data-stu-id="d4ae1-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="d4ae1-116">在上架中，上 **架** 會將實際架到 Defender 的 Windows 10 裝置數目與 Intune 管理 Windows 10 裝置的總數進行比較，以提供您上架速度的高層次概述。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="d4ae1-117">![裝置設定管理上架卡](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="d4ae1-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="d4ae1-118">*顯示架裝置的卡片（與 Intune 管理的 Windows 10 裝置總數相比較）*</span><span class="sxs-lookup"><span data-stu-id="d4ae1-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="d4ae1-119">如果您使用的是 Security Center Configuration Manager、上架腳本，或是未使用 Intune 設定檔的其他上架方式，可能會發生資料差異。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="d4ae1-120">若要解決這些矛盾，請建立適用于 Defender 上架的相關 Intune 設定檔，並將該設定檔指派給您的裝置。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="d4ae1-121">具有 Intune 設定檔的板載以上裝置</span><span class="sxs-lookup"><span data-stu-id="d4ae1-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="d4ae1-122">Defender for Endpoint 為上[架 Windows 10 裝置](onboard-configure.md)提供數種便利的選項。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="d4ae1-123">不過，對於 Intune 受管理的裝置，您可以利用 Intune 設定檔輕鬆地部署 Defender for Endpoint 感應器以選取裝置，並將這些裝置有效地上架至服務。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="d4ae1-124">從上 **架** 卡上，選取 [上 **架更多裝置** ]，以在 Intune 上建立並指派設定檔。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="d4ae1-125">此連結會帶您前往 Intune 上的裝置合規性頁面，此頁面提供您上架狀態的類似綜述。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="d4ae1-126">![Intune 裝置管理上的 Microsoft Defender for Endpoint device 相容性頁面](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="d4ae1-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="d4ae1-127">*Intune 裝置管理上的 Microsoft Defender for Endpoint device 相容性頁面*</span><span class="sxs-lookup"><span data-stu-id="d4ae1-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="d4ae1-128">或者，您可以從 **所有服務 > Intune > 裝置合規性 > Microsoft Defender ATP**，流覽至 [Microsoft Azure 入口網站](https://portal.azure.com/)中的 [Defender for Endpoint 上架符合性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="d4ae1-129">如果您想要查看最新的裝置資料，請按一下 [ **不含 ATP 感應器的裝置清單**]。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="d4ae1-130">在 [裝置符合性] 頁面上，建立專用於部署 Defender for Endpoint 感應器的設定檔，並將該設定檔指派給您想要上架的裝置。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="d4ae1-131">若要這麼做，您可以執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="d4ae1-131">To do this, you can either:</span></span>

- <span data-ttu-id="d4ae1-132">選取 [ **建立裝置設定檔]，將 ATP 感應器設定** 為從預先定義的裝置設定檔開始設定。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="d4ae1-133">從頭開始建立裝置設定檔。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="d4ae1-134">如需詳細資訊，請 [參閱使用 Intune 裝置設定設定檔將「板載裝置」設定為使用 Defender For Endpoint](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="d4ae1-135">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="d4ae1-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d4ae1-136">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d4ae1-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="d4ae1-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="d4ae1-137">Related topics</span></span>
- [<span data-ttu-id="d4ae1-138">確保您的裝置已正確設定</span><span class="sxs-lookup"><span data-stu-id="d4ae1-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="d4ae1-139">將合規性提升至 Endpoint security 基準的 Defender</span><span class="sxs-lookup"><span data-stu-id="d4ae1-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="d4ae1-140">優化 ASR 規則的部署和偵測</span><span class="sxs-lookup"><span data-stu-id="d4ae1-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
