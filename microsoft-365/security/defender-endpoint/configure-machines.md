---
title: 確定您的裝置設定正確
description: 適當設定裝置，以提升抵禦威脅的整體能力，並增強您偵測和回應攻擊的能力。
keywords: 板載，Intune management，MDATP，WDATP，Microsoft Defender，Windows Defender，高級威脅防護，攻擊面減少，ASR，安全性基準
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e7b00ceafc2761f42c316f434a27acf7c551e7cf
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163360"
---
# <a name="ensure-your-devices-are-configured-properly"></a><span data-ttu-id="20eb3-104">確定您的裝置設定正確</span><span class="sxs-lookup"><span data-stu-id="20eb3-104">Ensure your devices are configured properly</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="20eb3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="20eb3-105">**Applies to:**</span></span>
- [<span data-ttu-id="20eb3-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="20eb3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="20eb3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20eb3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="20eb3-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="20eb3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="20eb3-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="20eb3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="20eb3-110">透過適當設定的裝置，您可以提升抵禦威脅的整體能力，並增強您偵測和回應攻擊的能力。</span><span class="sxs-lookup"><span data-stu-id="20eb3-110">With properly configured devices, you can boost overall resilience against threats and enhance your capability to detect and respond to attacks.</span></span> <span data-ttu-id="20eb3-111">安全性設定管理可協助確保您的裝置：</span><span class="sxs-lookup"><span data-stu-id="20eb3-111">Security configuration management helps ensure that your devices:</span></span>

- <span data-ttu-id="20eb3-112">在 Microsoft Defender for Endpoint 上的板載</span><span class="sxs-lookup"><span data-stu-id="20eb3-112">Onboard to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="20eb3-113">符合或超過 Defender for Endpoint security 基準設定</span><span class="sxs-lookup"><span data-stu-id="20eb3-113">Meet or exceed the Defender for Endpoint security baseline configuration</span></span>
- <span data-ttu-id="20eb3-114">就地進行戰略性的攻擊面遷移</span><span class="sxs-lookup"><span data-stu-id="20eb3-114">Have strategic attack surface mitigations in place</span></span>

<span data-ttu-id="20eb3-115">按一下流覽功能表中的 [設定 **管理** ]，以開啟 [裝置設定管理] 頁面。</span><span class="sxs-lookup"><span data-stu-id="20eb3-115">Click **Configuration management** from the navigation menu to open the Device configuration management page.</span></span>

<span data-ttu-id="20eb3-116">![安全性設定管理頁面](images/secconmgmt_main.png)</span><span class="sxs-lookup"><span data-stu-id="20eb3-116">![Security configuration management page](images/secconmgmt_main.png)</span></span><br>
<span data-ttu-id="20eb3-117">*裝置設定管理頁面*</span><span class="sxs-lookup"><span data-stu-id="20eb3-117">*Device configuration management page*</span></span>

<span data-ttu-id="20eb3-118">您可以追蹤組織層級的設定狀態，並快速採取行動，以回應 Microsoft Intune 和 Microsoft 365 security center 上的裝置管理頁面直接連結，以回應不良的內架、法規遵從性問題和優化程度欠佳的攻擊面。</span><span class="sxs-lookup"><span data-stu-id="20eb3-118">You can track configuration status at an organizational level and quickly take action in response to poor onboarding coverage, compliance issues, and poorly optimized attack surface mitigations through direct, deep links to device management pages on Microsoft Intune and Microsoft 365 security center.</span></span>

<span data-ttu-id="20eb3-119">如此一來，您可以：</span><span class="sxs-lookup"><span data-stu-id="20eb3-119">In doing so, you benefit from:</span></span>
- <span data-ttu-id="20eb3-120">裝置上事件的完整可視性</span><span class="sxs-lookup"><span data-stu-id="20eb3-120">Comprehensive visibility of the events on your devices</span></span>
- <span data-ttu-id="20eb3-121">強大的威脅智慧及強大的裝置教學技術，用來處理原始事件及識別違規活動和威脅指示器</span><span class="sxs-lookup"><span data-stu-id="20eb3-121">Robust threat intelligence and powerful device learning technologies for processing raw events and identifying the breach activity and threat indicators</span></span>
- <span data-ttu-id="20eb3-122">設定為有效地停止安裝惡意 implants、劫持系統檔案與處理常式、資料 exfiltration 及其他威脅活動的完整安全功能堆疊</span><span class="sxs-lookup"><span data-stu-id="20eb3-122">A full stack of security features configured to efficiently stop the installation of malicious implants, hijacking of system files and process, data exfiltration, and other threat activities</span></span>
- <span data-ttu-id="20eb3-123">優化的攻擊面緩解，最大化對威脅活動的戰略性防護，同時將對生產力的影響降至最低</span><span class="sxs-lookup"><span data-stu-id="20eb3-123">Optimized attack surface mitigations, maximizing strategic defenses against threat activity while minimizing impact to productivity</span></span>

## <a name="enroll-devices-to-intune-management"></a><span data-ttu-id="20eb3-124">向 Intune 管理註冊裝置</span><span class="sxs-lookup"><span data-stu-id="20eb3-124">Enroll devices to Intune management</span></span>

<span data-ttu-id="20eb3-125">裝置設定管理與 Intune 裝置管理緊密合作，以建立組織中裝置的清查和基準安全性設定。</span><span class="sxs-lookup"><span data-stu-id="20eb3-125">Device configuration management works closely with Intune device management to establish the inventory of the devices in your organization and the baseline security configuration.</span></span> <span data-ttu-id="20eb3-126">您將能夠在 Intune 管理的 Windows 10 裝置上追蹤和管理設定問題。</span><span class="sxs-lookup"><span data-stu-id="20eb3-126">You will be able to track and manage configuration issues on Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="20eb3-127">在您可以確保您的裝置設定正確之前，請先將其註冊至 Intune management。</span><span class="sxs-lookup"><span data-stu-id="20eb3-127">Before you can ensure your devices are configured properly, enroll them to Intune management.</span></span> <span data-ttu-id="20eb3-128">Intune 註冊很強大，且有許多 Windows 10 裝置的註冊選項。</span><span class="sxs-lookup"><span data-stu-id="20eb3-128">Intune enrollment is robust and has several enrollment options for Windows 10 devices.</span></span> <span data-ttu-id="20eb3-129">如需 Intune 註冊選項的詳細資訊，請參閱 [設定 Windows 裝置的註冊](https://docs.microsoft.com/intune/windows-enroll)。</span><span class="sxs-lookup"><span data-stu-id="20eb3-129">For more information about Intune enrollment options, read about [setting up enrollment for Windows devices](https://docs.microsoft.com/intune/windows-enroll).</span></span>

>[!NOTE]
><span data-ttu-id="20eb3-130">若要將 Windows 裝置註冊至 Intune，系統管理員必須已獲指派授權。</span><span class="sxs-lookup"><span data-stu-id="20eb3-130">To enroll Windows devices to Intune, administrators must have already been assigned licenses.</span></span> <span data-ttu-id="20eb3-131">[閱讀指派裝置註冊的授權](https://docs.microsoft.com/intune/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="20eb3-131">[Read about assigning licenses for device enrollment](https://docs.microsoft.com/intune/licenses-assign).</span></span>

>[!TIP] 
><span data-ttu-id="20eb3-132">若要透過 Intune 優化裝置管理，請 [將 Intune 連線至 Defender For Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。</span><span class="sxs-lookup"><span data-stu-id="20eb3-132">To optimize device management through Intune, [connect Intune to Defender for Endpoint](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).</span></span>

## <a name="obtain-required-permissions"></a><span data-ttu-id="20eb3-133">取得必要的許可權</span><span class="sxs-lookup"><span data-stu-id="20eb3-133">Obtain required permissions</span></span>
<span data-ttu-id="20eb3-134">根據預設，只有已獲指派全域管理員的使用者或 Azure AD 上的 Intune 服務系統管理員角色，才能管理及指派上架裝置和部署安全性基準所需的裝置設定設定檔。</span><span class="sxs-lookup"><span data-stu-id="20eb3-134">By default, only users who have been assigned the Global Administrator or the Intune Service Administrator role on Azure AD can manage and assign the device configuration profiles needed for onboarding devices and deploying the security baseline.</span></span>

<span data-ttu-id="20eb3-135">如果您已被指派其他角色，請確定您具備必要的許可權：</span><span class="sxs-lookup"><span data-stu-id="20eb3-135">If you have been assigned other roles, ensure you have the necessary permissions:</span></span>

- <span data-ttu-id="20eb3-136">裝置設定的完整許可權</span><span class="sxs-lookup"><span data-stu-id="20eb3-136">Full permissions to device configurations</span></span>
- <span data-ttu-id="20eb3-137">安全性基準的完整許可權</span><span class="sxs-lookup"><span data-stu-id="20eb3-137">Full permissions to security baselines</span></span>
- <span data-ttu-id="20eb3-138">裝置合規性原則的讀取權限</span><span class="sxs-lookup"><span data-stu-id="20eb3-138">Read permissions to device compliance policies</span></span>
- <span data-ttu-id="20eb3-139">組織的讀取權限</span><span class="sxs-lookup"><span data-stu-id="20eb3-139">Read permissions to the organization</span></span>

<span data-ttu-id="20eb3-140">![Intune 上的必要許可權](images/secconmgmt_intune_permissions.png)</span><span class="sxs-lookup"><span data-stu-id="20eb3-140">![Required permissions on intune](images/secconmgmt_intune_permissions.png)</span></span><br>
<span data-ttu-id="20eb3-141">*Intune 上的裝置設定許可權*</span><span class="sxs-lookup"><span data-stu-id="20eb3-141">*Device configuration permissions on Intune*</span></span>

>[!TIP] 
><span data-ttu-id="20eb3-142">若要深入瞭解在 Intune 上指派許可權，請 [參閱建立自訂角色](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role)。</span><span class="sxs-lookup"><span data-stu-id="20eb3-142">To learn more about assigning permissions on Intune, [read about creating custom roles](https://docs.microsoft.com/intune/create-custom-role#to-create-a-custom-role).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="20eb3-143">本節內容</span><span class="sxs-lookup"><span data-stu-id="20eb3-143">In this section</span></span>
<span data-ttu-id="20eb3-144">主題</span><span class="sxs-lookup"><span data-stu-id="20eb3-144">Topic</span></span> | <span data-ttu-id="20eb3-145">描述</span><span class="sxs-lookup"><span data-stu-id="20eb3-145">Description</span></span>
:---|:---
[<span data-ttu-id="20eb3-146">取得架 to Defender for Endpoint 的裝置</span><span class="sxs-lookup"><span data-stu-id="20eb3-146">Get devices onboarded to Defender for Endpoint</span></span>](configure-machines-onboarding.md)| <span data-ttu-id="20eb3-147">透過 Intune 追蹤 Intune 管理裝置和板載以上裝置的內架狀態。</span><span class="sxs-lookup"><span data-stu-id="20eb3-147">Track onboarding status of Intune-managed devices and onboard more devices through Intune.</span></span> 
[<span data-ttu-id="20eb3-148">將合規性提升至 Endpoint security 基準的 Defender</span><span class="sxs-lookup"><span data-stu-id="20eb3-148">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md) | <span data-ttu-id="20eb3-149">追蹤基準相容性與不符合性。</span><span class="sxs-lookup"><span data-stu-id="20eb3-149">Track baseline compliance and noncompliance.</span></span> <span data-ttu-id="20eb3-150">將安全性基準部署到更多 Intune 管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="20eb3-150">Deploy the security baseline to more Intune-managed devices.</span></span>
[<span data-ttu-id="20eb3-151">優化 ASR 規則的部署和偵測</span><span class="sxs-lookup"><span data-stu-id="20eb3-151">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md) | <span data-ttu-id="20eb3-152">使用 Microsoft 365 security center 中的影響分析工具，檢查規則部署及調整偵測。</span><span class="sxs-lookup"><span data-stu-id="20eb3-152">Review rule deployment and tweak detections using impact analysis tools in Microsoft 365 security center.</span></span>

><span data-ttu-id="20eb3-153">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="20eb3-153">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="20eb3-154">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="20eb3-154">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)