---
title: 非 Windows 平台版適用於端點的 Microsoft Defender
description: 瞭解適用于非 Windows 平臺的 Microsoft Defender for Endpoint 功能
keywords: 非 windows，mac，macos，linux，android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dc5710a73685c67eff17c0f281bd14e48707e60f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964785"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a><span data-ttu-id="f16cd-104">非 Windows 平台版適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f16cd-104">Microsoft Defender for Endpoint for non-Windows platforms</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f16cd-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f16cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="f16cd-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f16cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f16cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f16cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f16cd-108">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="f16cd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f16cd-109">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f16cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f16cd-110">Microsoft 已在 Windows 和 Windows Server 之外擴充其業界領先的端點安全性功能，以 macOS、Linux、Android 及不久 iOS。</span><span class="sxs-lookup"><span data-stu-id="f16cd-110">Microsoft has been on a journey to extend its industry leading endpoint security capabilities beyond Windows and Windows Server to macOS, Linux, Android, and soon iOS.</span></span>

<span data-ttu-id="f16cd-111">組織面臨不同平臺和裝置的威脅。</span><span class="sxs-lookup"><span data-stu-id="f16cd-111">Organizations face threats across a variety of platforms and devices.</span></span> <span data-ttu-id="f16cd-112">我們的小組致力於建立並非 microsoft *的* 安全性解決方案，但 *在* microsoft 也致力於讓客戶能夠保護和保護其異構環境。</span><span class="sxs-lookup"><span data-stu-id="f16cd-112">Our teams have committed to building security solutions not just *for* Microsoft, but also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span></span> <span data-ttu-id="f16cd-113">我們正在聆聽客戶的意見反應，並與我們的客戶密切合作，以建立符合其需求的解決方案。</span><span class="sxs-lookup"><span data-stu-id="f16cd-113">We're listening to customer feedback and partnering closely with our customers to build solutions that meet their needs.</span></span>

<span data-ttu-id="f16cd-114">透過 Microsoft Defender for Endpoint，客戶可以從 Microsoft Defender 資訊安全中心、跨 Windows 和非 Windows 平臺的所有威脅和警示統一的觀點中受益，讓他們能取得環境中發生什麼事的完整畫面，讓他們能夠更快速地評估及回應威脅。</span><span class="sxs-lookup"><span data-stu-id="f16cd-114">With Microsoft Defender for Endpoint, customers benefit from a unified view of all threats and alerts in the Microsoft Defender Security Center, across Windows and non-Windows platforms, enabling them to get a full picture of what's happening in their environment, which empowers them to more quickly assess and respond to threats.</span></span>

## <a name="microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="f16cd-115">macOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f16cd-115">Microsoft Defender for Endpoint on macOS</span></span> 

<span data-ttu-id="f16cd-116">macOS 的「Microsoft Defender for Endpoint」提供防毒軟體和端點偵測及回應 (三個最新發行版本本) 的 EDR macOS 功能。</span><span class="sxs-lookup"><span data-stu-id="f16cd-116">Microsoft Defender for Endpoint on macOS offers antivirus and endpoint detection and response (EDR) capabilities for the three latest released versions of macOS.</span></span> <span data-ttu-id="f16cd-117">客戶可以透過 Microsoft 端點管理員和 Jamf 來部署及管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="f16cd-117">Customers can deploy and manage the solution through Microsoft Endpoint Manager and Jamf.</span></span> <span data-ttu-id="f16cd-118">就像 macOS 上的 Microsoft Office 應用程式一樣，microsoft 自動更新是用來管理 Mac 更新上的 microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f16cd-118">Just like with Microsoft Office applications on macOS, Microsoft Auto Update is used to manage Microsoft Defender for Endpoint on Mac updates.</span></span> <span data-ttu-id="f16cd-119">如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)。</span><span class="sxs-lookup"><span data-stu-id="f16cd-119">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).</span></span>

<span data-ttu-id="f16cd-120">如需如何開始的詳細資訊，請造訪 macOS [檔](microsoft-defender-endpoint-mac.md)上的 Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f16cd-120">For more details on how to get started, visit the Defender for Endpoint on macOS [documentation](microsoft-defender-endpoint-mac.md).</span></span>

