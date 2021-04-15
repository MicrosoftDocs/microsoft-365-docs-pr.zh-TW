---
title: 適用于 Mac 的 Microsoft Defender ATP 隱私權
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及 Microsoft Defender ATP for Mac 中所收集的診斷資料的相關資訊。
keywords: microsoft、defender、atp、mac、隱私權、診斷
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
ms.openlocfilehash: bf837dca5f05310045c06178b8fc587f3fc55137
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765776"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="49524-104">macOS 上的 Microsoft Defender for Endpoint 隱私權</span><span class="sxs-lookup"><span data-stu-id="49524-104">Privacy for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="49524-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="49524-105">**Applies to:**</span></span>
- [<span data-ttu-id="49524-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="49524-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="49524-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49524-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="49524-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="49524-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="49524-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="49524-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="49524-110">Microsoft 致力於為您提供您所需的資訊和控制項，讓您選擇在 macOS 上使用 Microsoft Defender 做為端點時，如何收集和使用資料。</span><span class="sxs-lookup"><span data-stu-id="49524-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="49524-111">本主題說明產品內可用的隱私權控制，如何使用原則設定管理這些控制項，以及收集的資料事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="49524-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="49524-112">Microsoft Defender for Endpoint on macOS 的隱私權控制的概覽</span><span class="sxs-lookup"><span data-stu-id="49524-112">Overview of privacy controls in Microsoft Defender for Endpoint on macOS</span></span>

<span data-ttu-id="49524-113">本節說明 Microsoft Defender for Endpoint on macOS 所收集之不同資料類型的隱私權控制。</span><span class="sxs-lookup"><span data-stu-id="49524-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="49524-114">診斷資料</span><span class="sxs-lookup"><span data-stu-id="49524-114">Diagnostic data</span></span>

<span data-ttu-id="49524-115">診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="49524-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="49524-116">某些診斷資料為必要，而某些診斷資料為選用。</span><span class="sxs-lookup"><span data-stu-id="49524-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="49524-117">我們可讓您選擇要透過隱私權控制 (如組織的原則設定) 向我們傳送必要或選用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="49524-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="49524-118">Microsoft Defender for Endpoint client 軟體有兩個層級的診斷資料，可供您選擇：</span><span class="sxs-lookup"><span data-stu-id="49524-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="49524-119">**必要**：必要的資料，以協助保持 Microsoft Defender 在其上安裝的裝置上具有最新的端點安全、最新和執行。</span><span class="sxs-lookup"><span data-stu-id="49524-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="49524-120">**選用**：其他資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷和修正問題。</span><span class="sxs-lookup"><span data-stu-id="49524-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="49524-121">根據預設，只會將所需的診斷資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="49524-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="49524-122">雲端已傳送保護資料</span><span class="sxs-lookup"><span data-stu-id="49524-122">Cloud delivered protection data</span></span>

<span data-ttu-id="49524-123">雲端提供的保護功能可讓您在存取雲端中的最新保護資料時，提供更快且更快速的保護。</span><span class="sxs-lookup"><span data-stu-id="49524-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="49524-124">啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和網路上的惡意程式碼提供重要防護。</span><span class="sxs-lookup"><span data-stu-id="49524-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="49524-125">資料範例</span><span class="sxs-lookup"><span data-stu-id="49524-125">Sample data</span></span>

<span data-ttu-id="49524-126">範例資料是用來改善產品的保護功能，方法是傳送 Microsoft 可疑的範例，使其能夠進行分析。</span><span class="sxs-lookup"><span data-stu-id="49524-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="49524-127">啟用自動範例提交是選用的。</span><span class="sxs-lookup"><span data-stu-id="49524-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="49524-128">啟用此功能且收集的範例可能包含個人資訊時，系統會提示使用者同意。</span><span class="sxs-lookup"><span data-stu-id="49524-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="49524-129">使用原則設定管理隱私權控制項</span><span class="sxs-lookup"><span data-stu-id="49524-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="49524-130">如果您是 IT 管理員，您可能會想要在企業層級設定這些控制項。</span><span class="sxs-lookup"><span data-stu-id="49524-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="49524-131">在 [macOS 上的 Microsoft Defender For Endpoint 的 [設定偏好設定](mac-preferences.md)] 中，詳細說明上述各節所述各類資料的隱私權。</span><span class="sxs-lookup"><span data-stu-id="49524-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="49524-132">就像任何新的原則設定一樣，您應該在有限的受控環境中仔細測試這些設定，以確保您設定的設定在您的組織中更廣泛地實施原則設定之前具有適當的效果。</span><span class="sxs-lookup"><span data-stu-id="49524-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="49524-133">診斷資料事件</span><span class="sxs-lookup"><span data-stu-id="49524-133">Diagnostic data events</span></span>

<span data-ttu-id="49524-134">本節說明什麼是被視為必要的診斷資料，以及哪些專案會被視為選用的診斷資料，以及所收集的事件及欄位的描述。</span><span class="sxs-lookup"><span data-stu-id="49524-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="49524-135">所有事件通用的資料欄位</span><span class="sxs-lookup"><span data-stu-id="49524-135">Data fields that are common for all events</span></span>
<span data-ttu-id="49524-136">有一些事件的相關資訊是所有事件通用，而不論類別或資料子類型為何。</span><span class="sxs-lookup"><span data-stu-id="49524-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="49524-137">下欄欄位對於所有事件都是常見的：</span><span class="sxs-lookup"><span data-stu-id="49524-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="49524-138">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-138">Field</span></span>                   | <span data-ttu-id="49524-139">描述</span><span class="sxs-lookup"><span data-stu-id="49524-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="49524-140">平台</span><span class="sxs-lookup"><span data-stu-id="49524-140">platform</span></span>                | <span data-ttu-id="49524-141">應用程式執行所在平臺的廣泛分類。</span><span class="sxs-lookup"><span data-stu-id="49524-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="49524-142">可讓 Microsoft 識別可能發生問題的平臺，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="49524-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="49524-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="49524-143">machine_guid</span></span>            | <span data-ttu-id="49524-144">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="49524-145">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="49524-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="49524-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="49524-146">sense_guid</span></span>              | <span data-ttu-id="49524-147">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="49524-148">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="49524-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="49524-149">org_id</span><span class="sxs-lookup"><span data-stu-id="49524-149">org_id</span></span>                  | <span data-ttu-id="49524-150">與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="49524-151">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目。</span><span class="sxs-lookup"><span data-stu-id="49524-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="49524-152">主機 名</span><span class="sxs-lookup"><span data-stu-id="49524-152">hostname</span></span>                | <span data-ttu-id="49524-153">本機裝置名稱 (，但沒有 DNS 尾碼) 。</span><span class="sxs-lookup"><span data-stu-id="49524-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="49524-154">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="49524-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="49524-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="49524-155">product_guid</span></span>            | <span data-ttu-id="49524-156">產品的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-156">Unique identifier of the product.</span></span> <span data-ttu-id="49524-157">可讓 Microsoft 區分影響不同產品風格的問題。</span><span class="sxs-lookup"><span data-stu-id="49524-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="49524-158">app_version</span><span class="sxs-lookup"><span data-stu-id="49524-158">app_version</span></span>             | <span data-ttu-id="49524-159">MacOS 應用程式上的 Microsoft Defender for Endpoint 版本。</span><span class="sxs-lookup"><span data-stu-id="49524-159">Version of the Microsoft Defender for Endpoint on macOS application.</span></span> <span data-ttu-id="49524-160">可讓 Microsoft 找出顯示問題的產品版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="49524-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="49524-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="49524-161">sig_version</span></span>             | <span data-ttu-id="49524-162">安全性情報資料庫的版本。</span><span class="sxs-lookup"><span data-stu-id="49524-162">Version of security intelligence database.</span></span> <span data-ttu-id="49524-163">可讓 Microsoft 找出顯示問題的安全性情報版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="49524-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="49524-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="49524-164">supported_compressions</span></span>  | <span data-ttu-id="49524-165">例如，應用程式支援的壓縮演算法清單 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="49524-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="49524-166">可讓 Microsoft 瞭解哪些類型的 compressions 可以在與應用程式通訊時使用。</span><span class="sxs-lookup"><span data-stu-id="49524-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="49524-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="49524-167">release_ring</span></span>            | <span data-ttu-id="49524-168">裝置與 (相關聯的環，例如，內幕人士快、內幕人士緩慢、實際執行) 。</span><span class="sxs-lookup"><span data-stu-id="49524-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="49524-169">可讓 Microsoft 識別可能發生問題的發行環，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="49524-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="49524-170">必要診斷資料</span><span class="sxs-lookup"><span data-stu-id="49524-170">Required diagnostic data</span></span>

<span data-ttu-id="49524-171">必要的 **診斷資料** 是必要的最少資料，以協助保持 Microsoft Defender 在安裝所在裝置上的「端點安全」、「最新」和「如期」執行。</span><span class="sxs-lookup"><span data-stu-id="49524-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="49524-172">必要的診斷資料可協助識別可能與裝置或軟體設定有關的 Microsoft Defender 端點相關問題。</span><span class="sxs-lookup"><span data-stu-id="49524-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="49524-173">例如，它可協助判斷在特定作業系統版本、新引進的功能，或是停用某些 Microsoft Defender for Endpoint 功能時，Microsoft Defender for Endpoint 功能是否會頻繁地崩潰。</span><span class="sxs-lookup"><span data-stu-id="49524-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="49524-174">必要的診斷資料可協助 Microsoft 偵測、診斷及修正這些問題，以加快對使用者或組織的影響。</span><span class="sxs-lookup"><span data-stu-id="49524-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="49524-175">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="49524-175">Software setup and inventory data events</span></span>

<span data-ttu-id="49524-176">**Microsoft Defender for Endpoint 安裝/卸載**</span><span class="sxs-lookup"><span data-stu-id="49524-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="49524-177">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-177">The following fields are collected:</span></span>

| <span data-ttu-id="49524-178">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-178">Field</span></span>            | <span data-ttu-id="49524-179">描述</span><span class="sxs-lookup"><span data-stu-id="49524-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="49524-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="49524-180">correlation_id</span></span>   | <span data-ttu-id="49524-181">與安裝相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="49524-182">版本</span><span class="sxs-lookup"><span data-stu-id="49524-182">version</span></span>          | <span data-ttu-id="49524-183">套件的版本。</span><span class="sxs-lookup"><span data-stu-id="49524-183">Version of the package.</span></span> |
| <span data-ttu-id="49524-184">嚴重性</span><span class="sxs-lookup"><span data-stu-id="49524-184">severity</span></span>         | <span data-ttu-id="49524-185">郵件的嚴重性 (例如，) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="49524-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="49524-186">code</span><span class="sxs-lookup"><span data-stu-id="49524-186">code</span></span>             | <span data-ttu-id="49524-187">描述工序的程式碼。</span><span class="sxs-lookup"><span data-stu-id="49524-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="49524-188">文字</span><span class="sxs-lookup"><span data-stu-id="49524-188">text</span></span>             | <span data-ttu-id="49524-189">產品安裝相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="49524-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="49524-190">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="49524-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="49524-191">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-191">The following fields are collected:</span></span>

| <span data-ttu-id="49524-192">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-192">Field</span></span>                                               | <span data-ttu-id="49524-193">描述</span><span class="sxs-lookup"><span data-stu-id="49524-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="49524-194">antivirus_engine antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="49524-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="49524-195">是否已在裝置上啟用即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="49524-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="49524-196">antivirus_engine antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="49524-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="49524-197">是否已在裝置上啟用被動式模式。</span><span class="sxs-lookup"><span data-stu-id="49524-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="49524-198">cloud_service。 enabled</span><span class="sxs-lookup"><span data-stu-id="49524-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="49524-199">是否已在裝置上啟用雲端已傳送保護功能。</span><span class="sxs-lookup"><span data-stu-id="49524-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="49524-200">cloud_service。超時</span><span class="sxs-lookup"><span data-stu-id="49524-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="49524-201">當應用程式使用 Microsoft Defender for Endpoint cloud 進行通訊時超時。</span><span class="sxs-lookup"><span data-stu-id="49524-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="49524-202">cloud_service cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="49524-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="49524-203">產品傳送至雲端的連續心跳之間的間隔。</span><span class="sxs-lookup"><span data-stu-id="49524-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="49524-204">cloud_service cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="49524-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="49524-205">用於與雲端通訊的 URI。</span><span class="sxs-lookup"><span data-stu-id="49524-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="49524-206">cloud_service cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="49524-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="49524-207">裝置的診斷層級 (必要，選用) 。</span><span class="sxs-lookup"><span data-stu-id="49524-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="49524-208">cloud_service cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="49524-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="49524-209">是否已開啟自動範例提交。</span><span class="sxs-lookup"><span data-stu-id="49524-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="49524-210">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="49524-210">edr.early_preview</span></span>                                   | <span data-ttu-id="49524-211">裝置是否應執行「及早預覽」功能。</span><span class="sxs-lookup"><span data-stu-id="49524-211">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="49524-212">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="49524-212">edr.group_id</span></span>                                        | <span data-ttu-id="49524-213">偵測及回應元件所使用的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-213">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="49524-214">edr 標記</span><span class="sxs-lookup"><span data-stu-id="49524-214">edr.tags</span></span>                                            | <span data-ttu-id="49524-215">使用者定義的標記。</span><span class="sxs-lookup"><span data-stu-id="49524-215">User-defined tags.</span></span> |
| <span data-ttu-id="49524-216">功能。 \[選用功能名稱\]</span><span class="sxs-lookup"><span data-stu-id="49524-216">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="49524-217">預覽功能的清單，及其是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="49524-217">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="49524-218">產品和服務使用資料事件</span><span class="sxs-lookup"><span data-stu-id="49524-218">Product and service usage data events</span></span>

<span data-ttu-id="49524-219">**安全性智慧更新報告**</span><span class="sxs-lookup"><span data-stu-id="49524-219">**Security intelligence update report**</span></span>

<span data-ttu-id="49524-220">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-220">The following fields are collected:</span></span>

| <span data-ttu-id="49524-221">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-221">Field</span></span>            | <span data-ttu-id="49524-222">描述</span><span class="sxs-lookup"><span data-stu-id="49524-222">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="49524-223">from_version</span><span class="sxs-lookup"><span data-stu-id="49524-223">from_version</span></span>     | <span data-ttu-id="49524-224">原始安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="49524-224">Original security intelligence version.</span></span> |
| <span data-ttu-id="49524-225">to_version</span><span class="sxs-lookup"><span data-stu-id="49524-225">to_version</span></span>       | <span data-ttu-id="49524-226">新的安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="49524-226">New security intelligence version.</span></span> |
| <span data-ttu-id="49524-227">地位</span><span class="sxs-lookup"><span data-stu-id="49524-227">status</span></span>           | <span data-ttu-id="49524-228">表明成功或失敗之更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="49524-228">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="49524-229">using_proxy</span><span class="sxs-lookup"><span data-stu-id="49524-229">using_proxy</span></span>      | <span data-ttu-id="49524-230">是否已透過 proxy 進行更新。</span><span class="sxs-lookup"><span data-stu-id="49524-230">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="49524-231">錯誤</span><span class="sxs-lookup"><span data-stu-id="49524-231">error</span></span>            | <span data-ttu-id="49524-232">如果更新失敗，則為錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="49524-232">Error code if the update failed.</span></span> |
| <span data-ttu-id="49524-233">reason</span><span class="sxs-lookup"><span data-stu-id="49524-233">reason</span></span>           | <span data-ttu-id="49524-234">更新的歸檔時的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="49524-234">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="49524-235">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="49524-235">Product and service performance data events</span></span>

<span data-ttu-id="49524-236">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="49524-236">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="49524-237">在應用程式意外退出時，收集系統資訊和應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="49524-237">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="49524-238">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-238">The following fields are collected:</span></span>

| <span data-ttu-id="49524-239">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-239">Field</span></span>                          | <span data-ttu-id="49524-240">描述</span><span class="sxs-lookup"><span data-stu-id="49524-240">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="49524-241">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="49524-241">v1_crash_count</span></span>                 | <span data-ttu-id="49524-242">在用戶端電腦上，V1 引擎處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="49524-242">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="49524-243">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="49524-243">v2_crash_count</span></span>                 | <span data-ttu-id="49524-244">在用戶端電腦上，V2 引擎處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="49524-244">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="49524-245">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="49524-245">EDR_crash_count</span></span>                | <span data-ttu-id="49524-246">在用戶端電腦上，EDR 處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="49524-246">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="49524-247">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="49524-247">**Kernel extension statistics**</span></span>

<span data-ttu-id="49524-248">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-248">The following fields are collected:</span></span>

| <span data-ttu-id="49524-249">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-249">Field</span></span>            | <span data-ttu-id="49524-250">描述</span><span class="sxs-lookup"><span data-stu-id="49524-250">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="49524-251">版本</span><span class="sxs-lookup"><span data-stu-id="49524-251">version</span></span>          | <span data-ttu-id="49524-252">MacOS 上的 Microsoft Defender for Endpoint 版本。</span><span class="sxs-lookup"><span data-stu-id="49524-252">Version of Microsoft Defender for Endpoint on macOS.</span></span> |
| <span data-ttu-id="49524-253">instance_id</span><span class="sxs-lookup"><span data-stu-id="49524-253">instance_id</span></span>      | <span data-ttu-id="49524-254">在內核擴充啟動時產生的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-254">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="49524-255">trace_level</span><span class="sxs-lookup"><span data-stu-id="49524-255">trace_level</span></span>      | <span data-ttu-id="49524-256">內核擴充的追蹤層級。</span><span class="sxs-lookup"><span data-stu-id="49524-256">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="49524-257">子系統</span><span class="sxs-lookup"><span data-stu-id="49524-257">subsystem</span></span>        | <span data-ttu-id="49524-258">用於即時保護的底層子系統。</span><span class="sxs-lookup"><span data-stu-id="49524-258">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="49524-259">ipc。連接</span><span class="sxs-lookup"><span data-stu-id="49524-259">ipc.connects</span></span>     | <span data-ttu-id="49524-260">內核擴充所接收的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="49524-260">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="49524-261">ipc。拒絕</span><span class="sxs-lookup"><span data-stu-id="49524-261">ipc.rejects</span></span>      | <span data-ttu-id="49524-262">內核擴充所拒絕的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="49524-262">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="49524-263">ipc。已連線</span><span class="sxs-lookup"><span data-stu-id="49524-263">ipc.connected</span></span>    | <span data-ttu-id="49524-264">是否有任何作用中連接至內核分機。</span><span class="sxs-lookup"><span data-stu-id="49524-264">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="49524-265">支援資料</span><span class="sxs-lookup"><span data-stu-id="49524-265">Support data</span></span>

<span data-ttu-id="49524-266">**診斷記錄**</span><span class="sxs-lookup"><span data-stu-id="49524-266">**Diagnostic logs**</span></span>

<span data-ttu-id="49524-267">僅當使用者同意提交功能時，才會收集診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="49524-267">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="49524-268">下列檔案會收集為支援記錄檔的一部分：</span><span class="sxs-lookup"><span data-stu-id="49524-268">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="49524-269">*/Library/Logs/Microsoft/mdatp/* 下的所有檔案</span><span class="sxs-lookup"><span data-stu-id="49524-269">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="49524-270">*/Library/Application 支援/microsoft/Defender/* （由 microsoft Defender for Endpoint on macOS 所建立及使用）下的檔案子集</span><span class="sxs-lookup"><span data-stu-id="49524-270">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="49524-271">MacOS 上的 Microsoft Defender for Endpoint 所使用之 [ */Library/Managed 偏好* 設定] 底下的檔案子集</span><span class="sxs-lookup"><span data-stu-id="49524-271">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="49524-272">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="49524-272">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="49524-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="49524-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="49524-274">選擇性診斷資料</span><span class="sxs-lookup"><span data-stu-id="49524-274">Optional diagnostic data</span></span>

