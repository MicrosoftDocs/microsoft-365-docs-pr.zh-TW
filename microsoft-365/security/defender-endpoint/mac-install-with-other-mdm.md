---
title: 使用不同的行動裝置管理來部署 (MDM) 系統（適用于 Mac 的 Microsoft Defender ATP）
description: 在其他管理解決方案上安裝適用于 Mac 的 Microsoft Defender ATP。
keywords: microsoft，defender，atp，mac，安裝，deploy，macos，catalina，mojave，high 塞拉里昂
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 28e57f1749ea9dce22e1a8a210f73cc3c7993738
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059683"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="fcd1e-104">使用不同的行動裝置管理來進行部署 (MDM) 系統（適用于 Mac 的 Microsoft Defender for Endpoint）</span><span class="sxs-lookup"><span data-stu-id="fcd1e-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fcd1e-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="fcd1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="fcd1e-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fcd1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="fcd1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fcd1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fcd1e-108">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="fcd1e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fcd1e-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="fcd1e-110">必要條件和系統需求</span><span class="sxs-lookup"><span data-stu-id="fcd1e-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="fcd1e-111">開始之前，請參閱 [《 Microsoft Defender For Mac 的主要端點」頁面](microsoft-defender-endpoint-mac.md) ，以取得目前軟體版本之必要條件和系統需求的描述。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-111">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="approach"></a><span data-ttu-id="fcd1e-112">方法</span><span class="sxs-lookup"><span data-stu-id="fcd1e-112">Approach</span></span>

> [!CAUTION]
> <span data-ttu-id="fcd1e-113">目前，Microsoft oficially 只支援 Intune 和 JAMF，以進行 Microsoft Defender for Mac 的部署和管理。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-113">Currently, Microsoft oficially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="fcd1e-114">Microsoft 對本所提供的資訊不提供任何明示或默示的保證。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="fcd1e-115">如果您的組織使用的行動裝置管理 (未正式支援的 MDM) 解決方案，這並不表示您無法為 Mac 部署或執行 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="fcd1e-116">適用于 Mac 的 Microsoft Defender 不取決於任何廠商特有的功能。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-116">Microsoft Defender for Endpoint for Mac does not depend on any vendor-specific features.</span></span> <span data-ttu-id="fcd1e-117">它可搭配任何支援下列功能的 MDM 解決方案使用：</span><span class="sxs-lookup"><span data-stu-id="fcd1e-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="fcd1e-118">將 pkg macOS 部署到受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="fcd1e-119">將 macOS 系統設定檔部署到受管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="fcd1e-120">在受管理的裝置上執行任何系統管理員設定的工具/腳本。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="fcd1e-121">大多數新式的 MDM 解決方案都包含這些功能，但它們可能會以不同的方式呼叫這些功能。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="fcd1e-122">您可以從前述清單的最後一個必要條件，部署 Defender，但不具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="fcd1e-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="fcd1e-123">您將無法以集中式方式收集狀態</span><span class="sxs-lookup"><span data-stu-id="fcd1e-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="fcd1e-124">如果您決定卸載 Defender，您必須以系統管理員身分登入用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="fcd1e-125">部署</span><span class="sxs-lookup"><span data-stu-id="fcd1e-125">Deployment</span></span>

<span data-ttu-id="fcd1e-126">大部分的 MDM 解決方案都使用相同的模型來管理 macOS 裝置，具有類似的術語。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="fcd1e-127">使用以 [JAMF 為基礎的部署](mac-install-with-jamf.md) 做為範本。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="fcd1e-128">套件</span><span class="sxs-lookup"><span data-stu-id="fcd1e-128">Package</span></span>

<span data-ttu-id="fcd1e-129">設定 [必要應用程式套件](mac-install-with-jamf.md)的部署，安裝套件 (wdav pkg) 從 [Microsoft Defender Security Center](mac-install-with-jamf.md)下載。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="fcd1e-130">若要將套件部署至您的企業，請使用 MDM 解決方案相關聯的指示。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="fcd1e-131">授權設定</span><span class="sxs-lookup"><span data-stu-id="fcd1e-131">License settings</span></span>

