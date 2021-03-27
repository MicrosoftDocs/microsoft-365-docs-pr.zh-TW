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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1386809778edeb92521a8656e9ece78591a682a4
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382898"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="320f4-104">適用于 Mac 的 Microsoft Defender 端點隱私權</span><span class="sxs-lookup"><span data-stu-id="320f4-104">Privacy for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="320f4-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="320f4-105">**Applies to:**</span></span>
- [<span data-ttu-id="320f4-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="320f4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="320f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="320f4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="320f4-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="320f4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="320f4-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="320f4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="320f4-110">Microsoft 致力於為您提供您所需的資訊和控制，讓您選擇如何在使用 Microsoft Defender for Mac 時收集和使用資料。</span><span class="sxs-lookup"><span data-stu-id="320f4-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="320f4-111">本主題說明產品內可用的隱私權控制，如何使用原則設定管理這些控制項，以及收集的資料事件的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="320f4-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="320f4-112">適用于 Mac 的端點 Microsoft Defender 中的隱私權控制</span><span class="sxs-lookup"><span data-stu-id="320f4-112">Overview of privacy controls in Microsoft Defender for Endpoint for Mac</span></span>

<span data-ttu-id="320f4-113">本節說明 Microsoft Defender for Mac 所收集的不同資料類型的隱私權控制。</span><span class="sxs-lookup"><span data-stu-id="320f4-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="320f4-114">診斷資料</span><span class="sxs-lookup"><span data-stu-id="320f4-114">Diagnostic data</span></span>

<span data-ttu-id="320f4-115">診斷資料是用來保持 Microsoft Defender 的端點安全且最新、偵測、診斷與修正問題，也可讓產品改進。</span><span class="sxs-lookup"><span data-stu-id="320f4-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="320f4-116">某些診斷資料為必要，而某些診斷資料為選用。</span><span class="sxs-lookup"><span data-stu-id="320f4-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="320f4-117">我們可讓您選擇要透過隱私權控制 (如組織的原則設定) 向我們傳送必要或選用的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="320f4-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="320f4-118">Microsoft Defender for Endpoint client 軟體有兩個層級的診斷資料，可供您選擇：</span><span class="sxs-lookup"><span data-stu-id="320f4-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="320f4-119">**必要**：必要的資料，以協助保持 Microsoft Defender 在其上安裝的裝置上具有最新的端點安全、最新和執行。</span><span class="sxs-lookup"><span data-stu-id="320f4-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="320f4-120">**選用**：其他資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷和修正問題。</span><span class="sxs-lookup"><span data-stu-id="320f4-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="320f4-121">根據預設，只會將所需的診斷資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="320f4-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="320f4-122">雲端已傳送保護資料</span><span class="sxs-lookup"><span data-stu-id="320f4-122">Cloud delivered protection data</span></span>

<span data-ttu-id="320f4-123">雲端提供的保護功能可讓您在存取雲端中的最新保護資料時，提供更快且更快速的保護。</span><span class="sxs-lookup"><span data-stu-id="320f4-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="320f4-124">啟用雲端傳送保護服務是選用的選項，但是強烈建議您這麼做，因為它會針對您的端點和網路上的惡意程式碼提供重要防護。</span><span class="sxs-lookup"><span data-stu-id="320f4-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="320f4-125">資料範例</span><span class="sxs-lookup"><span data-stu-id="320f4-125">Sample data</span></span>

<span data-ttu-id="320f4-126">範例資料是用來改善產品的保護功能，方法是傳送 Microsoft 可疑的範例，使其能夠進行分析。</span><span class="sxs-lookup"><span data-stu-id="320f4-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="320f4-127">啟用自動範例提交是選用的。</span><span class="sxs-lookup"><span data-stu-id="320f4-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="320f4-128">啟用此功能且收集的範例可能包含個人資訊時，系統會提示使用者同意。</span><span class="sxs-lookup"><span data-stu-id="320f4-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="320f4-129">使用原則設定管理隱私權控制項</span><span class="sxs-lookup"><span data-stu-id="320f4-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="320f4-130">如果您是 IT 管理員，您可能會想要在企業層級設定這些控制項。</span><span class="sxs-lookup"><span data-stu-id="320f4-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="320f4-131">在 [Microsoft Defender For Mac 的「設定偏好設定](mac-preferences.md)」中，會詳細說明上述各節所述各類資料的隱私權控制。</span><span class="sxs-lookup"><span data-stu-id="320f4-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

<span data-ttu-id="320f4-132">就像任何新的原則設定一樣，您應該在有限的受控環境中仔細測試這些設定，以確保您設定的設定在您的組織中更廣泛地實施原則設定之前具有適當的效果。</span><span class="sxs-lookup"><span data-stu-id="320f4-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="320f4-133">診斷資料事件</span><span class="sxs-lookup"><span data-stu-id="320f4-133">Diagnostic data events</span></span>

<span data-ttu-id="320f4-134">本節說明什麼是被視為必要的診斷資料，以及哪些專案會被視為選用的診斷資料，以及所收集的事件及欄位的描述。</span><span class="sxs-lookup"><span data-stu-id="320f4-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="320f4-135">所有事件通用的資料欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-135">Data fields that are common for all events</span></span>
<span data-ttu-id="320f4-136">有一些事件的相關資訊是所有事件通用，而不論類別或資料子類型為何。</span><span class="sxs-lookup"><span data-stu-id="320f4-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="320f4-137">下欄欄位對於所有事件都是常見的：</span><span class="sxs-lookup"><span data-stu-id="320f4-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="320f4-138">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-138">Field</span></span>                   | <span data-ttu-id="320f4-139">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="320f4-140">平台</span><span class="sxs-lookup"><span data-stu-id="320f4-140">platform</span></span>                | <span data-ttu-id="320f4-141">應用程式執行所在平臺的廣泛分類。</span><span class="sxs-lookup"><span data-stu-id="320f4-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="320f4-142">可讓 Microsoft 識別可能發生問題的平臺，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="320f4-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="320f4-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="320f4-143">machine_guid</span></span>            | <span data-ttu-id="320f4-144">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="320f4-145">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="320f4-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="320f4-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="320f4-146">sense_guid</span></span>              | <span data-ttu-id="320f4-147">與裝置相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="320f4-148">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="320f4-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="320f4-149">org_id</span><span class="sxs-lookup"><span data-stu-id="320f4-149">org_id</span></span>                  | <span data-ttu-id="320f4-150">與裝置所屬之企業相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="320f4-151">可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目。</span><span class="sxs-lookup"><span data-stu-id="320f4-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="320f4-152">主機 名</span><span class="sxs-lookup"><span data-stu-id="320f4-152">hostname</span></span>                | <span data-ttu-id="320f4-153">本機裝置名稱 (，但沒有 DNS 尾碼) 。</span><span class="sxs-lookup"><span data-stu-id="320f4-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="320f4-154">可讓 Microsoft 識別問題是否會影響一組選取的安裝，以及受到影響的使用者人數。</span><span class="sxs-lookup"><span data-stu-id="320f4-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="320f4-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="320f4-155">product_guid</span></span>            | <span data-ttu-id="320f4-156">產品的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-156">Unique identifier of the product.</span></span> <span data-ttu-id="320f4-157">可讓 Microsoft 區分影響不同產品風格的問題。</span><span class="sxs-lookup"><span data-stu-id="320f4-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="320f4-158">app_version</span><span class="sxs-lookup"><span data-stu-id="320f4-158">app_version</span></span>             | <span data-ttu-id="320f4-159">Mac 應用程式的 Microsoft Defender 端點版本。</span><span class="sxs-lookup"><span data-stu-id="320f4-159">Version of the Microsoft Defender for Endpoint for Mac application.</span></span> <span data-ttu-id="320f4-160">可讓 Microsoft 找出顯示問題的產品版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="320f4-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="320f4-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="320f4-161">sig_version</span></span>             | <span data-ttu-id="320f4-162">安全性情報資料庫的版本。</span><span class="sxs-lookup"><span data-stu-id="320f4-162">Version of security intelligence database.</span></span> <span data-ttu-id="320f4-163">可讓 Microsoft 找出顯示問題的安全性情報版本，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="320f4-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="320f4-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="320f4-164">supported_compressions</span></span>  | <span data-ttu-id="320f4-165">例如，應用程式支援的壓縮演算法清單 `['gzip']` 。</span><span class="sxs-lookup"><span data-stu-id="320f4-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="320f4-166">可讓 Microsoft 瞭解哪些類型的 compressions 可以在與應用程式通訊時使用。</span><span class="sxs-lookup"><span data-stu-id="320f4-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="320f4-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="320f4-167">release_ring</span></span>            | <span data-ttu-id="320f4-168">裝置與 (相關聯的環，例如，內幕人士快、內幕人士緩慢、實際執行) 。</span><span class="sxs-lookup"><span data-stu-id="320f4-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="320f4-169">可讓 Microsoft 識別可能發生問題的發行環，使其可正確地設定優先順序。</span><span class="sxs-lookup"><span data-stu-id="320f4-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="320f4-170">必要診斷資料</span><span class="sxs-lookup"><span data-stu-id="320f4-170">Required diagnostic data</span></span>

<span data-ttu-id="320f4-171">必要的 **診斷資料** 是必要的最少資料，以協助保持 Microsoft Defender 在安裝所在裝置上的「端點安全」、「最新」和「如期」執行。</span><span class="sxs-lookup"><span data-stu-id="320f4-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="320f4-172">必要的診斷資料可協助識別可能與裝置或軟體設定有關的 Microsoft Defender 端點相關問題。</span><span class="sxs-lookup"><span data-stu-id="320f4-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="320f4-173">例如，它可協助判斷在特定作業系統版本、新引進的功能，或是停用某些 Microsoft Defender for Endpoint 功能時，Microsoft Defender for Endpoint 功能是否會頻繁地崩潰。</span><span class="sxs-lookup"><span data-stu-id="320f4-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="320f4-174">必要的診斷資料可協助 Microsoft 偵測、診斷及修正這些問題，以加快對使用者或組織的影響。</span><span class="sxs-lookup"><span data-stu-id="320f4-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="320f4-175">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="320f4-175">Software setup and inventory data events</span></span>

<span data-ttu-id="320f4-176">**Microsoft Defender for Endpoint 安裝/卸載**</span><span class="sxs-lookup"><span data-stu-id="320f4-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="320f4-177">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-177">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-178">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-178">Field</span></span>            | <span data-ttu-id="320f4-179">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="320f4-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="320f4-180">correlation_id</span></span>   | <span data-ttu-id="320f4-181">與安裝相關聯的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="320f4-182">版本</span><span class="sxs-lookup"><span data-stu-id="320f4-182">version</span></span>          | <span data-ttu-id="320f4-183">套件的版本。</span><span class="sxs-lookup"><span data-stu-id="320f4-183">Version of the package.</span></span> |
| <span data-ttu-id="320f4-184">嚴重性</span><span class="sxs-lookup"><span data-stu-id="320f4-184">severity</span></span>         | <span data-ttu-id="320f4-185">郵件的嚴重性 (例如，) 的資訊。</span><span class="sxs-lookup"><span data-stu-id="320f4-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="320f4-186">code</span><span class="sxs-lookup"><span data-stu-id="320f4-186">code</span></span>             | <span data-ttu-id="320f4-187">描述工序的程式碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="320f4-188">文字</span><span class="sxs-lookup"><span data-stu-id="320f4-188">text</span></span>             | <span data-ttu-id="320f4-189">產品安裝相關的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="320f4-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="320f4-190">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="320f4-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="320f4-191">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-191">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-192">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-192">Field</span></span>                                               | <span data-ttu-id="320f4-193">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="320f4-194">antivirus_engine antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="320f4-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="320f4-195">是否已在裝置上啟用即時保護功能。</span><span class="sxs-lookup"><span data-stu-id="320f4-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="320f4-196">antivirus_engine antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="320f4-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="320f4-197">是否已在裝置上啟用被動式模式。</span><span class="sxs-lookup"><span data-stu-id="320f4-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="320f4-198">cloud_service。 enabled</span><span class="sxs-lookup"><span data-stu-id="320f4-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="320f4-199">是否已在裝置上啟用雲端已傳送保護功能。</span><span class="sxs-lookup"><span data-stu-id="320f4-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="320f4-200">cloud_service。超時</span><span class="sxs-lookup"><span data-stu-id="320f4-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="320f4-201">當應用程式使用 Microsoft Defender for Endpoint cloud 進行通訊時超時。</span><span class="sxs-lookup"><span data-stu-id="320f4-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="320f4-202">cloud_service cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="320f4-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="320f4-203">產品傳送至雲端的連續心跳之間的間隔。</span><span class="sxs-lookup"><span data-stu-id="320f4-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="320f4-204">cloud_service cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="320f4-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="320f4-205">用於與雲端通訊的 URI。</span><span class="sxs-lookup"><span data-stu-id="320f4-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="320f4-206">cloud_service cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="320f4-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="320f4-207">裝置的診斷層級 (必要，選用) 。</span><span class="sxs-lookup"><span data-stu-id="320f4-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="320f4-208">cloud_service cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="320f4-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="320f4-209">是否已開啟自動範例提交。</span><span class="sxs-lookup"><span data-stu-id="320f4-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="320f4-210">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="320f4-210">edr.early_preview</span></span>                                   | <span data-ttu-id="320f4-211">裝置是否應執行「及早預覽」功能。</span><span class="sxs-lookup"><span data-stu-id="320f4-211">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="320f4-212">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="320f4-212">edr.group_id</span></span>                                        | <span data-ttu-id="320f4-213">偵測及回應元件所使用的群組識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-213">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="320f4-214">edr 標記</span><span class="sxs-lookup"><span data-stu-id="320f4-214">edr.tags</span></span>                                            | <span data-ttu-id="320f4-215">使用者定義的標記。</span><span class="sxs-lookup"><span data-stu-id="320f4-215">User-defined tags.</span></span> |
| <span data-ttu-id="320f4-216">功能。 \[選用功能名稱\]</span><span class="sxs-lookup"><span data-stu-id="320f4-216">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="320f4-217">預覽功能的清單，及其是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="320f4-217">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="320f4-218">產品和服務使用資料事件</span><span class="sxs-lookup"><span data-stu-id="320f4-218">Product and service usage data events</span></span>

<span data-ttu-id="320f4-219">**安全性智慧更新報告**</span><span class="sxs-lookup"><span data-stu-id="320f4-219">**Security intelligence update report**</span></span>

<span data-ttu-id="320f4-220">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-220">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-221">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-221">Field</span></span>            | <span data-ttu-id="320f4-222">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-222">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="320f4-223">from_version</span><span class="sxs-lookup"><span data-stu-id="320f4-223">from_version</span></span>     | <span data-ttu-id="320f4-224">原始安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="320f4-224">Original security intelligence version.</span></span> |
| <span data-ttu-id="320f4-225">to_version</span><span class="sxs-lookup"><span data-stu-id="320f4-225">to_version</span></span>       | <span data-ttu-id="320f4-226">新的安全性智慧版本。</span><span class="sxs-lookup"><span data-stu-id="320f4-226">New security intelligence version.</span></span> |
| <span data-ttu-id="320f4-227">地位</span><span class="sxs-lookup"><span data-stu-id="320f4-227">status</span></span>           | <span data-ttu-id="320f4-228">表明成功或失敗之更新的狀態。</span><span class="sxs-lookup"><span data-stu-id="320f4-228">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="320f4-229">using_proxy</span><span class="sxs-lookup"><span data-stu-id="320f4-229">using_proxy</span></span>      | <span data-ttu-id="320f4-230">是否已透過 proxy 進行更新。</span><span class="sxs-lookup"><span data-stu-id="320f4-230">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="320f4-231">錯誤</span><span class="sxs-lookup"><span data-stu-id="320f4-231">error</span></span>            | <span data-ttu-id="320f4-232">如果更新失敗，則為錯誤碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-232">Error code if the update failed.</span></span> |
| <span data-ttu-id="320f4-233">reason</span><span class="sxs-lookup"><span data-stu-id="320f4-233">reason</span></span>           | <span data-ttu-id="320f4-234">更新的歸檔時的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="320f4-234">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="320f4-235">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="320f4-235">Product and service performance data events</span></span>

<span data-ttu-id="320f4-236">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="320f4-236">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="320f4-237">在應用程式意外退出時，收集系統資訊和應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="320f4-237">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="320f4-238">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-238">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-239">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-239">Field</span></span>                          | <span data-ttu-id="320f4-240">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-240">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="320f4-241">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="320f4-241">v1_crash_count</span></span>                 | <span data-ttu-id="320f4-242">在用戶端電腦上，V1 引擎處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="320f4-242">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="320f4-243">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="320f4-243">v2_crash_count</span></span>                 | <span data-ttu-id="320f4-244">在用戶端電腦上，V2 引擎處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="320f4-244">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="320f4-245">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="320f4-245">EDR_crash_count</span></span>                | <span data-ttu-id="320f4-246">在用戶端電腦上，EDR 處理常式每小時崩潰的次數</span><span class="sxs-lookup"><span data-stu-id="320f4-246">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="320f4-247">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="320f4-247">**Kernel extension statistics**</span></span>

<span data-ttu-id="320f4-248">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-248">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-249">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-249">Field</span></span>            | <span data-ttu-id="320f4-250">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-250">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="320f4-251">版本</span><span class="sxs-lookup"><span data-stu-id="320f4-251">version</span></span>          | <span data-ttu-id="320f4-252">Mac 版的 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="320f4-252">Version of Microsoft Defender for Endpoint for Mac.</span></span> |
| <span data-ttu-id="320f4-253">instance_id</span><span class="sxs-lookup"><span data-stu-id="320f4-253">instance_id</span></span>      | <span data-ttu-id="320f4-254">在內核擴充啟動時產生的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-254">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="320f4-255">trace_level</span><span class="sxs-lookup"><span data-stu-id="320f4-255">trace_level</span></span>      | <span data-ttu-id="320f4-256">內核擴充的追蹤層級。</span><span class="sxs-lookup"><span data-stu-id="320f4-256">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="320f4-257">子系統</span><span class="sxs-lookup"><span data-stu-id="320f4-257">subsystem</span></span>        | <span data-ttu-id="320f4-258">用於即時保護的底層子系統。</span><span class="sxs-lookup"><span data-stu-id="320f4-258">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="320f4-259">ipc。連接</span><span class="sxs-lookup"><span data-stu-id="320f4-259">ipc.connects</span></span>     | <span data-ttu-id="320f4-260">內核擴充所接收的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="320f4-260">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="320f4-261">ipc。拒絕</span><span class="sxs-lookup"><span data-stu-id="320f4-261">ipc.rejects</span></span>      | <span data-ttu-id="320f4-262">內核擴充所拒絕的連線要求數目。</span><span class="sxs-lookup"><span data-stu-id="320f4-262">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="320f4-263">ipc。已連線</span><span class="sxs-lookup"><span data-stu-id="320f4-263">ipc.connected</span></span>    | <span data-ttu-id="320f4-264">是否有任何作用中連接至內核分機。</span><span class="sxs-lookup"><span data-stu-id="320f4-264">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="320f4-265">支援資料</span><span class="sxs-lookup"><span data-stu-id="320f4-265">Support data</span></span>

<span data-ttu-id="320f4-266">**診斷記錄**</span><span class="sxs-lookup"><span data-stu-id="320f4-266">**Diagnostic logs**</span></span>

<span data-ttu-id="320f4-267">僅當使用者同意提交功能時，才會收集診斷記錄。</span><span class="sxs-lookup"><span data-stu-id="320f4-267">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="320f4-268">下列檔案會收集為支援記錄檔的一部分：</span><span class="sxs-lookup"><span data-stu-id="320f4-268">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="320f4-269">*/Library/Logs/Microsoft/mdatp/* 下的所有檔案</span><span class="sxs-lookup"><span data-stu-id="320f4-269">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="320f4-270">Microsoft Defender for Mac 所建立及使用之 */Library/Application 支援/Microsoft/Defender/* 所用的檔子集</span><span class="sxs-lookup"><span data-stu-id="320f4-270">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="320f4-271">Microsoft Defender for Mac 所使用之 */Library/Managed 偏好* 設定下的檔案子集</span><span class="sxs-lookup"><span data-stu-id="320f4-271">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="320f4-272">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="320f4-272">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="320f4-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="320f4-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="320f4-274">選擇性診斷資料</span><span class="sxs-lookup"><span data-stu-id="320f4-274">Optional diagnostic data</span></span>

<span data-ttu-id="320f4-275">**選用診斷資料** 是額外的資料，可協助 Microsoft 進行產品改進，並提供增強的資訊，以協助偵測、診斷及修正問題。</span><span class="sxs-lookup"><span data-stu-id="320f4-275">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="320f4-276">如果您選擇將選用的診斷資料傳送給我們，則也會包含必要的診斷資料。</span><span class="sxs-lookup"><span data-stu-id="320f4-276">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="320f4-277">選用診斷資料的範例包括 Microsoft 收集有關產品設定 (的資料，例如，) 裝置上的排除專案數目，以及產品) 的元件效能 (匯總度量。</span><span class="sxs-lookup"><span data-stu-id="320f4-277">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="320f4-278">軟體安裝和庫存資料事件</span><span class="sxs-lookup"><span data-stu-id="320f4-278">Software setup and inventory data events</span></span>

<span data-ttu-id="320f4-279">**適用於端點的 Microsoft Defender 設定**</span><span class="sxs-lookup"><span data-stu-id="320f4-279">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="320f4-280">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-280">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-281">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-281">Field</span></span>                                              | <span data-ttu-id="320f4-282">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-282">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="320f4-283">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="320f4-283">connection_retry_timeout</span></span>                           | <span data-ttu-id="320f4-284">與雲端通訊時，連線重試超時。</span><span class="sxs-lookup"><span data-stu-id="320f4-284">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="320f4-285">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="320f4-285">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="320f4-286">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="320f4-286">Size of the product cache.</span></span> |
| <span data-ttu-id="320f4-287">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="320f4-287">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="320f4-288">每天上傳的崩潰記錄檔限制。</span><span class="sxs-lookup"><span data-stu-id="320f4-288">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="320f4-289">antivirus_engine。排除 [] .is_directory</span><span class="sxs-lookup"><span data-stu-id="320f4-289">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="320f4-290">掃描的排除是否為目錄。</span><span class="sxs-lookup"><span data-stu-id="320f4-290">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="320f4-291">antivirus_engine。排除 [] 路徑</span><span class="sxs-lookup"><span data-stu-id="320f4-291">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="320f4-292">排除在掃描之外的路徑。</span><span class="sxs-lookup"><span data-stu-id="320f4-292">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="320f4-293">antivirus_engine。排除 [] 副檔名</span><span class="sxs-lookup"><span data-stu-id="320f4-293">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="320f4-294">排除來自掃描的分機號碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-294">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="320f4-295">antivirus_engine。排除 []。名稱</span><span class="sxs-lookup"><span data-stu-id="320f4-295">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="320f4-296">排除在掃描之外的檔案名。</span><span class="sxs-lookup"><span data-stu-id="320f4-296">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="320f4-297">antivirus_engine antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="320f4-297">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="320f4-298">產品快取的大小。</span><span class="sxs-lookup"><span data-stu-id="320f4-298">Size of the product cache.</span></span> |
| <span data-ttu-id="320f4-299">antivirus_engine antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="320f4-299">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="320f4-300">掃描時所用的執行緒數目上限。</span><span class="sxs-lookup"><span data-stu-id="320f4-300">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="320f4-301">antivirus_engine antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="320f4-301">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="320f4-302">在從隔離區還原的檔案之前，可再次偵測到超時。</span><span class="sxs-lookup"><span data-stu-id="320f4-302">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="320f4-303">filesystem_scanner filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="320f4-303">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="320f4-304">完整掃描目錄。</span><span class="sxs-lookup"><span data-stu-id="320f4-304">Full scan directory.</span></span> |
| <span data-ttu-id="320f4-305">filesystem_scanner filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="320f4-305">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="320f4-306">快速掃描中所用的目錄清單。</span><span class="sxs-lookup"><span data-stu-id="320f4-306">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="320f4-307">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="320f4-307">edr.latency_mode</span></span>                                   | <span data-ttu-id="320f4-308">偵測及回應元件所使用的延遲模式。</span><span class="sxs-lookup"><span data-stu-id="320f4-308">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="320f4-309">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="320f4-309">edr.proxy_address</span></span>                                  | <span data-ttu-id="320f4-310">偵測及回應元件所使用的 Proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="320f4-310">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="320f4-311">**Microsoft 自動更新設定**</span><span class="sxs-lookup"><span data-stu-id="320f4-311">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="320f4-312">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-312">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-313">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-313">Field</span></span>                       | <span data-ttu-id="320f4-314">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-314">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="320f4-315">how_to_check</span><span class="sxs-lookup"><span data-stu-id="320f4-315">how_to_check</span></span>                | <span data-ttu-id="320f4-316">會決定如何檢查產品更新 (例如，自動或手動) 。</span><span class="sxs-lookup"><span data-stu-id="320f4-316">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="320f4-317">channel_name</span><span class="sxs-lookup"><span data-stu-id="320f4-317">channel_name</span></span>                | <span data-ttu-id="320f4-318">更新與裝置相關聯的通道。</span><span class="sxs-lookup"><span data-stu-id="320f4-318">Update channel associated with the device.</span></span> |
| <span data-ttu-id="320f4-319">manifest_server</span><span class="sxs-lookup"><span data-stu-id="320f4-319">manifest_server</span></span>             | <span data-ttu-id="320f4-320">用於下載更新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="320f4-320">Server used for downloading updates.</span></span> |
| <span data-ttu-id="320f4-321">update_cache</span><span class="sxs-lookup"><span data-stu-id="320f4-321">update_cache</span></span>                | <span data-ttu-id="320f4-322">用來儲存更新的快取位置。</span><span class="sxs-lookup"><span data-stu-id="320f4-322">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="320f4-323">產品和服務使用</span><span class="sxs-lookup"><span data-stu-id="320f4-323">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="320f4-324">已開始診斷記錄上載報告</span><span class="sxs-lookup"><span data-stu-id="320f4-324">Diagnostic log upload started report</span></span>

<span data-ttu-id="320f4-325">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-325">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-326">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-326">Field</span></span>            | <span data-ttu-id="320f4-327">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-327">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="320f4-328">sha256</span><span class="sxs-lookup"><span data-stu-id="320f4-328">sha256</span></span>           | <span data-ttu-id="320f4-329">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-329">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="320f4-330">Size</span><span class="sxs-lookup"><span data-stu-id="320f4-330">size</span></span>             | <span data-ttu-id="320f4-331">支援記錄檔的大小。</span><span class="sxs-lookup"><span data-stu-id="320f4-331">Size of the support log.</span></span> |
| <span data-ttu-id="320f4-332">original_path</span><span class="sxs-lookup"><span data-stu-id="320f4-332">original_path</span></span>    | <span data-ttu-id="320f4-333">支援記錄檔的路徑 (always 低於 */Library/Application support/Microsoft/Defender/wdavdiag/*) 。</span><span class="sxs-lookup"><span data-stu-id="320f4-333">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="320f4-334">format</span><span class="sxs-lookup"><span data-stu-id="320f4-334">format</span></span>           | <span data-ttu-id="320f4-335">支援記錄檔的格式。</span><span class="sxs-lookup"><span data-stu-id="320f4-335">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="320f4-336">診斷記錄上載已完成報告</span><span class="sxs-lookup"><span data-stu-id="320f4-336">Diagnostic log upload completed report</span></span>

<span data-ttu-id="320f4-337">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-337">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-338">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-338">Field</span></span>            | <span data-ttu-id="320f4-339">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-339">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="320f4-340">request_id</span><span class="sxs-lookup"><span data-stu-id="320f4-340">request_id</span></span>       | <span data-ttu-id="320f4-341">支援記錄檔上載要求的相互關聯識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-341">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="320f4-342">sha256</span><span class="sxs-lookup"><span data-stu-id="320f4-342">sha256</span></span>           | <span data-ttu-id="320f4-343">支援記錄檔的 SHA256 識別碼。</span><span class="sxs-lookup"><span data-stu-id="320f4-343">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="320f4-344">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="320f4-344">blob_sas_uri</span></span>     | <span data-ttu-id="320f4-345">應用程式用來上傳支援記錄的 URI。</span><span class="sxs-lookup"><span data-stu-id="320f4-345">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="320f4-346">產品和服務效能資料事件</span><span class="sxs-lookup"><span data-stu-id="320f4-346">Product and service performance data events</span></span>

<span data-ttu-id="320f4-347">**非預期的應用程式結束 (當機)**</span><span class="sxs-lookup"><span data-stu-id="320f4-347">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="320f4-348">非預期的應用程式結束，以及在該情況下應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="320f4-348">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="320f4-349">**內核擴充統計資料**</span><span class="sxs-lookup"><span data-stu-id="320f4-349">**Kernel extension statistics**</span></span>

<span data-ttu-id="320f4-350">下列是收集的欄位：</span><span class="sxs-lookup"><span data-stu-id="320f4-350">The following fields are collected:</span></span>

| <span data-ttu-id="320f4-351">欄位</span><span class="sxs-lookup"><span data-stu-id="320f4-351">Field</span></span>                          | <span data-ttu-id="320f4-352">描述</span><span class="sxs-lookup"><span data-stu-id="320f4-352">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="320f4-353">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="320f4-353">pkt_ack_timeout</span></span>                | <span data-ttu-id="320f4-354">下列屬性是匯總數值，代表自內核延伸啟動之後發生的事件計數。</span><span class="sxs-lookup"><span data-stu-id="320f4-354">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="320f4-355">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="320f4-355">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="320f4-356">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="320f4-356">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="320f4-357">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="320f4-357">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="320f4-358">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="320f4-358">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="320f4-359">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="320f4-359">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="320f4-360">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="320f4-360">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="320f4-361">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="320f4-361">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="320f4-362">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="320f4-362">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="320f4-363">ipc ack。超時</span><span class="sxs-lookup"><span data-stu-id="320f4-363">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="320f4-364">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="320f4-364">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="320f4-365">ackd</span><span class="sxs-lookup"><span data-stu-id="320f4-365">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="320f4-366">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="320f4-366">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="320f4-367">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="320f4-367">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="320f4-368">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="320f4-368">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="320f4-369">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="320f4-369">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="320f4-370">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="320f4-370">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="320f4-371">vnode 讀取的 kauth</span><span class="sxs-lookup"><span data-stu-id="320f4-371">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="320f4-372">kauth vnode</span><span class="sxs-lookup"><span data-stu-id="320f4-372">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="320f4-373">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="320f4-373">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="320f4-374">vnode kauth</span><span class="sxs-lookup"><span data-stu-id="320f4-374">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="320f4-375">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="320f4-375">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="320f4-376">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="320f4-376">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="320f4-377">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="320f4-377">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="320f4-378">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="320f4-378">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="320f4-379">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="320f4-379">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="320f4-380">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="320f4-380">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="320f4-381">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="320f4-381">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="320f4-382">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="320f4-382">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="320f4-383">vnode 建立 kauth</span><span class="sxs-lookup"><span data-stu-id="320f4-383">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="320f4-384">vnode 移動的 kauth</span><span class="sxs-lookup"><span data-stu-id="320f4-384">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="320f4-385">vnode 裝載 kauth</span><span class="sxs-lookup"><span data-stu-id="320f4-385">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="320f4-386">kauth 拒絕的 vnode</span><span class="sxs-lookup"><span data-stu-id="320f4-386">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="320f4-387">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="320f4-387">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="320f4-388">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="320f4-388">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="320f4-389">ipc.kauth.file_op 遮罩</span><span class="sxs-lookup"><span data-stu-id="320f4-389">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="320f4-390">ipc.kauth_file_op。開啟</span><span class="sxs-lookup"><span data-stu-id="320f4-390">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="320f4-391">ipc.kauth.file_op。關閉</span><span class="sxs-lookup"><span data-stu-id="320f4-391">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="320f4-392">ipc.kauth.file_op ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="320f4-392">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="320f4-393">ipc.kauth.file_op。移動</span><span class="sxs-lookup"><span data-stu-id="320f4-393">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="320f4-394">ipc.kauth.file_op。連結</span><span class="sxs-lookup"><span data-stu-id="320f4-394">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="320f4-395">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="320f4-395">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="320f4-396">ipc.kauth.file_op。移除</span><span class="sxs-lookup"><span data-stu-id="320f4-396">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="320f4-397">ipc.kauth.file_op。卸載</span><span class="sxs-lookup"><span data-stu-id="320f4-397">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="320f4-398">ipc.kauth.file_op 的派生</span><span class="sxs-lookup"><span data-stu-id="320f4-398">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="320f4-399">ipc.kauth.file_op。建立</span><span class="sxs-lookup"><span data-stu-id="320f4-399">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="320f4-400">資源</span><span class="sxs-lookup"><span data-stu-id="320f4-400">Resources</span></span>

- [<span data-ttu-id="320f4-401">Microsoft 中的隱私權</span><span class="sxs-lookup"><span data-stu-id="320f4-401">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