<span data-ttu-id="49524-275">**選用診斷資料** 是額外的資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷及修正問題。</span><span class="sxs-lookup"><span data-stu-id="49524-275">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="49524-276">如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="49524-276">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="49524-277">選用診斷資料的範例包括 Microsoft 收集有關產品設定 (的資料，例如，) 裝置上的排除專案數目，以及產品) 的元件效能 (匯總度量。</span><span class="sxs-lookup"><span data-stu-id="49524-277">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="49524-278">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="49524-278">Software setup and inventory data events</span></span>

<span data-ttu-id="49524-279">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="49524-279">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="49524-280">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-280">The following fields are collected:</span></span>

| <span data-ttu-id="49524-281">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-281">Field</span></span>                                              | <span data-ttu-id="49524-282">描述</span><span class="sxs-lookup"><span data-stu-id="49524-282">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="49524-283">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="49524-283">connection_retry_timeout</span></span>                           | <span data-ttu-id="49524-284">與雲端通訊時，連線重試超時。</span><span class="sxs-lookup"><span data-stu-id="49524-284">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="49524-285">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="49524-285">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="49524-286">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="49524-286">Size of the product cache.</span></span> |
| <span data-ttu-id="49524-287">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="49524-287">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="49524-288">每天上傳的崩潰記錄檔限制。</span><span class="sxs-lookup"><span data-stu-id="49524-288">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="49524-289">antivirus_engine。排除 [] .is_directory</span><span class="sxs-lookup"><span data-stu-id="49524-289">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="49524-290">掃描的排除是否為目錄。</span><span class="sxs-lookup"><span data-stu-id="49524-290">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="49524-291">antivirus_engine。排除 [] 路徑</span><span class="sxs-lookup"><span data-stu-id="49524-291">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="49524-292">排除在掃描之外的路徑。</span><span class="sxs-lookup"><span data-stu-id="49524-292">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="49524-293">antivirus_engine。排除 [] 副檔名</span><span class="sxs-lookup"><span data-stu-id="49524-293">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="49524-294">排除來自掃描的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="49524-294">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="49524-295">antivirus_engine。排除 []。名稱</span><span class="sxs-lookup"><span data-stu-id="49524-295">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="49524-296">排除在掃描之外的檔案名。</span><span class="sxs-lookup"><span data-stu-id="49524-296">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="49524-297">antivirus_engine antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="49524-297">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="49524-298">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="49524-298">Size of the product cache.</span></span> |
| <span data-ttu-id="49524-299">antivirus_engine antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="49524-299">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="49524-300">掃描時所用的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="49524-300">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="49524-301">antivirus_engine antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="49524-301">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="49524-302">在從隔離區還原的檔案之前，可再次偵測到超時。</span><span class="sxs-lookup"><span data-stu-id="49524-302">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="49524-303">filesystem_scanner filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="49524-303">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="49524-304">完整掃描目錄。</span><span class="sxs-lookup"><span data-stu-id="49524-304">Full scan directory.</span></span> |
| <span data-ttu-id="49524-305">filesystem_scanner filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="49524-305">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="49524-306">快速掃描中所用的目錄清單。</span><span class="sxs-lookup"><span data-stu-id="49524-306">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="49524-307">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="49524-307">edr.latency_mode</span></span>                                   | <span data-ttu-id="49524-308">偵測及回應元件所使用的延遲模式。</span><span class="sxs-lookup"><span data-stu-id="49524-308">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="49524-309">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="49524-309">edr.proxy_address</span></span>                                  | <span data-ttu-id="49524-310">偵測及回應元件所使用的 Proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="49524-310">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="49524-311">**Microsoft 自動更新設定**</span><span class="sxs-lookup"><span data-stu-id="49524-311">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="49524-312">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-312">The following fields are collected:</span></span>

| <span data-ttu-id="49524-313">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-313">Field</span></span>                       | <span data-ttu-id="49524-314">描述</span><span class="sxs-lookup"><span data-stu-id="49524-314">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="49524-315">how_to_check</span><span class="sxs-lookup"><span data-stu-id="49524-315">how_to_check</span></span>                | <span data-ttu-id="49524-316">會決定如何檢查產品更新 (例如，自動或手動) 。</span><span class="sxs-lookup"><span data-stu-id="49524-316">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="49524-317">channel_name</span><span class="sxs-lookup"><span data-stu-id="49524-317">channel_name</span></span>                | <span data-ttu-id="49524-318">更新與裝置相關聯的通道。</span><span class="sxs-lookup"><span data-stu-id="49524-318">Update channel associated with the device.</span></span> |
| <span data-ttu-id="49524-319">manifest_server</span><span class="sxs-lookup"><span data-stu-id="49524-319">manifest_server</span></span>             | <span data-ttu-id="49524-320">用於下載更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="49524-320">Server used for downloading updates.</span></span> |
| <span data-ttu-id="49524-321">update_cache</span><span class="sxs-lookup"><span data-stu-id="49524-321">update_cache</span></span>                | <span data-ttu-id="49524-322">用來儲存更新的快取位置。</span><span class="sxs-lookup"><span data-stu-id="49524-322">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="49524-323">產品和服務使用</span><span class="sxs-lookup"><span data-stu-id="49524-323">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="49524-324">已開始診斷記錄上載報告</span><span class="sxs-lookup"><span data-stu-id="49524-324">Diagnostic log upload started report</span></span>

<span data-ttu-id="49524-325">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-325">The following fields are collected:</span></span>

| <span data-ttu-id="49524-326">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-326">Field</span></span>            | <span data-ttu-id="49524-327">描述</span><span class="sxs-lookup"><span data-stu-id="49524-327">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="49524-328">sha256</span><span class="sxs-lookup"><span data-stu-id="49524-328">sha256</span></span>           | <span data-ttu-id="49524-329">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-329">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="49524-330">Size</span><span class="sxs-lookup"><span data-stu-id="49524-330">size</span></span>             | <span data-ttu-id="49524-331">支援記錄檔的大小。</span><span class="sxs-lookup"><span data-stu-id="49524-331">Size of the support log.</span></span> |
| <span data-ttu-id="49524-332">original_path</span><span class="sxs-lookup"><span data-stu-id="49524-332">original_path</span></span>    | <span data-ttu-id="49524-333">支援記錄檔的路徑 (always 低於 */Library/Application support/Microsoft/Defender/wdavdiag/*) 。</span><span class="sxs-lookup"><span data-stu-id="49524-333">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="49524-334">format</span><span class="sxs-lookup"><span data-stu-id="49524-334">format</span></span>           | <span data-ttu-id="49524-335">支援記錄檔的格式。</span><span class="sxs-lookup"><span data-stu-id="49524-335">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="49524-336">診斷記錄上載已完成報告</span><span class="sxs-lookup"><span data-stu-id="49524-336">Diagnostic log upload completed report</span></span>

<span data-ttu-id="49524-337">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-337">The following fields are collected:</span></span>

| <span data-ttu-id="49524-338">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-338">Field</span></span>            | <span data-ttu-id="49524-339">描述</span><span class="sxs-lookup"><span data-stu-id="49524-339">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="49524-340">request_id</span><span class="sxs-lookup"><span data-stu-id="49524-340">request_id</span></span>       | <span data-ttu-id="49524-341">支援記錄檔上載要求的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-341">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="49524-342">sha256</span><span class="sxs-lookup"><span data-stu-id="49524-342">sha256</span></span>           | <span data-ttu-id="49524-343">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="49524-343">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="49524-344">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="49524-344">blob_sas_uri</span></span>     | <span data-ttu-id="49524-345">應用程式用來上傳支援記錄的 URI。</span><span class="sxs-lookup"><span data-stu-id="49524-345">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="49524-346">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="49524-346">Product and service performance data events</span></span>

<span data-ttu-id="49524-347">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="49524-347">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="49524-348">非預期的應用程式結束，以及在該情況下應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="49524-348">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="49524-349">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="49524-349">**Kernel extension statistics**</span></span>

<span data-ttu-id="49524-350">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="49524-350">The following fields are collected:</span></span>

| <span data-ttu-id="49524-351">欄位</span><span class="sxs-lookup"><span data-stu-id="49524-351">Field</span></span>                          | <span data-ttu-id="49524-352">描述</span><span class="sxs-lookup"><span data-stu-id="49524-352">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="49524-353">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="49524-353">pkt_ack_timeout</span></span>                | <span data-ttu-id="49524-354">下列屬性是匯總數值，代表自內核延伸啟動之後發生的事件計數。</span><span class="sxs-lookup"><span data-stu-id="49524-354">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="49524-355">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="49524-355">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="49524-356">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="49524-356">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="49524-357">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="49524-357">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="49524-358">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="49524-358">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="49524-359">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="49524-359">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="49524-360">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="49524-360">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="49524-361">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="49524-361">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="49524-362">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="49524-362">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="49524-363">ipc ack。超時</span><span class="sxs-lookup"><span data-stu-id="49524-363">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="49524-364">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="49524-364">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="49524-365">ackd</span><span class="sxs-lookup"><span data-stu-id="49524-365">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="49524-366">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="49524-366">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="49524-367">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="49524-367">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="49524-368">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="49524-368">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="49524-369">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="49524-369">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="49524-370">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="49524-370">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="49524-371">vnode 讀取的 kauth</span><span class="sxs-lookup"><span data-stu-id="49524-371">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="49524-372">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="49524-372">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="49524-373">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="49524-373">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="49524-374">vnode kauth</span><span class="sxs-lookup"><span data-stu-id="49524-374">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="49524-375">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="49524-375">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="49524-376">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="49524-376">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="49524-377">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="49524-377">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="49524-378">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="49524-378">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="49524-379">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="49524-379">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="49524-380">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="49524-380">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="49524-381">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="49524-381">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="49524-382">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="49524-382">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="49524-383">vnode 建立 kauth</span><span class="sxs-lookup"><span data-stu-id="49524-383">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="49524-384">vnode 移動的 kauth</span><span class="sxs-lookup"><span data-stu-id="49524-384">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="49524-385">vnode 裝載 kauth</span><span class="sxs-lookup"><span data-stu-id="49524-385">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="49524-386">kauth 拒絕的 vnode</span><span class="sxs-lookup"><span data-stu-id="49524-386">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="49524-387">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="49524-387">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="49524-388">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="49524-388">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="49524-389">ipc.kauth.file_op 遮罩</span><span class="sxs-lookup"><span data-stu-id="49524-389">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="49524-390">ipc.kauth_file_op。開啟</span><span class="sxs-lookup"><span data-stu-id="49524-390">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="49524-391">ipc.kauth.file_op。關閉</span><span class="sxs-lookup"><span data-stu-id="49524-391">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="49524-392">ipc.kauth.file_op ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="49524-392">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="49524-393">ipc.kauth.file_op。移動</span><span class="sxs-lookup"><span data-stu-id="49524-393">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="49524-394">ipc.kauth.file_op。連結</span><span class="sxs-lookup"><span data-stu-id="49524-394">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="49524-395">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="49524-395">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="49524-396">ipc.kauth.file_op。移除</span><span class="sxs-lookup"><span data-stu-id="49524-396">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="49524-397">ipc.kauth.file_op。卸載</span><span class="sxs-lookup"><span data-stu-id="49524-397">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="49524-398">ipc.kauth.file_op 的派生</span><span class="sxs-lookup"><span data-stu-id="49524-398">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="49524-399">ipc.kauth.file_op。建立</span><span class="sxs-lookup"><span data-stu-id="49524-399">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="49524-400">資源</span><span class="sxs-lookup"><span data-stu-id="49524-400">Resources</span></span>

- [<span data-ttu-id="49524-401">Microsoft 中的隱私權</span><span class="sxs-lookup"><span data-stu-id="49524-401">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