>[!NOTE]
><span data-ttu-id="f16cd-121">MacOS 端點上目前不支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="f16cd-121">The following capabilities are not currently supported on macOS endpoints:</span></span>
>- <span data-ttu-id="f16cd-122">資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="f16cd-122">Data loss prevention</span></span>
>- <span data-ttu-id="f16cd-123">即時回應</span><span class="sxs-lookup"><span data-stu-id="f16cd-123">Live response</span></span>
>- <span data-ttu-id="f16cd-124">SIEM</span><span class="sxs-lookup"><span data-stu-id="f16cd-124">SIEM</span></span>


## <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="f16cd-125">Linux 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f16cd-125">Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="f16cd-126">Linux 上的 Microsoft Defender for Endpoint 會為 Linux 伺服器提供預防性 (AV) 功能。</span><span class="sxs-lookup"><span data-stu-id="f16cd-126">Microsoft Defender for Endpoint on Linux offers preventative (AV) capabilities for Linux servers.</span></span> <span data-ttu-id="f16cd-127">這包括完整的命令列體驗，可供您設定及管理代理程式、起始掃描及管理威脅。</span><span class="sxs-lookup"><span data-stu-id="f16cd-127">This includes a full command line experience to configure and manage the agent, initiate scans, and manage threats.</span></span> <span data-ttu-id="f16cd-128">我們支援最常見的六個舊版 Linux 伺服器發行： RHEL 7.2 +、CentOS Linux 7.2 +、Ubuntu 16 LTS 或更高 LTS、SLES 12 +、Debian 9 + 及 Oracle Linux 7.2。</span><span class="sxs-lookup"><span data-stu-id="f16cd-128">We support recent versions of the six most common Linux Server distributions: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS, or higher LTS, SLES 12+, Debian 9+, and Oracle Linux 7.2.</span></span> <span data-ttu-id="f16cd-129">您可以使用 Puppet、Ansible 或使用現有的 Linux 設定管理工具，部署及設定 Linux 上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f16cd-129">Microsoft Defender for Endpoint on Linux can be deployed and configured using Puppet, Ansible, or using your existing Linux configuration management tool.</span></span> <span data-ttu-id="f16cd-130">如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)。</span><span class="sxs-lookup"><span data-stu-id="f16cd-130">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).</span></span>

<span data-ttu-id="f16cd-131">如需如何開始的詳細資訊，請流覽 Linux [檔](microsoft-defender-endpoint-linux.md)上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f16cd-131">For more details on how to get started, visit the Microsoft Defender for Endpoint on Linux [documentation](microsoft-defender-endpoint-linux.md).</span></span>

>[!NOTE]
><span data-ttu-id="f16cd-132">在 Linux 端點上目前不支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="f16cd-132">The following capabilities are not currently supported on Linux endpoints:</span></span>
>- <span data-ttu-id="f16cd-133">資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="f16cd-133">Data loss prevention</span></span>
>- <span data-ttu-id="f16cd-134">即時回應</span><span class="sxs-lookup"><span data-stu-id="f16cd-134">Live response</span></span>
>- <span data-ttu-id="f16cd-135">SIEM</span><span class="sxs-lookup"><span data-stu-id="f16cd-135">SIEM</span></span>



## <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="f16cd-136">Android 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f16cd-136">Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="f16cd-137">Android 上的 Microsoft Defender for Endpoint 是我們的行動威脅防護解決方案，適用于執行 Android 6.0 和更高版本的裝置。</span><span class="sxs-lookup"><span data-stu-id="f16cd-137">Microsoft Defender for Endpoint on Android is our mobile threat defense solution for devices running Android 6.0 and higher.</span></span> <span data-ttu-id="f16cd-138">同時支援 Android Enterprise (的工作設定檔) 和裝置管理員模式。</span><span class="sxs-lookup"><span data-stu-id="f16cd-138">Both Android Enterprise (Work Profile) and Device Administrator modes are supported.</span></span> <span data-ttu-id="f16cd-139">在 Android 上，我們提供 web 保護，包括反網路釣魚、封鎖不安全的連線，以及自訂指示器的設定。</span><span class="sxs-lookup"><span data-stu-id="f16cd-139">On Android, we offer web protection, which includes anti-phishing, blocking of unsafe connections, and setting of custom indicators.</span></span> <span data-ttu-id="f16cd-140">解決方案會將惡意程式碼和潛在有害的應用程式掃描 (PUA) ，並透過與 Microsoft 端點管理員和條件式存取的整合，提供額外的侵犯防護功能。</span><span class="sxs-lookup"><span data-stu-id="f16cd-140">The solution scans for malware and potentially unwanted applications (PUA) and offers additional breach prevention capabilities through integration with Microsoft Endpoint Manager and Conditional Access.</span></span> <span data-ttu-id="f16cd-141">如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)。</span><span class="sxs-lookup"><span data-stu-id="f16cd-141">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).</span></span>