<span data-ttu-id="fcd1e-132">設定 [系統設定檔](mac-install-with-jamf.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> <span data-ttu-id="fcd1e-133">您的 MDM 解決方案可能會呼叫它像是「自訂設定設定檔」，因為 Mac 版端點的 Microsoft Defender 不是 macOS 的一部分。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint for Mac is not part of macOS.</span></span>

<span data-ttu-id="fcd1e-134">使用 [屬性] 清單中的 jamf/WindowsDefenderATPOnboarding plist，可從 [Microsoft Defender 安全中心](mac-install-with-jamf.md)下載的上架套件中解壓縮。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="fcd1e-135">您的系統可能支援 XML 格式的任意屬性清單。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="fcd1e-136">在該情況下，您可以上傳 jamf/WindowsDefenderATPOnboarding plist 檔案。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="fcd1e-137">或者，您可能需要先將屬性清單轉換成不同的格式。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="fcd1e-138">通常，您的自訂設定檔具有識別碼、name 或 domain 屬性。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="fcd1e-139">您必須嚴格使用此值的 "wdav"。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="fcd1e-140">MDM 使用它將設定檔案部署至用戶端裝置上的 **/Library/Managed 偏好設定 wdav** ，而 Defender 使用此檔案載入上架資訊。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="fcd1e-141">內核擴充原則</span><span class="sxs-lookup"><span data-stu-id="fcd1e-141">Kernel extension policy</span></span>

<span data-ttu-id="fcd1e-142">設定 KEXT 或內核擴充原則。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="fcd1e-143">使用小組識別碼 **UBF8T346G9** ，允許 Microsoft 提供的內核擴充。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="fcd1e-144">系統擴充原則</span><span class="sxs-lookup"><span data-stu-id="fcd1e-144">System extension policy</span></span>

<span data-ttu-id="fcd1e-145">設定系統擴充原則。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-145">Set up a system extension policy.</span></span> <span data-ttu-id="fcd1e-146">使用小組識別碼 **UBF8T346G9** 及核准下列的束識別碼：</span><span class="sxs-lookup"><span data-stu-id="fcd1e-146">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="fcd1e-147">wdav epsext</span><span class="sxs-lookup"><span data-stu-id="fcd1e-147">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="fcd1e-148">wdav netext</span><span class="sxs-lookup"><span data-stu-id="fcd1e-148">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="fcd1e-149">完整磁片存取原則</span><span class="sxs-lookup"><span data-stu-id="fcd1e-149">Full disk access policy</span></span>

<span data-ttu-id="fcd1e-150">授與下列元件的完整磁片存取權：</span><span class="sxs-lookup"><span data-stu-id="fcd1e-150">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="fcd1e-151">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fcd1e-151">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="fcd1e-152">識別碼： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-152">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="fcd1e-153">識別碼類型：束識別碼</span><span class="sxs-lookup"><span data-stu-id="fcd1e-153">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="fcd1e-154">程式碼需求： `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-154">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="fcd1e-155">Microsoft Defender for Endpoint 安全性擴充</span><span class="sxs-lookup"><span data-stu-id="fcd1e-155">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="fcd1e-156">識別碼： `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-156">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="fcd1e-157">識別碼類型：束識別碼</span><span class="sxs-lookup"><span data-stu-id="fcd1e-157">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="fcd1e-158">程式碼需求： `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-158">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="fcd1e-159">網路擴充原則</span><span class="sxs-lookup"><span data-stu-id="fcd1e-159">Network extension policy</span></span>

<span data-ttu-id="fcd1e-160">做為端點偵測和回應功能的一部分，Mac 版端點的 Microsoft Defender 會檢查通訊端流量，並將此資訊報告給 Microsoft Defender Security Center 入口網站。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-160">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="fcd1e-161">下列原則允許網路分機執行這項功能。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-161">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="fcd1e-162">篩選類型：外掛程式</span><span class="sxs-lookup"><span data-stu-id="fcd1e-162">Filter type: Plugin</span></span>
- <span data-ttu-id="fcd1e-163">外掛程式捆綁識別碼： `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-163">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="fcd1e-164">篩選資料提供者束識別碼： `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-164">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="fcd1e-165">篩選資料提供者指定的需求： `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-165">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="fcd1e-166">篩選通訊端： `true`</span><span class="sxs-lookup"><span data-stu-id="fcd1e-166">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="fcd1e-167">檢查安裝狀態</span><span class="sxs-lookup"><span data-stu-id="fcd1e-167">Check installation status</span></span>

<span data-ttu-id="fcd1e-168">在用戶端裝置上執行 [Microsoft Defender For Endpoint](mac-install-with-jamf.md) 以檢查上架狀態。</span><span class="sxs-lookup"><span data-stu-id="fcd1e-168">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>