<span data-ttu-id="f16cd-142">如需如何開始的詳細資訊，請流覽 Android [檔](microsoft-defender-endpoint-android.md)上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f16cd-142">For more details on how to get started, visit the Microsoft Defender for Endpoint on Android [documentation](microsoft-defender-endpoint-android.md).</span></span>

## <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="f16cd-143">iOS 上適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f16cd-143">Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="f16cd-144">IOS 的 Microsoft Defender for Endpoint 是我們的行動威脅防護解決方案，適用于執行 iOS 11.0 和更高版本的裝置。</span><span class="sxs-lookup"><span data-stu-id="f16cd-144">Microsoft Defender for Endpoint on iOS is our mobile threat defense solution for devices running iOS 11.0 and higher.</span></span> <span data-ttu-id="f16cd-145">支援受監視和 Unsupervised 裝置。</span><span class="sxs-lookup"><span data-stu-id="f16cd-145">Both Supervised and Unsupervised devices are supported.</span></span> <span data-ttu-id="f16cd-146">在 iOS 上，我們提供 web 保護，包括反網路釣魚、封鎖不安全的連線，以及設定自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="f16cd-146">On iOS, we offer web protection which includes anti-phishing, blocking unsafe connections, and setting custom indicators.</span></span> <span data-ttu-id="f16cd-147">如需重要功能和優點的詳細資訊，請閱讀我們的 [宣告](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。</span><span class="sxs-lookup"><span data-stu-id="f16cd-147">For more information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span> 

<span data-ttu-id="f16cd-148">如需如何開始的詳細資訊，請流覽 iOS [檔](microsoft-defender-endpoint-ios.md)上的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f16cd-148">For more details on how to get started, visit the Microsoft Defender for Endpoint on iOS [documentation](microsoft-defender-endpoint-ios.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="f16cd-149">授權需求</span><span class="sxs-lookup"><span data-stu-id="f16cd-149">Licensing requirements</span></span> 

<span data-ttu-id="f16cd-150">合格授權的使用者最多可在最多五個並行裝置上使用 Microsoft Defender 端點。</span><span class="sxs-lookup"><span data-stu-id="f16cd-150">Eligible Licensed Users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span> <span data-ttu-id="f16cd-151">Microsoft Defender for Endpoint 也可從雲端解決方案提供者 (CSP) 購買。</span><span class="sxs-lookup"><span data-stu-id="f16cd-151">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="f16cd-152">客戶可以透過獨立 microsoft defender for endpoint 授權，在 macOS 取得 microsoft defender for endpoint，也可以在 Microsoft 365 A5/E5 或 Microsoft 365 安全性] 中取得。</span><span class="sxs-lookup"><span data-stu-id="f16cd-152">Customers can obtain Microsoft Defender for Endpoint on macOS through a standalone Microsoft Defender for Endpoint license, as part of Microsoft 365 A5/E5, or Microsoft 365 Security.</span></span>

<span data-ttu-id="f16cd-153">在 Android 和 iOS 上的 Microsoft Defender for Endpoint 的最近宣告功能，包含在適用于合格授權使用者之五個合格裝置的一部分中。</span><span class="sxs-lookup"><span data-stu-id="f16cd-153">Recently announced capabilities of Microsoft Defender for Endpoint on Android and iOS are included in the above mentioned offers as part of the five qualified devices for eligible licensed users.</span></span>

<span data-ttu-id="f16cd-154">您可以透過適用于商業及教育版客戶的 Defender for Endpoint Server SKU，取得 Linux 上的 defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="f16cd-154">Defender for Endpoint on Linux is available through the Defender for Endpoint Server SKU that is available for both commercial and education customers.</span></span>

<span data-ttu-id="f16cd-155">如需定價及其他資格需求，請與您的帳戶小組或 CSP 聯繫。</span><span class="sxs-lookup"><span data-stu-id="f16cd-155">Please contact your account team or CSP for pricing and additional eligibility requirements.</span></span>
